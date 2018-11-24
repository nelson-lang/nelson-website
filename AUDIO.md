## Audio module


Audio module provides tools for read and play audio data. ASIO and multichannel supports enable low latency streaming to audio devices.

Example:

```
info = audiodevinfo()
OUTPUT_DEVICE = 0;
INPUT_DEVICE = 1;
for k = [1:audiodevinfo(OUTPUT_DEVICE)]
  info.output(k)
end
for k = [1:audiodevinfo(INPUT_DEVICE)]
  info.output(k)
end
```

```
wav_audio = [modulepath('audio'), '/examples/haha.wav'];
[y, fs] = audioread(wav_audio);
playObj = audioplayer(y, fs);
playblocking(playObj)
delete(playObj)
clear playObj
```


[Previous page](FEATURES.md)