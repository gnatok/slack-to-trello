# Slack-to-Trello

A small NodeJS application which facilitates the communications between Slack and Trello.

## HowTo

1. Visit `https://trello.com/1/appKey/generate` in your browser. Copy the API key which is generated for you in the page. You will need it for the next step.
1. Now visit `https://trello.com/1/authorize?expiration=never&scope=read,write,account&response_type=token&name=<Useful Name Here>&key=<Your Key From Previous Step>` in your browser.
1. Click "Allow". You'll get a message "To complete the process, please give this token:". Note the token you will need to enter it into Heroku.
1. You can now click the Heroku deploy button below, or use `heroku create` from the command line (within your clone of this repo) to setup the NodeJS app in Heroku.
1. In the Heroku control panel for this app, go to "Settings" and in here you will find a section called "Config Variables". You need to setup two variables: `TRELLO_KEY` and `TRELLO_TOKEN`, from Step 1 and Step 2 of these instructions.
1. Before leaving Heroku, note the "Domains" section below the "Config Variables" section. You will need your app's URL which is listed here.
1. Next get the ID for the Trello board we want to work with. To do this open up trello.com and switch to the board you wish to use. Copy its URL and append ".json" to the end of the URL. Visit this URL and you will get a JSON response which includes an "id" property. Note this ID number.
1. Now from Slack pick "Apps & Integrations" from the main menu. This opens a web browser, and the page loaded offers you a search box, enter "Slash Commands" in here and select it.
1. From here click the "Configure" button and then "Add Configuration".
1. You will need a command name which is unique to the organization. Prepend a "/" to the front of it. Click the button.
1. Now you will be shown further configuration options. Enter the Heroku URL and append "/" and the Trello board ID from before. 
1. This is also where you can setup a description and a usage hint. Click "Save Integration"
1. Click the "Configure" button from here, and then the "Add Configuration" button.
1. Almost there!
1. Pick your Trello board from the dropdown. Check the "Card created" and "Card moved" actions, so those will show a message in Slack as cards get added and moved. If there are other actions you want reported in Slack, go ahead and check those boxes as well.
1. Click "Save Integration"
1. You're done. Go make a sandwich.

## Extra

Authentication with Trello is fairly easy, but if you need more information This is a bit tricky, there is [documentation here](https://developers.trello.com/authorize), but the steps to follow are:

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)