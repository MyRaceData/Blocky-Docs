# Blocky Lesson 2
If you have not done so, read the first lesson in this series to learn how to create your first rule. 

If you followed the first lesson, your should see your new rule in the **Setting ----> Rules**

![rule in list](https://user-images.githubusercontent.com/25418996/137604777-d870bb88-47f4-4bcc-a7a9-404f34e5c559.png)

You should be able to see a log entry every minute if your rule is functioning properly. We are now going to learn to do something more useful with rules. The first rule really was just to get the hang of creating a rule and actually just spams the log with messages so you may want to disable it or remove it. To do so, from the screen above, click **Select** in the upper right corner.

![select button](https://user-images.githubusercontent.com/25418996/137604993-8ae17957-3e5c-459e-813a-87ee569b43bb.png)

A selection box will appear next to all your rules. Click a rule to select it

![remove](https://user-images.githubusercontent.com/25418996/137604995-39396c1e-1904-4592-aa97-9a5a632cdda9.png)

And three buttons will appear across the bottom of the screen. You may then remove, disable or enable rules.
## Getting started
Now that we have created our first rule, we will try to do something more useful. When you create home automation often you need to know some basic things to make decisions. For example, suppose we want to turn on a light at night when it gets dark. We need to know when it gets dark to do so, and this rule will give us the ability to know when it is dark outside. But to do so, we will need to dive a little deeper into using openHAB. We will install a binding to use in our rule to help us learn when it is dark outside. You still will not need any actual home automation devices to complete this lesson if you are just taking openHAB for a test drive. So let's get started
## Install the Astro Binding
The first step in this lesson is to install the Astro binding. Binding are add-ons for openHAB. You can read more about them [here.](https://www.openhab.org/docs/tutorial/things_simple.html) Often a binding creates a connection with some home automation device hardware you have purchased or made. But some bindings, like the astro binding provide a service of some kind. 
### What does the Astro Binding do?
The Astro binding uses your location to track the position of the sun and moon. By knowing the position of the sun, we can calculate when sunrise and sunset occur (and a whole bunch of other stuff as well!) When you first installed openHAB, the set up asked you to enter your location on a map. If you did so, you are all set and can continue by installing the astro binding. If you did not set your location, go to **Settings ----> Regional Settings** In the regional setting, click the map button and set your location on the map, don't forget to hit the save button when you are done.

![reg set](https://github.com/MyRaceData/BlocklyImg/blob/main/reg%20set.jpg)

Installing a binding usually creates what is called a **Thing** in openHAB [nomenclature](https://en.wikipedia.org/wiki/Nomenclature)
Go to **Setting ----> Things** and install the astro binding by clicking the blue button in the lower right corner

![thing create](https://user-images.githubusercontent.com/25418996/137605790-2a931199-5ef2-4b7f-b7cf-80d73be39185.png)

A list of bindings will appear (as shown below) Scroll down until you find astro binding and click on it

![bindings](https://www.openhab.org/assets/img/install_hue.260e5df5.png)

A dialog box will pop up (as shown above for the Hue binding)
Wait a few minutes until the binding is installed and a couple things should pop up in your inbox. Accept them in your inbox and you should see two new **things** in your list, a Local Sun thing and a Local Moon thing

![local sun](https://user-images.githubusercontent.com/25418996/137606449-2af007a2-efb3-41c7-96ba-08393b083563.png)

Click on the Local sun thing. In the next screen, across the top of the screen you will see three tabs, Things, Channels and Code. Click on the Channels tab. Scroll all the way to the bottom and you should find the sun phase channel. 

![Sun phase](https://user-images.githubusercontent.com/25418996/137606399-ab3bf822-8e87-4072-ba0d-07d4f7946534.png)

Next we are going to create an **Item**. Read [here](https://www.openhab.org/docs/concepts/items.html) to understand what an **Item** is used for in openHAB. click the Add Link to Item button ![add a item](https://user-images.githubusercontent.com/25418996/137606608-f2e959ac-e761-4cde-ac81-f2e265221b42.png)

Click Create a New Item

![create item](https://user-images.githubusercontent.com/25418996/137606837-8374bf59-ccef-4ba0-b271-7864e7090f1b.png)

Create an Item and give it a name. I used Sun Phase Name. Leave everything else in the dialog box as it is, scoll to the bottom and 

![link button](https://user-images.githubusercontent.com/25418996/137607045-cb74b0f4-0aac-4055-b121-9089022a5c60.png)

Now go to **Setting ----> Items** and you shouls see your new Item
  
  ![Items](https://user-images.githubusercontent.com/25418996/137606756-41a6a2ec-0a0d-48b4-b2d0-954fe71167d8.png)

Don't worry if you don't understand exactly what all this **Item** and **Thing** stuff means yet, you will learn soon enough how to use these things and items you created
## Create another Script
First, if you do not have your log veiwer running, start it back up and leave it running. You will need it later
By now you should be familar with create a new rule. Do as you did in the first lesson and create a new rule. Set it to run every minute like the first rule you created. Create an Action and create a new script just as you did in the first lesson. when the Blocky visail editor screen appears, click openHAB, grab a log block like in the first lesson.

![Screenshot 2021-10-16 at 21-55-50 openHAB](https://user-images.githubusercontent.com/25418996/137607483-a79b634c-2221-46fe-b1fb-cbcc10916a9a.png)

Then go to Text. Grab a Create text with block and drag it into the editor

![create text](https://user-images.githubusercontent.com/25418996/137607654-cddbd35d-fba4-46cf-825c-9220466ad0fd.png)

Land the new Create text block on the log block like so

![Screenshot 2021-10-16 at 21-56-49 openHAB](https://user-images.githubusercontent.com/25418996/137607671-154d6bf5-dc19-4869-8195-759aea538a97.png)

Then go to back to Text and grab a plain text block and drag it into the editor

![plain text block](https://user-images.githubusercontent.com/25418996/137607539-b597eb59-a807-4468-9a97-1af312d345f2.png)

Land the plain text block on the create text block and type 'The sun phase is: ' (notice the extra space at the end of the text)

![Screenshot 2021-10-16 at 22-14-24 openHAB](https://user-images.githubusercontent.com/25418996/137607844-137a34e9-8d26-443e-85b4-24800f19a7e5.png)
## Creating a Variable
Next we are going to create a variable. A Variable is like a place holder. We can place information in a variable and use it later in the script. First pick Variables from the list

![click var](https://user-images.githubusercontent.com/25418996/137608291-55707b2b-a0df-44e6-9119-8ad408bd0db5.png)

Click Create Variable... A dialog box will pop up. With in the dialog box, in the text box labeled New variable name type 'MyVariable' then click OK. The dialog box will close and you will see some new Blocks to use

![myvar](https://user-images.githubusercontent.com/25418996/137608332-fc2b9636-e1ea-4a02-8a52-07c4122cd244.png)

Choose the one that says Set MyVariable to and drag it into the editor. Land it on top of the log block so it looks like this

![Screenshot 2021-10-16 at 22-35-19 openHAB](https://user-images.githubusercontent.com/25418996/137608395-7b50b120-016d-42b6-8295-a11cd0ca55b2.png)

Now go back to the openHAB tab and grab the block that says Get item state

![get state](https://user-images.githubusercontent.com/25418996/137608486-1bb9f3a2-21d2-45f8-8b02-fe31973f3ad8.png)

land it on the Set variable block so it looks like this

![Screenshot 2021-10-16 at 22-43-17 openHAB](https://user-images.githubusercontent.com/25418996/137608573-d8fb1eb9-dd6e-4a0e-ba71-264eb7a14d96.png)

Then click whereit says Item MyItem

![myitem](https://user-images.githubusercontent.com/25418996/137608634-a6c22b8d-c03f-4de6-8680-6487ca734241.png)

A screen will pop up where you can pick an Item. Pick you Sun phase item and then click Pick in the upper right corner

![Screenshot 2021-10-16 at 22-42-50 openHAB](https://user-images.githubusercontent.com/25418996/137608694-fd4e5757-5abb-4fe6-8ce2-92e4726203ff.png)

Your item will appear in the block like so

![Screenshot 2021-10-16 at 22-48-42 openHAB](https://user-images.githubusercontent.com/25418996/137608744-bef60d40-2c15-41f5-b654-e784a4ad3d9b.png)

Then go back to the Variables tab and grab another MyVariable block and add it to the create text block so it looks like this

![Screenshot 2021-10-16 at 22-53-40 openHAB](https://user-images.githubusercontent.com/25418996/137608893-38f030dc-5715-4470-85d8-57e338c53ab4.png)

At this point, if you hit the save button, 
