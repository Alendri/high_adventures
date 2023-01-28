#rust #coloring #treris #pixel-art #bevy #macroquad #

# Treris

After coloring in a book with my toddler during Christmas - *read finding crayon marks all over the wall* - I had an idea of making a coloring application for touch screen devices.

There are plenty of those already on phones already, but none made by me and most of them are very boring. An hour of research told me most are either too complicated for a toddler or too boring for anyone older.

I am also interested in learning more about [Rust](http://www.rust-lang.org) - the programming language. The game engine [Bevy](https://bevyengine.org/) has also caught my attention, their ECS philosophy is interesting to me so I wanted to learn how to use it as well.  
I decided to challenge myself by making a prototype of my idea in 10-15 hours to see if it would be a fun project to continue.

&nbsp;

### This is the story of making Treris.

&nbsp;

_Warning: Some of the Treris texts may be technical in nature._

&nbsp;  
&nbsp;  
&nbsp;  
&nbsp;  

## Concept
The basic concept was to use Rust and the game engine Bevy to create an app which allows selecting a _Palette_ and applying it to a sprite drawn on screen.

In essence you are picking colors and what to color, not drawing the colors yourself.  
Where is the fun in that? you may rightfully ask.  
When observing my toddler I do not believe they would be very happy to see things move, learn about what things are called and make things come to life. Rather than struggle to color a specific area of something.

With that in mind I wanted;

- To use a front-top Pixel Art style, inspired by [Chef RPG](https://www.kickstarter.com/projects/chefrpg/chef-rpg) and [Stardew Valley](https://www.stardewvalley.net/) and many others.
- The world to be alive, possibly by having some animations.
- There should be support for multiple hues, so just because you choose to make the house Yellow it doesn't have to all be the same yellow.
- I wanted the world to possibly be computer generated, so you don't pick a single "Image" to color in. Rather it should be a dynamic whacky whimsical messy world.
- You should be able to affect the world. Add things, especially moving things.

![Stardew Valley scene](images/stardew_valley.png)
Pixel art from Stardew Valley. Stardew Valley Copyright © ConcernedApe LLC.

&nbsp;  
&nbsp;

### The prototype scope
As much as I want to see all of the above as a software developer I would like to think I have learnt some lessons. One of those would be to reduce any prototyping to the bare essentials and clearly spell out what the expectations are.

What I decided on implementing for the prototype;

- Pixel art, made by myself. I have no experience but want to learn.
  - A few trees.
  - Some flowers.
  - A house.
    - Window
    - Door
    - Chimney
- Sprites (tiny images that makes up the art)
  - Should use gray scale values which serve as an index in to a color palette.
  - Sprite grouping support, so that for example a tree can be three separate sprites stacked on top of each other but act as one.
  - 3 layers of sprites should be stackable.
  - Each layer is independently colorable.
- A few basic palettes that can be switched between to prove the concept.
- A world which is created from values in an image, so that it can be manipulated and inspected easily. _This also felt like a decent way of sharing worlds in the future and easy enough to have as output from a world generating algorithm if I ever get that far._
- The world should be scrollable to give an "endless" feel, even if it isn't.

Very quickly I found that the documentation for the Bevy engine was a bit limited, I decided to go with something simpler so as to have _something_ to show at my deadline. Instead I went with [Macroquad](https://github.com/not-fl3/macroquad) for the prototyping.