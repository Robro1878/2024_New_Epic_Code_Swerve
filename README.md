# Swerve 2024 code
1740's swerve test repository for the FRC 2024 season. I am using this as a basis for the code structure of our actual 2024 codebase. To make changes to the repo, follow the [Github Setup in VSCode](#github-vscode-setup-tutorial). 
### Robot Physical Specifications
* size w l h
* camera positions
* Swerve specifications
* general position and idea GroundIntake
* general position and idea Note Pusher
* general position and idea Climber

### Subsystems
#### Climber
* num of NEOs
* how it works

#### GroundIntake
* num of NEOs
* how it works

#### Note Pusher
* num of NEOs
* how it works (is it belts or wheels)

#### Path Information
* Name: function and position

### Software Todo List (sorted by priority)
`People`
- [ ] Cordinate the software team and see who wants to help with software
- [ ] Inform software team of structure and git and PID
- [ ] Make sure they all have a solid understanding of the principles the code runs on ([see last year's repo](#last-year-repo))
- [ ] Make sure everyone has a solid understanding of java
- [ ] Cordinate tasks
- [ ] Assign some sort of laptop system

`General Software`
- [x] Update codebase to 2024.2 when full release is out so we aren't on version "2024.1.1-beta-2"! This involves changing: 
* Many SparkMAX declarations to Spark
* The version of the RoboRio so builds will succeed. (This is what is currently preventing update now)
- [ ] Finish readme [Robot Physical Specifications](#robot-physical-specifications)
- [ ] Consider Advantage kit and/or scope data logging for the season [Scope](https://github.com/Mechanical-Advantage/AdvantageScope) [Kit](https://github.com/Mechanical-Advantage/AdvantageKit)

`Shuffleboard`
- [ ] Set up the shuffleboard base code, (not the indivudal methods that use it) based off last years example
- [ ] Add logging to drive subsystem to see wheel angles and robot position
- [ ] Add logging for note subsystems
- [ ] Add climber logging

`Swerve`
- [X] Find out why turning motors were turning seemingly randomly and fix it
- [X] Fix the one random wheel that didn't turn correctly
- [X] Turn on field relitive control
- [ ] Add pathplanning for autos
- [ ] Finish the system functionality
- [ ] Tune the system so it works well
- [ ] If apriltag vision pose esimation should take precedence in getPose, update it to get the pos with the limelight if able

`Controls`
- [ ] Create a better controller scheme than last year to set up controls (addControlerFunction(func(), a)) ? (opt.)
- [ ] Create control ideas for the driver and co driver (talk to Abby and Co-Driver)
- [ ] Implement controls
- [ ] Make sure control feel is good and everything makes sense
- [ ] Different control selection from shuffleboard
- [ ] Controller rumble would be cool, could provide feedback on time left in match??

`Vision`
* Concurent work on limelight and lamelight
- [x] Import old code
- [x] Setup and update [limelight](https://docs.limelightvision.io/docs/docs-limelight/getting-started/summary)
- [ ] Calibrate the limelight with the online tool
- [ ] Check and fix imported limelight subsystem
- [ ] Incorperate limelight table with shuffleboard
- [ ] Get current limelight tag id and adjust co-driver controls based off it.
- [ ] Consider Using limelight to track gamepieces 

* Concurent work on limelight and lamelight
- [ ] Import old code
- [x] Grab the lamelight from last years robot
- [x] Set up lamelight (Photon vision) ([see last year's repo](#last-years-repo))
- [ ] Rename instances of vision with photonVision for clarity
- [ ] Incorperate lamelight table with shuffleboard
- [ ] Calibrate lamelight

`Climber`
- [ ] Actually figure out what the mechanics entail and how it works
- [ ] Find out how many motors it is
- [ ] Create stub code for testing
- [ ] See [Shuffleboard](#Shuffleboard)

`Note pusher`
- [ ] Figure out what this is called and rename it here
- [ ] Actually figure out what the mechanics entail and how it works
- [ ] See how the flap works
- [ ] Create stub code for testing
- [ ] See [Shuffleboard](#Shuffleboard)

`Ground Intake`
- [ ] See how the ground intake works
- [ ] Create stub code
- [ ] Create subsystem
- [ ] See [Shuffleboard](#Shuffleboard)

### Last Year's Repo
* :warning: This is intended as a place of reference to see the general structure, not to copy code without understanding it
* [2023 Souce Code](https://github.com/crephoto/CommandBased_2023)

### Important Devolopment Resources
This is the main resource we use besides googling things, this contains most, if not all the answers you need
* [Wpilib Documentation](https://docs.wpilib.org/en/stable/docs/zero-to-robot/introduction.html)
* [Java Wpilib Api](https://github.wpilib.org/allwpilib/docs/release/java/index.html)
* [Limelight Vision Documentation](https://docs.limelightvision.io/docs/docs-limelight/getting-started/summary)
* [The Most Important Resource](https://www.google.com)
* If you need any further help or explainations, feel free to talk to me, or any of the software mentors.


### Github VSCode Setup Tutorial 
This is a guide for setting up Github with VSCode
* Create a [Github account](https://github.com)
* Sign into the VSCode with Github via the person logo in the bottom left above the wheel
* Fork the repository through the button on github
* Copy the link to the forked repository
* Clone the forked repository with VSCode
* Open the terminal 
* Run git remote -v
* You should see 2 values, a fetch and a push for origin
* These are added automatically because you cloned the repository
* This now is your forked repository
* Paste this command into the terminal "git remote add upstream [Link to original repository you forked]"
* Run git remote -v again, and you should see 2 more values for upstream fetch and push
* Run git pull upstream main
* If this succeeds you probablly have it set up correctly for your main branch

* Now, you need to make a different branch for saftey
* Run git checkout -b [Branch Name]
* I recommend "[name]-working" as the branch name
* This will create a new branch, you can switch between them in the bottom left
* :warning: All changes should be done on a working branch or equivelent, not on main
* After use, you can delete it and re-sync your main branch
* Then, run git branch --set-upstream-to=origin
* See [Using Git](#using-git)

### Using Git
#### Pulling Code
* Ideally this should be done every time you open your code and as often as possible to avoid conflicts
* If it has been a long time since you have worked it's a good idea to pull so you don't get a lot of merge conflicts
* To pull code, make sure you have to pending changes (if you do, see [Pushing Code](#pushing-code))
* Change to your main branch
* Run git pull upstream main
* Change back to working
* Run git pull upstream [Branch Name]
* You're ready to get back to work!
#### Pushing Code
* Now that you have setup your github you can edit code on your working branch
* Make sure your changes work and make sure it builds and deploys before commiting
* After you finish the changes you now should look to the left panel and click the third git source control icon
* Hit Commit and if you haven't saved, hit Save all and Commit Changes
* It will ask you to input a message, either through a file or the message box at the top, either type in box or in the file save, and hit the checkmark to submit it
* Sync changes
* Go on github to your local fork of the repository
* Open a pull request via the contribute button
* If there are merge conflicts don't touch anything and ask someone who knows, it can be easily resolved but you can mess it up really bad
* Hopefully the code works and get accepted into the main repo
* Make sure to [pull](#pulling-code) code after pushing

[Team Git "How To"](https://docs.google.com/document/u/0/d/15Kb6Wxj8sjFqbPtVO2GGT9Oe1oe9GFOMFhPrwpMIeqQ/mobilebasic?pli=1)
[Additional Info](https://code.visualstudio.com/docs/sourcecontrol/overview)
