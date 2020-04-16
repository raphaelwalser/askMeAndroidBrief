# AskMe! Android App
Brief for the development of an Android version of the existing iOs app ["AskMe!"](https://apps.apple.com/app/id1217624457)

- **[Overview](#overview)**
  * [Background](#background)
  * [Core Functionality](#core-functionality)
  * [Revenue Strategy](#revenue-strategy)
  * [Existing App](#existing-app)
- [Content](#content)
  * [Content Sections](#content-sections)
    + [1 – The Big Picture](#1---the-big-picture)
    + [2 – A Closer Look](#2---a-closer-look)
    + [3 – On the Horizon](#3---on-the-horizon)
    + [4 – My Interpretation](#4---my-interpretation)
  * [Languages](#languages)
- [Visual Design](#visual-design)
  * [Graphics](#graphics)
  * [Typography](#typography)
  * [Animation](#animation)
- [Development](#development)
  * [Home](#home)
  * [AskMeMore!](#askmemore-)
  * [Info](#info)
    + [1 – About](#1---about)
    + [2 – Subscribe](#2---subscribe)
    + [3 – Glossary](#3---glossary)
  * [AskMe!](#askme-)
    + [1 – Choose Question Type](#1---choose-question-type)
    + [2 – Input Question](#2---input-question)
    + [3 – Coin Toss](#3---coin-toss)
  * [Questions](#questions)
    + [Empty](#empty)
    + [List](#list)
    + [Folders](#folders)
    + [Answer Modal](#answer-modal)
  * [Settings](#settings)
    + [Subscription](#subscription)
    + [Touch ID & PIN](#touch-id---pin)
    + [Help/FAQ](#help-faq)
    + [Contact Us](#contact-us)
    + [Share](#share)
    + [Review on the App Store](#review-on-the-app-store)
    + [About](#about)
   * [User Flow Diagram](#user-flow-diagram)
- [Project Management](#project-management)
  * [Responsibilities](#responsibilities)
  * [Timeline](#timeline)
  * [Offer](#offer)
  * [Disclaimer](#disclaimer)

# Overview
## Background
There currently exists an iPhone app named ["AskMe!"](https://apps.apple.com/app/id1217624457)

It is based on a book written by [Isabelle Kriegel](http://www.isabellekriegel.com/) – an interpretation of ancient Chinese divination texts also known as [“I Ching”](https://en.wikipedia.org/wiki/I_Ching) or "The Book of Changes".

In an effort to make the app available to a wider audience, we plan to develop a native Android version.

## Core Functionality
The user chooses from one of four options:

1. **Choice:** I need to make a decision
2. **Strategy:** How do I solve this problem?
3. **Attitude:** How should I react?
4. **Clarity:** Help me better understand

and enters a question regarding their current life situation, using the guidelines provided.

They then shake their phone 6 times to virtually “throw” 3 coins while guided through this process by adorable animated avatars. Light bulbs show the progress. The resulting pattern of heads and tails is analysed by an algorithm, choosing the corresponding text from the ["Book of Change"](https://en.wikipedia.org/wiki/I_Ching).

To not overwhelm the user with too much text, a condensed version is presented to capture their interest and allow them to dive deeper by expanding sections or opening a more detailed version of the same text.

## Revenue Strategy
**Freemium Model** – The app is free of charge, but a premium is charged for additional features that expand the functionality of the free version:

- More in-depth answers (expanded version)
- Unlimited saved questions (only last 3 in free version)
- Passcode lock
- Group questions by subject
- Delete questions
- Access to the glossary
 

## Existing App
Make yourself familiar with the existing app by downloading it from the [App Store](https://apps.apple.com/app/id1217624457).

A [User Flow Diagram](UserFlowDiagram.png) can be found in this repository.

Alternatively you can view this [Prototype](https://xd.adobe.com/view/a39d32b0-eea6-4b45-a2ff-353eb534245d/).
> Please note: The prototype does not represent the current state of the app – some changes to design and functionality have been made since.

# Content
The copy is provided in json format.\
There are 64 files for the condensed answers and another 64 for the expanded version.

You can see a sample file here: [content.json](content.json)

```json
{
  "summary": [
    "Creative energy, the strength of action",
    "Ability to create, produce, conceive, initialize",
    "Putting into motion, dynamism, impulse",
    "Power, strength, firmness"
  ],
  "bullets": [
    "Creative energy is the origin of all cycles, of all projects",
    "Sowing: the ability to begin, to undertake, to move forward",
    "Developing: the possibility to evolve, to progress, to assert ourselves",
    "Harvesting: the satisfaction of having gains",
    "Strengthening: the aptitude to be tenacious, consistent, resistant, courageous",
    "Formidable potential"
  ],
  "advices": {
    "hide": [
      "<bold>Image</bold>\nThe dragon: a symbolic animal that is an emblem of power and prosperity because it can make rain fall",
      "<bold>Metaphor</bold>\nYang energy\nYang initiates, Yin brings to completion; their efficiency depends on their interaction\nYang and Yin are complementary"
    ],
    "show": [
      "<bold>Words of wisdom</bold>\nLearn to manage your energy without forcing too much or draining yourself\nBe careful not to confuse firmness with rigidity",
      "<bold>Strategy</bold>\nEnergy creates energy; action creates action",
      "<bold>Warning</bold>\nDon't worry about the results; acting firmly is what's important"
    ]
  },
  "changingLines": {
    "intro": "Creative energy is a matter of",
    "lines": [
      "<bold>Preparation</bold>\nAs long as we're not ready, we shouldn't act\nBut still, it's best to remain attentive and open-minded",
      "<bold>Reflection</bold>\nBefore taking off, let's take time to reflect\nAnd allow ourselves to be guided and advised\nIn order to better get along with each other",
      "<bold>Behavior</bold>\nIt's important to take it easy on ourselves and be mindful of fatigue\nLet's manage our strength with prudence, without abusing it\nAnd learn to conduct ourselves appropriately",
      "<bold>Audacity</bold>\nLet's have the courage to act and move forward without being sure of the result",
      "<bold>Receptiveness</bold>\nSuccess should not stop us from accepting advice\nSo let's keep our ears open in order to accomplish great things",
      "<bold>Danger</bold>\nPower is exhilarating\nPower makes us arrogant and inflexible\nWith such an attitude, we have more to lose than we have to gain\nIt's time to react firmly"
    ]
  }
}
```
> For easy deployment of changes across platforms, we require you to maintain the structure and integrity of these source files – they may only be refactored by code.

## Content Sections

There are 4 main sections in an answer that are comprised of the following nodes in the .json file:

### 1 – The Big Picture

- `"summary"` : big bold text separated by green lines
- `"bullets"` : green bullets, indented text
- 	`"advices"` : bold title and small paragraph with alternating background colours.

> Both the bullets and the advices in the node `"hide"` are initially hidden and can be shown/hidden by clicking "more/less"

### 2 – A Closer Look

- `"changingLines"` > `"intro"` : big bold text
- `"changingLines"` > `"lines"` : small paragraph with bold title and alternating background colours.

> Depending on the coin combination thrown, 1-6 of the lines get displayed.

### 3 – On the Horizon
> This section is the same as "The Big Picture" but comes from a different answer file, chosen by the algorithm based on the coin combination thrown. In some rare cases the algorithm will replace this section with a hint:
>> ***This time your answer is short but even more powerful.***\
*Everything that you need to understand can be found above*

- `"summary"` : big bold text, separated by green lines
- `"bullets"` : green bullets, indented text 

> The bullets are initially hidden and can be shown/hidden by clicking "more/less"

### 4 – My Interpretation

The user can choose to write their own thoughts and save it to memory along with their question and the answer found.

> A few tags are used for styling:\
`<bold>` **Bold Text** `</bold>`\
`<italic>` *Italic Text* `</italic>`\
`\n` new line

## Languages
The app currently exists in two languages. All the translated copy and graphics needed will be provided.

- [x] **English** (base language)
- [x] **French** (implemented)
- [ ] **Spanish** (work in progress)

> Additional languages possible in the future

# Visual Design
## Graphics

The visual design will be provided in form of:

- Screenshots of all screens
- [User Flow Diagram](UserFlowDiagram.png)
- Detailed style guide (colours, typography, measurements)
- [Sketch](https://www.sketch.com/) file
- Vector graphics of all visual elements (svg, pdf, Illustrator)

> The app was designed for iPhone and is using components, navigation patterns and functionality common or unique to iOs. Though the look and feel should be the same across platforms, we expect that you adapt some aspects to mimic familiar Android patterns.

## Typography
The app features text heavily, so maintaining user focus and readability is crucial. A lot of effort has gone into crafting an optimal reading experience with a strong visual appeal. We expect a high level of attention to detail in regards to typography and layout.

We use the font [Avenir Next](https://www.fonts.com/font/linotype/avenir-next) which comes pre-installed on iOs devices and can therefore be used for free. This likely won't be the case on Android. To avoid additional licensing costs we might have to find and test a suitable free alternative like [Nunito Sans](https://fonts.google.com/specimen/Nunito+Sans).

## Animation
The animated robots were created as vector animations in [Adobe After Effects](https://www.adobe.com/products/aftereffects.html)  and exported as json with [Bodymovin](http://aescripts.com/bodymovin/). The files can be easily parsed via [Lottie](https://github.com/airbnb/lottie-android) and rendered natively on Android.

> You can find a sample animation for testing in this repository: [Submarine.json](Submarine.json)\
> See a preview here: [Animation Preview](https://lottiefiles.com/share/DOsS8v)

The only exception to this is the coin toss animation: Every throw is unique and randomised and animated in code.

# Development
The iPhone app is coded entirely in [Swift](https://swift.org/). You will get access to our complete code source.

You will be required to implement all functionality as it exists in the current iOs app (refer to [User Flow Diagram](UserFlowDiagram.png)):

## Home
- Launchscreen
- Robot animations
- Hint "start"
- Possibility of notification (e.g. updates, teasers)

> In the free version a teaser to AskMeMore! is shown

## AskMeMore!
This modal screen is presented whenever the user tries to access any of the payed features from within the free version:

- Open glossary
- Open question older than last 3
- Delete question
- Group question by subject
- Move/delete multiple (edit)
- Expanded answer version
- Touch ID & Pin

Or when clicking on any of the teaser links to AskMeMore! throughout the app.

- Teaser to all payed features
- Subscription info (free trial, price/periodicity, local currency)
- Subscription Terms and Privacy Policy (link to website)
 
## Info
This section consists of three tabs:

### 1 – About
- Short paragraphs separated by lines

### 2 – Subscribe
- Teaser to AskMeMore!
- Teaser to website email signup (link to website)

> If a subscription is active the AskMeMore! teaser is replaced with a "Thank You!" message.

### 3 – Glossary
- Short paragraphs separated by lines

> Locked in free version > Present subscription modal

## AskMe!
This is the core functionality of the app where the user gets to ask their question. This section is presented modally (no other navigation elements visible) in order to focus the user on the task at hand. It is a sequence that can only be played forward:

### 1 – Choose Question Type
The way you pose your question is important. They can choose from 4 options: **Choice, Strategy, Attitude or Clarity.**

- Robot: *"What can I help you with?*
- 4 options (title, brief explanation, icon)
- Close function (x) > back to previous context.

### 2 – Input Question
Depending on the type chosen, specific instructions are shown to help the user ask his question:

- Header (title, brief explanation, icon)
- Question input (textfield, button)
- Instructions (carousel: 3 text screens)

### 3 – Coin Toss 
1. A short instruction appears
2. User shakes phone or taps screen
3. Coins are animated in (randomly heads or tails)
4. Robot animation appears (random)
5. Progress indicator bulb lights up
6. Back to step 2 – repeat
7. After the 6th toss, the algorithm determines the answer
8. All 6 robots ask the user to reveal the answer (segue to answer modal)

> **Please note:** The robots indicate what combination was thrown by white/black elements. These are provided as separate animations that overlay the base animation.

- Question asked (read only)
- Instructions (robot, text)
- 3 coins animation (random)
- 6 animations
- Progress indicator (6 lightbulbs)
- Ready (6 robots, button, info)

## Questions
All questions asked get automatically saved and listed here.
On iPhone the answers are simply stored on the users device and backed up automatically to the cloud. No user sign up required. No storing of information on remote servers. We would like to maintain this simple approach on Android as well.

### Empty
When no questions are asked yet or a folder is empty, a robot instructs them to ask their first question.

- Robot
- Text
- Start arrow animation

### List
When questions were asked they get listed here.\
They can be deleted or organised by folders individually or in bulk (edit).

> Free version: Only 3 answers (others disabled), no folders, no edit/delete)

- Navigation (folders, title, edit)
- Question items (question, date, folder)

### Folders
AskMeMore! enables the user to group questions in folders:

- Create/delete folders
- Add/remove questions
- Switch folder

### Answer Modal
Displays a short (condensed) and long (expanded) answer. Some sections can be expanded through a "more/less" button. Refer to [Content](#content) section for more detailed information.

- Question asked (read only)
- Tabs "Condensed | Expanded"
- "Sticky" section titles
- Formatted text
- "more/less" (collapse/expand)
- Text input
- Save button

## Settings
Configurations and additional functionality are displayed using a master/detail style list.

### Subscription
- Subscribe
- Restore existing subscription
- Subscription Terms and Privacy Policy (link to website)

> If already subscribed, a "Thank You!" message is displayed along with the expiration date and a link to manage the subscription

### Touch ID & PIN
Switch on to enable lock screen: Before the app opens, the user is prompted to authenticate using fingerprint recognition or by entering a passcode.

### Help/FAQ
Scrollable text from a json file (provided).

### Contact Us
Opens up email client with pre-filled email.

### Share
Social sharing functionality (e.g. social media, message, email, copy link)

### Review on the App Store
Link to App Store page where users can leave a review.

### About
- Version number
- Team (list of names, role and icons)
- Privacy Policy (text from json)
- Terms & Conditions (text from json)
- Open-source Libraries (adapt for Android)

## User Flow Diagram
![User Flow Diagram](UserFlowDiagram.png)

# Project Management
## Responsibilities

| Task | raphii (iOs Dev) | Isabelle Kriegel (Client) | You (Android Dev) |
|:--|:--:|:--:|:--:|
| Project brief| x | (x) |  |
| Onboarding | x | (x) | (x) |
| Design delivery | x |  |  |
| Content delivery | x | x |  |
| Development |  |  | x |
| QA check | (x) | (x) | x |
| Deployment |  |  | x |
| Maintenance |  |  | x |

> (x) = only partial responsibility

## Timeline

| Date | Task |
|:--|:--|
| Project brief | 16/04/2020 |
| Offer | TBD |
| Onboarding | TBD |
| Delivery (Design & Content) | TBD |
| Development | TBD |
| QA check | TBD |
| Deployment | TBD |
| Language Adaption | TBD |

## Offer
Please provide us with an offer detailing:

- Scope of your work
- Technical proposal
- Cost statement
	- Detailed for each task
	- External costs (subscriptions, licensing, etc)
	- Language adaption costs
	- Maintenance costs
- Proposed timeline

## Disclaimer
These documents may not be used without permission nor passed on to third parties.

You will be required to sign a nondisclosure agreement upon project start.

The work produced for this project will be considered "works made for hire" and Isabelle Kriegel will be the copyright holding author.