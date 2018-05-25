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

This consists 2 servers such as front-end and back-end. The front-end is running as a React application within NodeJS and the back-end is running as a Spring boot application. Front-end sends /authorize request to server via API and AJAX.

This assumes that the registration is already done which means that the user created account with username and password and already got the QR code while registering. The QR code is generated based on a generated secret key which is safely saved somewhere in the server. While logging in, that secret key will be picked up and generate a verification code. This generated one will be compared with the one user entered.

# How to run
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
* Scan the QR code and follow the instruction in the webpage.