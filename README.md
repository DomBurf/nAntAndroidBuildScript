nAntAndroidBuildScript
======================

nAnt script for building a Visual Studio Android application. The Android plug-in used was Xamarin for Visual Studio.

The repository contains 3 files:

- FullBuild.Build.bat (Windows batch file for executing nNant with the required build parameters)
- FullBuild.Build.xml (the nAnt script)
- myProject.csproj (XML nodes that need to be added to your Visual Studio project to allow your APK file to be packaged, signed and aligned)


The nAnt build script is invoked from the Windows batch file. It peforms the following build operations.

- Performs a Clean build
- Performs a build in Debug mode
- Performs a build in Release mode
- Packages the Android APK file
- Signsand aligns the Android APK file
- Reads the version number from the AndroidManifest.xml file
- Reads the latest revision number from SVN and writes this into the AndroidManifest.xml file
- FTPs the file to the UAT server for testing into a folder named usng the version and revision numbers

To package and sign the Android APK file you will need to add the XML nodes contained within myProject.csproj to your own Visual Studio project file.

Usage

To use the script to build your own Android application with Visual Studio simply do the following.

 - copy the FullBuild.Build.bat and FullBuild.build.xml files to your Android project folder
 - open your project .csproj file and add the XML nodes from myProject.csproj

Assumptions

 - you have nAnt and nAntContrib installed (alongside your other development tools) and this path is added as an environment variable called BUILD_TOOLS
 - WinSCP is installed as the FTP client (you can your your own FTP client of choice if necessary)

