# 🌌 Universal Generator Scenario Publishing 🌌

A step-by-step guide to creating your own AI Dungeon scenario using Universal Generator and (optionally) Toolbox, and publishing it for others to play.

This guide assumes a basic understanding of how to create prompts with Universal Generator.
For a basic rundown of Universal Generator, enter /help in the scenario's Generate option, or go here:

[https://github.com/FaraC-scripts/Universal-Generator-Basics/](https://github.com/FaraC-scripts/Universal-Generator-Basics/)

__Contents__
1. [Create a Universal Generator Prompt](#Create-a-Universal-Generator-Prompt)
2. [Convert Prompt to Story Cards](#Convert-Prompt-to-Story-Cards)
3. [Create a New Scenario and Import Story Cards](#Create-a-New-Scenario-and-Import-Story-Cards)
4. [\(optional\) Add Toolbox](#Add-Toolbox)

__Advanced Features__
- [Dynamic Openings](#Dynamic-Openings)
- [Allow Players to Provide Universal Generator Protagonists or Add-Ons]
- [Schedule Commands in Advance]
- [Prompt Ordering]
- [Configure Default Toolbox Settings]
  

All Advanced Features require Toolbox. For more information about Toolbox, go here:

[https://github.com/FaraC-scripts/Toolbox/](https://github.com/FaraC-scripts/Toolbox/)

## Create a Universal Generator Prompt
Go to the Universal Generator scenario:
${UG Scenario}

Click Generate

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Click%20Generate.JPG />

Include "scenario" when entering a writing category into the first placeholder

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Include%20Scenario%20as%20Category.JPG width="80%" height="80%" />

Fill out the second placeholder, or leave blank, as normal.

When the generator starts and you get your first output, make sure the Component Sequence line starts with "Scenario." "Character", "Timeline", and "Style" are also critical components.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Component%20Sequence.JPG /> 

___NOTE: If you are not planning on using Toolbox for your scenario, make sure all of the components you generate are formatted as story cards, not as prompt cards, by including the -s option. Prompt cards do not get triggers, and expect additional handling from Toolbox. For more information on the differences between prompt and story cards, read the Basics guide linked above.___

Though not strictly necessary, having Scenario as the first component will have a few effects on dynamic opening generation (more on that later). It will also help guide the AI towards open-ended design as opposed to developing a more linear narrative.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Scenario%20Example.JPG />

When creating a user-definable protagonist for your scenario, you have serveral options.
The first option is to create a placeholder card for the user to fill in when they start the scenario.
To create this card, input "/character -p your character"

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Character%20Placeholder%20Input.JPG />

This will create a placeholder output using the component you have chosen and the request segment of your input, in this case, "your character." Note that the placeholders use "!{...}" instead of "${...}". They will get properly converted later, but technical limitations require the substitution. 

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Character%20Placeholder.JPG />

Placeholders can be made with components other than Character, but you will likely need to touch those up manually for grammatical consistency.

__The other option for character creation is to configure your scenario to accept a Universal Generator character prompt.__ This allows players much more flexibility when creating a character, and lets them generate it instead of typing into placeholders. More on how to do this later.

The Timeline component's Opening Circumstances field is useful for starting a scenario exactly how you envision; it is also used in the dynamic opening.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Timeline%20Example.JPG  width=90% height=90%/>

The Style component's Tense and Perspective fields are used both in the dynamic opening and several other places to maintain a consistent narrative. While not required, this component is very helpful to include.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Style%20Example.JPG width=75% height=75%/>

Your final output is the Universal Generator prompt. It should look very similar to a JSON array of objects:
- The entire thing should be inside of square brackets, and each component should be inside of curly brackets.
- Each component should have the component name, the component type, and then the rest of the component's fields and values.
- Fields and values must be inside of double quotes. All other double quotes present in the text are converted to single quotes.
- Fields and components must be separated by commas.

<!-- -->

However, not all JSON rules are obeyed. Most importantly, components __are__ allowed to have multiple fields with the same name.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Final%20Output.JPG width=50% height=50%/>

Once you have this prompt, you will need to copy it to clipboard. The easiest way to do this is to left click on the text of the final output, cick Edit, then ctrl-a, ctrl-v

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Click%20Edit.JPG  width=70% height=70%/>

## Convert Prompt to Story Cards

With your prompt copied to your clipboard, click on the Play option of the Universal Generator scenario.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Press%20Play.JPG />

Paste your prompt into the first placeholder.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Paste%20Prompt.JPG />

Go to your Story Cards and export them. This will save them as a file you will need for the next step

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Export%20Story%20Cards.JPG width=33% height=33% />

You may notice that there are four settings cards in addition to the ones you generated. If you are using Toolbox for your scenario, you don't need to do anything about these and shouldn't bother changing them. They will be deleted and recreated when your players start their own scenarios. If you want to configure the default Toolbox settings your players start their scenarios with, that is covered in its own topic later.

If you are not using Toolbox, you should delete all four cards in the Settings category before exporting them. They won't cause any issue if you leave them, as they have no triggers, but they might confuse players.

## Create a New Scenario and Import Story Cards

Create a new scenario as normal. Then, import the story cards you saved in the previous step.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Import%20Story%20Cards.JPG width=75% height=75% />

If you're not using Toolbox, that's it. You're done. Publish the scenario as normal. If you found Universal Generator helpful when making your scenario, I would appreciate it if you include the following somewhere in your scenario's description:
> Made with Universal Generator:\n${UG Scenario}

## Add Toolbox


## Dynamic Openings

Dynamic Openings create a small block of text that replaces the traditional opening section of a scenario.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Opening.JPG width=75% height=75% />

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Scenario%20Card.JPG width=40% height=40%/>

Instead, you get a scenario start based on its prompt cards. This is the dynamic opening created when pasting the prompt created in the above tutorial into Play, highlighted to distinguish different parts.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Dynamic%20Opening%20Marked.png />

🟡 This starting sentence changes based on the presence or absence of a Narrative or Scenario prompt card.

🔵 If a Timeline prompt card with an Opening Sequence field is present, that text will be used here. That field of the Timeline card will also be hidden from the AI, so it never sees the opening twice. If there are no Opening Circumstances, generic text will be used based the presence or absence of Narrative or Scenario.

🟢 This uses the protagonist's name if a prompt card with "${Name} - Character (Protagonist)" as its title is present. Otherwise, it generically uses "the protagonist." In this example, the protagonist's name is a placeholder the player can fill in. If player-provided prompts are enabled and they provide a protagonist prompt, that name will be used. 

🔴 This uses the perspective and tense from the Style prompt card, if available. If not, it defaults to second-person, present tense.

To enable Dynamic Openings, you need to change the Dynamic Opening field of DEFAULT_SETTINGS in Toolbox's library in your scenario's scripts from "false" to "true". It is under the "Hidden" category, as it is not an option players can see or change in-game.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Dynamic%20Opening%20Setting.JPG width=90% height=90% />
<!--
<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Stickers/With%20Toolbox%20Sticker.png width="200" />

Before you start creating components for your scenario, it is important to understand the differences between __story cards__ and __prompt cards.__ When you use Play to create a scenario from the final output of Generate, each component gets converted into a card in the Story Cards section of your new scenario.

__Prompt cards__ are what components get converted into by default. They require a scenario running Toolbox to function, as they do not use and should not have triggers. Prompt cards will always have "Prompt" as the first word of their card's Type.
