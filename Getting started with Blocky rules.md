# Writing your first rule using Blocky
By following along with this tutorial, you will learn to create your very first rule in openHAB and you don't need to know any programming. We will present easy to learn step by step instructions on how to create your first rule. All you will need is a running version of openHAB3. Then we will continue on by creating a rule which does something useful which can be used as the basis for your new automated home! Let's begin
## What you will need:
All you will need to complete this tutorial is a running version of openHAB 3. Even if you do not yet own any home automation devices, you can take a test drive of openHAB 3 and learn the power of this terrific automation tool. You do not need to have any programming experience. You will create your first rule using the easy Blocky visual interface, using drag and drop. Check the [installation instructions](https://www.openhab.org/docs/installation/) and get a version of openHAB running. To create your first rule, you will need to be logged in as the adminstrator. The first time openHAB runs, you set up a administrator account and password and the interface runs in the administrator role. Note the button in the lower left of the picture below which is labeled 'Sign in as an administrator to access setting'
![admin button](https://www.openhab.org/assets/img/welcome_page.a5b83d6f.png)

Once you are in the setting (see picture below) just click 'rules'

![rules button](https://www.openhab.org/assets/img/initial_settings.696acede.png)
## Creating your first rule
First, click the blue dot with the plus sign on it to create a new rule. Once you do, you will be in the rule editor as shown below.

![blue dot](https://www.openhab.org/assets/img/ui_rules_dsl_test_example.599c0fd5.png)

Once you are in the rule editor (pictured above), give your new rule a name and then create a trigger by clicking the green Add Trigger button. You will be presented with the When screen (pictured below)

![When screen](https://github.com/MyRaceData/Blocky-Docs/blob/main/When%20screen.png)

If you need more help, go to the rules section of the openHAB documentation. Follow the instructions to for: [UI based definition](https://www.openhab.org/docs/configuration/rules-dsl.html#ui-based-definition)  (which means User Interface based rule definition)

In this screen, you are going to create a trigger. A Trigger is an event that causes your rule to run. There are lots of things that openHAB can be made to trigger on. Devices in your home automation system can trigger events or you can create a trigger based on a certain time of day. That is what we are going to do, we are going to create a rule that triggers using time so pick the button that says 'Time Event' (shown in the picture above)
## Your first trigger action
We are going to create our first trigger to run on a schedule. To do so, we are going to create what is called a cron expression. A cron expression is a way of scheduling something to happen periodically at a certain time or on a certain day or just at a given interval of time. If this all sounds horribly complex, consider how powerful it could be to have your home automation do certain things at certain times. Cool huh? Let dig in!
Once you click the Time Event button you will see the screen below

![cron1](

