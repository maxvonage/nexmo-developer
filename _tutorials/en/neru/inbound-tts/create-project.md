---
title: Create a NeRu Project
description: In this step you learn how to create a NeRu Project.
---

# Create a NeRu Project

In your project folder, run

```
neru-cli project create
```

- Choose project name
- Choose runtime environment - `nodejs`
- Choose the application you created in the first stages of this guide
- Choose the instance name - `dev`
- Skip a template

## Install the NeRu SDK

You now need to install the NeRu SDK and other dependencies, run:

```sh
npm install neru-alpha uuid express
```

## Configure your project 

- Open the `neru.yml` file in your favorite editor
- Update the private-key field with the name of your private key (the private key file should be in the same folder as the `.yml` file so there's no need for a relative path)
- Update the configuration field, add a contact object with the number you bought, and linked to your application.

Your file should look similar to this:

```yml
project:
    name: neru-test-app
instances:
    name: eu-dev-test-app
    runtime: nodejs
    region: euw1
    application-id: fcd08ece-f3c2-4adf-bf84-5ba8a1c86e0e
    configuration:
        contact:
            number: "447520616665"
            type: "phone"
    secrets: []
```