# Welcome to my Minimal Minimal Semester 3 Portfolio!

## About Me
Welcome again to my portfolio! My name is Casper van den Dijk, a student at Fontys University of Applied Sciences in Eindhoven. Here I study the HBO ICT course, currently in the third semester of software engineering. 

For this semester I have been working on two projects: My individual project (IP) and the group project (GP).
<br> <br>

### The Concept
This project was inspired by my friends. Every year, Riot Games hosts the World Championship for League of Legends. With this, they add a web guessing game called 'PickEms'. Here you can guess who you think will win the next matches and the championship! Unfortunately, they don't have this mini-game during the regular seasons throughout the year, despite us wanting to continue this fun competition among ourselves. That's why I've decided to try and create a version of it myself!
<br> <br>

### Repositories
- [Individual Project](https://github.com/Vhalur-PickEms)
  - [Documentation](https://github.com/Vhalur-PickEms/documentation/tree/main) 
  - [Front-end - Vue Web App](https://github.com/Vhalur-PickEms/vue-front-end) 
  - [Back-end - Minimal Web API](https://github.com/Vhalur-PickEms/MinimalApi)
- [Group Project](https://github.com/wocevv)
<br> <br>

### Learning outcomes
#### 1. Web application (IP)

>Clarification:
>
>User friendly: You apply best practices when creating user interfaces and basic user experience testing and development techniques.
>
>Full-stack: You design and build a full stack application using a commonly accepted front end Javascript framework and back end application implementing relevant >communication protocols, persistence of data by usage of ORM and addressing asynchronous communication issues.

"The (main) [front-end](https://github.com/Vhalur-PickEms/lec-pickems-frontend) is made with a JavaScript front-end framework". This was a requirement for the indvidual project set by Fontys. My familiarity with Javascript was nil. After quick research on javascript frameworks, I decided to go with Vue, the same framework we used for the group project; the main reason I picked Vue. There are other, more statistically popular Javascript frameworks like React and Angular, but I liked the idea of using the same framework we used in the group project. I envisioned this would allow me to dive quicker and deeper into Vue rather than learning the basics of two frameworks.
<br><br>
The [back-end](https://github.com/Vhalur-PickEms/MinimalApi) for the application had a few more requirements. It had to be an OO based language, required use of an ORM and asynchronous communication was taken into account. With this in mind, I decided to opt for an ASP.NET Core Minimal Web API. These API's are written in C#, a language I am now familiar with thanks to my previous semesters. This quickened the process in which I was able to implement asynchronous communication and the ORM Entity Framework. 
<br><br>

#### 2. Software quality (IP)
>Clarification:
>
>Tooling and methodology: Carry out, monitor and report on unit integration, regression and system tests, with attention for security and performance aspects, as well >as applying static code analysis and code reviews.

To ensure software quality for my project I use SonarCloud. SonarCloud is a cloud-based static code analysis service. On every pull request that I make Sonarcloud will 'activate'. It looks through my code and checks for code smells, bugs, test coverage, vulnerabilities and more. Depending on the issue it found, SonarCloud will even offer solutions on how to fix this. 
<br><br>
While SonarCloud is a useful service, I shouldn't completely rely on third-party services to check MY code. To make sure the code I write works as intended, I have set-up integration tests. More on these during learning outcome 4.
<br><br>
To ensure proper security for my project I integrated OAuth 2 through Auth0. Both the front- and back-end require Auth0 authentication. Only with an Auth0 token created through my domain do these applications allow certain functionality. 

#### 3. Agile Software Development (GP)
>Clarification:
>
>Choose: You are aware of the most popular agile methods and their underlying agile principles. Your choice of a method is motivated and based on well-defined >selection criteria and context analyses.

When the group came together to work, we started every day with a "stand-up". During this, the current scrum master would be leading this conversation. Together with JIRA, we assigned tasks and outed potential issues that might require assistance. After the stand-up we would start working on our assigned tasks. When online (Mondays), people would split off in their assigned discord channel to ease communication where needed, mostly split between front-end and back-end. If a question ever came up that required someone from a different "team", we had no issue with quickly swapping channel and helping. 
<br><br>
At the start of every sprint, we would take some time to correctly set-up the JIRA board with upcoming stories, tasks and potential bugs. These would be worked out with sub-tasks, descriptions and definitions of done. After we had a list (backlog) filled with items we would select a few we would want to focus on during this sprint. Near the end of the semester we started using story points. These helped us gain a better perspective on how much work we could achieve within these two weeks. 
<br><br>
Every sprint would be finished with a sprint meeting with our stakeholders followed by a retrospective on the sprint. We used a ["custom method"](https://user-images.githubusercontent.com/124791770/238608067-51b6dd0e-0ed2-4983-bb5e-78583e631427.png) to hold our retrospectives. While this might not make a lot of sense to outsiders, it worked surprisingly well for us. 
<br><br>

#### 4. CI/CD (IP)
>Clarification:
>
>Design and implement: You design a release process and implement a continuous integration and deployment solution (using e.g. Gitlab CI and Docker).

"Cntinuous Integration and Continuous Deployment". This is a commonly used method introducing automation during app development. In my project, [my CI/CD pipeline](https://github.com/Vhalur-PickEms/MinimalApi/blob/main/.github/workflows/dotnet.yml) consists of three steps:
#### 1. Testing and Building the project 
When a pull request is made, the pipeline automatically tries to run the unit and integration tests in the project as well as trying to build the project. The tests it runs are written myself as mentioned in learning outcome 3. If this step does not fail, it moves to step 2.

#### 2. Static Code Analysis provided by SonarCloud
When step 1 succeeds, step 2 automatically starts. SonarCloud takes a few minutes to read through the project's code. When it's done, a report is made on the code quality and posted as a comment on the pull request. Should this check succeed, the pipeline continues to step 3.

#### 3. Building a docker image and pushing to dockerhub
It should be noted, this step has two conditions. The first being step 2 succeeds. Furthermore, this check is only done when the pull request goes to main. I want a docker image of code that has functionality and would be deployed into the real application. I do not need a docker image of a quick hotfix I made during development. <br>
Should both these conditions be met, a docker image of the project is made and automatically pushed to my private repository on DockerHub. 
<br><br>

#### 5. Cultural differences and ethics (GP)
>Clarifications:
>
>Recognize: Recognition is based on theoretically substantiated awareness of cultural differences and ethical aspects in software engineering.
>
>Take into account: Adapt your communication, working, and behavior styles to reflect project stakeholders from different cultures;
>
>Address one of the standard Programming Ethical Guidelines (e.g., ACM Code of Ethics and Professional Conduct) in your work.  

For our group project we have taken a look at the "ACM Code of Ethics and Professional Conduct". With this conduct in mind, we have written a [document](https://github.com/wocevv/Documentation/blob/main/Ethics.md) to explain how we experienced these ethical principles ourselves.
<br><br>

#### 6. Requirements and design (GP)
>Clarification:
>
>Multiple types of test techniques: You apply user acceptance testing and stakeholder feedback to validate the quality of the requirements. You evaluate the quality of >the design (e.g., by testing or prototyping) taking into account the formulated quality properties like security and performance.

One of the first things we did when we started this project was set-up a UI design. We had used the approach that we were taught last semester, wireframes. After sharing these with our stakeholder, they mentioned the concept of "Low-Res" and "High-Res" [UX designs](https://github.com/wocevv/Documentation/blob/main/Design.md). These would give an idea of the applications flow, not just the looks. We started with the Low-Res design and shared these for feedback. With the received feedback we worked on the High-Res design. After a round of feedback and ideas from the stakeholder, we started adjusting our web application to the looks of the High-Res UX design. 
<br><br>
To make sure the flow and design of our website was readable for those not involved in the development, we used [usability tests](https://github.com/wocevv/Documentation/blob/main/usability-test.md). We asked a few students (who had not seen the project before) to complete an assignment. 
<br><br>

#### 7. Business process (GP)
>Clarification:
>
>Simple: Involving stakeholders, predominantly sequential processes with one or two alternative paths.
>
>Related: Business processes during which the software that you are developing will be used (business processes that the software must support by fully or partially >automating them). 
>
>or
>
>Business processes needed for the success of your software development project (e.g., product release, market release, financial assurance).

When we started this project, our stakeholders mentioned they had interest in continuing the project after we finished the semester. To make sure they could pick-up the project, we have written multiple guides/documents on our work. These range from an [ERD](https://github.com/wocevv/Documentation/blob/main/ERD.md), [UX Designs](https://github.com/wocevv/Documentation/blob/main/Design.md), [advice/tips](https://github.com/wocevv/Documentation/blob/main/Advice%20for%20the%20project.md) and [code explenation](https://github.com/wocevv/Documentation/blob/main/CodeDocument.md).
<br><br>

#### 8. Proffessional (GP/IP)
>
>Clarification:
>
>Professional manner: 
>
>You develop software as a team effort according to a prescribed software methodology and following team agreements. You are able to track your work progress and >communicate your progress with the team.
>
>You actively ask and apply feedback from stakeholders and advise them on the most optimal technical and design (architectural) solutions.
>You choose and substantiate solutions for a given problem.

I started the semester horribly. No motivation, no communication and I did nothing for my IP. This is not the first time this happened to me. Before I started this study, I was a student at the HAN Academy of Physical Education. The main reason I did not finish this study was mental health. During this study I showed a similar lack of motivation. Thankfully I was able to pull myself back and I started, albeit late, semester 3. 
<br><br>
During this shortened journey of semester 3 I have learned a lot about being a software engineer, a student and myself. While I am happy with the progress I have made as a software developer and the new techniques I have learned, I am most proud of my personal growth. I have written a small [journal](https://github.com/Vhalur-PickEms/documentation/edit/main/reflection.md) about this journey and reflected on my progress. 
<br><br>
For the learning outcome itself, I often tried to get feedback and engage in discussion about technical designs. Furthermore, I have tried to be open and communicate often with my teachers, stakeholders and project group members. 
