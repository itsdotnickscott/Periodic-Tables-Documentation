# Periodic Tables Capstone Guide
### _Table of Contents_
* **0 : Introduction**
  * (0.1) Changelog
  * (0.2) My Current Progress on the Capstone
  * (0.3) Starter Code Won't Start
  * (0.4) Deploying Your App
  * (0.5) Creating Your Databases
  
* **1 : US-01 - Create and list reservations (front end)**
  * (1.1) Tests
  * (1.2) Form
  * (1.3) Dipping our toes back into React
  * (1.4) Dashboard

---

# **0 : Introduction**
Hi everybody! We are SO close to graduating. I am literally SO PROUD of every single one of you. We've (almost) made it through the hell that is Thinkful by Chegg. My hope is that this guide will be able to relieve some of the stress on you and that it pushes you in a comfortable direction. I will be updating this README as I work through the project and will be putting as much as here as I can. 

On top of that, you can use the Issues tab if you have ANY (literally any) questions or you can post suggestions of content to add to the guide for everyone to see. I will try to be as attentive as I can on this repo. If you would ever like to look at [my project repo](https://github.com/itsdotnickscott/periodic-tables), or the [deployed version of my app](https://periodic-tables-frontend-7tiv1r4sx-itsdotnickscott.vercel.app/dashboard) I will be pushing to the repo when I finish checkpoints as frequently as I can. It's not cheating - this is software engineering. We do not need to reinvent the wheel. Observe and learn through example. Feel free to use that Issues tab to also ask about why I implemented a feature a certain way or how I got around a certain problem.

Of course, I am not proclaiming to be any type of expert at this. I am learning just as much as all of you, and I will make mistakes and blunders. It's all part of the coding experience, baby. I recommend you read the instructions first before reading the sections. They'll make a lot more sense in-context!

If I've been a help to you at all during this cohort, I would greatly appreciate some LinkedIn endorsements? Is this basically me asking you to smash that like button?

---

### *(0.1) Changelog*
If I significantly edited a section after it was already written, there's a chance you are missing some updated information. If I ever add a significant chunk to a section, I will put it here so you can stay updated. Also, I will put all edits under an "edit" section so changes are easy to find. Cheers y'all!

---

### *(0.2) My Current Progress on the Capstone*
Front End:
- [ ] US-01 Create and list reservations
- [ ] US-02 Create reservation on a future, working date
- [ ] US-03 Create reservation within eligible timeframe
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

### *(0.3) Starter Code Won't Start*
Surprise! Thinkful starter code will crash when running `npm run start:dev`. If you read my guide for Flashcards, you'll remember the fix.
In `./package.json` (make sure you're looking at the file in the root directory), change the `start:dev` script to: `"npx concurrently \"npm run start:dev --prefix ./back-end\" \"npm start --prefix ./front-end\""`

---

### *(0.4) Deploying Your App*
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

### *(0.5) Creating Your Databases*
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

Front End:
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

// why did i use underscore_case here instead of camelCase?
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

Looks like you got to the bottom. 0_0 I am updating this guide as I build the program, so hopefully some sections get added soon. You're killing it!
