---
layout: post
title: An api and NextJS frontend in typescript on Zeit Now
---

## Zeit and FaaS
I recently learned more about [Zeit](https://zeit.co/), and decided to roll up my sleeves and dive in for a little project. Zeit's product, [Now](https://zeit.co/now), claims to make serverless application deployment easy and I can just push my code and get work done. I have to say, I've been super impressed! There was a bit of a learning curve to tie together all of the pieces of configuration, but the [example projects](https://github.com/zeit/now-examples) and [documentation](https://zeit.co/docs) are really great.. all of the issues I ran into had solutions readily available.  

Thinking about FaaS (Functions as a Service / Serverless) code, the first concern that comes to mind is how to account for databases and the time it takes to establish a new connection. Provisioning a traditional database like Postgres isn't going to fit in this type of application architecture. I chose to use DynamoDB for this little project, it has great support and [documentation](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GettingStarted.NodeJs.html) for use with NodeJS and Typescript. The database is always alive in AWS and the API provides way more functionality that I'd need.

The second concern is how long it takes a function to come alive from a "cold start" so that the application doesn't feel ridiculously slow. In terms of using Zeit as the provider, this concern is largely out of the hands of the developer, [here's what Zeit has to say about it.](https://zeit.co/docs/v2/deployments/concepts/lambdas/?query=cold%20start#cold-and-hot-boots)

## Typescript and Jest
I wanted to take an opportunity to refresh my experience with Typescript and try to establish it as my go-to for writing Javascript. VSCode has first-class support and integration with Typescript, and helps improve my code and surface the documentation to the methods I use. 

## VSCode Goodness
- Make the most of VSCode
  - vscode-eslint
  - vscode-jest
  - prettier-vscode

## Some Code
