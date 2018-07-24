# XcodeServerBotApp
A sample project to achive CI/CD by integrating XcodeServer and Xcode Server bot.

## Installation
Installation by cloning the repository
* Go to directory.
* Setup Xcode Server
* Use command + B or Product -> Build to build the project
* Press run icon in Xcode or command + R to run the project on Simulator.
* Configure Server Bot to achive CI/CD.
 

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

   
