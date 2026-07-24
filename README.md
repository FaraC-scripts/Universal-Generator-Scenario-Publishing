#🌌 Universal Generator Scenario Publishing 🌌
A step-by-step guide to creating your own AI Dungeon scenario using Universal Generator and (optionally) Toolbox, and publishing it for others to play.

This guide assumes a basic understandning of how to create prompts with Universal Generator.
For a basic rundown of Universal Generator, enter /help in the scenario's Generate option, or go here:
[Universal Generator User Manual](https://github.com/FaraC-scripts/Universal-Generator-User-Manual/)

### Step 1: Create a Universal Generator Prompt
Go to the Universal Generator scenario:
${UG Scenario}

Click Generate
<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Click%20Generate.JPG />

Make sure to include "scenario" when entering a writing category into the first placeholder
<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Include%20Scenario%20as%20Category.JPG />

Fill out the second placeholder, or leave blank, as normal.

When the generator starts and you get your first output, make sure the Component Sequence line starts with "Scenario." "Character", "Timeline", and "Style" are also critical components.
<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Component%20Sequence.JPG />

Though not strictly necessary, having Scenario as the first component will have a few effects on dynamic initial input generation (more on that later). It will also help guide the AI towards open-ended design as opposed to developing a more linear narrative.
<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Scenario%20Example.JPG />

When creating a user-definable protagonist for your scenario, you have serveral options.
The first option is to create a placeholder card for the user to fill in when they start the scenario.
To create this card, input "/character -p your character"
<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Character%20Placeholder%20Input.JPG />

This will create an output that replaces what the AI would have generated with placeholders using the request segment of your input, in this case, "your character". However, there will be a few places where manual edits are needed for
<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Guide%20Images/Initial%20Character%20Placeholder.JPG width="1301" height="538" />

<img src=https://github.com/FaraC-scripts/Universal-Generator-Scenario-Publishing/blob/main/Images/Stickers/With%20Toolbox%20Sticker.png width="200" />
