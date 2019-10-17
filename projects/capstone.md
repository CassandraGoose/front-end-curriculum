---
title: Cross-Pollination Capstone Project
---

For the first time ever, you get to work across programs and create a project that might not be possible otherwise! In this project plan, we'll kick-off the project and define expectations and deliverables for teams.

## Learning Goals

This is a unique opportunity that presents some valuable goals:

* Ultimately, demonstrate knowledge you've gained throughout Turing
* Use an agile process to turn well defined requirements into deployed and production ready software
* Gain experience dividing applications into components and domains of responsibilities to facilitate multi-developer teams. Service oriented architecture concepts and patterns are highly encouraged.
* Explore and implement new concepts, patterns, or libraries that have not been explicitly taught while at Turing
* Practice an advanced, professional git workflow (see whole-team expectations)
* Gain more experience using continuous integration tools to build and automate the deployment of features in various environments
* Build applications that execute in development, test, CI, and production environments
* Focus on communication between front-end and back-end teams in order to complete and deploy features that have been outlined by the project spec

## Kick-Off

### Schedule

1. Submit Capston Pitches by Thursday morning at 8am via form
1. Meet as group to go over any questions that came from reading the spec
1. Vote for which projects you would like to work on (If the project, is your idea please indicate with your vote)
1. Instructors will form teams
1. Gather into your teams
1. Start working on Day 1 deliverables!
  * Go through project expectations again with your team
  * Ask us any questions along the way!

## Expectations

### Whole-Team

Generally, this project will consist of a front-end (FE) and back-end (BE) with the following:

* The FE and BE applications live in separate repositories that communicate to each other using API requests
* FE and BE teams utilize a scrum board and tasks/stories updated accordingly on a daily basis as they are initialized, implemented, and deployed
* Both the FE and BE should be deployed to production and using continuous integration (like TravicCI) for automated deployment
* Early and consistent deployment to production (instructors will check build history)
* In-depth `README.md` for each repository describing the project, setup procedure, testing procedure, and screenshots, if applicable (API documentation, if applicable)
* Each student should have a goal for something you would like to learn about the other stack (BE student creates learning goal for something about the FE, and vice versa)
* Create and use pull request templates that document and create discussion for finished features - use rebasing instead of merging in git workflow

If you do not see your project following this outline, then speak to your instructors about it.

### Back-End Creators

* Use service oriented architecture patterns that split the application into their respective parts and responsibilities
* Create various services that serve up JSON, so that an FE system can effectively utilize the data from the BE
* Test the BE:
  * If you use Rails for your BE, then we expect above 80% test coverage
  * If you experiment with a new BE language/framework outside of Rails, then BE test coverage is expected to be at least 25%
* Implement a stretch goal (listed below)

Pick **2** of the following stretch goals:

* Implement BE in a framework or language you have not used before in a project
* Create a Backend API using GraphQL
* Create a micro service or two and abstract out functionality into a separate application
* Utilize websockets rather than traditional HTTP/HTTPS

### Front-End Creators

* Interface with the BE team’s API(s) that serve JSON data and incorporate that data into your FE
* Test the FE:
  * If you use React/Redux for your FE, then we expect above 85% test coverage
  * If you experiment with a new FE framework outside of React/Redux, then FE test coverage is expected to be at least 25%
* Implement a stretch goal (listed below)

Possible stretch goals:

* Implement FE in a framework you have not used before in a project
* Utilize internationalization and localization tools to localize the FE based on the user's locale
* Implement Progressive Web App (PWA) technologies like: background sync, IndexedDB, static assets caching using a Service Worker
* Utilize websockets rather than traditional HTTP/HTTPS (maybe [socket.io](https://socket.io/))

**Note:** FE students can be the BE creators and vice versa, if it fits into your learning goals

## Day 1 Deliverables (Friday)

By the end of the kick-off session today, you should have a full proposal of your project, which should include:

* DTR
* Initialize your repositories (don't write any code just yet!)
* Set up your scrum board with Github projects. You'll be requireed to use a single board for all repos. This will make it easier to see what everyone is working on during the project. 
* Each student create your goal for something you would like to learn about the other stack (BE student creates learning goal for something about the FE, and vice versa)
* Normalize on git workflow (we recommend using a "rebase" workflow, as opposed to "merge", as it is most common on the job) - use a PR template
* Determine MVP (knowing it could change as the project continues)
* Create user stories
* Create wireframes
* Construct schema design
* Decide on rough tech stack

Instructors will come around to each team to make sure these items are complete.

## Going Forward

### Check-Ins

Instructors will serve as project managers and hold check-ins with teams at least every other day to check:

* Progress and focus toward MVP
* Check deployment and build logs to make sure teams are deploying regularly
* Difficulties, roadblocks, and bugs
* Spikes (dedicated time for research and experiments)
* Next steps


### End-of-Project Demos

Thursday morning of week 6 your team will demo your application to the class and instructors (the application should be demo'd using _production_). It will be a great preparation for demo night so you can nail your demos!

_Demo Expectations:_
1. Live demo your application in production (Have a recording as a back-up)
1. Include the problem you are trying to solve and how your application does that
1. Include the challenges on the Frontend and Backend and solutions to those challenges
1. Have your application up and ready to go when you start. Other windows should be closed, be logged in(if applicable), etc.
1. Be proud of your applications! You've spent a lot of time and hard work on this, now is your chance to show it off. Your demo should really showcase that hardwork and accomplishments.

We recommend that you have a quick 30 sec - 1 min statement about what your app is and then jump straight into your demo. After the demo is complete, you can go in more depth and talk about the other points.

### Evaluation

Evaluation will take place Thursday afternoon of week 5. Each team will meet with a BE and FE instructor to:

* Walk through the application (FE and BE) and justifications of code
* Run the test suites
* Show the application is running on production
* Show application is using continuous integration
* Talk about lessons learned

Teams - it's your responsibility to keep and ensure you are on track to meet expectations of the rubric, which can be found [here](https://backend.turing.io/module4/projects/cross_pollination/cross_pollination_rubric).