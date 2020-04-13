# AskMe! Android App
Brief for the development of an Android version of the existing iOs App ["AskMe!"](https://apps.apple.com/app/id1217624457)

{{TOC}}

## Overview
### Background
There currently exists an iPhone app named ["AskMe!"](https://apps.apple.com/app/id1217624457).

It is based on a book written by [Isabelle Kriegel](http://www.isabellekriegel.com/) – an interpretation of ancient Chinese divination texts also known as [“I Ching”](https://en.wikipedia.org/wiki/I_Ching) or the book of change.

In an effort to make the app available to a wider audience, we plan to develop a native Android version.

### Core Functionality
The user gets to choose one of four options:

1. **Choice:** I need to make a decision\
2. **Strategy:** How do I solve this problem?\
3. **Attitude:** How should I react\
4. **Clarity:** Help me better understand

Upon choosing, they get prompted to type a question regarding their current life situation. Some information on how to pose a question is provided.

They then shake their phone 6 times to virtually “throw” 3 coins. They are guided through this process by adorable animated avatars. Light bulbs are used to show the progress. The resulting pattern of heads and tails is analysed by an algorithm choosing the corresponding text from the "Book of Change" ([I Ching](https://en.wikipedia.org/wiki/I_Ching)).

In an effort to not overwhelm the user with too much text a condensed version is presented to capture their interest and allow them to dive deeper by expanding sections or opening a more detailed version of the same text.

### Revenue Strategy
**Freemium Model** – The app is free of charge, but a premium is charged for additional features that expand the functionality of the free version:

- More in-depth Answers (Expanded Version)
- Unlimited saved questions (only last 3 in free version)
- Passcode lock
- Group questions by subject
- Delete questions
- Access to the glossary
 

### Existing App
Make yourself familiar with the existing app by downloading it from the [App Store](https://apps.apple.com/app/id1217624457).

Alternatively you can view this [Prototype](https://xd.adobe.com/view/a39d32b0-eea6-4b45-a2ff-353eb534245d/).
> Please note: The prototype does not represent the current state of the app – some changes to design and functionality have been made since.

## Content
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
> For easy deployment of changes across platforms we require to maintain the structure and integrity of these source files – they may only be refactored by code.

There are 4 main sections in an Answer that are comprised of the following nodes in the .json file:

1. **The Big Picture**\
	- "summary": big bold text separated by green lines
	- "bullets": green bullets, indented text
	- 	"advices": bold title and small paragraph with alternating background colours.
> Both the bullets and the advices in the node "hide" are initially hidden and can be shown/hidden by clicking "more/less"

2. **A Closer Look**
	- "hangingLines" > "intro": big bold text
	- "lines": bold title and small paragraph with alternating background colours.
> Depending on the coin combination thrown, 1-6 of the lines get displayed.

3. **On the Horizon**
	> This section is the same as "The Big Picture" but comes from a different answer file chosen by the algorithm depending on the coin combination thrown.\
	> If the same file as above gets chosen a hint is shown (instead of repeating the same text twice):
>> **This time your answer is short but even more powerful.**\
Everything that you need to understand can be found above
	- "summary": big bold text separated by green lines
	- "bullets": green bullets, indented text 
> The bullets are initially hidden and can be shown/hidden by clicking "more/less"

4. **My Interpretation**
	- The user can choose to write their own interpretation here and save it to memory along with their question and the I Ching answer.

> A few tags are used for styling:\
`<bold>` **Bold Text** `</bold> `\
`<italic>` *Italic Text* `</italic> `

### Languages
The app currently exists in two languages. All the translated copy and graphics needed will be provided.

- [x] **English** (base language)
- [x] **French** (implemented)
- [ ] **Spanish** (work in progress)

> Additional languages possible in the future

## Visual Design
### Graphics

![User Flow Diagram](UserFlowDiagram.png)

The visual design will be provided in form of:

- Screenshots of all screens
- User flow diagram
- Detailed style guide (colours, typography, measurements)
- Sketch file
- Vector graphics of all visual elements (pdf, svg, illustrator)

> The app was designed for iPhone and is using components, navigation patterns and functionality common or unique to iOs. Though the look and feel should be the same across platforms, we expect that you adapt some aspects to mimic familiar Android patterns.

### Animation
[https://lottiefiles.com/share/DOsS8v](https://lottiefiles.com/share/DOsS8v)
### Typography
## Development

## Project Management
### Responsibilities
### Timeline
### Offer
### Disclaimer
These documents may not be used without permission nor passed on to third parties.