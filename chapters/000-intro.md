# 0. Node.js Training Introduction

## Working Mode

The following text is quite verbose, but we ask that you read it carefully.

This training provides an introduction to the Node.js framework, consisting of several steps. In each step, a set of theoretical concepts is explored, supported by reference documentation, book chapters, tutorials, and videos.

In parallel, a simple application—the _Online Shop_—will be built using the learned concepts. After the learning material for a given step has been sufficiently explored, either new functionality will be added to this application or existing functionality will be refactored.

The application will have little to no user interface. Developers are expected to perform API tests using Postman once the REST APIs are implemented.

All the code written must be published on GitHub.

- Create your own repository on your personal account and give access to your mentors (make sure you specify your name in case you have an esoteric username).
- Commit messages should be suggestive of the changes made. You can push the commits when each individual chapter is finished. 
- [Create](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository) a `develop` branch from the `main` branch **before starting work**.
- In order to request a **code review** from the mentors, you must [open a Pull Request](https://help.github.com/en/articles/creating-a-pull-request) from the `develop` to the `main` branch. Inform them in your **daily standup** of this or through a PM.
- Once the Pull Request is **approved** by the mentors, merge it into `main`.
- Create a new branch from `main` or continue your work on the `develop` branch. Open a Pull Request when you want to request another code review and merge it into `main` after it is approved.
- Repeat as necessary until the training has ended.


## Timeline

This timeline is just for guidance; take time to understand the concepts before moving on.

- **Day 1**: Chapter 0, Chapter 1, Chapter 2
- **Day 2**: Chapter 3
- **Day 3**: Chapter 4 
- **Day 4**: Chapter 5
- **Day 5**: Chapter 5, Chapter 6, **Open a Pull Request**, Fix Review Remarks → Merge to `main` → Create a new branch
- **Day 6**: Chapter 7
- **Day 7**: Chapter 8, **Open a Pull Request**, Fix Review Remarks → Merge to `main` → Create a new branch
- **Day 8**: Chapter 9, Optional Chapters or Fix Review Remarks/Refactor Code

## Notes

- If you find any link broken, **please** inform your mentors to provide you with an alternative.
- Try to speed up the videos to *1.5x/2x* if you find them too slow.

## Environment Setup

You need to install:
 - [Node.js 20 or the latest version](https://nodejs.org/en/)
    - Preferably use [NVM](https://github.com/coreybutler/nvm-windows) to quickly switch between versions.
 - An IDE (Integrated Development Environment) for coding:
    - [VSCode](https://code.visualstudio.com/download) with the [ESLint plugin](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
    - [WebStorm](https://www.jetbrains.com/webstorm/) as an alternative to VSCode. Note: if you are a student, you can use your student license; otherwise, you can use the 30-days trial.
 - [Postman](https://www.postman.com/)
 - [PostgreSQL](https://www.postgresql.org/download/) for the database
    - Preferably, install [Docker Destkop on Windows](https://docs.docker.com/desktop/install/windows-install/) and start a [Postgres database container](https://www.docker.com/blog/how-to-use-the-postgres-docker-official-image/) with Docker Compose.
    - **DO NOT FORGET YOUR USERNAME AND PASSWORD**
 - Optional: [Notepad++](https://notepad-plus-plus.org/downloads/) for a better basic file editing experience
 
 For conducting static code quality checks, two separate mechanisms will be used:
 - The plugin for ESlint code analysis must be used to identify code issues.
 - [Prettier](https://prettier.io) will be enabled, and developers should run it to ensure their code complies with the basics of good formatting.
 
 ## Online Shop
 
The application will handle the management and daily functioning of a small online shop. Business processes include:
 - **Order creation**: an end customer places an order to buy several products (based on stock availability).
 - **Stock management**: product stocks are automatically updated based on customer orders.
 - **Shop analytics**: management should be able to view daily revenue evolution for each individual shop location.

Throughout the application, we assume that prices are always in euros (EUR) and weights are always in kilograms (KG). 

![Data Model](https://raw.githubusercontent.com/msg-CareerPaths/nodejs-training/main/diagrams/careerStart-data-model.svg "Data Model")

 
## ZScaler Issues (OPTIONAL - only when needed)

You might encounter ZScaler issues due to company policies. ZScaler is a proxy that scans and routes the internet traffic of your device, sometimes blocking you from accesing certain internet endpoints.
Thus, if you encounter **SSL certificate errors** (e.g., `UNABLE TO GET LOCAL ISSUER CERTIFICATE`) or simply **connection issues**, this may indicate a ZScaler problem.

First steps:
- Download the certificate offered by the company.
- Save the certificate in `C:\zscaler.crt`.

### WebStorm Issues
- Go to `File → Settings` in your IDE.
- Search for `Proxy` in the search bar.
   - Turn on `Auto-detect proxy settings`.
- Now search for `Server Certificates`.
   - Press the `+` icon in the `Accepted Certificates` section and add the ZScaler certificate.

### Git Issues
- Go to `C:\Users\<your_username>\AppData\Local\Programs\Git\mingw64\ssl\certs` and open `ca-bundle.crt` in Notepad.
- Open `zscaler.crt` in a parallel Notepad instance.
- **Copy** the content from `zscaler.crt` to the bottom of the `ca-bundle.crt` file (leave an empty space after the previous certificate).
- You can make `Git` trust the Windows certificate store by running the following command in a terminal instance: `git config --global http.sslBackend schannel`.

### Node.js Issues
- Open the Windows search bar and type environment.
- Select `Edit environment variables...` and choose `Environment Variables` from the new window.
- In `User variables`, add a new variable with the name `NODE_EXTRA_CA_CERTS` and the value being the path to your saved certificate (`C:\zscaler.crt`).
- Restart your computer.
