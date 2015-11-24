# Stuff.txt

### A simple file format for taking notes

## Why?

I have a problem remembering things. Especially details. I'm OK with remembering
that I know something but bad at remembering what that thing is (like 
you know the music that's playing and you know who sings it but at this moment
you can't recall what the title or the name of the singer is).

One day my boss said to me: *"write down everything in a text file then grep it later"*.
So I started writing down stuff in a simple **stuff.txt** file. The problem is that after
some time the notes in the file would lose context. Is this thing I'm looking at related
to the note above? So i started to separate the "notes" in the file using a simple delimiter:
A long line of underscores "____". So the stuff.txt file format was born.

## What?

The core idea of the **stuff.txt** format is simple:

> It should be simple enough for a normal person to read/write in a simple text editor
> (textedit/notepad/vi) but contain just enough structure to be useful.

And by "useful" I mean able to be processed by computer programs. This definition
of "usefulness" is important because it means we can develop tools to process our
stuff.txt files.

## Format

The format really is simple, each note is separated by a line of 4 or more underscores.
And that's it. That's the only rule.

Yeah ok just to clarify, the separator line must contain only underscores and nothing else.
This makes it easy to include underscores in the actual note itself (for example a
mock-up of a form).

It is strongly encouraged that the separator be 80 characters long. 

Also, the first note is special. It's sort of the "metadata" for the stuff.txt file. It's not
supposed to be an actual note. Normally it just contains your name. There is no
restriction on what the first note can or should contain. It can be blank or it can be
a long essay. It's just that tools are supposed to ignore the first note.

Empty notes should be ignored by tools.

Inspired by git, the first line of each note is supposed to be interpreted by tools as the
note title when presenting the notes as a list.

What qualifies as the *first line* is simply the first line after a separator that contains
printable characters. So all empty lines between the separator and the first line are
ignored (and empty lines include lines containing only spaces and tabs).

Example file:

    My stuff
    ________________________________________________________________________

    First Note

    This is the first note
    ________________________________________________________________________

    Second Note

    This is the second note
    ________________________________________________________________________

## Canonical stuff.txt file

Programs procesing stuff.txt files should expect to find a stuff.txt file in the users'
home directory (on Unix) or the user's documents directory (Mac & Windows).

## App

