writeCode

Create a basic express server

- add listener on port 4000
- create a custom app level middleware which consoles request `url` and `method` and passes executio to next middleware in line.

var express = require('express')

var app = express()

app.use('/about', (req, res, next) => { next() })

app.get('/', (req, res) => {
  res.send('welcome')
})

app.listen(3000, () => {})
