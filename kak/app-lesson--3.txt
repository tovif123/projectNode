const express = require('express');
const bodyParser = require("body-parser");
const app = express();
app.use(bodyParser.json());


app.get('/', (req, res) => {

    res.send("wellcome")
})
app.get('/home', (req, res) => {

    res.status(200).json("hello home")
})

app.get('/user/:name', (req, res) => {

    console.log(req.params.name)
    res.send(`hello ${req.params.name}`)
})

app.get('/admin/:name/:age', (req, res) => {

    console.log(`hello ${req.params.name} your age ${req.params.age}`)
    res.send(`hello ${req.params.name} your age ${req.params.age}`)

})
app.post('/', (req, res) => {


})
app.post('/home', (req, res) => {
    console.log(req.body)
    res.send(`hello ${req.body.name} your age ${req.body.age}`)
})

app.post('/user', (req, res) => {

    console.log(req.body.name)
    res.json(req.body)
})

app.post('/admin/:name', (req, res) => {
    console.log(req.body)
    res.send(`hello ${req.params.name} your age ${req.body.age}`)

})
app.listen(3000, () => console.log("listenint to port 3000"));