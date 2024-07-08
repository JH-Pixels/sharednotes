>I use this file to explain what conventions etc. I'm using in Obsidian. Entirely optional.
>The absolute Goal is to be organised without having to worry too much about organisation itself and eventually to publish some notes.
# PKM System
First things first. I do not natively speak english, but I still chose to write almost all of my notes in English. The simple reason for that is: I enjoy writing in the English language more than in any other.

Here are a few important **overall statements**:
- The overall concept is very similar to the A.C.C.E.S.S system by Nick Milo
- Parts of the famous Zettelkasten concept have been implemented
- In my PKM generally the "What is it?" is handled with tags and the "What is it about?" with MOCs. There are however some exceptions
- I try to only put things in here that I want to learn and apply in the future. A PKM is not an archive of useless information
- Whenever I come across something interesting (Information, Ideas etc.), I use the notes app on my phone to then add the info later to my Vault. Reason: Obsidian Mobile takes some time to load and index the vault.


## Dashboard
The Home Note should always be kept clutter-free and organised. It consists of many different elements and it's there to give me an overview of everything in my vault. 

## Folders
>[!Hint]+ I try to use as few folders as possible; too many destroy key features of Obsidian.

I use 7 Folders:
`_attachments` for all attachments, such as images, pdf's, drawings etc. . I also use this folder for all Canvas's and Excalidraw's.
`_templates` for my templates. Examples: `Person_temp`, `Book_temp`,`Effort_temp`.
`Atlas` for all MOCs and everything where I want to have easy access to; such as: `Quotebook`,`Plan&Review`, `Inbox`, `Library`, `Notebox`.
`Cards&Encounters` for almost all other Notes. This is the folder where the "actual" knowledge is stored. Examples: `Python`, `SHA-2`, `OSINT` and *many* more.
`Efforts`for all past, current and future projects. If you are curious as to how this works, check out [this video](https://youtu.be/Ew7ZBu4r8vg?si=Aw8yqk-j0xQnmv02) by nick milo.
`Journal` this is the place for all my Calendar Notes. I only do Daily and Weekly notes.
`Sources` for everything that is not from me, such as: books, videos, lectures, people.
## MOCs
I got this concept from Nick Milo. A map of content is note that is created manually to contain an overview of something. It is a note that can be broken down into several components and can address a number of notes that make up a bigger idea or concept. It can link out to a number of other Maps of Content in a hierarchical manner. In short: A MOC is an overview note that provides structure for a number of other notes. The main reason why I love to use MOCs is that they allow for organisation without organisation. Notes organise themselves by Linking to relevant topics. It is also possible for one note to have multiple MOCs, which is something that would not work with the typical folder structure. Some of my MOCs are `Thinking_MOC`,`Psychology_MOC`,`Finance_MOC`,`Life_MOC` and as a sub-MOC `Habits_MOC`. 

As stated previously, my MOCs go into the `Atlas` folder. They also get the `#map`tag.

My `MOC_temp` file looks like this:
```
*up::* [[Home]]
*tags::* #map
# {{title}}

## Data View
%%everything that has a reference to this MOC%%
```dataview
table
WHERE contains(file.outlinks, this.file.link) AND contains(file.path, "/") AND !contains(file.path,"_templates")```
```

## Daily & Weekly Notes
I like to write a note every day. I don't see it as an obligation to do it tough. My daily notes are used to reflect on the day, go back to ideas I had and to track my habits (via yaml). I like to add a "Memory Trigger" as Heading of my daily notes to better remember the day; this can be something that happened or something that I learned.
At the end of every week I try to write a weekly note, where I track my accomplishments and think about improvements.
Daily notes go in the `Journal/Daily` folder and weekly notes in `Journal/Weekly`.
My current `Daily_temp` file looks like this:
```
---
created: {{date}}
kmRun: 0
readPages: 0
productivity: 0
mood: 0
---
*up::* [[Calendar_Notes]]
*tags::* #log/d_journal 
*time machine::* [[{{ date-7d }}]] *>>* [[ {{ date-1d }}]] *> Today >* [[ {{ date+1d }} ]] *>>* [[{{ date+7d }}]] 

# {Memory Trigger}
---
## What Did I Learn Today?
## What's On My Mind? Any Ideas?
## Brief Description
## Did Anything Out Of Ordinary Happen?
## Tasks For The Day
## Notes Created
```dataview
TABLE created
FROM "Efforts" OR "Cards&Encounters" OR "Atlas" OR "Sources"
WHERE contains(dateformat(created, "YYYY-MM-DD"), dateformat(this.file.day, "YYYY-MM-DD")) ```
```

## Tags
I use Tags for a few things. I love using tags inside of templates, since this makes organisation even easier.
Here are my tag use-cases:
- Sources such as videos, blogs or books get the `#source` tag with a suitable subtag(e.g.: `#source/video`)
- Concepts are tagged with the `#concept` tag. I try to keep these notes as *concise* as possible.
- Notes that are ready to be shared get a `#publishable` tag
- I use tags for notes that I want to review as Flashcards (using the `Speced Repetition` plugin)
- for pre-MOCs I usually do nested tags with `#on`. For example `#on/cybersecurity/hashes`. This makes creating a MOC in the future easier.

I also use tags for quotes and a few other personal things.
## Templates
I do not use the `Templater` plugin, because the regular Obsidian template functionality is sufficient for all of my use cases. 

## Processes
There are many processes I do to keep myself organised. I won't be going over all of them.
### Retaining Process
When it comes to knowledge, there a three phases. *Acquire*, *Learn* and *Practice*. 
Whenever I acquire a new interesting piece of information, it goes into my Vault. If it it something I want to learn, I create flashcards and then try to practice 
## Canvas
I use a Canvas to Brainstorm, to visualise relations (e.g. Home Network) and to manage efforts that can use some visualisation.

## Other Conventions I Use
- Every note that refers to a person has a @ as the first character (e.g.: @RobertGreene)
- One piece of literature usually goes in one single note; even if it consists of many videos/lectures
- Past notes are not an archive; they are meant to be reviewed and updated/changed
- There is a big difference between working and working on a PKM!
- Create first organise later; with this system notes usually organise themselves
