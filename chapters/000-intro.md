# 0. NodeJS Training Introduction

## Description 
First, I would like to start by emphasizing with reader that the following read is quite verbose, but I would like to ask that you read the following carefully.

This is a roadmap/training for a introduction into the Angular Framework consisting of several steps.
In each step, a set of theoretical concepts are explored, supported by reference documentation, book chapters, tutorials and videos. 

In parallel, a simple application will be built with the learned concepts: the *Online Shop* application.
After the learning material for a given step was sufficiently explored either some new functionality will be added to this application or old functionality will be refactored.

## Working Mode

The road-map consists of several steps. In each step, a set of theoretical concepts are explored, supported by reference documentation, book chapters, tutorials and videos. In parallel, a simple application will be built with the learned concepts: the *Online Shop* application.

After the learning material for a given step was sufficiently explored, either some new functionality will be added to this application or old functionality will be refactored.

The application will have little-to-no user interface. Developers are expected to perform developer tests with Postman once the REST APIs are implemented.

All the code written must be published on GitHub.

- Create your own repository on your personal account and give access to your mentor (make sure you specify your name in case you have an esoteric username).
- Commits must be pushed when each individual chapter is finished. 
- [Create](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository) a `develop` branch from the `master` branch **before starting work**.
- **In order to request a code review from the mentors**, you must [open a pull request](https://help.github.com/en/articles/creating-a-pull-request) from the `develop` to the `master` branch. Inform them in your **daily standup** of this or through a PM.
- **Once the Pull Request is approved** by the mentors, merge it into `main` and create another branch from master to continue work.
- Take care to delete your `develop` branch then, go back inside your IDE to `main` and update it (git pull)
- Carry on your work by creating another `develop` branch and working on it
- Repeat ad infinitum (until the training has ended)


## Timeline
This timeline is just for guidance, take time to understand the concepts before moving on.

- **Day 1**: Chapter 0, Chapter 1, Chapter 2
- **Day 2**: Chapter 3
- **Day 3**: Chapter 4, 
- **Day 4**: Chapter 5
- **Day 5**: Chapter 5, Chapter 6, **Open a Pull Request**, Fix Review Remarks => Merge to Master => Create a new branch,
- **Day 6**: Chapter 7
- **Day 7**: Chapter 8, **Open a Pull Request**, Fix Review Remarks => Merge to Master => Create a new branch,
- **Day 8**: Chapter 9, Optional Chapters or Fix Review Remarks/Refactor Code

## Notes
- If you find any link broken, **please** inform your mentor to give you an alternative.
- Try to speed up the videos to *1.5x/2x* if you find them too slow.

## Environment Setup
You can work using your local environment. You need to install:
 - Install [NodeJS 20 or latest](https://nodejs.org/en/)
    - Preferably use [NVM](https://github.com/coreybutler/nvm-windows) to quickly switch between versions
 - You will need an IDE (Integrated Development Environment) so you can code
    - [VSCode](https://code.visualstudio.com/download) with the [ESLint plugin](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
    - [Webstorm](https://www.jetbrains.com/webstorm/) as an alternative to VSCode. Note if you are still a student you can use your student license on it, otherwise you can use the 30 days trial.
 - [Postman](https://www.postman.com/)
 - Install [PostgreSQL](https://www.postgresql.org/download/) for the database
    - Preferably install [Docker Destkop on Windows](https://docs.docker.com/desktop/install/windows-install/) and start a [Postgres Database container](https://www.docker.com/blog/how-to-use-the-postgres-docker-official-image/) with Docker Compose
    - **DO NOT FORGET YOUR USERNAME AND PASSWORD**
 - Have also [Notepad++](https://notepad-plus-plus.org/downloads/) for a nicer basic file editing experience
 
 For doing static code quality checks, two separate mechanisms will be used:
 - The plugin for ESlint code analysis must be used to identify code issues.
 - [Prettier](https://prettier.io) will be enabled and developers should run it in order to make their code comply with basics of good format.
 
 ## Online Shop
The application will deal with the management and daily functioning of a small online shop. Business processes:
 - **Order creation**: an end customer places an order to buy several products (based on the availability of the products in the stock).
 - **Stock management**: the existing product stocks are updated automatically based on the orders placed by customers.
 - **Shop analytics**: the management must be able to view the evolution of the daily revenue for each individual location of the shop.

Throughout the application, we assume that prices are always in EUR and weights are always in KG. 

![Data Model](https://raw.githubusercontent.com/msg-CareerPaths/nodejs-training/main/diagrams/careerStart-data-model.svg "Data Model")

 
## ZScaler Issues (OPTIONAL - only when needed)

You might encounter ZScaler issues due to company bureaucracy. ZScaler is proxy that scan and routes the internet traffic of your device, blocking you from accesing certain internet endpoints.
Thus, if you encounter `SSL CERTIFICATE ERRORS`, `UNABLE TO GET LOCAL ISSUER CERTIFICATE` or simply connection issue this **may** point you to a ZScaler problem.

First steps:
- Download the certificate offered by the company
- Save the certificate in C:\zscaler.crt

### Webstorm Issues
- Go to File\Settings in your IDE
- Search for `Proxy` in the search bar
- Turn on the `Auto-detect proxy settings`
- Search for `Server Certificates`
- Press the `plus` icon in the Accepted Certificates tables and add the Zscaler certificate

### Git Issues
- Go to `C:\Users\<your_username>\AppData\Local\Programs\Git\mingw64\ssl\certs` and open `ca-bundle.crt` in Notepad
- Open in a parallel notepad instance the `zscaler.crt`
- **Copy** the content from `zscaler.crt` to the bottom of the `ca-bundle.crt` file (leave an empty space between)
- You can make `Git` trust the Windows certificate store by running in a terminal instance `git config --global http.sslBackend schannel`

### Node.js Issues
- Open windows search bar and type `environment`
- Select `Edit environment variables...` and select `Environment Variables` from the new window
- In User variables add a new one with the name `NODE_EXTRA_CA_CERTS` and the value being the `path to your saved certificate` (C:\zscaler.crt)
- Restart your computer