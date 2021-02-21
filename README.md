# :rocket: MERN authentication with email verification, hooks and docker (prod/dev).

![capture du 2018-12-16 13-57-42](https://user-images.githubusercontent.com/40322270/50053751-aa653080-013a-11e9-9a8d-35a55c9042f1.png)

:video_game: Demo: <https://mern-auth-client.herokuapp.com/login>

:warning: CSS styles, Google Captcha, Sentry usage and some other not essential dependencies like notifications are only in the demo. This repository aim to have a fast to use boilerplate.

## :star: The project if it helped you!

# :whale: Docker

Boilerplate now is fully usable with docker, it integrate the MongoDB database, the React/Redux frontend and NodeJS/Express backend.

If you do not have docker: <https://docs.docker.com/get-docker/>

Docker allows to deloy the app in docker containers in one line in the CLI.

## Environment variables

In both docker-compose.yml and docker-compose-prod.yml file you have to set the following environment variables:

- SENDGRID_API_KEY, the backend uses Send Grid to send emails, you can register and get a free key on their website: <https://sendgrid.com/>. :warning: You cannot use the app without a key. Validation links are sent in http not https, you can modified that in server/routes/auth.js if you want to go https in deployment.

- SESSION_KEY, it is the secret key that is used to compute the hash of sessions. It is important to use a strong key: <https://cloud.google.com/network-connectivity/docs/vpn/how-to/generating-pre-shared-key>.

- SENDING_EMAIL, email address that sends emails in the app. Has to be set.

## Development

in the root directory:

`docker-compose up --build`

It supports hot reloading for both the frontend and backend.

## Production

in the root directory:

`docker-compose -f docker-compose-prod.yml up --build`

Frontend app uses an Nginx server to deliver static files.

You may want to use the flag `--remove-orphans`

To deploy on Heroku refer to their documentation:
<https://devcenter.heroku.com/categories/deploying-with-docker>

## :computer: Boilerplate

MERN Stack with advanced authentication :

- Email verification (Token Based) with resend/reset option, Login with forgot password feature.

- Server side sessions.

- Docker for development and production with hot reloading.

- Mongodb.

- Express.

- React/Redux based on Create React App.

- React Hooks.

- Nodejs.

- Passport-js local.

- Sendgrid API for emails.

## :lock: Security

This repository is scanned with snyk and code scanning from github for vulnerabilities. Do not use this code blindly, audit it first.

## :information_source: How to ?

- Use emails for authentication instead of usernames: <https://github.com/flaviuse/mern-authentication/issues/7>

- I added a dependency but my docker container does not found it: <https://medium.com/@semur.nabiev/how-to-make-docker-compose-volumes-ignore-the-node-modules-directory-99f9ec224561> (either install the dependency in the container with the cli or reset the volume).
