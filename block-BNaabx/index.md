writeCode

Q. Create a middleware which is similar to morgan(logger) which logs


var express = require('express')
var app = express()

app.get('/', (req,res) => {
  res.send('hi')
})
app.get('/about', (req,res) => {
 res.send('info')
})

app.listen(3000, () => {})

- requested method
- requested url
- current time

Q. Create a middleware which is similar to express.json()

- parses json data and puts it into `req.body`

Q. Create a middleware which functions similar to express.static()
