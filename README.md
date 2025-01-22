java c
CIT   5940   -   Module   1   Programming   Assignment 
ArrayLists:   Dynamic   Arrays
Assignment Overview In this   module,   you   saw   how   an   ArrayList works by performing operations using   an   underlying   array   hidden   to   users.   In   this   assignment,   you   will   modify   the   implementation   of an   ArrayList   so   that   it   uses   Java   Generics,   as   well   as   adding   custom   functionality.
Learning Objectives 
• Understand   the   implementation   of   an   ArrayList in   Java
•    Gain familiarity   with   reading   and   modifying   existing   code
• Verify   that   you   can   submit   code   to   our   autograding   platform.
Advice We   highly   encourage   you   to   utilize   the   course   discussion   forum   to   discuss   the   project   with   class-   mates   and   TAs.      Before   asking   the   question,   please   search   in   the   forum   to   see   if   there   are   any   similar   questions   asked   before.   Please   check   all   suggestions   listed   there.
For   this   and   all   other   assignments   in   this   course,   we   recommend   that   you   work   on   your   local   computer   using   an   integrated   development   environment    (IDE)   such   as   Eclipse,    IntelliJ,   Visual   Studio   Code,   or   whatever   IDE   you   used   for   any   prior   Java   courses   that   you   are   familiar   with. Although you will need to upload your solution to Gradescope for grading (see the Submission Section below) and could develop your solution on that platform, we recommend using industry standard tools   such   as   Eclipse   or   IntelliJ   so   that   you   become   more   used   to   them   and   can   take advantage   of   their   features. 
If   you   have   trouble   setting   up   your   IDE   or   cannot   get   the   starter   code   to   compile,   please   post   a note in the discussion forum and a member of the instruction staff   will try to help you get started.
We   have   provided   an   example   JUnit   test   file to help check your implementation. Please read the   comments   and   complete   the   code   to   validate   your   solution   before   submission.
1 Setup 
1.    Begin   by   downloading   the   CIT594-arraylists   .   zip   archive   from   Canvas,   then   extract   the   contents.       The    main   file   you   will   work   is   MyArrayList   .   java.       This    contains   the   unimplemented   methods   for   the   code   that   you   will   write   in   this   assignment.
2.   We   have   also   provided   a   JUnit test   file,   MyArrayListTest   .   java as an example of JUnit   tests.    Please   read   the   comments   in   the   file   and   complete   the   code   to   validate   your   solution   before   submission.
3.    Compile   this   code   before   making   any   changes.      This   will   ensure   your   local   environment   is   configured   correctly.
4.   Review   the   current   implementation.   You’ll   want   to   understand   the   various   parts   of   the   code and   how   they   work   together   before   making   changes!
2          Requirements 
2.1 Structure and Compiling 
1.    You    MUST   use   a   Java   Development   Kit    (JDK)   version   of   17   or   higher.       This   is   because   Gradescope   is   using   Java   17.
2.    You   MAY   use   a   JDK   version   higher   than   17,   but   you   MUST   set   the   Java   language   level   to
17   for   compatibility   with   Gradescope.
3.    You    MUST    NOT   change   any   method   signatures   for   any   of   the   provided   methods.       This   includes   the   parameter   lists,   names,   and   return   value   types,   etc.
4.    You   MUST   leave the MyArrayList.java   in the   default   package.
5.    You   MUST   NOT   create   additional      .   java   source   files   for   your   solution.
6.    You   SHOULD   create   JUnit   tests   to   help   validate   your   code.    These   tests   SHOULD   NOT   be   a   part   of your   solution.   The   starter   code   includes   a   partial   JUnit   test   file   as   a   refresher.   We
do   expect   you   to   test   your   code   thoroughly   with   additional   JUnit   tests.
7.    You   MUST   follow   our   directives   in   the   starter   code   comments.    This   means   if we   ask   you   to   not   change   a   variable’s   value,   you   MUST   NOT   change   that   variable’svalue.
8.    You   MAY   create   additional   helper   functions,   as   long   as they   meet the   other   requirements   of   the   assignment   (e.g.   uses   Java   Generics,   doesn’t   crash   with   invalid   inputs).
9.    You   MUST   fill   out   the   required   Academic   Integrity   signature   in   the   comment   block   at   the top   of your   submission   file.
2.2 Functionality Specifications 
2.2.1 General Requirements 
1.   Your method MUST NOT crash if a user   enters   an   invalid   input.    Remember you do   not   have   control   over   what   a   user   inputs   as   arguments.   Your   program   should   not   throw   an   exception   except   when   specified.
2.   Note   specifically   that   Java   allows   you   to   add   the   value   null   to   a   list   of   objects.       Your program   MUST   consider   null   as   a   valid   element.
3.   You   MUST   maintain   the   size   field.    This   is   the   number   of   elements   in   the   underlying   array,   NOT   the   length   of the   array.
4.   You   MUST   check   for   element   equivalence   using   the   equals   method.
2.2.2 Java Generics 
1.   You   MUST   modify   the   starter   code   to   use   Java   Generics   instead   of   Strings.    This   includes parameters   and   return   values.
2.   Your   underlying   array   MUST   be   of   type   Object[].
3.   As   a   hint,   find   all   the   references   to   String,   these   will   be   replaced!
4.    As   an   example,   you   should   be   able   to   create   an   instance   of the   class   for   any   type   like   this:
// create an ArrayList    that holds Integers 
MyArrayList> integerList = new MyArrayList<>();  

// create an ArrayList    that holds Doubles 
MyArrayList doubleList = new MyArrayList<>(); 
2.2.3 remove method 
You   MUST   implement   the   remove   method   as   follows:
1.   This method   MUST take   an object of the   parameterized   type   as   the   single   input   parameter.
2.   If   at   least   one   equivalent   element   exists   in   the   underlying   array,   this   method   MUST   do   the   following:
(a)   remove   only   the   first   instance   of   an   equivalent   element,
(b)   shift   the   remaining   elements   to   the   left   to   fill   the   empty   space,   AND
(c)   return   true.
3.   If   an   equivalent   element   does   not   exist   in   the   underlying   array,   this   method   MUST   do   the following:
(a)   leave   the   underlying   array   untouched,   AND   (b)   return   false
4.   the   order   of the   remaining   elements   MUST   remain   the   same
5.    As an example, assume the underlying array for myStringArrayList contains   these   values   in   this   order
"Cat" 
"Dog" 
"Banana" 
"Aardvark" 
null 
null 
If   you   were   to   call   myStringArrayList   .remove("Banana"),   then   the   array   should   look   like   this:
"Cat" 
"Dog" 
"Aardvark" 
null 
null 
null 
and the   return   value   would   be   true.
2.2.4 Shrink Array 
You   MUST   shrink   the   underlying   array   when   it   is   too   large   as   follows:
1.   Both   your   remove   method   (from   the   section   above)   and   the   remove   method   provided   in the starter code MUST shrink the length of   the underlying array when both of   the following   conditions   are   true:
(a)   the   method   successfully   removed   an   element,   AND
(b)   the   new   size   of   the   underlying   array   is   less   than   OR   equal   to   25%   of   the   length   of the   underlying   array2.   the   length   of   the   underlying   array   MUST   shrink   to   half   the   current   length
3.   the   other   requirements   for   remove   above   MUST   be   implemented
4.    As an example, assume the underlying array for myAnimalArrayList contains   these   values   in   this   order:
"Ant" 
"Bat" 
"Cow" 
null 
null 
null 
null 
null 
If you were to call either myAnimalArrayList   .remove("Bat") or
myAnimalArrayList   .remove(1), then the array should   look   like   this:
"Ant" 
"Cow" 
null 
null 
null 
null 
null 
null 
Because   the   number   of elements   (2)   is   now   less   than   or   equal   to   25%   of the    length   of the   array   (8),   the   array   should   be   cut   in   half,   and   should   then   look   like   this:
"Ant" 
"Cow" 
null 
null 
That   is,   the   elements   should   stay   the   same,   but   the   underlying   array   should   now   have   a   length of   4   instead   of   8.
2.2.5 set(index, value) method 
You   MUST   implement   the   set(index,    value) method as   follows:
1.   This   method   MUST   take   in   two   arguments:
(a)    index,   an   integer,   AND
(b)   value,   a   value   of   the   parameterized   type   (from   your   Java   Generics   implementation)
2.   This   method   MUST   replace   the   existing   element   in   the   underlying   array   at   that   index   with the   new   value.
3.   The   return   value   MUST   be   the   old   value   (that   is,   the   element   that   was   replaced).
4.   If   the   index   is   out   of   range, this   method   MUST   throw   an   IndexOutOfBoundsException.
5.    As   an   example,   assume   the   underlying   array   for   myOtherAnimalArrayList   contained   these   values   in   this   order:
"Cat" 
"Dog" 
"Banana" 
"Aardvark" 
null 
null 
If   you   were   to   call   myOtherAnimalArrayList   .set(1,    "Monkey"),   then   the   array   should   look   like   this:
"Cat" 
"Monkey" 
"Banana" 
"Aardvark" 
null 
null 
And   the   method   should   return   "Dog"   since   that   is   what   was   replaced.
2.2.6          indexOf method 
You   MUST   implement the   indexOf   method   as   follows:1.   This method   MUST take   an object of the   parameterized   type   as   the   single   input   parameter.
2.    This   method   takes   an   object   and   returns   the   index   of   the   first   occurrence   of   the   specified   element   in   this   list,   or   -1   if this   list   does   not   contain   the   element.
2.2.7 Create Constructor 
You MUST   create   a   constructor   to   initialize   the   underlying   array   as   follows:
1.   This   method   MUST   take   a   single   argument:   an   array   of the   parameterized   type   (from   you
Java   Generics   implementation).
2.   If   the   argument   is   null   OR   non-null   with   length   zero,   then   this   constructor   MUST   behave   exactly   the   same   as   the   default   constructor   (the   default   constructor   being   the   con-   structor   that   takes   no   arguments).
3.    Otherwise,   this   constructor   MUST   do   the   following:
(a)   set the MyArrayList   .size field to be equal to the   length of the input array, AND
(b)   ensure   the   length   of the   MyArrayList   underlying   array   is   either   the   length   of the   input   array   OR   the   value   of   INITIAL_CAPACITY,   whichever   is   greater.
4.   The   object   returned   by   this   constructor   MUST   be   distinct   from   the   input   array.   That   is,
(a)   a   call that modifies MyArrayList   MUST   NOT   modify the   input   array.   (b)   a   call that modifies the   input   array   MUST   NOT   modify   MyArrayList
5.    As   an   example,   consider   the   following   code:
// create an array of Strings  with    three    elements 
String[] data =    {"cat", "dog",    "elephant"} 
// construct a new MyArrayList called list , // using the data array as input 
MyArrayList list = new MyArrayList<>(data); 
// modify the    contents 
data[1] = "bat"; 
list .set(0, "mouse"); 
The   contents   of   data would   be   initialized to:
"cat" 
"dog" 
"elephant" 
while the   contents   of   list’s   underlying   array would   be:
"cat" 
"dog" 
"elephant" 
null 
Note   that   the   underlying   array   in   list has a length of   four, because INITIAL_CAPACITY   had   the   larger   value   at   the   time   of construction.
After   running   the   two   lines   that   modify   the   contents, the   contents   of   data   would   be   modified to:
"cat" 
"bat" 
"elephant" 
while the   contents   of   list’s   underlying   array would   be:
"mouse" 
"dog" 
"elephant" 
null 
3 Submission 
3.1          Pre-submission Check 
Before   you   submit,   please   double   check   that   you   followed   all   the   instructions,   especially   the   items   in   the Structure   and   Compiling   section   above. 
3.2 Gradescope Submission 
1.    When   you   are   ready   to   submit   the   assignment,   go   to   the   Module      1   Programming   Assignment Submission   item   and   click   the   button   to   go   to   the   Gradescope   platform.
2.    Once   you      are   logged   into   Gradescope,   locate      the      assignment      name      you      would      like      to   submit.   This should   be   the   first   thing   that   appears   in   the   Dashboard.
3.    Upload   your   solution   and   any   JUnit   test   files   via file upload or   a private   GitHub   repo.   Please   pay   attention to preserve the file structure   as presented   in   the   starter   code   given.
4.    When   you      are   sure   you   are   ready   to   submit,    confirm      at   the   prompt.
5.    You    will   see   quite   a   bit   of   output    after   a   while    (which    can   be   at   most   a   few   minutes),   even if   all   the   tests   pass.      At   the   bottom   of   the   output, starting    at   "Autograder   Results"   you   will see the   number   of   successful and   failed   test   cases.
6.    If   you      want      to      update   your      code      and      resubmit,    for      example      if   you      did   not   pass      all      of   the tests,   simply   edit   your      code      and      submit.
4          Grading 
4.1 Grading Overview 
1.    There is no   peer   review   for   this   assignment.    You will   not   be   marked   on   code   style.    However,   we   do   expect   you   to   use   best   practices   (comments,   indentation,   etc),   especially   if you   want   to   review   with   a   TA.
2.    There may be   hidden tests.   You   will   be   able   to   see   the   name   of each   test,   if it   passed   or   failed, and   the   associated   point   value.
3.    Failed   tests   will   have   brief feedback   about   the   specifics   of the   failure.
4.    We   will   not   provide   the   exact   test   cases.
5.   You have unlimited submissions,   until the   due   date   of the   assignment   as   noted   in   Canvas   (or   your   approved   extension).
6.    The   score   at   the   due   date   is   final.   Scores   will   sync   to   Canvas   relatively   immediately.
4.2 Rubric Items 
This    assignment   will   be   marked   on    6   main   rubric   items.       You    will    be    marked    based    on    how   successfully   your   implementation   meets   these   requirements.
• Java Generics :    10   points   spread   across   10   test   cases
• remove method :    12   points   spread   across   5   test   cases
• Shrink Array :   6   points   spread   across   2   test   cases
• set(index,    value) method :   7 points   spread   across   5 test   cases
• indexOf method :   5   points   spread   across   5   test   cases
• Create Constructor :    10   points   spread   across   5   test   cases
Total :   50   points



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
