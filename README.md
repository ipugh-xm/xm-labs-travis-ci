# Travis CI

This integration allows you to get the results of a Travis CI build in xMatters.


---------

<kbd>
  <img src="https://github.com/xmatters/xMatters-Labs/raw/master/media/disclaimer.png">
</kbd>

---------

# Files

* [TravisCI.zip](TravisCI.zip) - Workflow zip file with the step and example flow
* [travisci.png](/travisci.png) - Travis CI logo

# How it works
This integration is triggered by a webhook notification in Travis CI.
**Warning**: This integration does not verify the inbound payload.

# Installation

## Travis CI Setup
In your **.travis.yml** file, include the following:
```yaml
notifications:
    webhooks:
        urls:
            - https://instance.xmatters.com/api/integration/1/functions/UUID/triggers?apiKey=APIKEY
```
The URL is retrieved from the HTTP trigger step in the xMatters flow.

### Get your API Key
1. Go to **Account > Settings**.
2. Find your API key in the **Settings** tab.

## xMatters Setup
1. Download the [TravisCI.zip](TravisCI.zip) file onto your local computer
2. Navigate to the Workflows tab of your xMatters instance
3. Click Import, and select the zip file you just downloaded
4. Fill in recipients in the **Create Event** step.

## Troubleshooting
Look at the Activity Log in xMatters to see if any messages are coming in. If there are none, then try checking that the right xMatters Trigger URL was provided in the **.travis.yml** file.
