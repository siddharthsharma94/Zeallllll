#Zeal [![Build Status](https://travis-ci.com/taylorcox75/Zeal.svg?token=XbqCKDp6PtzWG54UBd9w&branch=master)](https://travis-ci.com/taylorcox75/Zeal)
[Taylor Cox](mailto:taylorcox75@gmail.com), [YuanJun Ma](mailto:yuanma@email.arizona.edu), [Siddharth Sharma](mailto:siddi.sharma@gmail.com),[ Chioke Aarhus](mailto:caarhus@email.arizona.edu)

<h1 align="center">Remind yourself about a task.</h1>
<h3 align="center"> Zeal is a bot that re-thinks the way you deal with reminders.
<br>Send Zeal a message to create a reminder.
<br>
<img src="http://i.imgur.com/9YOhOud.png"></h3>
<br>




##Project Setup

###Prerequisites

>Ruby on Rails

>`gem install rails`

>`bundle install` 

> `brew update`

> `brew install postgresql`

> `gem install pg` 

>`bundle install` 

###In Terminal at Desired Location
>`git clone https://github.com/taylorcox75/Zeal.git`

>`cd Zeal`

To Reinit Main Bot
> `curl -X POST "https://graph.facebook.com/v2.6/me/subscribed_apps?access_token=EAAZAWPnkEQSsBAEUWcLGQbOX0p80br14CXyddWdKhvKe52wWSDzpHZB0q3bbKcuvNxDiYpOfwcMDN7yGks8ZCr1WPc9wZBlVRATf3FZAdb566RvLTR85AFnsOxQ7rf8CDwStaL9yZCP8uSKGEXZASLfvkiZCmpxHycoK8OoVCZCz8eQZDZD"`

>`rails s`

To Reinit Development Bot
>`curl -X POST "https://graph.facebook.com/v2.6/me/subscribed_apps?access_token=EAAEaNSbDzrwBAMHdn3oJ7cbSRwumMt9nwfFUZAIpGDuajvKM2FvuvbNklf1ZCevkroE9ZAbEDZCZAMwLQlvGTzzlpThBsHaeVSvpOULDj1eCMtzPJ2cfrYencmWtH6J0lZALEvaJnVWZCzXbQqUaorKvKo1MjILdM225rc7bmkldgZDZD"`

>`rails s`(start server)

Must run rake jobs:work to run reminder workers in local machine databse.

> `rake jobs:work`
 
>New Terminal Tab

>`./ngrok http 3000 -subdomain=zeal2`

>Initializing Persistent Menu
> `curl -X POST -H "Content-Type: application/json" -d '{
  "setting_type" : "call_to_actions",
  "thread_state" : "existing_thread",
  "call_to_actions":[
    {
      "type":"postback",
      "title":"View Upcoming⏲",
      "payload":"VIEW_SCHEDULE_PAYLOAD"
    },
    {
      "type":"postback",
      "title":"View Completed✅",
      "payload":"VIEW_COMPLETED_PAYLOAD"
    },
    {
      "type":"web_url",
      "title":"View Help Page",
      "url":"http://zealbot.me/help"
    }
  ]
}' "https://graph.facebook.com/v2.6/me/thread_settings?access_token=EAAZAWPnkEQSsBAEUWcLGQbOX0p80br14CXyddWdKhvKe52wWSDzpHZB0q3bbKcuvNxDiYpOfwcMDN7yGks8ZCr1WPc9wZBlVRATf3FZAdb566RvLTR85AFnsOxQ7rf8CDwStaL9yZCP8uSKGEXZASLfvkiZCmpxHycoK8OoVCZCz8eQZDZD"`

Pushing to Heroku (PUBLIC RELEASE OF BOT)
>`git push heroku master`


