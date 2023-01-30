# Enterprise-Web-Development-Labs-
The lab work for CM4025 Enterprise web development

Below is for personal reference only.
------------------------------------------------------------------------------
Basic Instructions?
npm init
npm install express ejs

create public
create public \css : \js : \img   //self explanatory

create views //pages will be stored here .html and .ejs

server js goes outside of sub folders

------------------------------------------------------------------------------
IF START DOESNT WORK
inside package.json 
"scripts":{
  "test": "echo \"Error: no test specified\" && exit 1",
  "start": "server.js" //what is being started so the server file
}
------------------------------------------------------------------------------
SERVER FILE
//Imports
const express = require('express')
const app = express()
const port = 8080
 
//Static files
app.use(express.static('public))
app.use('/css', express.static(_-dirname + 'public/css')) //make sure 2 underscores
app.use('/js', express.static(_-dirname + 'public/js'))
app.use('/img', express.static(_-dirname + 'public/img'))

//Set views
app.set('views', './views')
app.set('view engine', 'ejs')

//for html files
app.get('', (req, res) => {
  res.sendFile(_-dirname + '/views/index.html')
})

//for ejs
app.get('', (req, res) => {
  res.render('index')
})

//ejs when you want to access a page with the url /page
app.get('/about', (req, res) => {
  res.render('about')
})

//Listen on port 8080
app.listen(port, () => console.info('Listening on port ${port}')) //Located on bottom of server



