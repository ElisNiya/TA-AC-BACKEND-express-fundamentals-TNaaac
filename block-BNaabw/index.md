writeCode

Q. Create a scaffold express application from the scratch with necessary middlewares and routes
touch server.js
npm i morgan cookie-parser


var express = require('express')
var logger = require('morgan')
var cookieParser = require('cookie-parser')

var app = express()
app.use(express.json())
app.use(express.urlencoded({extended:false}))
app.use(express.static(__dirname +'/public'))

app.use(logger('dev'))
app.use(cookieParser())

app.get('/', (req,res) => {
  res.send('__dirname + '/index.html')
})
app.get('/projects', (req,res) => {
  res.send('__dirname + '/projects.html')
})


app.get('/users', (req,res) => {
  res.send(Users Page')
})
app.use((req,res, next) => {
  res.send('Page not found')
})

//custom client/server error

app.use((err, req, res, next) => {
  res.send(err)
})
app.listen(4000, () => {})




- add package.json
- install express and create an express server listening on port 4000
- add middlewares for capturing form/json data
- add middleware for handling static assets
- add third party mddleware for logging and handling cookies
- add 2 sample routes with some random response of your choice

  1. GET -> `/` route
  2. GET -> `/users` route

- add middleware for handling errors

Q. Using the above structure, convert a multipage HTML/CSS project into a node application.

- render all pages on seperate routes, for example
  - main page on `/` route
  - projects page on `/projects` routes etc..
- keep all static assets in public directory, for example

  - images in images/media directory
  - css in stylesheets directory

  Directory Structure should be

  - package.json
  - server.js // main server file
  - public // static asset path for images/css
  - index.html
  - projects.html and so on ..
