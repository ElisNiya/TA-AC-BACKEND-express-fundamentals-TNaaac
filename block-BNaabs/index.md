writeCode

Create a basic express server and add routes:-

- Add a GET request on '/' route and render 'index.html' file using `res.sendFile`.
- Add a GET request on '/new' route and render new.html with a html form.
- add a post request on '/new' route and display submitted form data
- add a route with params to grab request made on `/users/1234` or `/users/asdf`

var express = require('express')

var app = express()

app.use(express.json)
app.use(urlencoded({extended:false}))
app.use(express.static(__dirname + '/public'))
app.use(logger('dev'))



app.get('/', (req,res) => {
  res.sendFile(__dirname + 'index.html')
})

app.get('/new', (req,res) => {
  res.sendFile(__dirname + 'new.html')
})

app.post('/new', (req,res) => {
  res.json(req.body)
})

app.get('/users/:username, (req,res) => {
  var username = req.params.username
  res.send(username)
})

app.listen(3000, () => {})
