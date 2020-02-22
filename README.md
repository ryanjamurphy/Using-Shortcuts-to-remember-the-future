# Using Shortcuts to remember the future
A Shortcut—or collection of Shortcuts—to help you push through a stressful milestone using (short-term) [futures thinking](https://fulcra.design/resources#getting-started-with-futures-thinking).

## Installation
These Shortcuts require Shortcuts on iOS. To install them, simply download the links on an iOS device and install. **Important: you must first go into Settings → Shortcuts and enable the "Allow Untrusted Shortcuts" preference before your device will let you install these.**

## Basic edition
I mean, the basic edition is simple. List a few nice visions as `Text`, `Split Text` by new lines, `Get Item from List` randomly, and `Show Result`. 

https://www.icloud.com/shortcuts/6f6fb855bb684956a8e678be4db6580e

## Getting fancy
My version is a little fancier. I put my items in a [DEVONthink](http://devontechnologies.com) markdown file to make it easy to add to it anywhere, and I used recursion to make it easy to loop. This made it more complicated, of course. There are five (five!) interlocking Shortcuts. 

### [Visualize](https://www.icloud.com/shortcuts/bc1c7bb743714b599519c5a33dd63a2c)
The first part of the "controller". This runs two shortcuts: **Get Visualizations** to pull the list from the DEVONthink file, and then it runs **Recursive Visualization** to give me a looping prompt.

### [Get Visualizations](https://www.icloud.com/shortcuts/2ca3733852b7453c9c5dec317939a364)
The "model". Give it a DEVONthink item link and the markdown heading level of the images of the future in that file, and it feeds that link to a **Get list from DEVONthink md headings** Shortcut that pulls them into a nice list for you. 

### [Get list from DEVONthink md headings](https://www.icloud.com/shortcuts/7a04eeb082fc4c5bb055af9c989a7adb)
This is a helper function I've developed to make it easy to grab headings in a markdown file saved in DEVONthink. I use it elsewhere too. It accepts:
- a `Dictionary` containing...
  - a `Heading` value indicating the level of headings you want to parse (in the form of a number of # symbols).
  - a `File` value in the form of an x-devonthink-item:// link.

It switches that item link into an x-callback-url to, grabs and decodes the text content of the DEVONthink item, grabs each of the appropriate heading lines, cleans the hashtags from each line (so they don't appear in your resulting list), and outputs that final list.

### [Recursive Visualize](https://www.icloud.com/shortcuts/766fd82ebf4e438db088ce7d5be9bff5)
The second part of the "controller". This shortcut receives a list and then runs the **Visualizing Positive Futures** sub-shortcut (to facilitate recursion). It then offers a simple menu with "Another?" as a prompt, and the options yes or no. If you chose yes, it runs itself again, looping without having to re-do all of the above shortcut actions (speedy!)

### [Visualizing Positive Futures](https://www.icloud.com/shortcuts/7a04eeb082fc4c5bb055af9c989a7adb)
The "view". Nice and simple. This shortcut accepts a list, gets a random item, and shows the item as a result.
