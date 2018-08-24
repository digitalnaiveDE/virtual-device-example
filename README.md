# Bespoken Virtual Device: YAML Test Scripts Demo
The Virtual Device Test Scripts are meant to make it easy for anyone to write automated tests for Alexa (and Google Assistant, soon).

They use a simple YAML syntax for allowing anyone to write complex (but still readable) end-to-end tests.

## Setup

### Install Bespoken Virtual Device
Make sure you have npm installed, [get it here](https://www.npmjs.com/get-npm).

Install Bespoken CLI to run the scripts. Open a command-line and run this command:  

```
npm install bespoken-tools -g
```
### Get your Virtual Device Token
First, you need to get a token. See [here for instructions](https://read.bespoken.io/end-to-end/setup/).

### Configure your test scripts:  
Each test script contains the token for each locale and other important parameters. We have included our tokens on each test script file in this repo so you can run them and see them in action. You should add
your tokens when creating your own test scripts. 

**FYI - the included tokens are so that new users can get started quickly. However, they are common tokens and will NOT work as reliably as creating your own.** Please follow the steps above to create your own Virtual Device Tokens.

* Within your test script add a configuration section like the example shown below.
* Add the locale for the test script, the Amazon Polly voiceId you wish to use and the Virtual Device token.
```yaml
---
configuration:
  locale: en-US
  voiceId: Joey
  virtualDeviceToken: f7e91d64-0477-427c-95b6-15cade37a323
```

### Additional parameters  
You will notice there is a file named testing.json in the sample project. This file contains extra configuration parameters like these:
```json
{
  "type": "e2e",
  "homophones": {
    "lettuce": ["let us"],
    "figs": ["six","6","vicks"]
  },
  "trace": false,
  "jest": {
    "silent": true
  }
}
```
* Homophones: Use this to specify words with similar sound, for example if you receive "let us" instead of "lettuce" or "six" instead of "figs".
* Trace and silent: Both parameters allows you to get extra information from the response payload, to enable set trace to true and silent to false.
 
## Running tests
Once you have created your tests, you can run a particular file by entering:
```
bst test test-directory\my-test-file.yml
```

To run a directory containing many tests, provide the directory path instead:
```
bst test test-directory
```

That command will run all yml files that are contained within that directory.

That's it! Now just wait, and your tests will run.

## More Info and Docs
See the full docs for the test scripts [here](https://read.bespoken.io/end-to-end/getting-started/).

## Questions/Feedback? 
Help is only a few clicks away. Have questions or feedback? Email us at [ivan@bespoken.io](mailto:ivan@bespoken.io) or [jpk@bespoken.io](mailto:jpk@bespoken.io) 
