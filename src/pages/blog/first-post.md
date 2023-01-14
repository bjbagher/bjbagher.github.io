---
layout: "../../layouts/BlogPost.astro"
title: "error: getaddrinfo ENOTFOUND localhost"
description: "Lorem ipsum dolor sit amet"
pubDate: "Jan 08 2023"
heroImage: "/assets/astro-image.jpg"
---

## Why is it happening

When installing Astro for the first time or any other framework on Mac, you may encounter with the following error:

`error: getaddrinfo ENOTFOUND localhost`

This is because your machine could not find a mapping to localhost. To solve the issue you are going to want to add this mapping.

## How to solve

1. Run the following command(use your preferred editor)
   `sudo vim /etc/hosts`

2. Add the following line to the file
   `127.0.0.1 localhost`
