---
title: Create a NeRu Project
description: In this step you learn how to create a NeRu Project.
---

# Create a NeRu Project

In your project folder, run
```sh
neru-cli project create
```

- Choose project name (You can leave it with the folder name as default by just pressing enter)
- Choose runtime environment - `nodejs`
- Choose the application you created in the first stages of this guide
- Choose the instance name - `dev`
- Choose the template for this sample - `AkiraQuizVoice`

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

## Initialize JavaScript dependencies

By initializing your NeRu project with the `AkiraQuizVoice` template you now have in your folder the code to run the quiz.

You now just need to make sure to have all the dependencies of the JS code set correctly, run:

```sh
npm install
```