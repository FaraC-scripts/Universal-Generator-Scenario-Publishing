# 🌌 Universal Generator Scenario Publishing 🌌

A step-by-step guide to creating your own AI Dungeon scenario using Universal Generator and (optionally) Toolbox, and publishing it for others to play.

This guide assumes a basic understandning of how to create prompts with Universal Generator.
For a basic rundown of Universal Generator, enter /help in the scenario's Generate option, or go here:

[Universal Generator User Manual](https://github.com/FaraC-scripts/Universal-Generator-User-Manual/)

Contents:
1. [Create a Universal Generator Prompt](#Create-a-Universal-Generator-Prompt)
2. [Convert Prompt to Story Cards]

### Create a Universal Generator Prompt
Go to the Universal Generator scenario:
${UG Scenario}

Click Generate

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Click%20Generate.JPG />

Include "scenario" when entering a writing category into the first placeholder

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Include%20Scenario%20as%20Category.JPG width="80%" height="80%" />

Fill out the second placeholder, or leave blank, as normal.

When the generator starts and you get your first output, make sure the Component Sequence line starts with "Scenario." "Character", "Timeline", and "Style" are also critical components.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Component%20Sequence.JPG />

Though not strictly necessary, having Scenario as the first component will have a few effects on dynamic opening generation (more on that later). It will also help guide the AI towards open-ended design as opposed to developing a more linear narrative.

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Scenario%20Example.JPG />

When creating a user-definable protagonist for your scenario, you have serveral options.
The first option is to create a placeholder card for the user to fill in when they start the scenario.
To create this card, input "/character -p your character"

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Character%20Placeholder%20Input.JPG />

This will create a placeholder output using the component you have chosen and the request segment of your input, in this case, "your character."

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

Once you have this prompt, you will need to copy it to clipboard. The easiest way to do this is to right click on the text of the final output, cick Edit, then ctrl-a, ctrl-v

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Click%20Edit.JPG  width=80% height=80%/>

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Stickers/With%20Toolbox%20Sticker.png width="200" />
