---
title: Adventure Choosen Project
description: Social Media App to connect people with events
date: 2023-09-13
tags: 
---
# Adventure Choosen
Have you ever moved to a new city, and wanted to start pursuing your hobbies, or wanted to see what events were going on with your friends. These are the usecases that the Adventure Choosen project created by my team for the Software Development Practices class. In this class, we made a Spring Boot backend paired with a java - android front end to make a compelling app to help connect people to events near them.
We used a CI/CD pipeline that allowed us to get immediate feedback on the progress of our project, and thouroughly tested our code through both unit and integration testing. As a member of the backend team, I used Jakarta Persistence to manage data and store it in our mysql database.

## Structure
To create Adventure Choosen, we had Users, Interests, and Events. Each of these entities had an associated image that was stored in a database file.
Users could be friends with other Users, and Users had Interests.
Events had Users who would be attending them, and would have an interest associated with them. Example: 
Name is Volleyball at the park, Location: Address of some park, Interest: Volleyball, Users Coming: (List Of Users Coming)
```

On the Users feed, Users would be recommended events based off of location, interests, friends who had already signed up.
This would be ranked by the algorithm which is based off of previous behaviour, optimized for events that you are most likely to attend.

After an event, You can rate the event which will help to optimize the algorithm for future recomendations

## Experienced Gained
Through this project, I gained experience in working on a Team, Java - Springboot, Jakarta Persistance, Unit testing, Integration Testing, CI/CD.
It also helped cement the project development process, going from just an idea to a functioning demo. This class reinforced my experience modeling data, as that was a huge part of the design decisions that I made.

If you have any questions about this project, feel free to reach out, my linkedin is at the top of the page!
