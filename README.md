cloudanswers-toolbelt
=====================

easily manage your dev environments for your distinct projects

We work with a ticketing systems and source control systems for our projects, which most force.com developers are not knowledable about.
This is a helper script to cut down on the overhead of having to learn how each project and client is structured and how to test/deploy each feature.


Usage
-----

Initial setup:
    
    $ cloudanswers login
    Open url in a browser to authenticate: http://clouxxxxxx/xxxxxx
    Copy and paste result code here: 123123
    Successfully connect the toolbelt to CloudAnswers 
    $ cloudanswers features

    CloudAnswers Features (relevant to you)
    
    Id        | Name
    ---------------------------------------------------------
    123123123 | Bluewolf/Entravision: Alter budget logic to increase resolution
    321321321 | RamRacing: Budget comparison during entry
    918239293 | Internal: External API for pod based metrics

    $ cloudanswers workon 321321321
    No existing feature folder found, creating a new one!

    <git clone output>

    Switching to feature branch: 321321321-budget-comparison
    Connecting to salesforce (devacct1@test.com.dev1)...
    Setting up MavensMate...
    Setting up Eclipse...
    Detected existing change set: 321321321-budget-comparison
    Linking package.xml to change set...
    Refreshing package information from salesforce...
    
    All done!

    You can now from this folder:
    - login to the developer org using `cloudanswers browser`
    - open Sublime/MavensMate with `cloudanswers mavensmate`
    - refresh your code with `cloudanswers refresh`
    - push your changes back with `cloudanswers checkin`
    
    $ cloudanswers browser
    $ cloudanswers checkin


Work on a project:

    $ cloudanswers workon 123123123
    cloudanswers workon 123123123
    Found existing local git repo: ~/Documents/cloudanswers/features
    Switching to feature folder...
    Feature folder already on correct branch (task-email-123123123)
    $ cloudanswers refresh-from-salesforce
    <ant refresh messages>
    $ cloudanswers checkin
    $ cloudanswers finish
    <commit and push>
    <open pull request>


Data Model
----------

Each feature in PivotalTracker contains:
* link to the github repo
* branch name for this feature
* change set name
* connection details for sandbox


