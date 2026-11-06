---
title: Compile Nelson code to native executables
description: Package a Nelson program into a standalone native executable that runs without a Nelson installation and without a C or C++ toolchain, with static dependency analysis, bundled or installed runtimes, and installers.
---

# Standalone applications

**Turn a Nelson program into a native executable that runs without Nelson installed.**

Nelson's optional **compiler** module analyses the dependencies of your `.m` files and
builds a native application from them. There is no C or C++ toolchain to set up and no
separate SDK to install: the module uses a precompiled launcher and the Nelson engine you
already have. Load it on demand with `ncc`.

## From a script to an executable

The example below is shipped with Nelson under `modules/compiler/examples/standalone`. The
entry point reads a command-line argument, loads a data file, calls a helper function, and
prints a result.

```matlab
% Load the optional compiler module on demand.
ncc('--help');

% Describe the build: entry point, name, and an extra data file.
options = ncc('options', 'app_entry.m', ...
  'ExecutableName', 'application', ...
  'ExecutableVersion', '2.0', ...
  'AdditionalFiles', 'factor.txt');

% Inspect the dependency plan, then build.
plan   = nelson.compiler.analyze(options);
result = ncc(options);
```

The build produces a native executable. On Windows it is an `.exe`; on other platforms it
uses their native executable format. Run it like any other program, passing arguments on
the command line:

```text
$ ./application 5
TUTORIAL_RESULT=30
```

The same build is also available through the object interface
`compiler.build.standaloneApplication(AppFile, Name, Value, ...)`, which returns a
read-only results object.

## What the executable contains

The output is self-contained. Running it needs neither the Nelson command line, nor your
original `.m` sources, nor a compiler:

- **Your application**, stored as Nelson bytecode (`.nbc`) together with the data files it
  needs. By default these are embedded in the executable; with `EmbedArchive=false` they
  live in an adjacent `.nca` archive distributed alongside it.
- **The Nelson engine**, which runs that bytecode. Your code executes on the same bytecode
  virtual machine as an interactive session, so results and behaviour match Nelson exactly.

## Only the dependencies you use

Before building, Nelson performs a **static analysis** of the entry point and follows the
functions and modules it actually reaches. `nelson.compiler.analyze` returns a plan you can
inspect, so you know what will be shipped:

```text
>> disp(plan.runtime.modules)
    {'console'      }
    {'core'         }
    {'data_structures'}
    {'elementary_functions'}
    {'engine'       }
    {'interpreter'  }
    {'operators'    }
    {'string'       }
    {'types'        }
    ...
```

Helper functions reached from the entry point are selected automatically; data files can be
added explicitly with `AdditionalFiles` (files, directories, and patterns, including `.nh5`
and `.mat` resources) or detected automatically.

## Bundled or installed runtime

The engine can travel with your application or be found on the target machine:

- **Bundled** (`RuntimeMode='bundled'`) ships the engine in an adjacent `.runtime`
  directory next to the executable. The result is a fully portable distribution that runs
  with nothing pre-installed. Keep the executable and its `.runtime` directory together.
- **Installed** (`RuntimeMode='installed'`) produces the smallest output and relies on a
  compatible Nelson runtime already present on the target, located through the
  `NELSONC_RUNTIME_ROOT` environment variable. The architecture and engine fingerprint must
  match, not merely the version number.

## Console, graphics, and windows

- **Console** applications are directly executable and read their arguments from the command
  line.
- **Graphics** are enabled with `Mode='gui'`. Figure and `uicontrol` callbacks keep the
  graphical event loop alive while the application's windows remain open.
- On Windows, `NoConsole=true` builds an application with no console window. Console
  visibility and graphics support are independent settings.

Inside a packaged application, `isdeployed` returns `true`, and `ctfroot` points to the
temporary directory where resources are extracted. Store any results you want to keep
outside that directory, since it is removed on shutdown.

## Installers and packaging

Beyond a bare executable, the module can produce a distributable installer with
`compiler.package.installer`, which also wraps a graphical application in a `.app` bundle on
macOS. The `compiler.runtime` functions report and package the runtime dependencies an
installer needs.

## Build once per target

Nelson does not cross-compile: build on each platform you want to target. A Windows build
produces a `.exe`, and other supported platforms produce their own native executable format.
A verified previous build of the same name and architecture can be rebuilt safely in place,
and the previous outputs are restored if a build is interrupted.

---

Read the full reference in the
[compiler module documentation](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/compiler/compiler.build.standaloneApplication.html),
or follow the
[standalone tutorial](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/compiler/compiler_standalone_tutorial.html).

[Back to home](index.html)
