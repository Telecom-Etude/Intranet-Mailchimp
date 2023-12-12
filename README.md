# Faster Email Campaigns *using Mailchimp API*

This intranet website is available at [https://mri.telecom-etude.fr](https://mri.telecom-etude.fr) !

## Introduction

The goal of this project is to take advantage of the Mailchimp API to send quickly custom HTML-emails to a professional mailing-list.
As the sent emails all use the same template, and as the only difference between them is the content of the sections, we created a website allowing users to write the text of these sections.
Then, the node.js backend creates the HTML content of the email from the content written, and creates a Mailchimp campaign.
Finally, a test email is sent to auditors for review.

![example](/resources/ExampleMRI.png)

- We thanks [corentin-ryr](https://github.com/corentin-ryr) and [hugoqnc](https://github.com/hugoqnc) for the first version of this project.
- documentation is available at [https://corentin-ryr.github.io/Intranet-Mailchimp/](https://corentin-ryr.github.io/Intranet-Mailchimp/)
- the ability to create campaigns with this deployed website is restricted to active members of [Telecom Etude](https://telecom-etude.fr) Junior-Entreprise. This is achieved with the necessity to sign in with a `@telecom-etude.fr` Google Workspace account.

## Development

### Front-End

The Front-End development uses the [Vue.js](https://vuejs.org) framework, with the [Vuetify](https://vuetifyjs.com/en/) library. This allow beautiful handcrafted Material Design components.

![animation](/resources/SendingAnimation.gif)

### Back-End

The Back-End uses [Node.js](https://nodejs.org/en/), with the [Mailchimp API](https://mailchimp.com/developer/marketing/api/). This Back-End is hosted with Firebase, using [Cloud Functions for Firebase](https://firebase.google.com/docs/functions).

## Deployment
