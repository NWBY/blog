So I'll start of by saying that this site took a lot longer than it needed to. It was simply me being lazy that made it take so long.

Building a site similar is very simple and can be deployed in a few hours, all that may take a bit longer is your customisation and styling. This post will only contain a brief overview of the technologies I used to build this project. Part II will start the build process.

The technologies I've used for this project are: [Hugo](https://gohugo.io/), [Gitlab](https://gitlab.com/), [Firebase](https://firebase.google.com/), [AWS Route 53](https://aws.amazon.com/route53/)

# Hugo

Hugo is a static-site generator written in Go. Don't worry if you don't know the Go language, it's really not that important when working with Hugo. All we will use that is related to Go is it's `html/template` library which allows us to build our templates.

# Gitlab

Gitlab is very similar to Github, however it provides built in Continiuous Integration/Continiuous Deployment, with Gitlab Runner. It's completely free when building this project as we stay well within Gitlab's free limits. Their free tier is very generous so you will be able to build other projects with your free account as well.

# Firebase

Firebase is actually designed for app building and deployment, however they provide very generous free static site hosting which includes free SSL support and connecting your site to your own domain.

# AWS Route 53

Route 53 from Amazon Web Services is a cloud based Domain Name System (DNS). It allows us to manage the Nameservers for our site with ease, it's very fast and cheap.

Thats all for the first post in this tutorial series. In the next part of this series I will move onto building the site.
