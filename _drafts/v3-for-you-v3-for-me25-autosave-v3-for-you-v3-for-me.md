---
id: 115
title: v3 for you, v3 for me!
date: 2008-10-20T00:25:46+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/?p=115
permalink: /gruedorf/25-autosave/
---
### To make a new vergec function:</3></p> 

#### Step 1.

You must create a C function to actually implement your new vc function&#8217;s logic. The naming convention is vc\_NAMEofYOURnewFUNCTION, and convention says to put it in vc\_builtins.cpp. If you&#8217;re returning a string, you will want to alter the std::string variable vc->vcretstr within your new function. If you&#8217;re returning an int, you&#8217;ll want to alter the integer vc->vcreturn instead.

#### Step 2.

You must add a function call to the array of libfuncs, also in vc_builtins.cpp. This is an ordered list of droupings of 3 c-style strings apiece. Each grouping represents a vc function: The first is the return signature, the second is the name, the third is the argument signature. 

Here is an example line: {&#8220;3&#8221;, &#8220;DictListKeys&#8221;, &#8220;13&#8221;},

The &#8220;3&#8221; for the return type says it returns a vc string. &#8220;DictListKeys&#8221; is the name of the vc function. The &#8220;13&#8221; signifies that this function takes two arguments: an int and a string, in that order. The character &#8220;1&#8221; represents a vc int, and the character &#8220;3&#8221; represents a vc string.

The order of this list determines what integer represents each function in the vergec bytecode. Fun, eh?

#### Step 3.

Whenever you add a function to the libfuncs list, you must also increment the NUM\_LIBFUNCS define in opcodes.h. libfuncs is a static array, and NUM\_LIBFUNCS is that static array&#8217;s size declaration.

#### Step 4.

Finally, you must add a new case clause to the giant switch in VCCore::HandleLibFunc() within the vc_library.cpp file. The case&#8217;s integer is the opcode in the vergec bytecode that represents the function. This is the index of the function&#8217;s definition in the libfuncs array from step 2. 

#### Step 5.

Compile a new verge.exe, and debug your function. Congrats, you&#8217;ve made your first vergec function.

### Grue, why are you altering vc?

Good question, me. I thank myself for asking it.

&#8230;

Anyways, I wanted to add a way to get the list of vergec functions presently defined by the user in their system.vc code. To this end I first set out to make ListUserFunctionsm, which would work like ListBuiltinFunctions. However when I made this it failed horribly because I have so many functions: the string was simply too big for vc to handle. Not wanting to venture into vergec&#8217;s string handling functionality tonight, I looked for an alternate method.

Quickly I settled on a vc_GetUserFunctionCount() and GetUserFunctionByIdx() solution, which was better by far in my opinion instead of returning a ginormous pipe-character-delimited string. However, I failed at this for mysterious and retarded reasons unknown to me at this time. So&#8230; I&#8217;ve utterly failed where I was trying to rock.

### But&#8230; why do you want those functions?

Excellent follow-up, self. 10 points to Ravenclaw.

While these two functions have several fun uses, I was making these functions so I could introduce a light unit-testing framework within vc. With some function-name introspection, I could find any function starting with, say, &#8220;grunit_&#8221; and use CallFunction() on it to execute said test. Making it automatically execute like that would be a great boon overall in the future, and would make it so I could develop a complicated system (such as say&#8230; a battle system) without fear of time lost in the future to hidden bugs caused by future feature implementation.

Yeah, that&#8217;s right. I&#8217;ve caught the Agile bug. Don&#8217;t ask why I&#8217;m still using vergec, though: I&#8217;ve only partially caught it. ;)

No SVN update this week. 4 hours in and I&#8217;ve still got a wash. I&#8217;m going to continue on, but I wanted to get this post out without too much more of a delay. So as I don&#8217;t feel bad about today, though, it should be noted that the development copy of <a href=http://breadbros.com>breadbros.com</a> improved by leaps and bounds today. Hooray!