# openroberta-connector [![Build Status](https://travis-ci.org/OpenRoberta/openroberta-connector.svg?branch=master)](https://travis-ci.org/OpenRoberta/openroberta-connector)

### Supported robots
- EV3Lejos
- Arduino Uno
- Arduino Mega
- Arduino Nano
- BOB3
- Bot'n'Roll
- mBot
- NAO

Standalone program for connecting robot hardware to the Open Roberta lab using
an usb or ssh connection.

### Fast installation with maven

#### Clone the repository and compile
    git clone git://github.com/OpenRoberta/openroberta-connector.git
    cd openroberta-connector
    mvn clean install

### Run Open Roberta Connector
For running the Connector use Java.

    java -jar target/OpenRobertaConnector-*.jar

### Development notes

You can follow the test status on https://travis-ci.org/OpenRoberta/.

Development happens in the `develop` branch. Please sent PRs against that
branch.

    git clone git://github.com/OpenRoberta/openroberta-connector.git
    cd openroberta-connector
    git checkout -b develop origin/develop
    
### Installer creation

#### Automatically

TravisCI automatically generates installers for Linux, Windows and OSX when a tag is created.
These are added to a release draft for the tag.
 
#### Manual

Linux:
- run `mvn clean install` in the project directory
- run `release.sh linux` in the `installers` directory
- add the version to the resulting file

Windows:
- download and install [WiX Toolset](https://github.com/wixtoolset/wix3/releases)
- download and install [WDK 8.1](https://www.microsoft.com/en-us/download/details.aspx?id=42273)
  - or run
    - `curl 'https://download.microsoft.com/download/0/8/C/08C7497F-8551-4054-97DE-60C0E510D97A/wdk/wdksetup.exe' --output wdksetup.exe`
    - `./wdksetup.exe //features + //q //norestart //ceip off`
- add a environment variable `WIX=<wix-install-path>\bin`
- run `mvn clean install` in the project directory
- run `release.sh windows` in the `installers` directory (e.g. in Git Bash)
- add the version to the resulting files

Mac:
- run `mvn clean install` in the project directory
- run `release.sh osx` in the `installers` directory
- add the version to the resulting file