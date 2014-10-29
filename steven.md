Steven's Work Diary
===================

2014-10-13
----------
* A team member committed a whole bunch of merge conflicts before resolving them ending up breaking a bunch of files. Regex to the resuce!

```
<<<<<<< HEAD\s([\s\S]+?)
=======\n*?([\s\S]*?)
>>>>>>> FETCH_HEAD
```

Resolved all the conflicts by using the newer version. Not pretty but we don't have time to waste.

2014-10-21
----------
* I'm finding it really hard without an IDE to develop in C++, the guys with XCode seem to have it easy. I tried installing Codeblocks but couldn't get our code to compile in it.

2014-10-25
----------
* ArgoUML is old and abandoned and a major pain to use, https://www.lucidchart.com was so simple for my tutorials so I whipped up a simple script to extract the attributes and methods from each class. In total 4 regular expressions were used and made creating the new class diagram from scratch take a little over 10 minutes.

2014-10-27
----------
```
^\s*
(?!friend\s+class\s+)
[a-zA-Z0-9\: \*<>_]+\s+
\*? #Tim likes to do UserDatabase *shared()
(?<name>\w+)
(?:\s*=\s*.*)?; #stuff at end eg. = false;
(?:[ \t]*//(?<description>.+))
```

I can't work why the description was including a new line in it's capture group, so rather than waste time I used a callback function to strip whitespace at the start and end. Elegant no, Works yes.