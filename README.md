# Lab - Parallel and Distributed Systems (HSE): ToDo List Application with Vue.js

## About

This project is a simple to-do list application built with Vue.js as part of the lab assignment of the module “Parallel and Distributed Systems”. It allows the addition and deletion of ToDo items and thus offers an uncomplicated way to manage tasks. 

## Features

- Add new ToDo items
- Delete existing ToDo items (by entering)
- Display a list of all current ToDo's in table form

## Installation

To get started with this project, clone the repository to your local machine:

### Install the project dependencies:

## Usage
To run the application in development mode, use the following command:

Change to the directory of the project: <br />
`cd frontend`

Build the docker-image from the definition of the dockerfile: <br />
`docker build -t frontend .`

Run the docker-container: <br />
`docker run -p 80 frontend`

This will start a local development server, navigating to "PORTS" and open in your web browser.

## Acknowledgments

- Vue.js for providing a powerful and flexible framework for building web applications.
- The Vue.js community for the support and resources available.

## References

- https://vuejs.org/
- https://vuejs.org/guide/introduction.html
- https://vuejs.org/api/
