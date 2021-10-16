# Writing your first rule using Blocky
By following along with this tutorial, you will learn to create your very first rule in openHAB and you don't need to know any programming. We will present easy to learn step by step instructions on how to create your first rule. All you will need is a running version of openHAB3. Then we will continue on by creating a rule which does something useful which can be used as the basis for your new automated home! Let's begin
## What you will need:
All you will need to complete this tutorial is a running version of openHAB 3. Even if you do not yet own any home automation devices, you can take a test drive of openHAB 3 and learn the power of this terrific automation tool. You do not need to have any programming experience. You will create your first rule using the easy Blocky visual interface, using drag and drop. Check the [installation instructions](https://www.openhab.org/docs/installation/) and get a version of openHAB running. To create your first rule, you will need to be logged in as the adminstrator. The first time openHAB runs, you set up a administrator account and password and the interface runs in the administrator role. Note the button in the lower left of the picture below which is labeled 'Sign in as an administrator to access setting'
![admin button](https://www.openhab.org/assets/img/welcome_page.a5b83d6f.png)

Once you are in the setting (see picture below) just click 'rules'

![rules button](https://www.openhab.org/assets/img/initial_settings.696acede.png)
## Creating your first rule
First, click the blue dot with the plus sign on it (in the lower right corner of the picture below) to create a new rule.

![new rule](https://user-images.githubusercontent.com/25418996/137599610-613b181a-2f74-4888-a410-fe73f3a26770.png)

Once you do, you will be in the rule editor as shown below.

![create rule](https://user-images.githubusercontent.com/25418996/137599724-d54efca4-5b69-43b0-b2af-14987ff51802.png)

Once you are in the rule editor (pictured above), give your new rule a name and then create a trigger by clicking the green Add Trigger button. You will be presented with the When screen (pictured below)

![When screen](https://github.com/MyRaceData/Blocky-Docs/blob/main/When%20screen.png)

If you need more help, go to the rules section of the openHAB documentation. Follow the instructions to for: [UI based definition](https://www.openhab.org/docs/configuration/rules-dsl.html#ui-based-definition)  (which means User Interface based rule definition)

In this screen, you are going to create a trigger. A Trigger is an event that causes your rule to run. There are lots of things that openHAB can be made to trigger on. Devices in your home automation system can trigger events or you can create a trigger based on a certain time of day. That is what we are going to do, we are going to create a rule that triggers using time so pick the button that says 'Time Event' (shown in the picture above)
## Your first trigger action
We are going to create our first trigger to run on a schedule. To do so, we are going to create what is called a cron expression. A cron expression is a way of scheduling something to happen periodically at a certain time or on a certain day or just at a given interval of time. If this all sounds horribly complex, consider how powerful it could be to have your home automation do certain things at certain times. Cool huh? Let dig in!
Once you click the Time Event button you will see the screen below

![Cron 1](https://user-images.githubusercontent.com/25418996/137599511-d01315ae-74a1-4c9f-aa53-0be315d329e6.png)

Under When choose the button that says 'on a schedule (cron)' (as shown in the picture above) Next, below that, where it says cron expression on the right is a little orange colored button that says 'Build'.
Once you click that button, you will see a screen as shown below

![cron secs](https://user-images.githubusercontent.com/25418996/137601631-81863857-6a67-423f-ba53-aac086b9fe60.png)

This is the built in cron expression builder, which makes creating a cron expression really easy. Notice there are tabs for Seconds, Minutes, Hours, Days, Month and Years at the top. In the photo, we are in the seconds tab. If it is not already selected, click on the third button down, Specific second (choose one or many). Then click on the Minutes tab

![cron mins](https://user-images.githubusercontent.com/25418996/137602584-94225e2c-4e44-4c62-90f5-751ce661e69b.png)

Click on the second button down Every (as shown above) and change it to 1 (every 1 minute). Then click the Hours tab.


 ![cron hours](https://user-images.githubusercontent.com/25418996/137601803-f8402e8b-791e-4e59-90f4-c3b6944bd697.png)

 Click the top button Every hour (as shown in the photo above). You can click though the remaining tabs the same way choosing every day, every month and every year. Notice at the very top of the photo above it says Cron:0 * * * * ? * and below that every minute. The 0 * * * * ? * is the actual cron expression you have created. Now click the Done button in the upper right corner of the photo. This will return you to the Add Trigger screen (shown below) 
 
![cron every](https://user-images.githubusercontent.com/25418996/137601875-a3d4296d-abfd-4efb-a5f0-998c73c45e02.png)

You have now create a trigger which will run once every minute by creating a cron expression. Notice in the photo above, in the lower left corner, it nows shows your new cron expression. Click the Done button (in the top right corner of the photo above) You will return to the rule editor, it should look like below

![almost there](https://user-images.githubusercontent.com/25418996/137602007-1a8eaca5-cd93-4a70-b6b8-261e0b54ef75.png)
 
Notice under When it now says Every minute. Our rule will now run once every minute. It is now time to create an Action to perform every time our rule runs. Click on the green button under Then that says Add Trigger (at the bottom of the photo above
## Your first script
Finally, it is time to create a script to run when our rule triggers. Once you click Add Action, you should see a screen like below

![Add Action](https://user-images.githubusercontent.com/25418996/137602324-73b6db0c-96e9-4c59-8fe9-3af356070676.png)
 
 Click the top right button that says run script. You will be sent to a screen that looks like the photo below
 
 ![pick blocky](https://user-images.githubusercontent.com/25418996/137602368-e2e7f917-ced1-4bfe-9d5b-2014e76356b8.png)

 Under Then, under Run a script click Design with Blocky. You will see the Blocky script editor as shown below
 
 ![blocky1](https://user-images.githubusercontent.com/25418996/137602650-a1f75487-e8e4-40af-9b4c-e5b7cea21da7.png)

 This is where you will create your first script. Notice the tabs on the left. They say things like Logic, Loops, Math and so on. Clicking each tab shows all the various 'blocks' which you can add to your script. Click the one that says openHAB

![cur oh stuff](https://user-images.githubusercontent.com/25418996/137602703-ab7940d1-262c-45c9-b330-04b3babb28d1.png)

 Now you can see all the openHAB commands you can use. With your cursor, drag the one that says log into the editor. (It is the forth one down in the photo above) Once your log block is in the editor, click the down arrow next to error and pick info as shown in the photo below
 
 ![log1](https://user-images.githubusercontent.com/25418996/137602810-8155c6b3-a6b9-4a04-a3ba-b22b1809b07a.png)

Now your script should look like this

![log info](https://user-images.githubusercontent.com/25418996/137602941-b9ea5366-1141-4b64-9a38-dab3308f8077.png)

Add the text into the block as shown. Now click Save and then Back (in the upper left corner of the photo above) and the screen should look like below

![done](https://user-images.githubusercontent.com/25418996/137603004-e5346fa6-07ad-45fc-b33f-9f25c8a538a5.png)

Congratulations... you have just created your first openHAB rule!!
easy right? You can see the status of your rule (IDLE in the green bubble above) and click the blue arrow on the right to run your rule.

This is great but you might be asking yourself what exactly does my new rule do? Well what you have done is create a rule that runs every minute and sends a message to the log file. Why is the important? Because as you learn to use openHAB, you will try to do things and some times... well.. they are not going to work like you think they should. An important part of figuring out why things don't work right, or just seeing what it going on is learning to read the log. So...
## Let's check the log
openHAB creates a log file as it runs. Every time an event happens, it is logged into the log file. As you learn to use openHAB, looking at the log will (at times) become very important. 

![other apps](https://user-images.githubusercontent.com/25418996/137603618-23007e2d-c7bb-4da1-9e89-2134974f44f4.png)

Returning to the main page (by clicking the big openHAB icon in the top left corner) you will notice a little retangle orange button in the upper right corner next to an icon that looks like a pen. This is the other apps button, click it

![log viewer](https://user-images.githubusercontent.com/25418996/137603402-38931c3b-776f-4437-a162-62190c6fc241.png)

Choose openHAB Log Viewer (top right above) to open the log viewer. The log viewer should open in a new browser tab and you should be able to see the log running and every minute, you should see an entry like below

![log entry](https://user-images.githubusercontent.com/25418996/137603949-7540d000-9bdb-4b32-b4bc-2213fd74d185.png)

if the log viewer does not open, you may need to install logtail. If you used openHAbian to install openHAB check [Here](https://www.openhab.org/docs/installation/openhabian.html#optional-components) on how to install logtail
