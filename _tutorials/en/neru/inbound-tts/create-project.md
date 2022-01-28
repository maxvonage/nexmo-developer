---
title: Create a NeRu Project
description: In this step you learn how to create a NeRu Project.
---

# Create a NeRu Project

In your project folder, run

```
neru init
```

- Choose project name
- Choose the application you created earlier
- Choose runtime environment - `nodejs`
- Choose a region
- Choose the instance name - `dev`
- Skip a template

## Install the NeRu SDK

You now need to install the NeRu SDK and other dependencies, run:

```sh
npm install neru-alpha uuid
```

## Configure your project 

- Open the `neru.yml` file in your favorite editor
- Update the configuration object with the number you bought earlier, and linked to your application.

Your file should look similar to this, with `$VONAGE_NUMBER` being your Vonage number:

```yml
project:
    name: inboundtts
instance:
    name: dev
    runtime: nodejs
    region: aws.euw1
    application-id: f739b3d4-3d49-43b2-91d3-593905857f3a
    configurations:
        contact:
            number: "$VONAGE_NUMBER"
            type: "phone"
```