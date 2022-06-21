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

### Milestone Two Review

For milestone two I set out to compare MEVN (MongoDb, Express, Vue and Node) and MERN (MongoDb, Express, React and Node) stacks. Since the backend is the exact same it is just comparing the front end, React vs Vue.

I compared React and Vue on a theoretical basis on its pros and cons, while React/Vue have different approaches they are both easy to use and customise. They both have long term support, large communities, and documentation. (Detailed Web Framework Comparison With Features in 2022, 2021)
I gave a quick introduction to what frameworks are and what their common features are like URL mapping, routing, middleware, and what architecture it was made to be used with primarily but not exclusively (MVC).

I then went over their purpose in the development cycle, mostly their ability to be a scaffold to take care of the routing, middleware and the creation of the server. (‘What Is a Web Framework?’, 2017) This takes many development hours away from making that same scaffolding yourself and you can get on with the business logic which is far more important for interacting with your specific database.

I wrote up the proposal as if I was a part of a charity or a contractor writing about what I propose they should go with to help complete the project as best as possible. Taking into account, React experience among the developers i.e., me, how closely it follows MVC architecture, toolsets of each framework, security like updates to the framework regularly so known security risks are patched, and the ability to find pointers to deal with any known issues. To finally choose React over Vue because while Vue is excellent it loses out on some of those metrics.

While I chose React it would not be a bad choice to use Vue even though I did not choose it. 

Vue has lots of upsides and it would be great to use if I had more experience in it. 

#### References

Detailed Web Framework Comparison With Features in 2022. (2021, October 19). https://www.monocubed.com/blog/web-development-framework-comparison/

What is a Web Framework? (2017, July 28). GoodFirms Glossary - GoodFirms. https://www.goodfirms.co/glossary/web-framework/

### Milestone Three Review

For milestone three I started by writing a report about serverless technology namely, serverless technology. I wrote an introduction to serverless technology, how the technology is relevant to the current state of the internet or web technologies, my research methodology/how to implement it in my project. Then I described the impact it has or will have on users from my perspective, lastly I provided a summary of my findings in the conclusion.

I imported all my backend and reactclient code from milestone two (ms2 folder) and updated the dependencies in ms3 and the reactclient folders plus added new ones like concurrently and axios. Concurrently runs the server and the client at the same time with npm run dev and helps to test and use the build. Axios is a routing and data transfer package that replaces fetch from Javascript/React. It makes it easier because JSON is return automatically and can bypass the object: object Javascript error.

I opted to put the functions for the components above the component JSX,  this made the component files quite large but instead of having screens as one component and components as the logic for them to then import one into the other as a composite component for smaller files I elected to have them in one component file in the components folder.

```
// Home is a component structure example 

const Home = () => {

    return ( 
        <section>
        <h1> <h1/>
            <p>
            
            </p>
        </section>
    )
}

// exports the function and since it is the only component we export as default

export default Home
```
How the home component is called in the App file.
```
// Importing browser router from react router dom for the components

import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';

// Importing components from the components folder

import Home from "./Components/home.js";

// Running the application 

const App = () => {

  // returning the component as JSX to display thems on the page

  return (

    // Router from react-router-dom as a wrapper around main

    <Router>
    <main> 
      {/* 
          Routes from react-router-dom which declare a route, 
          the exact path and the element which is the component for that route 
      */}
    <Routes>
        <Route exact path="/" element={<Home />} />
        </Routes>
    </main>
    </Router>

  );
}

// Exporting the app as default since it is the only function

export default App;
```
As you can see the components use braces {} around code within JSX that compiles down into html to differentiate Javascript from regular html syntax.

I created a registration page which uses react hooks ```import { useRef, useState, useEffect } from "react"; ``` useState, useEffect, and useRef were very helpful as state is used when tracking the changes between valid and invalid usernames, passwords and emails according to my regexor regular expressions.
```
// Using regex or regular expressions to filter out unwanted characters or sequences for usernames

const USER_REGEX = /^[A-z][A-z0-9-_]{3,23}$/;

 const [username, setUser] = useState('');
 const [validName, setValidName] = useState(false);
 const [userFocus, setUserFocus] = useState(false);
```
The useRef was helpful for having a reference of current.focus for user to check the mutable value of the fields in my registration and login form.
```
    const userRef = useRef();
    
        useEffect(() => {
        userRef.current.focus()
    }, [])

 <label htmlFor="username">
                    Username:
                </label>
                <input
                    type="text"
                    id="username"
                    ref={userRef} // Referencing the userRef hook to set the focus on the input field
                 /> // snippet of user to show userRef
                 
    useEffect(() => {

    // Checking if the username is valid by testing the regex on the username value input in the field

        setValidName(USER_REGEX.test(username));
    }, [username])
```
As you can see useEffect is great for having the userRef show the current value of the mutable fields and for checking if the username is valid by using our custom state of setValidName to be the user regex we defined above.

Next I added screen reader functionality to the registration form by using the code below to tell the screen reader what to read out in what voice.
```
aria-invalid={validPassword ? "false" : "true"} 
aria-describedby="passwordnote" 
```
The biggest part of the code is the handleSubmit function which deals with the data and submits the form onSubmit as a class in the form JSX.

It has the axios data handler function called response uses axios.post to pass a variable = to the server route with the username, email, and password we passed along with the state we need to track login success plus error handling to stop bad usernames, emails and passwords passing.

It changes a bit across registration and login but it is quite similar.

I enjoyed making the login and registration for this app. Interacting between the frontend and backend is quite satisfying.
