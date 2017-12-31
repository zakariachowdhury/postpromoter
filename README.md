# Tailer Bot
Steem Bid-Based Voting Tailer Bot to Earn Curation Rewards

## Installation
```
$ git clone https://github.com/zakariachowdhury/tailerbot
$ npm init --yes
$ npm install request --save
```

## Configuration
First rename config-example.json to config.json:
```
$ mv config-example.json config.json
```

Then set the following options in config.json:
```
{
  ....
  "account": "your_bot_account_name",
  "bidbot": "bot_account_to_tail",
  "posting_key": "your_private_posting_key",
  ....
}
```

## Run
```
$ node postpromoter.js
```

## API Setup
If you would like to use the API functionality set the "api.enabled" setting to "true" and choose a port. You can test if it is working locally by running:

```
$ curl http://localhost:port/api/bids
```

If that returns a JSON object with bids then it is working.

It is recommended to set up an nginx reverse proxy server (or something similar) to forward requests on port 80 to the postpromoter nodejs server. For instructions on how to do that please see: https://medium.com/@utkarsh_verma/configure-nginx-as-a-web-server-and-reverse-proxy-for-nodejs-application-on-aws-ubuntu-16-04-server-872922e21d38

In order to be used on the bot tracker website it will also need an SSL certificate. For instructions to get and install a free SSL certificate see: https://certbot.eff.org/
