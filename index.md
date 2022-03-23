## WEB701 Milestone Reviews

### Milestone One Review

In this milestone I created a complete information architecture report for WEB701 Activity Central, Azure devops backlog/sprints and CRUD analysis for the API stubs I made in node/express framework. I tested the API stubs with Postman an application for testing APIs.

I started with my devops backlog creating epics, features, user stories and tasks. It took a while to get off the ground but once I figured out how to assign features to epics and show parents of the features, I assigned to epics so that they show up in the backlogs it was just time consuming to finish the rest. It comprised of adding story points, sprint times assigned to each epic, feature, user stories and tasks.

The information architecture report which had many components from wireframes to mockups and user scenarios. I had a hard time wrapping my head around the metaphors in the report for a while, but I eventually got my head around them. The competitive analysis was hard to do since my idea was quite unique, but I found some charities that had minimal overlap and that didn’t have horrible websites.

My CRUD analysis was spot on. I detailed fourteen APIs between six groups split between registration, login, account, token, activity, and activity sign up. 
Registration and login are very similar with the main difference being one creates a user and the other checks against the database to login. They have one controller each.
Next is account which has a method to find the users own account by ID. From there they will be able to update the details they signed up with in the registration API. Finally, they can choose to delete their account. For a total of total account three APIs.

Token has three APIs. The first is receive token, which creates a token in the use account. The next is a find token API which lets the user view the token on their account page. Finally, the ability to delete a token which will trigger either on the removal of the participation from an event or the user can manually do it themselves and the event auto updates when the corresponding token is deleted.

Lastly there are six APIs for activities, split between activity signup and activities in general. Partners will be able to create activities, update them and delete them from a screen dedicated to them that individuals will not see. There is also an API to get all activities so that we can create a list of events for our homepage and carousel. For four APIs dedicated to seeing activities and managing them.

Activity signup has a method to find an activity so we can bring it up as a pop-up component then an update API for signing up for an activity where clicking “signup” updates the created event by adding a participant then generates a token that updates the individuals account with a reference to the event. These are the last two APIs.
