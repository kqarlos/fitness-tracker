# Fitness Tracker

![Languages](https://img.shields.io/github/languages/count/kqarlos/fitness-tracker)
![Top Language](https://img.shields.io/github/languages/top/kqarlos/fitness-tracker)
![Code Size](https://img.shields.io/github/languages/code-size/kqarlos/fitness-tracker)
![Repo Size](https://img.shields.io/github/repo-size/kqarlos/fitness-tracker)
![Total Lines](https://img.shields.io/tokei/lines/github/kqarlos/fitness-tracker)
![Express V](https://img.shields.io/github/package-json/dependency-version/kqarlos/fitness-tracker/express)
![Mongoose V](https://img.shields.io/github/package-json/dependency-version/kqarlos/fitness-tracker/mongoose)
![Morgan V](https://img.shields.io/github/package-json/dependency-version/kqarlos/fitness-tracker/morgan)
![Last Commit](https://img.shields.io/github/last-commit/kqarlos/fitness-tracker)
[![HitCount](http://hits.dwyl.com/kqarlos/fitness-tracker.svg)](http://hits.dwyl.com/kqarlos/fitness-tracker)
![Followers](https://img.shields.io/github/followers/kqarlos?style=social)

## Description

Track your workouts with Fitness Tracker. The app will keep track of every exercise in your workout. The app dashboard will display weekly summary graphs of all workouts done in a week.

## Table of Contents

* [Installation](#installation)
* [Usage](#usage)
    * [Screenshots](#screenshots)
    * [Snippets](#snippets)
* [Credits](#credits)
* [License](#license)

## Installation

1. Clone repository. 
2. Check in routes/api-routes and comment in block of code if you want the database to be prepopulated with dummy values
3. npm install
4. node server.js

Running seeders/seed.js is optional to have a prepopulated database.

* [See Live Site](https://track-your-fitness.herokuapp.com/?id=5e3b1ea870e2390017f01261)

## Usage

### Screeshots

1. Homepage displaying last workout

![Site](public/assets/homepage.png)

2. Creating Workouts

![Site](public/assets/live.gif)


3. Last Week's Summary

![Site](public/assets/dash.png)

### Snippets


1. Adding to an array type

```javascript

    // add exercise
    app.put("/api/workouts/:id", (req, res) => {

        db.Workout.findOneAndUpdate(
            { _id: req.params.id },
            {
                $inc: { totalDuration: req.body.duration },
                $push: { exercises: req.body }
            },
            { new: true }).then(dbWorkout => {
                res.json(dbWorkout);
            }).catch(err => {
                res.json(err);
            });

    });
    
```
* This function will add an exercise to the array of exercises that belong to the workout with the given id. Here we will locate the workout with the given ID and update its fields. We will increase the total duration of the workout by the duration of the exercise being inserted. We will push the exercise to the array of exercises.


## Credits

### Author

- Carlos Toledo: [portfolio](https://professional-portfolio2020.herokuapp.com/)
- Github: [kqarlos](https://www.github.com/kqarlos)
- LinkedIn: [carlos-toledo415](https://www.linkedin.com/in/carlos-toledo415/)

### Built With

* [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
* [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [Bootstrap](https://getbootstrap.com/)
* [Javascript](https://www.javascript.com/)
* [Node.js](https://nodejs.org/en/)
* [Express](https://www.npmjs.com/package/express)
* [MongoDB](https://www.mongodb.com/)

## License

![License](https://img.shields.io/github/license/kqarlos/fitness-tracker)
