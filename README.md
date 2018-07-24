# XcodeServerBotApp
A sample project to achive CI/CD by integrating XcodeServer and Xcode Server bot.

&nbsp; 
&nbsp; 

## Installation
Installation by cloning the repository
* Go to directory.
* Setup Xcode Server
* Use command + B or Product -> Build to build the project
* Press run icon in Xcode or command + R to run the project on Simulator.
* Configure Server Bot to achive CI/CD.
 
 &nbsp; 

## Xcode Server
Xcode Server is used for CI/CD. Xcode server bots post script will be used to trigger fastlane lane if you want to integrate fastlane for Build deployment. We canrun them using terminal also.

XcodeServer And XcodeServer Bot
Xcode server is setup on local development machine with a new user. Steps for Xcode Server Setup: https://developer.apple.com/library/content/documentation/IDEs/Conceptual/xcode_guide-continuous_integration/index.html

Xcode Bot is setup on development machine with git configuration using master branch. Bot run periodically once per-day and configured for the following jobs:

Pull changes from remote repository if there any .
Configure to test parallel on specific simulator.
Run unit test cases.
Run UI Test cases.
Run the Static analyser for leaks and warnings.
Generate the report for UnitTest,UITest,Static analyser on project codebase.
We did not setup for exporting the build or code-singing for now as iTunes credential required. Once credential is there we can setup these activity by re-edit the XcodeServer Bot .
Post script for trigger fastlane lanes for screen shot and fastlane+scan code coverage.
To run fastlane lanes configure PATH in XcodeServer Bot configuration under environment tab

PATH="/usr/local/bin:$PATH"

&nbsp; 
&nbsp; 

## License

Copyright (c) 2018 Rupesh Kumar

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
