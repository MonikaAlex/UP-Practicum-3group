# Koe IDE да използваме

- Visual Studio
- VS Code
- CLion

# Visual Studio Setup for C++

1. Download Visual Studio

Open the official Visual Studio website:
https://visualstudio.microsoft.com/

Click Download Visual Studio.

Choose Visual Studio Community if you are a student, individual developer, or using Visual Studio for personal/educational projects.

Download the Visual Studio Installer.

Recommended: Visual Studio Community is free for individual developers and is usually sufficient for learning and university C++ projects.

2. Install Visual Studio

Run the downloaded Visual Studio Installer.

Allow the installer to make changes to your computer if Windows asks for administrator permission.

Wait for the Visual Studio Installer to load.

The installer will display a list of Workloads.

3. Install the C++ Workload

In the Workloads tab, select:

Desktop development with C++

This workload provides the tools required to create and compile standard C++ applications.

Make sure the workload includes:

MSVC C++ build tools

Windows 10/11 SDK

C++ CMake tools for Windows

C++ core features

The default selections are normally sufficient.

Recommended additional components

If they are not already selected, consider installing:

Git for Windows

C++ AddressSanitizer

C++ profiling tools

C++ Clang tools for Windows

For a normal university C++ project, these are optional.

4. Choose the Installation Location

At the bottom of the Visual Studio Installer, you can choose where Visual Studio will be installed.

The default location is recommended unless you have a specific reason to change it.

Click:

Install

The installation can take some time because Visual Studio needs to download the compiler, SDKs, libraries, and development tools.

5. Launch Visual Studio

After the installation finishes:

Open Visual Studio from the Start Menu.

Sign in with your Microsoft account if required.

Choose your preferred development settings.

Select a color theme.

Click Start Visual Studio.

6. Create Your First C++ Project

On the Visual Studio start screen, click:

Create a new project

Search for:

Console App

Select:

Console App

Make sure the language is:

C++

Click Next.

# Visual Studio Code --- C++ Setup Guide

1. What you need

For C++ development, you need three main things:

Visual Studio Code --- the code editor.

A C++ compiler --- such as GCC/MinGW-w64.

The Microsoft C/C++ extension --- provides IntelliSense,
debugging, code navigation, and other C++ features.

Important: Installing VS Code alone does not install a C++
compiler.

2. Download Visual Studio Code

Open the official VS Code website:

https://code.visualstudio.com/

Click Download for Windows.

Download the Windows installer.

Run the downloaded installer.

Accept the license agreement.

Keep the default installation location unless you have a reason to
change it.

On the Select Additional Tasks screen, enable these options if
available:

Add "Open with Code" action to Windows Explorer file context
menu

Add to PATH

Register Code as an editor for supported file types

Click Next and then Install.

Start Visual Studio Code after the installation finishes.

3. Install a C++ compiler

VS Code needs a compiler to turn your .cpp files into executable
programs.

A common choice on Windows is MinGW-w64/GCC.

Option A --- Install MinGW-w64 through MSYS2

MSYS2 is a convenient way to install and update GCC and other
development tools.

Open:

https://www.msys2.org/

Step 1: Install MSYS2

Download the latest MSYS2 installer.

Run the installer.

Keep the default installation directory unless you have a specific
reason to change it.

Finish the installation.

Step 2: Open the MSYS2 UCRT64 terminal

From the Windows Start menu, open:

MSYS2 UCRT64

Use the UCRT64 environment for a modern GCC/MinGW-w64 setup.

Step 3: Update MSYS2

Run:

pacman -Syu

If MSYS2 tells you to close the terminal, close it.

Open MSYS2 UCRT64 again and run:

pacman -Syu

Repeat the update if MSYS2 asks you to.

Step 4: Install GCC and debugging tools

Run:

pacman -S --needed mingw-w64-ucrt-x86_64-gcc mingw-w64-ucrt-x86_64-gdb mingw-w64-ucrt-x86_64-make

Press Enter to accept the default selections.

4. Add the compiler to Windows PATH

Adding GCC to PATH allows Windows and VS Code to find commands such as
g++ from a normal terminal.

For the MSYS2 UCRT64 installation, the usual compiler directory is:

C:\msys64\ucrt64\bin

Add it to PATH

Press Windows key.

Search for:

Environment Variables

Select Edit the system environment variables.

Click Environment Variables.

Under User variables, select Path.

Click Edit.

Click New.

Add:

C:\msys64\ucrt64\bin

Click OK on all open dialogs.

If you installed MSYS2 somewhere other than C:\msys64, use the
corresponding ucrt64\bin directory.

5. Verify the compiler

Close any terminals that were already open.

Open a new PowerShell or Command Prompt window.

Run:

g++ --version

You should see GCC version information.

Then run:

gdb --version

You should also see GDB version information.

If g++ is not recognized, see the troubleshooting section near the end
of this guide.

6. Install the C/C++ extension in VS Code

Open Visual Studio Code.

Click the Extensions icon on the left side.

Search for:

C/C++

Install C/C++ published by Microsoft.

The extension provides features including:

C++ IntelliSense

Syntax highlighting

Error detection

Code navigation

Debugging integration

Code completion

You can also open the official extension page here:

https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools

7. Create your first C++ project

Create a folder for your C++ projects.

For example:

C:\Users\YourName\Documents\cpp-projects

Inside it, create a folder called:

hello-world

Your project should look like:

hello-world/
└── main.cpp

8. Open the project in VS Code

In VS Code:

Select File → Open Folder.

Select the hello-world folder.

Click Select Folder.

VS Code should now show your project in the Explorer panel.

# CLion --- C++ Setup Guide

1. What you need

For C++ development with CLion, you need:

CLion --- the C++ IDE from JetBrains.

A C++ compiler/toolchain --- GCC through MSYS2 is used in this
guide.

CMake --- CLion uses CMake to configure and build projects.

GDB --- used for debugging.

CLion can work with several toolchains, including MinGW, Microsoft
Visual C++, Clang, and WSL. This guide uses MSYS2 UCRT64 + GCC
because it provides a modern GCC-based Windows environment.

2. Download CLion

Open the official JetBrains CLion website:

https://www.jetbrains.com/clion/

Click Download.

Select the Windows version.

Download the installer.

Run the downloaded installer.

Accept the license agreement.

Keep the default installation location unless you have a reason to
change it.

Continue through the installation wizard.

Finish the installation.

Start CLion.

3. Install MSYS2

CLion needs a C++ compiler.

A convenient GCC/MinGW-w64 setup on Windows is MSYS2.

Open:

https://www.msys2.org/

Download the latest MSYS2 installer.

Run the installer.

Use the default installation directory if possible:

C:\msys64

Finish the installation.

4. Open the MSYS2 UCRT64 terminal

From the Windows Start menu, search for:

MSYS2 UCRT64

Open it.

Use the UCRT64 environment for a modern GCC/MinGW-w64 setup.

5. Update MSYS2

Inside the MSYS2 UCRT64 terminal, run:

pacman -Syu

MSYS2 may ask you to close the terminal after updating core packages.

If it asks you to close the terminal:

Close the terminal.

Open MSYS2 UCRT64 again.

Run:

pacman -Syu

Repeat the update if MSYS2 requests it.

6. Install GCC, GDB and Make

Run:

pacman -S --needed mingw-w64-ucrt-x86_64-gcc mingw-w64-ucrt-x86_64-gdb mingw-w64-ucrt-x86_64-make

Press Enter to accept the default package selections.

You now have:

g++ --- C++ compiler

gcc --- C compiler

gdb --- debugger

mingw32-make --- Make build tool

7. Verify GCC

Inside the MSYS2 UCRT64 terminal, run:

g++ --version

You should see GCC version information.

Then:

gdb --version

You should see GDB version information.

8. Add GCC to Windows PATH

CLion can often find MSYS2 installations automatically, but adding the
compiler to Windows PATH is useful for working with C++ from PowerShell,
Command Prompt, and other tools.

The usual MSYS2 UCRT64 binary directory is:

C:\msys64\ucrt64\bin

Add it to PATH

Press the Windows key.

Search for:

Environment Variables

Open Edit the system environment variables.

Click Environment Variables.

Under User variables, select Path.

Click Edit.

Click New.

Add:

C:\msys64\ucrt64\bin

Click OK on all dialogs.

Close and reopen terminals after changing PATH.

9. Verify the Windows PATH

Open a new PowerShell window.

Run:

g++ --version

Then:

gdb --version

You can also find the compiler with:

where.exe g++

You should see something similar to:

C:\msys64\ucrt64\bin\g++.exe

10. Start CLion

Open CLion.

On the welcome screen, you should see options such as:

New Project

Open

Clone Repository

Select:

New Project
