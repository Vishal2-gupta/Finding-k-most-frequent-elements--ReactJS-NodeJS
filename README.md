# Invictus Assignment
Impleted Using Create React Project as Front-end with bootstrap css and Node.js as Backend.

Live - [Click here to see invictus Test Cases in HEROKUAPP](https://invictus-work.herokuapp.com/ )


## Folder Structure for Invictus Assignment
![Folder-Structure]
![Screenshot (420)](https://user-images.githubusercontent.com/62341045/118395555-a79efa80-b668-11eb-9108-23d55bedb46b.png)
![Screenshot (421)](https://user-images.githubusercontent.com/62341045/118395570-bc7b8e00-b668-11eb-89de-1bf120a1e782.png)
![Screenshot (422)](https://user-images.githubusercontent.com/62341045/118395573-c1d8d880-b668-11eb-8f90-8faf50e19edb.png)

## Frontend
Following packages are used:
* react
* react-router-dom
* axios - for making promise based api calls in react
* sweet alert - for showing alerts
* Bootstrap css

There are following 2 Components:
* Nav -
It is the Navigation components shown at the top of the page.

* Home -
The Home page shown when you run it. <br/>
It has an input field that takes an integer n and a submit button to send to the backend.<br/>
OnSubmit ```getOccurence()``` function is called that takes N from inout and makes an API call to ```/get-occurence?n=${n}```. It uses axios i.e promise based to make ajax requests.</br>
Upon Success the the response comes in ```then()``` block and in case of error it comes in ```catch()``` block.<br/>
In then we got the response and if response Status is 1 then i set the state ```data``` as the ```response.data``` using the ```setState()``` function.
In catch i show an alert showing error message.<br/>
```render method:```
In render function I iterate over the this.state.data array and create a row i.e. '<tr>' containing the word and no of occurence and then that row is shown in the table.

## Backend
Following packages are use:
* express
* body-parser - to parse the POST req body in node
* axios - to make call to fetch a file hosted at [https://raw.githubusercontent.com/invictustech/test/main/README.md]  (https://raw.githubusercontent.com/invictustech/test/main/README.md)
* cors - to enable cross origin resource sharing

The ```GET /get-occurence``` endpoint is called after submitting the value of N from front-end. The N is passed in the query string.

Let's undertand the code that fetches file README.md and finds top N most frequent occurance words.

We use ```axios.get``` to fetch the ```README.md``` file from Invictus website.

I got the string in the ```result``` variable, then I replce the new line characters and tabs with spaces using ```result.replace(/\n\t/g, " ")```.

Then i split the string by delimeter ```" "``` which returns an array of words from the result string.

Then iterate over each word in the array and store the no of occurence of each words in the object ```occrenceMap```.

Then finally sort the ```OccurenceMap``` object by value i.e by count of occurence and return an array from it.

Then slice the top N most frequent words from the array and return it as response.

## The TestCase with data and Screenshot is placed below.

->Startup screen as below.
![Screenshot (425)](https://user-images.githubusercontent.com/62341045/118396206-10d43d00-b66c-11eb-8cbf-b6f326de61bd.png)

User can enter N number and do submit.The result is shown below as N=13
![Screenshot (427)](https://user-images.githubusercontent.com/62341045/118396243-4842e980-b66c-11eb-9bab-b29de45548cf.png)

Table Screenshot
![Screenshot (426)](https://user-images.githubusercontent.com/62341045/118396271-690b3f00-b66c-11eb-81d4-c246bfea3f37.png)

## About HerokuApp
Heroku is a container-based cloud Platform as a Service (PaaS). Developers use Heroku to deploy, manage, and scale modern apps.The Heroku experience provides services, tools, workflows, and polyglot support—all designed to enhance developer productivity.

## About Command for HerokuApp

->For login use
$ heroku login -i
heroku: Enter your login credentials
Email [XYZ@gmail.com]:
Password: XYZ

->To upload files on HerokuApp
$ git push heroku master

->To know more about CLI command for heroku
https://devcenter.heroku.com/articles/heroku-cli-commands









