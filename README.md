# pseudo-notification

Local Notification, a new feature of FileMaker ver17, at first glance, it looks so great, but it is not the real notification system, which other iOS Apps present us.  
Though collaborating with iOS native App or PWA(Service worker) gives us real notification benefit, I tried here making realtime dynamic notification system via only current FileMaker native assets.
So there are some restrictions.
1. FileMaker must be foreground.
2. To get the notification, a web viewer which enables the notification must be placed in the current layout.
In this sample file, you can do 
1. Check which account is active(online)
2. Send the message to the specific user( who is online and FileMaker is foreground)
3. Pseudo-notification(Card Window) is shown.


Under the hood - Script trigger beyond device

I use this technique here. This is just a fmp-url script.
If the code of web viewer is like this,
“data:text/html, call fmp-url <script>location.href=’fmp://$/MYFILE?script=trigger&param=“ + TRIGGER::FIELD + ”’</script>” 
Then, when TRIGGER::FIELD changes,  the fmp-url script is triggered on each device.


This is just an experiment mimicking notification system using FileMaker native assets.
