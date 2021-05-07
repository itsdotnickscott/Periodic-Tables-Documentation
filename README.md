# Periodic Tables Capstone Guide
Hi everybody! We are SO close to graduating. I am literally SO PROUD of every single one of you. We've (almost) made it through the hell that is Thinkful by Chegg. My hope is that this guide will be able to relieve some of the stress on you and that it pushes you in a comfortable direction. I will be updating this README as I work through the project and will be putting as much as here as I can. 

On top of that, you can use the Issues tab if you have ANY (literally any) questions or you can post suggestions of content to add to the guide for everyone to see. I will try to be as attentive as I can on this repo. If you would ever like to look at [my project repo](https://github.com/itsdotnickscott/periodic-tables), I will be pushing to the repo when I finish checkpoints as frequently as I can. It's not cheating - this is software engineering. We do not need to reinvent the wheel. Observe and learn through example. Feel free to use that Issues tab to also ask about why I implemented a feature a certain way or how I got around a certain problem.

Of course, I am not proclaiming to be any type of expert at this. I am learning just as much as all of you, and I will make mistakes and blunders. It's all part of the coding experience, baby. I recommend you read the instructions first before reading the sections. They'll make a lot more sense in-context!

---

### _Table of Contents_
* (0.1) My Current Progress on the Capstone
* (0.2) Starter Code Won't Start
* (0.3) Deploying Your App
* (0.4) Creating Your Databases

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

#### *(0.3) Deploying Your App*
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

#### *(0.4) Creating Your Databases*
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

I hope that was easy for you, but it is okay if it isn't yet. This is all new stuff!

---
