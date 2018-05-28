# spring-react-2-factor-auth

An example how to implement 2-factor authentication

# Overview
Two-factor authentication (also known as 2FA) is a type (subset) of multi-factor authentication. It is a method of confirming a user's claimed identity by utilizing a combination of two different factors: 1) something they know, 2) something they have, or 3) something they are.

# Technology
* Java
* Javascript
* Spring Boot
* React with Node JS
* Time-based OTP
* Docker
* Docker compose

This consists 2 servers such as front-end and back-end. The front-end is running as a React application within NodeJS and the back-end is running as a Spring boot application. Front-end sends /authorize request to server via API and AJAX.

This assumes that the registration is already done which means that the user created account with username and password and already got the QR code while registering. The QR code is generated based on a generated secret key which is safely saved somewhere in the server. While logging in, that secret key will be picked up and generate a verification code. This generated one will be compared with the one user entered.

# How to run without Docker
## Front-end server running as a React application
* Install npm on your local machine.
* Clone this repository
* From terminal, Go to the directory spring-react-2-factor-auth/react-2fa-frontend
* Run command: npm start

## Back-end server running as a Spring Boot application
* Install maven
* From terminal, go to directory spring-react-2-factor-auth/spring-boot-2-factor-auth
* Run command: mvn spring-boot:run

## Open a web browser
* Visit: http://localhost:3000
* Download Google Authenticator App to your mobile phone
* Scan the QR code and follow the instruction in the web page.

# How to run with Docker / Docker Compose
## Docker and Docker Compose installation
* Install docker. Follow the link: https://docs.docker.com/install/
* Install docker-compose. Follow the link: https://docs.docker.com/compose/install/

## Build docker images
### For back-end
I used the plugin "dockerfile-maven-plugin" of Spotify to create docker. Run the following commands:
* cd spring-boot-2-factor-auth
* ./mvnw install dockerfile:build

### For front-end
Run the following commands:
* cd react-2fa-frontend
* docker build -t react-2fa-frontend .

## Run docker images by using docker-compose
Run the docker-compose command to start up both servers:
* docker-compose -f docker-compose-dev.yml up -d
