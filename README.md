# ChatBot-with-Recast.Ai
Build your first bot with Recast.AI

## `No Coding Required`

```
When you’re a beginner bot builder, learning about natural language understanding, conversation flows and messaging platforms can feel a bit overwhelming.

In this guide, I’m going to help you build your first bot on Recast.AI.

You will have a functional chatbot, and you will know how to:

  Make your bot understand human language
  Build a conversation flow
  Deploy your bot to Facebook Messenger
  With Recast.AI, you can easily design complex conversational flows fueled by a powerful artificial intelligence .
  
```
## REQUIREMENTS

<br /> To begin, `create an account on Recast.AI! It’s free.`
<br /> Once you’re logged in, it’s time to create your first bot. Click on the button `“Start with a template”, or just on + NEW BOT` in the header section.
![alt-text](recast_ss/recast_ai.png)
<br />Choose `“Create a complete chatbot”.`
<br />You can choose one or many pre-defined skills for you bot. This will help you get started faster. Just select `“Greetings”` for now, but I encourage you to check the others later.
<br />Choose your name. `“joke-bot”` would be appropriate
<br />Add a description. `“My awesome and funny joke bot”` or something less cocky
<br />Set `English` as the default language.
<br />You can keep your bot `public` as there is no private info, but you can change this setting later.
<br /> ![alt text](recast_ss/make_bot.png)

```
There are 5 phases in your bot life, represented on our platform through the use of 5 tabs:

  Train – Teach your bot what it needs to understand
  Build – Create your conversational flow with our Bot Builder tool
  Code – Connect your bot with external APIs or a database
  Connect – Ship your bot to one or several messaging platforms
  Monitor – Train your bot to make it sharper, and get insights on its usage!

For this repo I’ll skip the “Code” part, because we won’t need any external information
```
## TRAIN YOUR BOT TO UNDERSTAND HUMAN LANGUAGE
```
This is the brain of your bot, where all its understanding is gathered, divided into intents.

An intent is a “box” of sentences that all carry the same meaning, even though they can be very different to one another. When a user sends some text to your bot, our algorithm compares it to the phrases in your intents. Then it checks if it’s close enough to one of them and decides what the intention of the message is.

For example:

    Are you a bot?
    You reply so fast, I’m sure you must be some kind of robot.
    Am I speaking to a human or not?

are all different, but they all ask the same question that we can can sum up as: Are you a bot? Well, that would make a great intent! If your bot is able to recognize this question, you can prepare a smart reaction, like “I’m a robot and I’m proud of it “.
```
## FORK INTENTS

```
All bots should understand basic things such as ‘greetings’, ‘agree’, ‘disagree’, or when a user asks for help.

If you chose the pre-defined Skill “Greetings” when you setup your bot, you will already have two intents: goodbye and greetings.

As Recast.AI is collaborative, you do not have to recreate each intent every time! You can ‘fork’ an intent someone already created to clone it right into your bot. Since we need to understand that our user wants to be told a joke, let’s find if the community has already created this intent for us.
```
## CREATE A NEW INTENT

```
If you want a custom intent, you can build it from scratch. Here, we want the bot to understand when someone laughs at the joke.

Click on + CREATE on the right of the search field, and choose a name for your intent:

Repeat this process for intent that gathers negative reactions to your jokes:

```
## ADD EXPRESSIONS

```
Now that we have intents, we need to populate them with various expressions. An expression is the name of a sentence added to an intent.

A golden rule would be to add 20 expressions to an intent for a development bot, and 50 or more for a production bot.

Click on an intent and add sentences you want your bot to understand. Put yourself in the shoes of the people talking to your bot.What could they possibly ask? Enter a new expression by typing it into the field Add an expression. Here are some examples:

Laughs:

    hahah that’s hilarious
    ROFL you’re good!
    That, my friend, was an amazing joke.
    I haven’t laughed that much in a long time!
    
Lame:

    You have no sense of humour whatsoever.
    That’s both terrible and offensive.
    What the heck was that?
    Try harder, that was a very bad joke.
```
## TEST YOUR BOT
```
Now that your bot is full of expressions, let’s test it with the console:

Click on the TEST bubble icon on the top right, and select the tab “Analyse text”. Type a sentence you have not trained your bot with: “Botty bot, can you tell me a joke please?”

You will see which intent was detected under “He’s referring to”. If the algorithm did not detect an intent, or detected an invalid intent, that means that you need to train your bot with more expressions.

Once you’re happy with your bot intent detection, it’s time to move to next phase: building your bot flow.
```
## BUILD AND MANAGE THE CONVERSATION FLOW
```
Now that the brain of your bot is all filled up, click on the Build tab.

The Build tab is where you find Bot Builder. It helps you construct the conversation flow of your bot using Skills.
```
### WHAT IS A SKILL?
```
Each Skill represents one thing that your bot knows how to do, and they can interact with each other. Your skill can be a complicated one – such as managing payment by credit or simple – answering basic questions

When you create a new bot, forking skills you already made to the new one will keep making your bots more powerful. You can also fork skills created by other people on the platform, so you don’t have to reinvent the wheel!

If you chose the pre-defined skill “Greetings” during the creation of your bot, it will already be in your interface.
```
<b>A skill has four parts:</b>

``` ```<b>Readme:</b> Where you explain the purpose of your skill.<br />
``` ```<b>Triggers:</b> Where you define why this skill should be activated after a user message<br />
``` ```<b>Requirements:</b> Describes what information this skill has to collect, and what questions need to be asked to fulfill the requirements.<br />
``` ```<b>Actions:</b> What to do once the requirements are fulfilled.<br />

```
If you navigate through the tabs, you’ll see that this skill is structured as follows:

      1) It is triggered if the intention greetings or the intention goodbye are matched.
      2) It has no requirements, because it does not need to collect additional information. That means that it will execute actions directly after a trigger.
      3) It has two possible actions: If the intention matched is greetings, it sends a random welcoming message chosen from a list, and if the intention is goodbye, it does the same thing, but picks the message from a different list

It’s time to create our own Skill with the same structure.
```

## BUILD YOUR OWN SKILL

```
Go back to the Build tab and click on + Add a new skill on the left.

You have three different types of skills: Business, Floating, and Fallback. On the one hand, Business and Floating have no structural differences. Yet differentiating the two types of skill helps when you have a lot of them. Fallback skills, on the other hand, trigger when no other skill has their Triggers fulfilled after a user message. Most of the time, you’ll have only one of this kind, where you can remind the user what your bot can do, and ask them to rephrase.

Our skill will be of Floating type. Give it the name you want, I chose tell-me-a-joke.

Go to the Triggers tab. We want to activate our skill if one of the three intentions we created are matched.

Don’t forget to change the condition to OR, since it is an AND condition by default and we want to activate our skill when any of these intentions are matched.

We won’t need to do anything in the Requirements, because we don’t have anything to ask. But you can improve the bot by asking for some information there, like what kind of jokes they prefer, or how old they are if you want to add some adult jokes.

Head to the Actions tab and create your first message group.

Click on ADD CONDITION to trigger messages and add the condition:If @greetings is-present. The “@” stands for intent type. We’ll cover other types later.

Then choose the action type “SEND MESSAGE”, choose Text format and type the best joke you know.

```
## CONNECT YOUR BOT TO A MESSAGING PLATFORM

```Now, it’s time to let go the test console and deploy your bot to a public messaging platform.

Go to the Connect tab, choose the messaging platform you prefer and follow the instructions.

You won’t have anything else to do other than the initial configuration to deploy your bot to a new channel. For this reason, you should not hesitate to configure multiples to broaden your audience!

Beware that some platforms are not as powerful as others. For example, Telegram is very easy to configure but does not support GIF images, so you should adapt your bot accordingly.

If you don’t know where to start, Facebook Messenger is a very powerful platform with a large audience.

```


### For complete and detailed reference : https://recast.ai/blog/build-your-first-bot-with-recast-ai/
