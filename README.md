# Periodic Tables Capstone Guide
Hi everybody! We are SO close to graduating. I am literally SO PROUD of every single one of you. We've (almost) made it through the hell that is Thinkful by Chegg. My hope is that this guide will be able to relieve some of the stress on you and that it pushes you in a comfortable direction. I will be updating this README as I work through the project and will be putting as much as here as I can. 

On top of that, you can use the Issues tab if you have ANY (literally any) questions or you can post suggestions of content to add to the guide for everyone to see. I will try to be as attentive as I can on this repo. If you would ever like to look at [my project repo](https://github.com/itsdotnickscott/periodic-tables), I will be pushing to the repo when I finish checkpoints as frequently as I can. It's not cheating - this is software engineering. We do not need to reinvent the wheel. Observe and learn through example. Feel free to use that Issues tab to also ask about why I implemented a feature a certain way or how I got around a certain problem.

Of course, I am not proclaiming to be any type of expert at this. I am learning just as much as all of you, and I will make mistakes and blunders. It's all part of the coding experience, baby.

---

### _Table of Contents_
* (0.1) My Current Progress on the Capstone
* (0.2) Starter Code Won't Start
* (0.3) Some Initial Roadblocks

---

#### *(0.1) My Current Progress on the Capstone*
- [ ] US-01 Create and list reservations
- [ ] US-02 Create reservation on a future, working date
- [ ] US-03 Create reservation within eligible timeframe
- [ ] US-04 Seat reservation
- [ ] US-05 Finish an occupied table
- [ ] US-06 Reservation Status
- [ ] US-07 Search for a reservation by phone number
- [ ] US-08 Change an existing reservation

---

#### *(0.2) Starter Code Won't Start*
Surprise! Thinkful starter code will crash when running `npm run start:dev`. If you read my guide for Flashcards, you'll remember the fix.
##### In `./package.json` (make sure you're looking at the file in the root directory):
Change the `start:dev` script to: `"npx concurrently \"npm run start:dev --prefix ./back-end\" \"npm start --prefix ./front-end\""`

---
