# 🌌 Universal Generator Scenario Publishing 🌌

A step-by-step guide to creating a publishable AI Dungeon scenario using Universal Generator and (optionally) Toolbox.

This guide assumes a basic understanding of how to create prompts with Universal Generator.
For a basic rundown of Universal Generator, enter /help in the scenario's Generate option, or go here:

[https://github.com/FaraC-scripts/Universal-Generator-Basics/](https://github.com/FaraC-scripts/Universal-Generator-Basics/)

__Contents__
1. [Create a Universal Generator Prompt](#Create-a-Universal-Generator-Prompt)
2. [Convert Prompt to Story Cards](#Convert-Prompt-to-Story-Cards)
3. [Create a New Scenario and Import Story Cards](#Create-a-New-Scenario-and-Import-Story-Cards)
4. [\(optional\) Add Toolbox](#Add-Toolbox)

__Advanced Topics__
- [Dynamic Openings](#Dynamic-Openings)
- [Universal Generator Protagonist and Background Placeholders](#Universal-Generator-Protagonist-and-Background-Placeholders)
- [Configure Default Toolbox Settings](#Configure-Default-Toolbox-Settings)
- [Schedule Commands in Advance](#Schedule-Commands-in-Advance)
- [Prompt Ordering](#Prompt-Ordering)

All Advanced Features require Toolbox. For more information about Toolbox, go here:

[https://github.com/FaraC-scripts/Toolbox/](https://github.com/FaraC-scripts/Toolbox/)

## Create a Universal Generator Prompt
Go to the Universal Generator scenario:
${UG Scenario}

Click Generate

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Click%20Generate.JPG />

Include "scenario" when entering a writing category into the first placeholder.

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

If you're not using Toolbox, that's it. You're done. Finish creating and publish the scenario as normal.

If you found Universal Generator helpful when making your scenario, it would be appreciated if you included the following somewhere in your scenario description:
> Made with Universal Generator:
>
> ${UG Scenario}

Or put the universal generator sticker somewhere in your scenario image (you can click the image and download it from GitHub).

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Stickers/Universal%20Generator%20Sticker.png width=12.5% height=12.5% />

## Add Toolbox

In the Details tab of your scenario, under Scripting, make sure the toggle is set to Scripts Enabled.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Enable%20Scripts.JPG width=70% height=70% />

Click Edit Scripts to open the scenario's script editor.

Go to [https://github.com/FaraC-scripts/Toolbox/tree/main/Scripts](https://github.com/FaraC-scripts/Toolbox/tree/main/Scripts)

For each file (Library, Input, Context, Output), copy the script and paste it into the corresponding tab of your script editor.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Copy%20Code%20from%20Github.JPG />


<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Paste%20into%20Editor.JPG />

Finally, you will either need to disable AI Dungeons built-in AI Instructions, or Toolbox's Default Instructions, as both add their own AI Instructions. Having both enabled doesn't conflict, and in fact might make the final outputs slightly better, but it will increase the amount of context used for little additional gain.

If you plan on using Toolbox's Default Instructions, you need to create a blank AI Instructions component in your scenario __and press enter to create an empty line__. If you don't create one, or leave the instructions entirely blank by leaving out the empty line, AI Dungeon will include its own default instructions __in addition to the ones Toolbox provides__.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Blank%20AI%20Instructions.JPG width=65% height=65% />

If you want to use your own instructions, or AI Dungeon's default AI Instructions, you should disable Toolbox's default instructions to conserve context. To do so, go to the Library section of your scripts, and under the Context section of DEFAULT_SETTINGS change "Default Instructions" to false.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Change%20Default%20Instructions.JPG/>


# Advanced Topics

## Dynamic Openings

Dynamic Openings create a small block of text that replaces the traditional Opening plot component of a scenario.

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

___NOTE: Even if Dynamic Openings is enabled, AI Dungeon will have issues if the Opening plot component under the Setup tab has no text in it. Make sure to put some text there.___

## Universal Generator Protagonist and Background Placeholders

If you use Toolbox in your scenario, it can be configured to accept Universal Generator final outputs (prompts) from your players. 

The two placeholders you can create are the __protagonist placeholder__ and the __background placeholder__.

The __protagonist placeholder__ accepts a prompt from the player and filters it to find a Character component with "Character (Protagonist)" in its name. Failing that, it will find the first Character component. It will also find any other Character-type components associated with the protagonist, such as Appearance or Equipment. It takes these components and uses them to __replace any already-existing "Character (Protagonist)" prompt card__. It will also remove Appearance, Personality, and Speech cards associated with the old protagonist. Other components from the player-provided protagonist like Equipment and Abilities will override old components of the same type.

To enable the protagonist placeholder, create a story card with the custom type "Placeholder" and the name "Placeholder - Protagonist". The story card's entry needs to include a normal AI Dungeon placeholder to allow the player somewhere to paste their prompt, e.g., "${🌌 Paste a Universal Generator protagonist here}". It can be anything, though, as long as there is "${}" in the entry with some text between the brackets.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Protagonist%20Placeholder.JPG width=40% height=40%/>

The __background placeholder__ accepts a prompt from the player and adds every component in that prompt as a prompt card. If you already have Universal Generator prompt cards in your scenario, the background prompt cards will be placed behind them. There is no filtration or special handling for backgrounds.

To enable the background placeholder, create a story card with the custom type "Placeholder" and the name "Placeholder - Background". The story card's entry needs to include a normal AI Dungeon placeholder to allow the player somewhere to paste their prompt, e.g., "${🌌 Paste a Universal Generator prompt here}". It can be anything, though, as long as there is "${}" in the entry with some text between the brackets.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Background%20Placeholder.JPG width=40% height=40%/>

## Configure Default Toolbox Settings

You can configure the default Toolbox settings your player's scenarios will start with by editing the DEFAULT_SETTINGS object in the Library section of your scenario's scripts. Do not change any of the text in quotation marks. Only change numbers and true|false values.

Aside from Dynamic Openings (discussed above) these are the same settings your players will have access to. For details on exactly what each setting does, see the Toolbox documentation:

[https://github.com/FaraC-scripts/Toolbox/](https://github.com/FaraC-scripts/Toolbox/).

## Schedule Commands in Advance

As a scenario creator, you can schedule automatic Toolbox tool use in advance for your players. To do so, create a story card with the custom type "Schedule" and the name "Auto Tool Schedule". Format the entry as shown below. It should not have any triggers.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Auto%20Tool%20Schedule%20Card.JPG width=35% height=35%/>

The easiest way to do this is to play any Toolbox scenario and enter the auto commands you want. For example, entering "/motive -a5 the protagonist" produces the above. You will then have to copy the card to your scenario.

For more details on scheduling commands, see the Toolbox documentation:

[https://github.com/FaraC-scripts/Toolbox/](https://github.com/FaraC-scripts/Toolbox/).

## Prompt Ordering

Prompt cards are presented to the AI in a specific order. This can be important, as, for instance, you likely want the card for Kerry's Equipment to come pretty closely after the card for Kerry. By default, prompts are ordered in the same sequence they are in in the final Generator output.

While the player has access to a Prompt Sequence settings card to adjust the order of prompts mid-scenario, __when creating a scenario you cannot use a Prompt Sequence card__ to order prompt cards. It will be assumed to be an artifact of the scenario creation process and get deleted, like all other Settings-type cards.

Instead, if you wish to order your prompts after creating a scenario, you need to do so by ordering the story cards. To do this, export your scenario's story cards, open them in a text or code editor (they will be in JSON), and make sure your prompt cards are in the correct order there. Then, re-import the file. 
