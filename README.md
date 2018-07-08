# Creating a Retail Chatbot using Watson Conversation, Discovery and Database Services

*Read this in other languages: [English](README.md), [한국어](README_ko.md)*

In this developer Code Pattern we will create a Watson Conversation based chatbot that allows a user to: 1) find items to purchase using Watson Discovery, and 2) add and remove items from their cart by updating a Cloudant NoSQL Database.

When the reader has completed this Code Pattern, they will understand how to:

* Create a chatbot dialog with Watson Conversation
* Dynamically store and update a Cloudant NoSQL database based on chatbot results
* Seed data into Watson Discovery and leverage its natural language capabilities
* Manage and customize a Slack group to add a chatbot

![](doc/source/images/architecture.png)

## Flow

1. The user sends a message to the slackbot for online store.
2. Slack sends this message to the running application.
3. The application orchestrates the interactions between the various Watson services.
4. The application queries the Cloudant database for the user's information, including the contents of their shopping cart, and writes the contents back to the database as they change.
5. The application interacts with Watson Conversation to determine which response to send to Slack, and information passed back and forth in the conversation context determines actions within the application.
6. Watson Discovery is used to get information about the items in the online store.

## Included Components

* [Watson Conversation](https://www.ibm.com/watson/developercloud/conversation.html): Create a chatbot with a program that conducts a conversation via auditory or textual methods.
* [Watson Discovery](https://www.ibm.com/watson/developercloud/discovery.html): A cognitive search and content analytics engine for applications to identify patterns, trends, and actionable insights.
* [Cloudant NoSQL DB](https://console.ng.bluemix.net/catalog/services/cloudant-nosql-db): A fully managed data layer designed for modern web and mobile applications that leverages a flexible JSON schema.
* [Slack](https://slack.com): Slack is a cloud-based set of team collaboration tools and services with chat bot integration.

## Featured Technologies

* [Python](https://www.python.org/): Python is a programming language that lets you work more quickly and integrate your systems more effectively.

# Steps

**NOTE:** Perform steps 1-7 **OR** click the ``Deploy to IBM Cloud`` button and hit ``Deploy`` and then jump to step 6.

## Deploy to IBM Cloud

[![Deploy to IBM Cloud](https://metrics-tracker.mybluemix.net/stats/5fd641e32af04e4adb16f26c46de3587/button.svg)](https://bluemix.net/deploy?repository=https://github.com/IBM/watson-online-store&cm_mmc=github-code-_-native-_-retailchatbot-_-deploy2bluemix)

> There is no web UI (only Slack), so don't use the ``View app`` button to see the app. Use the IBM Cloud dashboard to find and manage the app. Use your Slack UI to chat.

## Run locally

1. [Clone the repo](#1-clone-the-repo)
2. [Create IBM Cloud services](#2-create-ibm-cloud-services)
3. [Get IBM Cloud credentials and add to .env](#3-get-ibm-cloud-services-credentials-and-add-to-env-file)
4. [Configure Watson Conversation](#4-configure-watson-conversation)
5. [Configure Watson Discovery](#5-configure-watson-discovery)
6. [Configure Slack](#6-configure-slack)
7. [Run the application](#7-run-the-application)
