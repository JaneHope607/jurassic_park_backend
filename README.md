# Tyrannogotchi App Backend

Tyrannogotchi is a web browser application inspired by Tamagotchi. A user can create an account, and take care of their virtual dinosaur.

## How To Run: 

In order to run this application, you need to create a free [Okta Developer account](https://developer.okta.com/).

Once you have created an account, follow these steps;

- Log in to your Okta account and navigate to Applications > Add Application



- Click Web and then Next
- Name your app and specify http://localhost:8080/login/oauth2/code/okta as a Login redirect URI
- Click Done, then click Edit to edit General Settings
- Add http://localhost:3000 and http://localhost:8080 as Logout redirect URIs, then save again
- Open this repository with IntelliJ IDEA
- Create application.yml file inside src/main/resources
- Copy and paste the URI of your default authorization server, client ID, and the client secret and add it to the file like this:

spring:
  security:
    oauth2:
      client:
        registration:
          okta:
            client-id: {clientId}
            client-secret: {clientSecret}
            scope: openid, email, profile
        provider:
          okta:
            issuer-uri: https://{yourOktaDomain}.okta.com/oauth2/default
            
- Install the Lombok plugin in IntelliJ IDEA > Preferences > Plugins
- Run ./mvnw spring-boot:run in the Terminal to start

## The brief

Tyrannogotchi is a browser game application where a user can create an account, choose dinosaurs to take care of by feeding and healing them and choose which pen they live in.

### A user should be able to:

- Create an account
- Choose three dinosaurs from the database
- Have a choice of two pens to put their dinosaurs in
- Keep their dinosaurs happy, healthy and full, otherwise they'll die
- Save the game progress


### Extensions:

- Random events such as all dinosaurs breaking out of their pens
- Score system where the user receives points for taking care of the dinosaurs
- Drag and drop for putting dinosaurs into the pens

### Technologies used:

- JavaScript
- React
- Java
- Spring
- Okta
- CSS, Bootstrap
