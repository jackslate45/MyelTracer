# MyelTracer
Using MyelTracer for a publication? Cite the [MyelTracer publication](https://doi.org/10.1523/ENEURO.0558-20.2021)!
- [Windows Installation](#windows-installation)
- [MacOS Installation](#macos-installation)
- [Development](#development)

## Windows installation

Requirements: Windows 10

1. Download [the Windows installer](https://github.com/HarrisonAllen/MyelTracer/releases/download/v1.3/MyelTracerSetup.exe)
2. Run `MyelTracerSetup.exe`
   * You may see the following warning when installing:

     ![Windows Warning](https://github.com/HarrisonAllen/MyelTracer/blob/master/readme_resources/WindowsWarning.png)
   * Click on `More info` to get the following message:

     ![Windows Warning, more info](https://github.com/HarrisonAllen/MyelTracer/blob/master/readme_resources/WindowsWarningBypass.png)
   * Finally, click `Run anyway`
3. Follow the instructions in the installer
4. MyelTracer can now be run from the start menu

## MacOS installation

Requirements: MacOS High Sierra (10.13) or higher

1. Download [the MacOS installer](https://github.com/HarrisonAllen/MyelTracer/releases/download/v1.3/MyelTracer.dmg)
2. Open `MyelTracer.dmg`
3. Drag the `MyelTracer` icon to the `Applications` shortcut in the volume
4. MyelTracer can now be run from the `Applications` folder
   * You may see the following warning the first time you run the application:

     ![MacOS Warning](https://github.com/HarrisonAllen/MyelTracer/blob/master/readme_resources/MacOSWarning.png)
   * Just click `Open` to launch MyelTracer

## Development

Want to customize MyelTracer to fit your needs? Here's what you need to get started.

### Setup

1. Download (or clone) this repository
2. Set up a Python 3.6 environment

    I personally use [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
    1. Create the environment by typing `conda create --name MyelTracer python=3.6`
    2. Activate the environment by typing `conda activate MyelTracer`
3. `cd` to the repository on your computer in the terminal
4. Type `pip install -r requirements.txt`

### Editing the software

All of the code is stored in `SourceCode/src/main/python/main.py`. This is the file you should edit.

The software GUI is designed with [PyQt5](https://pypi.org/project/PyQt5/).

Image processing is done using [OpenCV](https://opencv.org/).

Software is packaged with [fman build system](https://build-system.fman.io/).

### Running the software

1. In the `SourceCode` directory, type `fbs run`

### Packaging the software

1. In the `SourceCode` directory, type `fbs freeze`
2. Type `fbs installer`

Before you can use the installer command on Windows, please install [NSIS](https://nsis.sourceforge.io/Main_Page/) and add its installation directory to your PATH environment variable. You can also right-click on the Installer file in `SourceCode\target\installer` and select `Compile NSIS Script`

This will generate a standalone installer for the operating system that you are currently using. 
* For example, if you are using MacOS High Sierra 10.13, then this will generate an installer that should work on MacOS 10.13 and up. To create a Windows installer, you would have to repeat this process on a Windows machine.


### Compatability Issues Any -> 1.4
In 1.4, 3 additional miscellaneous select tools were added to the tracker.  This allows the tracker to have be able to track 5 different points across the map.  Axon / Misc 1 / Misc 2 / Misc 3 / Misc 4.
 
However, this causes an issue when loading old data sets.  While this bug is being worked out, at this time the quick fix is to add the misc2 / misc3 / misc4 trackers to any previously created data files:
 
photo here
 
This will allow the program to load the older files, and have access to the new updates.
 
Additionally, by compiling the code without the compatible versions, it will allow the program to determine itself that it is not able to load the file.  
 
photo here
 
The balance here is any previously completed files will not have access to the additional select and count trackers. The original client was made aware of this issue, and is discussing internally how to proceed.  Once determined, this section will be updated accordingly.
