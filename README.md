The Gatsby project included in this Hasura project is the one that you would get when running `gatsby new <project-name>`

## Pre-requisites

- Ensure that you have the HasuraCLI installed. If not, you can find instructions to install it [here](https://docs.hasura.io/0.15/manual/install-hasura-cli.html).
- Login into Hasura by running `hasura login` in your command shell.

## Getting started 

To get the project, run the following in your command shell:

```bash
$ hasura quickstart hasura/react-gatsby
$ cd react-gatsby
$ git add . && git commit -m "Initial Commit"
```

To deploy the app:

```bash
# Ensure that you are inside the react-gatsby directory
$ git push hasura master
```

The Gatsby app will run at the `ui` subdomain. To open the app in your browser, run 

```bash
$ hasura microservice open ui
```

## Where does my code live?

The code to the Gatsby app can be found inside the `microservices/ui/app` directory.

## Running the app locally

Running the app locally is just like running any node app. Navigate to `microservices/ui/app`

```bash
# If this is the first time
$ npm install
# you can also run gatsby develop to locally run the app
$ npm run develop
```

## Deploying changes 

Deploying on Hasura is literally `git pushing` to an external remote. In this case, that remote is automatically added for you during the `quickstart` step. 

So, after you are done with your changes

```bash
$ git add . && git commit -m "Changes"
$ git push hasura master
```

## Migrating an existing Gatsby app into Hasura

As mentioned in the earlier sections. Your code resides inside the `microservices/ui/app` directory. You can go ahead and modify/replace the contents based on your requirements. 

The only assumptions made for deployment to work seamlessly is 
- All your code resides inside `microservices/ui/app`
- We run the`npm run build` command to build the app. 
- We run the `npm run start` command to serve the built files. 
- The Gatsby app is served at port 8080

If you require, any sort of modification, it's best to modify the build and start command in `package.json`. If that does not suffice, you will mostly have to modify the `Dockerfile` or the `k8s.yaml` file inside `microservices/ui/`. 
