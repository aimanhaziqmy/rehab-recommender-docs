---
sidebar_position: 1
---

## Getting Started

To test the api, you can use **[https://www.postman.com/](https://www.postman.com/)**

## Below are the list of api
### Users

#### GET

```bash
https://rehab-recommender-v1.vercel.app/api/user
```
List all the users. You also can add `email=me@example.com` query to get the specific person. For example : 

```bash
https://rehab-recommender-v1.vercel.app/api/user?email=aimanhaziqyazik@gmail.com
```

#### POST

Create exercise 
```bash
https://rehab-recommender-v1.vercel.app/api/user
```

Create a user into the database. Here are the json body needed to create a user : 
```bash 
{
  name: string(), //required
  email: string(), //required
  height : number(), //required
  weight: number(), //required
  age: number(), //required
  heartRate: number(), //required
  spo2: number(), //required
  comordibities : boolean(), //required
}
```

#### PUT

To update the user information
```bash
https://rehab-recommender-v1.vercel.app/api/user
```

To update a user. Here are the json body needed to create a user : 
```bash 
{
  name: string(), //required
  email: string(), //required
  height : number(), //required
  weight: number(), //required
  age: number(), //required
  heartRate: number(), //required
  spo2: number(), //required
  comordibities : boolean(), //required
}
```

### Exercises

#### GET

Get all list of exercise in the database.
```bash
https://rehab-recommender-v1.vercel.app/api/exercises
```

#### POST

Create an exercise into the database
```bash
https://rehab-recommender-v1.vercel.app/api/exercises
```
Here are the body required to create exercise into the database : 
```bash
{
  name: string(), //required //name of the exercise
  intensity: number(), //required //intensity from 1 to 8
  duration: number(), //required //in seconds
  intensityType: string(), //required //Beginner - Intermediate - Advance
  type : string(), //required //strength-cardio-etc
}
```
### Recommendation system

#### GET
Get personalize exerxise recommendation by using GET with `email=me@example.com` query for specific patients. 

```bash
https://rehab-recommender-v1.vercel.app/api/exercises?email=aimanhaziqyazik@gmail.com
```

#### POST (optional)

This is an optional process, but necessary to do. After finished doing all the exercise, to make the system more robust and meet the user need in the future - the ratings data of each exercise must be feed back into the system. The data should be in this form for each exercise : 

```bash
{
  ratings : [
    {
      name : "name of the exercise"
      rating : 1 - 5
      type : "cardio"
      item : "ids of the exercise that fetch early from the database"
    },
    {
      name : "test"
      rating : 3
      type : "strength"
      item : "afhoifhn134qagffs"
    },
    {
      name : "test2"
      rating : 3
      type : "cool down"
      item : "pfakh283hn154trsx"
    },
    {
      name : "test3"
      rating : 5
      type : "warm up"
      item : "90xgf823gax72i1af"
    }
  ]
}
```

```bash
https://rehab-recommender-v1.vercel.app/api/exercises
```