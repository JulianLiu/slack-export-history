# Export DM and private channel conversations from Slack

Including im(1 on 1 dm), mpim (group chat), and private channels. To do so, follow two steps:

## (1) Clone this repo
`git clone https://github.com/JulianLiu/slack-export-history`

All credits belong to https://github.com/margaritageleta/slack-export-history and 
https://github.com/margaritageleta/slack-export-history/issues/1 , 
only small modifications are made here

## (2) Create a Slack App
Go to https://api.slack.com/apps and go straight to `Create New App`. Choose your Workspace and press `Create App`. Then, click on your app and go to `Add features and functionality` -> `Permissions` -> `Scopes` and add the following scopes in `User Token Scopes` (be careful, `User Token Scopes` NOT `Bot Token Scopes`):

+ `channels:history`
+ `channels:read`
+ `groups:history`
+ `groups:read`
+ `im:history`
+ `im:read`
+ `mpim:history`
+ `mpim:read`
+ `users:read`

Then install the app in your workspace (you can go to `OAuth & Permissions` section and press `Reinstall app`), accept the permissions and copy the OAuth Access Token. 


## We are ready to download the messages
Install required python packages `pip3 install requests pick`

Run `python3 slack.py --token COPY_YOUR_OAUTH_TOKEN_HERE --all`
