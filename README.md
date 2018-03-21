# Hayden's Journal

### A place for my musings.

I created a blog a while ago on GitHub pages, and this blog was a place for me to share my tech learnings as well as some ideas around emotional intelligence. I enjoyed and appreciated having this place to express myself.

Now that I know new technologies, I would really like to continue having a place to share my technical learning as well as my daily musings on a variety of different subjects.

I considered getting a blog that I can just post to, but since I am trying to practice and revise my craft,
I have decided to build one instead. I hope this can be a visually pleasing and accessible way for me to share my knowledge and thoughts with all of you! Feedback is always welcome :)


## User Stories

### MVP

As an /authorised/ user:
  * I want to be able to view a home page
  * I want to be able to add a post 
  * I want to be able to view my posts
 

As a user:
  * I want to be able to view a home page
  * I want to be able to see a list of posts to choose from 
  * I want to read a single post in a clear and non cluttered way
  

### Stretch
As an /authorised/ user:
  * I want to be able to edit a post
  * I want to be able to delete a post
  * I want to be able to categorise my posts into 3 categories

As a user:
  * I want to be able to select between 3 different categories of posts.
  * I want see when posts were written
  * I want to be able to contact the person who wrote this
  * I want to be able to see what technologies were used in the making of this site. 

  ---

## Authorised Views (Client Side)
  | name | purpose |
  | --- | --- |
  | CreatePost | A feature on the home page that takes you to a create page, where you can select from a dropdown menu which category this post will be under, and then a basic text entry field which could later become a basic text editor, and then a post button at the bottom which takes you to your new specific post page |
  | EditPost | A feature on a specific post page that takes you to a form that has the preadded details of the post inside of it, and has a 'save changes' button at the bottom, which redirects you to the updated version of that specific post page. |
  | DeletePost | A feature on a specific post page that takes you to an 'are you sure?' screen. |
  
## Views (Client Side)
  | name | purpose |
  | --- | --- |
  | Home | A landing page, includes a variety of subsections for the user to go to. |
  | Technical | A page to display a list of different posts specifically about technical things |
  | Selfcare | Same as technical, just of a different category. |
  | Other | Same as above, a list of posts about some other topics. |
  | SpecificPost | A generic layout for any post added by Hayden the user. Will change based on content. Using ID's of the different posts.|

## Reducers (Client Side)

  | name | purpose |
  | --- | --- |
  | auth | Store information regarding user logins, auth status and auth errors |
  | . | . |
  | . | . |
  | . | . |
  
 ## Actions
 
 ### posts
 
 | type | data | purpose | 
 | --- | --- | --- | 
 | . | . | . | 
 | . | . | . | 
 
 ### auth? 
 | type | data | purpose |
 | --- | --- | --- |
 | RECEIVE_USERS | users | retreive the users from the server | 
 
 ### categories 
  | type | data | purpose | 
| --- | --- | --- | 



## API (Client - Server)

| Method | Endpoint | Protected | Usage | Response |
| --- | --- | --- | --- | --- |
| Post | /api/auth/login | Yes | Log In a User | The Users JWT Token |
| Post | /api/auth/register | Yes | Register a User | The Users JWT Token |
| Get | /api/posts | Yes | Get a list of posts | An Array of posts |
| Post | /api/posts | Yes | Save a completed post | The post has been saved in db |
| Get | /api/post/:id | Yes | Get a specific post from the db | An object that represent the post. |


## DB (Server Side)
  There should be a table of posts. And one table for Hayden's user info, so that the login credentials are remembered. Basically just a default seed that ran, so that nobody else can register.

### User
  | Column Name | Data Type |
  | --- | --- |
  | id | Integer |
  | user_name | String |
  | first_name | String |
  | last_name | String |
  | hash | text |

### Posts
  | Column Name | Data Type |
  | --- | --- |
  | id | Integer |
  | post_name | String |
  | time | Timestamp |
  | contents | String/html |
  | category_id | string |

  ### Categories

 | Column Name | Data Type |
  | --- | --- |
  | id | Integer |
  | category_name | String |
  

 ---
 

## Setup

Run the following commands in your terminal:

```sh
npm install (or yarn install)
knex migrate:latest
knex seed:run

```

  `npm run dev` || `yarn dev` for bundling, watch and nodemon

  `npm start` only runs server (setup for heroku)


## Heroku!!!

### Creating your app

Create your app with `heroku create [name]`

You can check that this was successful by running `heroku apps` to view a list of your apps


### Adding postgres

Add postgresql (hobby dev) to your app at `https://dashboard.heroku.com/apps/[APP NAME HERE]/resources`

Check that pg has been added by running `heroku addons` to ensure the postgresql db is on your app


### Deploying!

Several npm scripts that will be useful for deploying your app to heroku easily:

`npm run h:deploy` will push your local master branch to your heroku app

`npm run h:migrate` will run your knex migrations on your deployed heroku app

`npm run h:seed` will run your seeds on your deployed app

If ever you need to rollback, you can also just use `npm run h:rollback`


### Ta-Da!
Your app should be deployed!