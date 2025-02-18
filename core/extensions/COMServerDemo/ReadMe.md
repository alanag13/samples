COM Server Demo
================

This is a basic example of providing a managed COM server in .NET Core 3.0. Documentation on the inner workings of activation can be found [here](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/COM-activation.md).

Key Features
------------

Demonstrates how to provide a COM server in .NET Core 3.0 Preview 5 or later.

Additional comments are contained in source and project files.

Build and Run
-------------

The project will only build and run on the Windows platform.

### Registered COM ###

1) Install .NET Core 3.0 Preview 5 or later.

1) Navigate to the root directory and run `dotnet.exe build`.

1) Follow the instructions for COM server registration that were emitted during the build.

1) Navigate to `COMClient/` and run `dotnet.exe run`.

Program should output an estimated value of &#960;.

**Note** Remember to unregister the COM server when the demo is complete.

### RegFree COM ###

1) Install .NET Core 3.0 Preview 5 or later.

1) Navigate to the root directory and run `dotnet.exe build /p:RegFree=True`.

    - If the Registered COM demo was previously run, the project should be cleaned first - `dotnet.exe clean` 

1) Run the generated binary directly e.g. `COMClient\bin\Debug\netcoreapp3.0\COMClient.exe`.

Program should output an estimated value of &#960;.

**Note** The RegFree COM scenario requires a customized [application manifest](https://docs.microsoft.com/windows/desktop/sbscs/manifests) in the executing binary. This means that attempting to execute through `dotnet.exe` will not work and instead trigger a rebuild of the project.
