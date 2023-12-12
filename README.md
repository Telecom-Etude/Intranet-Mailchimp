# Faster Email Campaigns *using Mailchimp API*

This intranet website is available at [https://mri.telecom-etude.fr](https://mri.telecom-etude.fr) !

## Introduction

The goal of this project is to take advantage of the Mailchimp API to send quickly custom HTML-emails to a professional mailing-list.
As the sent emails all use the same template, and as the only difference between them is the content of the sections, we created a website allowing users to write the text of these sections.
Then, the node.js backend creates the HTML content of the email from the content written, and creates a Mailchimp campaign.
Finally, a test email is sent to auditors for review.

![example](/resources/ExampleMRI.png)

- We thanks [corentin-ryr](https://github.com/corentin-ryr) and [hugoqnc](https://github.com/hugoqnc) for the first version of this project.
- Vue documentation is available at [https://telecom-etude.github.io/mri.telecom-etude.fr](https://telecom-etude.github.io/mri.telecom-etude.fr)
- the ability to create campaigns with this deployed website is restricted to active members of [Telecom Etude](https://telecom-etude.fr) Junior-Entreprise. This is achieved with the necessity to sign in with a `@telecom-etude.fr` Google Workspace account.

## Development

### Front-End

The Front-End development uses the [Vue.js](https://vuejs.org) framework, with the [Vuetify](https://vuetifyjs.com/en/) library. This allow beautiful handcrafted Material Design components.

![animation](/resources/SendingAnimation.gif)

### Back-End

The Back-End uses [Node.js](https://nodejs.org/en/), with the [Mailchimp API](https://mailchimp.com/developer/marketing/api/). This Back-End is hosted with Firebase, using [Cloud Functions for Firebase](https://firebase.google.com/docs/functions).

## Deployment

```bash
# to have the firebase command (which is the firebase CLI)
npm install -g firebase-tools

# we recommend to login and even to logout and login again
firebase logout
firebase login

# in the project, files like firebase.json and .firebaserc are used to configure the deployment
# they have been generated with the command
cd mailchimp-backend && firebase init
cd mailchimp-frontend && firebase init
```

### Deployment Front-End

```bash
# as the project is quite old, we use nvm to use the specific node 12 version
cd mailchimp-frontend

# set up creds, you need to have the credentials
# from https://console.firebase.google.com/project/mailchimp-backend/settings/general/
touch src/firebaseCredentials.json

# build with node 12
nvm use lts/erbium
npm install
npm run build
# deploy with latest node
nvm use default
firebase deploy
```

### Deployment Back-End

```bash
cd mailchimp-backend
firebase deploy
```
