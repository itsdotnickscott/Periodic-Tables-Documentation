# Periodic Tables Capstone Guide
### _Table of Contents_
* **0 : Introduction**
	* (0.1) Changelog
	* (0.2) My current progress on the capstone
	* (0.3) Starter code won't start
	* (0.4) Deploying your app
	* (0.5) Creating your databases
  
* **1 : US-01 - Create and list reservations (front end)**
	* (1.1) Tests
	* (1.2) Form
	* (1.3) Dipping our toes back into React
	* (1.4) Dashboard

* **2 : US-02 - Create reservation on a future, working date (front end)**
	* (2.1) Tests
	* (2.2) Tuesdays
	* (2.3) Reservation date is in the past
	* (2.4) Hooking it up

* **3 : US-03 - Create reservation within eligible timeframe (front end)**
	* (3.1) Tests
	* (3.2) Time is in the past
	* (3.3) Time constraints
	* (3.X - Optional) Form validation

---

# **0 : Introduction**
Hi everybody! We are SO close to graduating. I am literally SO PROUD of every single one of you. We've (almost) made it through the hell that is Thinkful by Chegg. My hope is that this guide will be able to relieve some of the stress on you and that it pushes you in a comfortable direction. I will be updating this README as I work through the project and will be putting as much here as I can. 

On top of that, you can use the Issues tab if you have ANY (literally any) questions. You can also post suggestions of content to add to the guide for everyone to see. I will try to be as attentive as I can on this repo. If you would ever like to look at [my project repo](https://github.com/itsdotnickscott/periodic-tables), or the [deployed version of my app](https://periodic-tables-frontend-7tiv1r4sx-itsdotnickscott.vercel.app/dashboard), I will be pushing to the repo when I finish checkpoints as frequently as I can. Looking at my code and my process is not cheating! This is software engineering - we don't need to reinvent the wheel. Observe and learn through example. :P Feel free to use that Issues tab to also ask about why I implemented a feature a certain way or how I got around a certain problem.

Of course, I am not proclaiming to be any type of expert at this. I am learning just as much as all of you, and I will make mistakes and blunders. It's all part of the coding experience, baby. I recommend you read the instructions first before reading the sections. They'll make a lot more sense in-context!

If I've been a help to you at all during this cohort, I would greatly appreciate some LinkedIn endorsements? Is this basically me asking you to smash that like button?

---

### *(0.1) Changelog (NEW 5/11/2021)*
If I significantly edited a section after it was already written, there's a chance you are missing some updated information. If I ever add a significant chunk to a section, I will put it here so you can stay updated. Also, I will put all edits under an "edit" section so changes are easy to find. Cheers y'all!

#### May 11th
* Edited all of Section 2. (solution changed)

---

### *(0.2) My current progress on the capstone*
Front End:
- [ ] US-01 Create and list reservations
- [X] US-02 Create reservation on a future, working date
- [X] US-03 Create reservation within eligible timeframe
- [ ] US-04 Seat reservation
- [ ] US-05 Finish an occupied table
- [ ] US-06 Reservation Status
- [ ] US-07 Search for a reservation by phone number
- [ ] US-08 Change an existing reservation

Back End:
- [ ] US-01 Create and list reservations
- [ ] US-02 Create reservation on a future, working date
- [ ] US-03 Create reservation within eligible timeframe
- [ ] US-04 Seat reservation
- [ ] US-05 Finish an occupied table
- [ ] US-06 Reservation Status
- [ ] US-07 Search for a reservation by phone number
- [ ] US-08 Change an existing reservation

---

### *(0.3) Starter code won't start*
Surprise! Thinkful starter code will crash when running `npm run start:dev`. If you read my guide for Flashcards, you'll remember the fix.
In `./package.json` (make sure you're looking at the file in the root directory), change the `start:dev` script to: `"npx concurrently \"npm run start:dev --prefix ./back-end\" \"npm start --prefix ./front-end\""`

---

### *(0.4) Deploying your app*
The project recommends you deploy early and often. The EASIEST way to do this is by deploying via GitHub, not the commandline.
1. Initialize and push your app onto a new GitHub repository.
2. If you cloned the project, then it is possible that the project is still connected to Thinkful's repo. We need to delete the `.git` folder in the directory (NOT `.github`). If you can't find the `.git` folder, go to your File Explorer, and view hidden items. You should be able to see it and delete it.
3. [Create a project on Vercel](https://vercel.com/new).
4. Link up your GitHub account if you haven't already.
5. If everything's good up till this point, you should be able to import your capstone project into vercel.
6. Select your personal account.
7. Select the `back-end` folder, and press 'Continue'.
8. Blah blah blah options. Name the project so you can tell it is the backend, something like `periodic-tables-backend`.
9. Deploy, baby!!
10. After it is deployed, the preview should say something like `{"error":"Path not found: /"}`. Good news: this error is good. It means it deployed correctly.
11. Time to do the same process but for the `front-end` folder. [Create a project on Vercel again](https://vercel.com/new) and import the same GitHub repo. You don't have to do anything special. You'll notice that the final settings page recognizes that it is a React app. That's neat!
12. If everything worked out, you should see the base template of the starter project. The BEST part about deploying via GitHub is that Vercel will automatically update your website **every time you push your project into your GitHub repo**. That saves SO MUCH headache from deploying via the command line, at least in my opinion.

---

### *(0.5) Creating your databases*
Here's a refresher on ElephantSQL and DBeaver!
1. [Create a new instance](https://customer.elephantsql.com/instance/create).
2. Select a name and tag. I named one of mine `pt-devlopment` and gave it a `Periodic Tables` tag.
3. Select a region closest to you. I chose US-West because.....west coast best coast. I'm sorry, I don't make the rules.
4. Create instance.
5. Time to do this three more times for `test`, `preview`, and `production`! : ^)

Time to move onto DBeaver.
1. Click on New Connection (it looks like a blue plug with a plus sign).
2. Choose PostgreSQL.
3. Using the information from ElephantSQL:
  * Host will be the "Server"
  * Database and Username will be the "User & Default database"
  * Password can be copied using the clipboard icon
4. If all of that works, the "Test Connection" button should show a successful connection.
5. Rename the connection so they're easily identifiable.
6. Time to do this three more times!!! Don't have too much fun!
7. (Optional) I made a `periodic-tables` folder using the yellow folder icon and moved all of my connections into there. Organization! B)

Last thing to do...
1. Go to your `.env` file in the `./back-end` folder.
2. Update all of those URLs with the corresponding "URL" on ElephantSQL. Like the password, there is a clipboard button for easy pasting.

I hope that was easy for you, but it is okay if it isn't yet. You're going to be a pro in no time.

---

# **1 : US-01 - Create and list reservations (front end)**
The testing for this project is a bit more frustrating than what we've dealt with before. Running `npm run test:1`, firstly, cannot run at the same time as your servers if you ran `npm run start:dev` (they are on the same port...). Secondly...I have a hard time getting `npm run test:1` to even work. It just crashes, and I'm guessing it's because I haven't done some part of the code yet. (However, I have been successful with `npm run test:1:frontend`.) Thirdly, even when the tests do run, it's sometimes really difficult to see what the tests even are.

---

### *(1.1) Tests*
You can always look at the test files yourself, but I LOVE having all of the tests in a list for easy reference, so here they are! (tests checked off are tests that are passing for my current code).

- [ ] filling and submitting form creates a new reservation and then displays the dashboard for the reservation date
- [X] canceling form returns to previous page

---

### *(1.2) Form*
I am going to try my best to be as in-depth as I can about my process as a programmer and how I am personally building my app. I'm going to start by building up the front-end entirely. I'm not working to style it at all. I'm getting what I need to be displayed on each page to create a minimum-viable product (MVP) without focusing on little details. I am a very detail-oriented person, but I know I have to ignore it and save it for later, because it's not going to help right now!

Of course, this is YOUR project and YOUR workflow. YOU decide what to do and when!

Let's make our new component. Here is what I generally do when first creating a React component.
```javascript
// 1. import react
// 2. create component function & export it
// 3. create a return statement (most, if not all react components will return some JSX)

import React from "react";

// i named my component NewReservation:
export default function NewReservation() {
	return (
    	// JSX will be placed here as we build our component
	);
}
```

`/layout/routes.js` - Before we build our page, we need to route it!
```javascript
// code before & after ommited for brevity (from now on, this will be represented by ...)

<Route exact={true} path="/reservations/new">
	<NewReservation />
</Route>
```

`/reservations/NewReservation.js` - Let's make our form and our inputs.
```javascript
// here is what my form looks like
return (
	<form>
		<label htmlFor="first_name">Field Name</label>
		<input
			name="first_name"
			id=="first_name"
			type="text"
			onChange={} // we will add this in soon!
			value={} // this as well!
			required // this will make the field non-nullable
		/>
        
		// now to make the rest of them!
	</form>
);
```

Let's look at some helpful input types:
* "text" - value is a string
* "number" - value is a number
* "tel" - value is a phone number (i'd suggest looking up the [pattern attribute](https://www.w3schools.com/tags/att_input_pattern.asp) as well)
* "date" - string
* "time" - string

Let's make some buttons.
```javascript
<form>
	// ...
	<button type="submit" onClick={}>Submit</button>
	<button type="button" onClick={}>Cancel</button>
</form>
```

Byotiful.

---

### *(1.3) Dipping our toes back into React*
*shudder* It's React...

Let's start by setting up our form data with the `useEffect` hook.
```javascript
import React, { useState } from "react";

export default function NewReservation() {
	// recall that useState takes the form [state, setState], where setState is an asynchronous function
	const [formData, setFormData] = useState();
}
```

We now want to create an initial, default form that the user will see when first visiting the page.
```javascript
// we get to put this right inside of our useState hook as an object:
const [formData, setFormData] = useState({
	first_name: "",
	last_name: "",
	mobile_number: "",
	reservation_date: "",
	reservation_time: "",
	people: 0,
});

// ??? why did i use underscore_case here instead of camelCase?
// all of our <input> fields have a name that uses underscore case. when we are editing the form fields later, we want to be consistent with the field names.
```

Everytime a user makes a change to an input, we want to record that as a state.
```javascript
function handleChange({ target }) { // i deconstruct the `event` argument
	// we will be using our useState hook to store whatever changes are made.
	// this is why we use underscore case; when we access target, we get the input name in underscore_case.
	setFormData({ ...formData, [target.name]: target.value });
	// remember to use the spread operator `...` so all previous values do not get overwritten.
}
```

Recall that we left some attributes blank on the inputs...`onChange` and `value`. Let's go in and fill it now!
```javascript
// example:
<input

	// ...
    
	onChange={handleChange} // the function we just made! the onChange attribute will automatically pass the `event` argument based off of which input was clicked
	// we can use our useState hook to store the values of each input now
	value={formData.first_name}
/>

```

Both the cancel and submit button will be redirecting people. Let's refresh ourselves with our useHistory hook:
```javascript
import { useHistory } from "react-router-dom";

export default function NewReservation() {
	const history = useHistory();

	// example code:
	// recall how to bring back someone back a page:
	history.go(-1);
    
	// you can also call:
	history.goBack(); // this is the same as the one above!
    
	// great, let's put this into our onClick handler for cancel!
	<button type="button" onClick={history.goBack}>Cancel</button>
```

As of now, the cancel button test is passing for me.

Let's make our submit handler. As of right now, I'm not going to be sending this form anywhere, because there's no where to send it to! We'll come back to this in the future.
```javascript
function handleSubmit(event) {
	event.preventDefault(); // the normal submit refreshes the entire page. we don't want that to happen!
  
	// in the future, we will be editing this submit handler to actually post the request to the database. i'm not worried about it right now though!
  
	// the submit button will be redirecting the user to the dashboard on a specific date.
	// the dashboard will have a URL query with the date. it looks like /dashboard?date=2035-12-30
	// so i will be replicating this here. on top of this, i imported one of the util functions in the utils folder. yeesss! less code for me to write.
	// the push function literally "pushes" the user to whatever path you give.
	history.push(`/dashboard?date=${formatReservationDate(formData.reservation_date)}`);
}

// ...

// time to add our function to the submit button!
<button type="submit" onClick={handleSubmit}>Submit</button>
```

If you run your tests, you'll see hat the submit test is still failing. It's an async error, so I think this might be because not everything is set up yet. Great job refreshing yourselves with React. It's been a bit.

Here's what my page looks like now. Ugly and unformatted! :)

![/reservations/new initial screenshot](https://user-images.githubusercontent.com/64234681/117707205-1ff64f00-b183-11eb-8991-188f07d50f97.JPG)

---

## *(1.4) Dashboard*
Thinkful is hiding a lot of information in different files. Keep in mind the starter code that is already written for you because they WILL be helpful. Particularly, the `utils` folder. Let's go look at how we can use some of them!

You'll see in the Dashboard that a lot of it is already set up. It's great because it means we don't have to figure out how to do certain tasks, and it sucks because we don't quite know what it even does right now. Let's go over the existing code together and point out some important bits of code.

```javascript
// at the top of the function, we can see that there are two states being stored. the reservations state is especially important because it is holding the response from our API! (right now the API returns nothing; we haven't made it yet)
const [reservations, setReservations] = useState([]);
const [reservationsError, setReservationsError] = useState(null);

// useEffect will call loadDashboard every time the date prop changes
useEffect(loadDashboard, [viewDate]);

function loadDashboard() {
	// recall that the abort controller is used for async calls. it is used to avoid race conditions!
	const abortController = new AbortController();
	
	// no errors
	setReservationsError(null);
	
	// time to make our API call! the first parameter { date } is the search parameter for the database. we will come back to this function later.
	listReservations({ date }, abortController.signal)
		.then(setReservations)
		.catch(setReservationsError);
		
	// here's where all other abortControllers will dump their async calls - race conditions fixed!
	return () => abortController.abort();
}

// this return statement already has a component that will show errors if something goes wrong. then, it stringifies the response from the API.
// right now, the stringify will still output some javascript-looking strings. we will want to find another way later to format this nicely for the user. however, we don't have to worry about that yet!
return (
	<main>
		<h1>Dashboard</h1>
		<div className="d-md-flex mb-3">
			<h4 className="mb-0">Reservations for {date}</h4>
		</div>
		<ErrorAlert error={reservationsError} />
		{JSON.stringify(reservations)}
	</main>
);
```

Firstly, we have to acknowledge the query in the URL. If there is no date query, today's date will be used. You can see this happening in `/layout/Routes.js` at the `<Dashboard />` component. Luckily, our handy `utils` folder has a custom React hook to grab the query! Let's check it out in `/utils/useQuery.js`:
```javascript
/**
 * useQuery is a custom hook that makes use of the useLocation and the URL class to parse the query parameters.
 *
 * @example
 *
 * const query = useQuery();
 * const date = query.get("date")
 */

import { useLocation } from "react-router-dom";

function useQuery() {
	return new URLSearchParams(useLocation().search);
}
```

We don't need to fully understand how the function works to use it! Let's go implement it in `layout/Routes.js`!
```javascript
// i chose this file because this is where the dashboard is routed from.
import useQuery from "../utils/useQuery";

function Routes() {
	const query = useQuery();
	const date = query.get("date");

// ...

// now we can use this for our Dashboard component:
<Route path="/dashboard">
	{ /* i use a ternary here. if date exists, pass in that date. otherwise, just send in today's date. */ }
	<Dashboard date={date ? date : today()} />
</Route>
```

Let's make some buttons back in `reservations/NewReservation`. The `utils` folder has some helpful functions for us! We will be importing and creating a history variable with the useHistory hook.
```javascript
// these functions will give the day before, the day today, and the next day, respectively.
import { previous, today, next } from "../utils/date-time";
import { useHistory } from "react-router-dom";

function Dashboard({ date }) {
	const history = useHistory();
	
	// ...

	return (
		<main>
			<h1>Dashboard</h1>
			<div className="d-md-flex mb-3">
				<h4 className="mb-0">Reservations for {date}</h4>
			</div>
			<ErrorAlert error={reservationsError} />

			{JSON.stringify(reservations)}

			<button type="button" onClick={() => history.push(`/dashboard?date=${previous(date)}`)}>Previous</button>
			<button type="button" onClick={() => history.push(`/dashboard?date=${today()}`)}>Today</button>
			<button type="button" onClick={() => history.push(`/dashboard?date=${next(date)}`)}>Next</button>
		</main>
	);
```

Notice I edited the `<h4>` element to show the date. If we go to our web page and test out our buttons, we can see the date actually changing!

![dashboard buttons example](https://user-images.githubusercontent.com/64234681/117718994-b7fb3500-b191-11eb-8c2c-a7afcd860419.gif)

---

# **2 : US-01 - Create reservation on a future, working date (front end)**
For this user story, we will be adding some features onto our NewReservation component. We will be validating the reservation date after a user tries to submit the form. Let's head on over to `/reservations/NewReservation.js`! (This is where I organized this file - yours might be in a different location / have a different name.)

I'd like to note that for this section, I spent a bit coming up with a solid solution to this problem. The Date class CAN be tricky, since dates are treated as if they are a UTC time. However, sometimes JavaScript will use your local time zone at times to interpret them. We have to be careful what "time zone" we are working in (I'm referring to UTC as a time zone even though it technically isn't).

Looking at the [Date class documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) was helpful during this user story.

There are two paths we can go down:
- Work completely in UTC
- Work completely in the user's time zone

I'm deciding to work in the user's time zone so we can base everything off of their local time zone.

I didn't record my whole process in this guide. I'm just giving you my current solutions to the checkpoints. What might seem like a simple solution took a good bit of refactoring and simplifying. If you'd like to take a good shot at this before reading, please do! Otherwise, let's go solve this thing!

> EDIT (5/11): If you read this before it was changed, my old solution worked completely in UTC. After moving onto the third user story, I realized that working in the user's local time zone might be easier in the long run.

---

## *(2.1) Tests*
- [X] displays an error message if the date of the reservation occurs in the past
- [X] displays an error message if reservation date falls on a Tuesday

---

## *(2.2) Tuesdays*
Second worst only to Mondays. Looks like the restaurant is closed on Tuesdays, and we should display errors to the user if they try to reserve on a Tuesday.

`/layout/ErrorAlert.js` - Before we start writing our validation code, let's take a look at the `ErrorAlert` component that was included with the starter code.
```javascript
/**
 * Defines the alert message to render if the specified error is truthy.
 * @param error
 *  an instance of an object with `.message` property as a string, typically an Error instance.
 * @returns {JSX.Element}
 *  a bootstrap danger alert that contains the message string.
 */

function ErrorAlert({ error }) {
	return (
		error && (
			<div className="alert alert-danger m-2">Error: {error.message}</div>
		)
	);
}

export default ErrorAlert;
```

This component was also used in the `Dashboard` component when there is an error grabbing the reservations. `ErrorAlert` uses a `<div>` with `className="alert alert-danger m-2"`, so this will satisfy the tests.

`reservations/NewReservation.js` - Let's check to see if the reservation date is a Tuesday!
```javascript
// i'm going to create my own function here, specialized to validating the reservation date.
function validateDate() {
	// we will be using the built-in Date class to be comparing our dates
	// previously in this file, we stored the form's input values in a react state called formData
	// we can access that here, and use the Date constructor
	// the string is already stored in the format YYYY-MM-DD, so we don't have to do anything special to the string...at least not yet.
	const reserveDate = new Date(formData.reservation_date);
	
	// it's possible we can have multiple errors when a date is submitted. i am going to initialize an array to hold these errors
	const foundErrors = [];
	
	// the Date class has many functions, one of which returns the day (0 is sunday, 6 is saturday)
	if(reserveDate.getDay() === 2) {
		// it's tuesday...let's push in an error object to our array!
		foundErrors.push({ message: "Reservations cannot be made on a Tuesday (Restaurant is closed)." });
	}
}
```

---

## *(2.3) Reservation date is in the past*
Let's keep building on our validation function. I would like to start by grabbing today's date.
```javascript
function validateDate() {
	const reserveDate = new Date(formData.reservation_date);
	
	// we will need to compare the reservation date to today's date.
	// an empty constructor defaults the date to whatever it is right now
	const todaysDate = new Date();

	const foundErrors = [];

	if(reserveDate.getDay() === 2) {  
		foundErrors.push({ message: "Reservations cannot be made on a Tuesday (Restaurant is closed)." });
	}
}
```

Next, we will be comparing dates. After creating a bit of a complex algorithm to check if a certain date is in the past, I realized the `Date` class can be compared normally. This solution is significantly more elegant. There are some restrictions on comparing dates...if you want to know more about them, [check this out](https://stackoverflow.com/questions/492994/compare-two-dates-with-javascript)!
```javascript
if(reserveDate < todaysDate) {
	foundErrors.push({ message: "Reservations cannot be made in the past." });
}
```

---

## *(2.4) Hooking it up*
We should now successfully be finding these errors, but as of right now, we're not doing anything with them. The reservation will still submit normally, no matter what. We will need to hook it up with the rest of the `NewReservation` component.
```javascript
// my solution involves creating a new state that will contain the errors
const [errors, setErrors] = useState([]);
```

We'll have the validation function set its found errors into the state. If there were no errors, it'll remain an empty array.
```javascript
function validateDate() {
	// ...

	setErrors(foundErrors);
}
```

Now, we'll have the validation be called after every time the submit button is pressed.
```javascript
function handleSubmit(event) {
	event.preventDefault();

	// if there are errors, we don't want to push the user onto a different page, we want them to stay on this page until the issue is resolved.
	// because of this, i'm thinking of adding a return statement to our validation function that will be true when the date is valid and false if it isn't.
	// that way, we only push the user if there are no errors with the reservation date.
	if(validateDate()) {
		history.push(`/dashboard?date=${formData.reservation_date}`);
	}
}
```

Great! I want to go add those return statements I was talking about.
```javascript
function validateDate() {
	// ...

	setErrors(foundErrors);

	// we can use our foundErrors array to check if there were any problems.
	if(foundErrors.length > 0) {
		return false;
	}
	// if we get here, our reservation date is valid!
	return true;
}
```

The last thing we have to do is have the errors display if there are any.
```javascript
// ...
	
// i'm going to create an errors variable that maps every error into an ErrorAlert component
// no errors? returns nothing.
const errors = () => {
	return dateErrors.map((error, idx) => <ErrorAlert key={idx} error={error} />);
}

return (
	<form>
		{ /* we can throw our errors right at the top, so they'll be noticeable to the user */ }
		{errors()}

		<label htmlFor="first_name">First Name:&nbsp;</label>
			
		// ...
	</form>
);
```

All my front-end tests for US-02 are passing! Time to see it in action:

![new reservations date errors example](https://user-images.githubusercontent.com/64234681/117870533-15a28680-b251-11eb-9f0d-a3252f8a1d02.gif)

---

# 3 : **US-03 - Create reservation within eligible timeframe (front end)**
This user story is exactly like the previous one except with the time instead of the date. We'll mostly keep working within the same file with the same validation function. Let's go!

---

## *(3.1) Tests*
- [X] displays an error message if reservation time is before 10:30 AM
- [X] displays an error message if reservation time is too close to close time
- [X] displays an error message if reservation time is after the close time

---

## *(3.2) Time is in the past*
Let's talk about date strings. They look like this: `2021-05-11T01:48:04.123`. The date YYYY-MM-DD goes first, then a capital letter T, then the time in HH:MM:SS:XXX, where XXX is milliseconds ranging from 000 - 999. Knowing this, we can change how we initialize our `Date` object so we can utilize time in our validation function as well.
```javascript
// i changed the constructor to be a date string with time included
const reserveDate = new Date(`${formData.reservation_date}T${formData.reservation_time}:00.000`);
```

The best part is, this small change still works on this piece of code! If you try to make a reservation for today at 12:00pm when the time is already 12:01pm, this error message will pop up.
```javascript
// this comparison still works, because it is taking account time as well now
if(reserveDate < todaysDate) {
	foundErrors.push({ message: "Reservation cannot be made: Date is in the past." });
}
```

---

## *(3.3) Time constraints*
The rest of this user story is easy to implement. We set up some conditions and check to see if any of them are triggered.
```javascript
function validateDate() {
	const reserveDate = new Date(`${formData.reservation_date}T${formData.reservation_time}:00.000`);
	const todaysDate = new Date();
	
	const foundErrors = []

	if(reserveDate.getDay() === 2) {  
		foundErrors.push({ message: "Reservation cannot be made: Restaurant is closed on Tuesdays." });
	}

	if(reserveDate < todaysDate) {
		foundErrors.push({ message: "Reservation cannot be made: Date is in the past." });
	}

	// in english: if it is before 10:30am...
	// in code: if the hour is not yet 10 or the hour is 10 but below 30 minutes...
	if(reserveDate.getHours() < 10 || (reserveDate.getHours() === 10 && reserveDate.getMinutes() < 30)) {
		foundErrors.push({ message: "Reservation cannot be made: Restaurant is not open until 10:30AM." });
	}
	
	// in english: if it is after 10:30pm...
	// if the hour is after 22 or the hour is 22 and after 30 minutes...
	else if(reserveDate.getHours() > 22 || (reserveDate.getHours() === 22 && reserveDate.getMinutes() >= 30)) {
		foundErrors.push({ message: "Reservation cannot be made: Restaurant is closed after 10:30PM." });
	}
	
	// in english: if it is after 9:30pm...
	// if the hour is after 21 or the hour is 21 and after 30 minutes...
	else if(reserveDate.getHours() > 21 || (reserveDate.getHours() === 21 && reserveDate.getMinutes() > 30)) {
		foundErrors.push({ message: "Reservation cannot be made: Reservation must be made at least an hour before closing (10:30PM)." })
	}
	
	setErrors(foundErrors);

	if(foundErrors.length > 0) {
		return false;
	}
	return true;
}
```

Errors working as expected!

![new-reservation-time-errors-example](https://user-images.githubusercontent.com/64234681/117885032-2ad3e100-b262-11eb-9a83-064bef47f23b.gif)

---

## *(3.X - Optional) Form validation*
While we're still working on this form, I think it's important for the form to show an error if fields are left blank. I won't go in-depth about my process, since it isn't connecte to a certain test, but you can check out how I did it here.
```javascript
function handleSubmit(event) {
	event.preventDefault();

	// i move the foundErrors array in the submit handler so both validation functions can push to the same array
	const foundErrors = [];

	// i created a validateFields function. you can see i now pass foundErrors as an argument
	if(validateFields(foundErrors) && validateDate(foundErrors)) {
		history.push(`/dashboard?date=${formData.reservation_date}`);
	}

	// this also used to be inside of validateDate(), now moved here.
	setErrors(foundErrors);
}

// sparkly new validation function
function validateFields(foundErrors) {
	for(const field in formData) {
		if(formData[field] === "") {
			foundErrors.push({ message: `${field.split("_").join(" ")} cannot be left blank.`})
		}
	}

	if(formData.people <= 0) {
		foundErrors.push({ message: "Party must be a size of at least 1." })
	}

	if(foundErrors.length > 0) {
		return false;
	}
	return true;
}
```

Here's what this looks like:

![new-reservation-field-validation-example](https://user-images.githubusercontent.com/64234681/117885758-147a5500-b263-11eb-9ced-c667421f2fbf.gif)

---

Looks like you got to the bottom. 0_0 I am updating this guide as I build the program, so hopefully some sections get added soon. You're killing it!
