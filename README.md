# 3.12 Serverless CICD Pipeline

Sample repository for assignment with practical walkthrough on Feb 22

Note: `index.js` have been updated for a practical walkthrough on Mar 5, refer to last header

---

## Main assignment objective

- Deploy the application to AWS Lambda (serverless platform)
- Configure the pipeline to automatically deploy the code to the serverless platform whenever changes are pushed to the code repository and all tests pass.

## Step 1

- Create a blank repository on Github with README.md
- Update README.md

## Step 2

- Run command on local Linux terminal to install Serverless Framework

`nvm install lts` & `npm install -g serverless`

- Check to confirm installation

`serverless -v` or `sls -v`

- Create json file 

Run `npm init` or `serverless`, introduce new files `index.js` & `serverless.yml`

## Step 3

- Update `serverless.yml` with configuration

`npm install serverless`

`npm install serverless-offline --save-dev`

- Run serverless

`sls offline start` or `serverless offline`

- Edit code to change port

`sls offline start --httpPort 3003`

## Step 4

Deploy Serverless

`serverless deploy` or `sls deploy`

## Step 5

- Add unit testing

`npm install --save-dev jest` or `npm install --save-dev jest -g`

New file `index.test.js` will be created

- Update `package.json`

Within `scripts :`

Replace `"test": "echo \"Error: no test specified\" && exit 1"` with `"test": "jest"`

- Update `index.js`

Replace `input: event`

## Step 6

- Delete/remove serverless application

`sls remove`

## Step 7

- Update CICD Github Actions workflow

Create `main.yml` to deploy to serverless platform with workflow

## Additional practical

`index.js` content prior to Mar 5 CloudWatch application logging practical walkthrough

```json
module.exports.handler = async (event) => {
    return {
      statusCode: 200,
      body: JSON.stringify(
        {
          message: "THIS IS OUR HTTP RESPONSE!",
          input: event,
        },
        null,
        2
      ),
    };
  };
  ```
