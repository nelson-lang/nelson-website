## Interprocess Communication

ipc builtin allows to execute, get, put variables between multiple nelson's process.

All serializable nelson's types are supported. Unsupported types will be replaced by an empty matrix and a warning.

Example:

```matlab
master_pid = getpid()
initial_pids = getpid('available')

% Creates 4 nelsons process
N = 4;
for i = 1:N
    cmd = sprintf('nelson-gui -e MASTER_PID=%d &', i);
    unix(cmd);
    sleep(5)
end
current_pids = getpid('available')

% wait clients ready
for p = current_pids
    if p ~= master_pid
        while(~ipc(p, 'isvar', 'MASTER_PID')), sleep(1), end
    end
end

% Creates random matrix in others Nelson
n = 0;
for p = current_pids
    if p ~= master_pid
        cmd = sprintf('rng(%d);M = rand(10, 10); disp(M)', n);
        ipc(p, 'eval', cmd);
        n = n + 1;
    end
end

% Creates a matrix with matrix from others Nelson
C = [];
for p = current_pids
    if p ~= master_pid
        R = ipc(p, 'get', 'M');
        C = [C; R]
        n = n + 1;
    end
end

% close all clients
for p = current_pids
    if p ~= master_pid
        ipc(p, 'eval', 'exit')
    end
end

```

[Previous page](FEATURES.md)
