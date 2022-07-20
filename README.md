# Dialogue-tutorial-Y2S2
Write up for how the Dialogue system for '3D Blocks...' was made (Year 2 Semester 2)

# 1) The Scripts
For this dialogue system, we need to have 5 different scripts intertwined with each other; DialogueCall, DialogueUI, EnableDialogue, Person and TypewriterEffect.

##2) DialogueCall
To start with on this script, we need the following components:

![image](https://user-images.githubusercontent.com/91538155/180027752-a2873b3c-8863-41ad-8a66-49f7b3bad639.png)

After labelling those components, we need the following lace of if statements in Update (skipping Start):

![image](https://user-images.githubusercontent.com/91538155/180027902-25d4fcd8-d94d-4b82-9481-7bc79a3ab397.png)

These statements detail the process of interacting with NPCs in the first place, before the actual text boxes even begin.

Attach this script to the Player character and label the Look Range as desired:

![image](https://user-images.githubusercontent.com/91538155/180028477-823e466e-65dd-4ae9-9cff-37837db55c23.png)


# 3) DialogueUI

For this script, we need the following components, some of which call on other scripts:

![image](https://user-images.githubusercontent.com/91538155/180028648-e2846831-b3fa-449a-ab07-4581a10c5514.png)

Next, in Start, use the following code to call on whatever object (in this case the player and camers) has the character controller and camera controller respectively, and begin the TextProgress function (which will be below update):

![image](https://user-images.githubusercontent.com/91538155/180029001-81b66e86-5a87-449d-9b64-65753261fc52.png)

Before tackling that void, in Update we need the following if statement:

![image](https://user-images.githubusercontent.com/91538155/180029198-5c1393ca-6fae-49dd-889c-d55c3287ce1f.png)

In that statement, start with the following:

![image](https://user-images.githubusercontent.com/91538155/180029480-3a09505b-d4ca-495f-8542-e1e0fe1c70b6.png)

After that, add an else statement directly below and add the following:

![image](https://user-images.githubusercontent.com/91538155/180029343-2c976da3-71a9-4660-b958-4b3881221eb3.png)

Underneath all that, still within the first if statement, add:

![image](https://user-images.githubusercontent.com/91538155/180029678-371b1f29-02d1-4c34-be10-1ec690a7cddb.png)

This is in order to check for context related to the Capsule NPC, as this NPC can't be interracted with unless you 'date' the other NPCs first. Following on, underneath that if and still in the first if statement, add this:

![image](https://user-images.githubusercontent.com/91538155/180029926-b9cdac8f-ba38-4fed-b8ea-115cd673e238.png)

In order to close the dialogue that only appears after dating all other NPCs.


After closing off the if statement in Update, we now look to making the TextProgress function. In that function, begin with the following if statement:

![image](https://user-images.githubusercontent.com/91538155/180030286-3fc86d60-3717-4d99-946e-e8a33499a845.png)

Within that statement, we need the following code:

![image](https://user-images.githubusercontent.com/91538155/180030349-05185c05-c319-42e1-a02c-a2a876ffb1c2.png)

This is in order to bring in the later-tackled Typewriter Effect, and spawn in the dialogue box and text. Underneath those lines, we need another embedded if statement:

![image](https://user-images.githubusercontent.com/91538155/180030504-65a5afb3-8d4a-452a-aa07-6c7a6158c61c.png)

This is so that, once the dialogue is up and it gets to a point where the player is given the choice to date or not date, the buttons are enabled and a choice can be made between the two options. Underneath that now closed second if statement, but still in the first, we need:

![image](https://user-images.githubusercontent.com/91538155/180030776-d0180da2-87f3-474e-8f9c-d1533ef62aff.png)

This is for the Capsule, as his routeis player choice dependent. Now, we can close that first if statement, and add a second if beneath it:

![image](https://user-images.githubusercontent.com/91538155/180030996-30b84c73-c772-4c08-af45-f9a1a173a7a0.png)

This is for if the player chooses the Date route, each NPC will have their date route dialogue play, dialogue which can be changed for each NPC in the inspector. The same is true for the Not Date route:

![image](https://user-images.githubusercontent.com/91538155/180031563-400048e4-f81e-488b-a6f2-5840173682e6.png)

After that, we need an if statement to check if we've run through either dialogue:

![image](https://user-images.githubusercontent.com/91538155/180031701-f0605219-ae11-45f9-80ae-fe9334ab1e1d.png)

And finally, for thisd function, we need one more if:

![image](https://user-images.githubusercontent.com/91538155/180031819-b6b9f3a4-a591-4448-a3a3-300bed919998.png)

Now, we ned voids for each route; Date and Not Date. To start with, forthe Date route we need the following code:

![image](https://user-images.githubusercontent.com/91538155/180032003-06c52701-4a0f-4462-98dc-d04555308c2c.png)

This is for after the player has chosen this route. The buttons are then disabled, and the actual command for writing out the Date dialogue for each NPC is coded here. This is the same for the Not Date function:

![image](https://user-images.githubusercontent.com/91538155/180032810-6b0846c4-90ee-42de-bff8-62c0aca5ca1d.png)

After completing that, that is the end of this script.


# 4) EnableDialogue Script
After creating this script, we need the following components to be included before anything else:

![image](https://user-images.githubusercontent.com/91538155/180033040-c4385ec6-ef50-4f22-a67b-bd5dea52914f.png)

Then, in Start, we need the following lines of code to call on the character and camera controllers:

![image](https://user-images.githubusercontent.com/91538155/180033168-3842984c-dd77-4c39-8bb2-4e02d2ba4433.png)

Then, deleting update, we create a private function and call on the dialogue box:

![image](https://user-images.githubusercontent.com/91538155/180033393-7b70d110-0833-4ca5-9508-9e8aa95994a2.png)

Underneath this, we need an if statement to check how the player has progressed in dating everyone else, specifically for the Capsule:

![image](https://user-images.githubusercontent.com/91538155/180033530-5353901e-413d-4aa0-b4b8-9c0ce4a594ec.png)

Now, those ifs are complete, and to round off the function we need the following code:

![image](https://user-images.githubusercontent.com/91538155/180033653-9d232f76-a3e8-4823-96fe-cd4b41c00302.png)

That is the end of this script.


# 5) Person script
This is a reasonably short script used to adjust the text itself within the dialogue box as seen in the inspector. For this, we dont need any components, Start or Update, just the following three public classes for default dialogue, the date option and the not date option:

![image](https://user-images.githubusercontent.com/91538155/180034018-4bfef1d9-9924-41d4-a38d-8ce475242fdf.png)

That is all that's needed for this script.


# 6) TypewriterEffect script
For this script, we only need the two following components:

![image](https://user-images.githubusercontent.com/91538155/180034157-20d08dcd-437f-48bb-a208-e8c62fbcac4c.png)

Then, getting rid of both Start and Update, we need the following function:

![image](https://user-images.githubusercontent.com/91538155/180034295-1a7d5ad0-13d2-4bef-9b3b-59745c7b3bb4.png)

After that, we need a private IEnumerator and set up the index:

![image](https://user-images.githubusercontent.com/91538155/180034537-24b6f132-fcfd-40e3-903f-0fbc7e3c5c3e.png)

Beneath that, we need the following white statement:

![image](https://user-images.githubusercontent.com/91538155/180034735-2f79ee80-1aff-4f3c-9d43-d79acdb7673d.png)

Still within that while statement, we now need an if statement with the following code inside it in order to check for any text effects withing a < symbol:

![image](https://user-images.githubusercontent.com/91538155/180034939-2dd24cfe-4515-4231-ac60-61c085175e7b.png)

AFter this if statement but still within the while, add the following four lines, this is to guage the speed and enable the typewreiter effect once the dialogue itself is established:

![image](https://user-images.githubusercontent.com/91538155/180035129-d1c7f162-20b8-4e61-885b-481e5b87d6df.png)

Now, after closing off that while statement, we need the following line of code to close off the script:

![image](https://user-images.githubusercontent.com/91538155/180035558-29dfe8cc-9df6-4e64-9d01-f7a28b391810.png)


# 7) Implementing the Dialogue in Unity
Now, for implementation, add the DialogueUI and TypewriterEffect scripts to each NPC's dialogue objects in Unity:

![image](https://user-images.githubusercontent.com/91538155/180035862-29b61acc-dda1-4f50-bb6a-3bf8a903f82d.png)
![image](https://user-images.githubusercontent.com/91538155/180035936-08e9ba11-3e81-4033-9522-2972a5b65cee.png)

Now, you can edit the speed of the typewriter effect, and also implement custom dialogue for each character. At the end of the standard dialogue, ticking for Has Choice will implement the Date or Not Date buttons and mean you can then below write the dialogue for each choice:

![image](https://user-images.githubusercontent.com/91538155/180036225-8fec9532-f6c4-415a-89b6-574ad8d1118f.png)

For the special, player progress based NPC, this one needs a separate game object as a child of itself, with the parent being for the dialogue for not yet progressing enough and the child for when you do progress enough (this child is labelled Senpai Paywall):

![image](https://user-images.githubusercontent.com/91538155/180036475-e02056a9-9263-4784-bfda-552150f5b282.png)

Now, in Senpai Paywall, the dialogue works exactly the same as the non blocked NPCs, and you can add the choices how and where you see fit:

![image](https://user-images.githubusercontent.com/91538155/180036648-afcde501-2ac0-4bc6-9988-2d77403a2cf9.png)


# That is the end of the Dialogue Scripts
