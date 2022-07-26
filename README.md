#In this there are two types of project codes which are in AIML and another one is in python.

#Both the two files are two different kind of chatbots which runs in different languages.


#For running the python chatbot just follow the below steps:

## Setup

Requires python3 (but porting this minimal script to python 2 is very easy)


    pip3 install python-aiml

Then just run

    ./chatbot.py

_____________________________________________________________________________________

#For running the AIML chatbot follow the below steps:

I personally suggesst pandorabots platform (website).

create an account in it and run the AIML_code.xml for the result.

______________________________________________________________________________________


#Contents
1 • Fundamentals 
2 • AIML Syntax 
3 • Chatbot training and demo 
4 • Conclusion 
5 • Further development 
6 • Pandorabots


#1. Fundamentals 
• What is a chatbot? 
▫ A chatbot (or bot) is a conversational software program designed to chat with humans via voice or text. 
▫ It is a natural language processing (NLP) chatbot designed to engage in a conversation by reacting to human input and responding as naturally as possible. 
▫ ALICE has won three times Loebner Prize winner (2000, 2001, 2004) - an award for accomplished humanoid and talking robots. 
▫ Turing test: a test for intelligence in a computer, requiring that a human being should be unable to distinguish the machine from another human being by using the replies to questions put to both. 
▫ Talk with ALICE: https://www.pandorabots.com/pandora/talk?botid=a847934aae3456cb 
• AIML stands for Artificial Intelligence Modelling Language. 
• AIML is a simple, XML-based scripting language and the open standard for writing chatbots.
• There are many script languages supporting writing a chatbot 
▫ AIML (1995) ▫ Façade (2005) 
▫ RiveScript (2009) 
▫ ChatScript (2010) 

• Why we use AIML? 
 Easy to learn and implement for beginners for its based on XML 
 Strong support interpreters with popular programming languages (Java, Python, Ruby …) 
 Various available platforms, AIML resources and documents for inheritance 


 • AIML interpreter ▫ a program that can load and run an AIML bot and provide responses to conversational requests according to the AIML specification in this document. 
▫ Program O is an AIML interpreter written in PHP 
▫ Program Y is an AIML interpreter written in Python 
▫ Program AB is an AIML interpreter written in Java (used in TIMA chatbot) 


• Chatbot using AIML workflow 8 User input to-text converter AIML Intepreter data text AIML dataset query Output match F T.

______________________________________________________________________________

#Create the Project Structure

	
1.c:/ab/bots

Stores AIML bots

2	
c:/ab/lib

Stores Java libraries

3	
c:/ab/out

Java class file directory

4	
c:/ab/run.bat

batch file for running Program AB

______________________________________________________________________________-

#create a directory test inside C > ab > bots and create the following directories in it.

1	
c:/ab/bots/test/aiml

Stores AIML files

2	
c:/ab/bots/test/aimlif

Stores AIMLIF files

3	
c:/ab/bots/test/config

Stores configuration files

4	
c:/ab/bots/test/sets

Stores AIML Sets

5	
c:/ab/bots/test/maps

Stores AIML Maps

___________________________________________________________________________________

#Create Source Files

<?xml version = "1.0" encoding = "UTF-8"?>
<aiml version="1.0.1" encoding = "UTF-8"?>
   <category>
      <pattern> HELLO ALICE </pattern>
      
      <template>
         Hello User
      </template>
      
   </category>
</aiml>

______________________________________________________________________________________

#Execute the Program

java -cp lib/Ab.jar Main bot = test action = chat trace = false

___________________________________________________________________________________

#Verify the Result
-----------------

Working Directory = C:\ab

Program AB 0.0.4.2 beta -- AI Foundation Reference AIML 2.0 implementation
bot = test
action = chat
trace = false
trace mode = false
Name = test Path = C:\ab/bots/test

C:\ab
C:\ab/bots
C:\ab/bots/test
C:\ab/bots/test/aiml
C:\ab/bots/test/aimlif
C:\ab/bots/test/config
C:\ab/bots/test/logs
C:\ab/bots/test/sets
C:\ab/bots/test/maps

Preprocessor: 0 norms 0 persons 0 person2
Get Properties: C:\ab/bots/test/config/properties.txt
addAIMLSets: C:\ab/bots/test/sets does not exist.
addCategories: C:\ab/bots/test/aiml does not exist.
AIML modified Tue Apr 07 22:24:29 IST 2015 AIMLIF modified Tue Apr 07 22:26:53 I
ST 2015
No deleted.aiml.csv file found
No deleted.aiml.csv file found
Loading AIML files from C:\ab/bots/test/aimlif

Reading Learnf file
Loaded 1 categories in 0.009 sec
--> Bot test 1 completed 0 deleted 0 unfinished
(1[6])--HELLO-->(1[5])--ALICE-->(1[4])--<THAT>-->(1[3])--*-->(1[2])--<TOPIC>-->(
1[1])--*-->(0[null,null]) Hello User...
7 nodes 6 singletons 1 leaves 0 shortcuts 0 n-ary 6 branches 0.85714287 average
branching
Human:

__________________________________________________________________________________


#Type Hello Alice and see the result and then type anything else to see the changed result.

Human: hello alice
Robot: Hello User
Human: bye
Robot: I have no answer for that.
Human:

_________________________________________________________________________________


#Basic tags 
__________
----------

<aiml> tag
----------
<aiml version = "1.0.1" encoding = "UTF-8"?>
   ...
</aiml>



#<category> tag
--------------
<category>
   <pattern> HELLO ALICE </pattern>
   
   <template>
      Hello User
   </template>
   
</category>



#<pattern> tag
-------------
<category>
   <pattern> HELLO ALICE </pattern>
   
   <template>
      Hello User
   </template>
   
</category>



#<template> tag
--------------
<category>
   <pattern> HELLO ALICE </pattern>
   
   <template>
      Hello User
   </template>
   
</category>

________________________________________________________________________________________


#AIML star.aiml
______________
--------------

#star.aiml
---------
<category>
   <pattern> A * is a *. </pattern>
   
   <template>
      When a <star index = "1"/> is not a <star index = "2"/>?
   </template>
   
</category>

_____________________________________________________________________________________


#AIML <srai> Tag
_______________
---------------

#<srai> Tag - Create categories
------------------------------
<category>
   <pattern>WHO IS ALBERT EINSTEIN?</pattern>
   <template>Albert Einstein was a German physicist.</template>
</category>

<category>
   <pattern> WHO IS Isaac NEWTON? </pattern>
   <template>Isaac Newton was a English physicist and mathematician.</template>
</category>


#<srai> Tag - Create generic category using <srai> tag
-----------------------------------------------------
<category>
   <pattern>DO YOU KNOW WHO * IS?</pattern>
   
   <template>
      <srai>WHO IS <star/></srai>
   </template>
   
</category>

_______________________________________________________________________________________


#AIML <random> Tag
_________________
-----------------

#<random> Tag
------------
<random>
   <li> pattern1 </li>
   <li> pattern2 </li>
   ...
   <li> patternN </li>
</random>

#Example for <random> Tag
------------------------
<?xml version = "1.0" encoding = "UTF-8"?>
<aiml version = "1.0.1" encoding ="UTF-8"?>
   <category>
      <pattern>HI</pattern>
      
      <template>
         <random>
            <li> Hello! </li>
            <li> Hi! Nice to meet you! </li>
         </random>
      </template>
      
   <category>      
</aiml>

____________________________________________________________________________________


#AIML <set> tag
______________
--------------

#<set> tag
---------
<set name = "variable-name"> variable-value </set>


#<get> tag
---------
<get name = "variable-name"></get>


#Example fro setget.aiml
-----------------------
<?xml version = "1.0" encoding = "UTF-8"?>
<aiml version = "1.0.1" encoding = "UTF-8"?>
   <category>
      <pattern>I am *</pattern>
      <template>
         Hello <set name = "username"> <star/>! </set>
      </template>  
   </category>  
   
   <category>
      <pattern>Good Night</pattern>
      <template>
         Hi <get name = "username"/> Thanks for the conversation!
      </template>  
   </category>  


_____________________________________________________________________________________

#AIML - <condition> Tag
______________________
----------------------
<condition name = "variable-name" value = "variable-value"/>

#Example for <condition> tag
---------------------------
<?xml version = "1.0" encoding = "UTF-8"?>
<aiml version = "1.0.1" encoding = "UTF-8"?>
   <category>
      <pattern> HOW ARE YOU FEELING TODAY </pattern>
      
      <template>
         <think><set name = "state"> happy</set></think>
         <condition name = "state" value = "happy">
            I am happy!
         </condition>
         
         <condition name = "state" value = "sad">
            I am sad!
         </condition>
      </template>
      
   </category>
</aiml>

_______________________________________________________________________________________

#AIML - <think> Tag
__________________
------------------

#<think> Tag
-----------
<think>
<set name = "variable-name"> variable-value </set>
</think>

Example for <think> Tag
-----------------------
<?xml version = "1.0" encoding = "UTF-8"?>
<aiml version = "1.0.1" encoding = "UTF-8"?>
   <category>
      <pattern>My name is *</pattern>
      <template>
         Hello!<think><set name = "username"> <star/></set></think>
      </template>  
   </category>  
   
   <category>
      <pattern>Byeee</pattern>
      <template>
         Hi <get name = "username"/> Thanks for the conversation!
      </template>  
   </category>  
   
</aiml>

_____________________________________________________________________________________


#OUR CODE FOR RESTAURANTS CHATBOT :-
-----------------------------------
-----------------------------------

    <category>
      <pattern>HELLO</pattern>
      <template>
          <random>
            <li> Hello 😍 <split/>can i know your name please?</li>
            <li> Hi there! 😍 <split/>can i know your name please? </li>
            <li> Hola 😍 <split/>can i know your name please?</li>
            <li> Hey 😍 <split/>can i know your name please?</li>
            <li> Hi 😍 <split/>can i know your name please?</li>
          </random>
      </template>
    </category>
    
    <category>
      <pattern>How are you</pattern>
      <template>
          <random>
              <li> iam fine <split/>How are you?😍 </li>
              <li> i will be always fine <split/>How about you?😍 </li>
              <li> Thanks for asking ! iam fine. <split/>how about you? 😍 </li>
          </random>
      </template>
    </category>
    
    <category>
          <pattern>I am *</pattern>
          <template>
            Hello <set name = "username"> <star/>!</set>
          </template>
    </category>
    
    <category>
          <pattern>call me *</pattern>
          <template>
            Hello <set name = "username"> <star/>!</set>
          </template>
    </category>
    
    <category>
        <pattern>yeah fine</pattern>
        <template>ok😃.<split/> Are you feeling hungry?</template>
    </category>
    
    <category>
        <pattern>fine</pattern>
        <template>ok😃. <split/>Are you feeling hungry?</template>
    </category>
     
     <category>
        <pattern>yeah</pattern>
        <template>ok.<split/> what do you want ?</template>
     </category>
     
     <category>
        <pattern>ok</pattern>
        <template>Hmm</template>
     </category>
     
     <category>
        <pattern>nope</pattern>
        <template>ok</template>
     </category>
     
     <category>
        <pattern>thanks</pattern>
        <template>My pleasure!</template>
     </category>
     
     <category>
        <pattern>thank you</pattern>
        <template>My pleasure!</template>
     </category>
     
     <category>
        <pattern>thankyou</pattern>
        <template>My pleasure!</template>
     </category>
     
     <category>
        <pattern>yep</pattern>
        <template>Hmm</template>
     </category>
     
     <category>
        <pattern>yes</pattern>
        <template>ok. what do you want ?</template>
     </category>
     
     <category>
      <pattern>What about drinks</pattern>
      <template>we also delevery <set name = "topic">drinks</set></template>  
     </category>
   
         <topic name = "drinks">
     <category>
         <pattern>nice</pattern>
         <template>would you like to have something in drinks.</template>
      </category>
      
      <category>
         <pattern> yes </pattern>
         <template>we provide cool drinks, hot drinks and also we provide soups.</template>
      </category>
      
      <category>
        <pattern>drinks menu</pattern>
        <template> 
	        <think><set name="menu"><star/></set></think>
	        Here is the menu. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to view menu</text>
	            <url>https://workflowy.com/#/e017e1ab80d9<star/></url> 
	        </button> 
	    </template>
     </category>
          </topic>
          
     <category>
      <pattern>* pizza</pattern>
      <template><split/>sorry, we don't have that pizza<split/>recomended to view menu
          <button> 
	            <text>Click here to view menu</text>
	            <url>https://workflowy.com/#/5e715ca29f33<star/></url> 
	        </button>
      </template>  
     </category>
   
        
      
     <category>
        <pattern>pizza menu</pattern>
        <template> 
	        <think><set name="menu"><star/></set></think>
	        Here is the menu. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to view menu</text>
	            <url>https://workflowy.com/#/5e715ca29f33<star/></url> 
	        </button> 
	    </template>
     </category>
          
          
     <category>
        <pattern>pizza</pattern>
        <template> 
	        <think><set name="it"><star/></set></think>
	        Here is menu of pizza <formal><star/></formal>. 
	        <button> 
	            <text>Click here</text>
	            <url>https://workflowy.com/#/5e715ca29f33<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>drinks</pattern>
        <template> 
	        <think><set name="it"><star/></set></think>
	        Here is menu of drinks <formal><star/></formal>. 
	        <button> 
	            <text>Click here</text>
	            <url>https://workflowy.com/#/e017e1ab80d9<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>what is your name</pattern>
        <template>💓iam pinky .<split/>iam here to help you💓.</template>
     </category>
     
     <category>
        <pattern>no</pattern>
        <template>ok.</template>
     </category>
     
     <category>
        <pattern>what can you do for me</pattern>
        <template>i can help you out to purchase your pizza.</template>
     </category>
     
      <category>
        <pattern>hi pinky </pattern>
        <template>
          <random>
            <li> Hello 😍 <get name = "username"/></li>
            <li> Hi there! 😍 <get name = "username"/></li>
            <li> Hola 😍 <get name = "username"/></li>
            <li> Hey 😍 <get name = "username"/></li>
            <li> Hi 😍 <get name = "username"/></li>
          </random>
        </template>
     </category>
     
     <category>
        <pattern>hi pinky </pattern>
        <template>
          <random>
            <li> Hello 😍 <get name = "username"/></li>
            <li> Hi there! 😍 <get name = "username"/></li>
            <li> Hola 😍 <get name = "username"/></li>
            <li> Hey 😍 <get name = "username"/></li>
            <li> Hi 😍 <get name = "username"/></li>
          </random>
        </template>
     </category>
     
     <category>
        <pattern>menu</pattern>
        <template>  <split/>Neapolitan Pizza(300/-).
                    <split/>Chicago Pizza(350/-).
                    <split/>New York Style Pizza(400/-).
                    <split/>Sicilian Pizza(450/-).
                    <split/>Greek Pizza(200/-).
                    <split/>California Pizza(300/-).
                    <split/>Detroit Pizza(350/-).
                    <split/>St. Louis Pizza(200/-).
                    <split/>chilly pizza(250/-)10% off😍.</template>
     </category>
     
  <category>
      <pattern>HI</pattern>
      <template><srai>HELLO</srai></template>
  </category>
     
   
    <category>
	    <pattern> TELL ME ABOUT *</pattern>
	    <template> 
	        <think><set name="it"><star/></set></think>
	        Here is some information about <formal><star/></formal>. 
	        <button> 
	            <text>Click here</text>
	            <url>https://en.wikipedia.org/wiki/Pizza_Hut<star/></url> 
	        </button> 
	    </template> 
	</category>
	 
	 <category>
        <pattern>what items do you have in pizzas</pattern>
        <template><split/>we have Neapolitan Pizza(300/-).
                             <split/>Chicago Pizza(350/-).
                      <split/>New York Style Pizza(400/-).
                            <split/>Sicilian Pizza(450/-).
                               <split/>Greek Pizza(200/-).
                          <split/>California Pizza(300/-).
                             <split/>Detroit Pizza(350/-).
                           <split/>St. Louis Pizza(200/-).
                      <split/>chillie pizza(250/-)10% off😍.
        </template>
     </category>
     
     <category>
        <pattern>pizza menu</pattern>
        <template> 
	        <think><set name="menu"><star/></set></think>
	        Here is the menu. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to view menu</text>
	            <url>https://workflowy.com/#/5e715ca29f33<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>can i get a pizza menu</pattern>
        <template> 
	        <think><set name="menu"><star/></set></think>
	        Here is the menu. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to view menu</text>
	            <url>https://workflowy.com/#/5e715ca29f33<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>can i have a pizza menu</pattern>
        <template> 
	        <think><set name="menu"><star/></set></think>
	        Here is the menu. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to view menu</text>
	            <url>https://workflowy.com/#/5e715ca29f33<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>can i get a pizza menu </pattern>
        <template> 
	        <think><set name="menu"><star/></set></think>
	        Here is the menu. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to view menu</text>
	            <url>https://workflowy.com/#/5e715ca29f33<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>What is the cost of chilly pizza</pattern>
        <template>ON 10% DISCOUNT , YOU WILL GET IT FOR RS /-200.</template>
     </category>
     
     <category>
        <pattern>i want a chilly pizza</pattern>
        <template> 
	        <think><set name="chillie pizza"><star/></set></think>
	        ON 10% DISCOUNT, YOU WILL GET IT FOR RS /-200. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>chilly pizza</pattern>
        <template> 
	        <think><set name="chillie pizza"><star/></set></think>
	        ON 10% DISCOUNT , YOU WILL GET IT FOR RS /-200. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Cost of chilly pizza</pattern>
        <template>ON 10% DISCOUNT, YOU WILL GET IT FOR RS /-200.</template>
     </category>

     <category>
        <pattern>What is the cost of Neapolitan Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (300/-) 😋.</template>
     </category>
     
     <category>
        <pattern>i want a Neapolitan Pizza</pattern>
        <template> 
	        <think><set name="Neapolitan Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (300/-)😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern> Neapolitan Pizza</pattern>
        <template> 
	        <think><set name="Neapolitan Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (300/-)😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Cost of Neapolitan Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (300/-) 😋.</template>
     </category>
     
     <category>
        <pattern>Cost of Chicago Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (350/-) 😋.</template>
     </category>
     
     <category>
        <pattern>i want a Chicago Pizza</pattern>
        <template> 
	        <think><set name="Chicago Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (350/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Chicago Pizza</pattern>
        <template> 
	        <think><set name="Chicago Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (350/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>What is the cost of Chicago Pizza </pattern>
        <template>YOU WILL GET IT FOR RS (350/-) 😋.</template>
     </category>
     
     <category>
        <pattern>What is the Cost of California Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (300/-) 😋.</template>
     </category>
     
     <category>
        <pattern>i want a California Pizza</pattern>
        <template> 
	        <think><set name="California Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (300/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>California Pizza</pattern>
        <template> 
	        <think><set name="California Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (300/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Cost of California Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (300/-) 😋.</template>
     </category>
     
     <category>
        <pattern>What is the cost of New York Pizza </pattern>
        <template>YOU WILL GET IT FOR RS (400/-) 😋.</template>
     </category>
     
     <category>
        <pattern>i want a New York Pizza</pattern>
        <template> 
	        <think><set name="New York Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (400/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>New York Pizza</pattern>
        <template> 
	        <think><set name="New York Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (400/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Cost of New York Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (400/-) 😋.</template>
     </category>
     
     <category>
        <pattern>What is the cost of Sicilian Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (450/-) 😋.</template>
     </category>
     
     <category>
        <pattern>i want a Sicilian Pizza</pattern>
         <template> 
	        <think><set name="Sicilian Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (450/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Sicilian Pizza</pattern>
         <template> 
	        <think><set name="Sicilian Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (450/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Cost of Sicilian Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (450/-) 😋.</template>
     </category>
     
     <category>
        <pattern>What is the cost of Greek Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (200/-) 😋.</template>
     </category>
     
     <category>
        <pattern>i want a Greek Pizza</pattern>
         <template> 
	        <think><set name="Greek Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (200/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Greek Pizza</pattern>
         <template> 
	        <think><set name="Greek Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (200/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     <category>
        <pattern>Cost of Greek Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (200/-) 😋.</template>
     </category>
     
     <category>
        <pattern>What is the cost of Detroit Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (350/-) 😋.</template>
     </category>
     
     <category>
        <pattern>i want a Detroit Pizza</pattern>
         <template> 
	        <think><set name="Detroit Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (350/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Detroit Pizza</pattern>
         <template> 
	        <think><set name="Detroit Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (350/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Cost of Detroit Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (350/-) 😋.</template>
     </category>
     
     <category>
        <pattern>What is the cost of St Louis Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (200/-) 😋.</template>
     </category>
     
     <category>
        <pattern>i want a St Louis Pizza</pattern>
         <template> 
	        <think><set name="St Louis Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (200/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>St Louis Pizza</pattern>
         <template> 
	        <think><set name="St Louis Pizza"><star/></set></think>
	        YOU WILL GET IT FOR RS (200/-) 😋. <formal><star/></formal>. 
	        <button> 
	            <text>Click here to order</text>
	            <url>https://pizzaonline.dominos.co.in/<star/></url> 
	        </button> 
	    </template>
     </category>
     
     <category>
        <pattern>Cost of St Louis Pizza</pattern>
        <template>YOU WILL GET IT FOR RS (200/-) 😋.</template>
     </category>
     
     <category>
         <pattern>*</pattern>
         <template>
            <random>
            <li>I don't understand.</li>
            <li>Can you say that in a different way?</li>
            </random>
         </template>
     </category>
     
     <category>
         <pattern>What is your age</pattern>
         <template>sir vishnu has just programmed me a couple of days ago and iam not elder than you 😂. </template>
    
     </category>
     
     <category>
         <pattern>MY NAME IS *</pattern>
         <template>HELLO <star index="1"/>.Welcome to vishnu's pizza, iam here to help you.</template>
    
     </category>
     
     <category>
      <pattern> What are you </pattern>
      <template>
         I am a bot and iam here to help you.
      </template>
     </category>
     
     <category>
      <pattern>i want to buy a * pizza</pattern>
      <template><split/>sorry, we don't have that pizza<split/>recomended to view menu
          <button> 
	            <text>Click here to view menu</text>
	            <url>https://workflowy.com/#/5e715ca29f33<star/></url> 
	        </button>
      </template>  
     </category>
     
     <category>
      <pattern>i want to buy a pizza</pattern>
      <template><split/>ok<split/>recomended to view menu
          <button> 
	            <text>Click here to view menu</text>
	            <url>https://workflowy.com/#/5e715ca29f33<star/></url> 
	        </button>
      </template>  
     </category>
     
     <category>
        <pattern>any discount</pattern>
        <template>ofcourse, today we have 10% discount on chilly pizza and pay through paytm to get 5% cashback </template>
     </category>
     
     <category>
        <pattern>can i get any discount</pattern>
        <template>ofcourse, today we have 10% discount on chilly pizza and pay through paytm to get 5% cashback</template>
     </category>
     
     <category>
        <pattern>discount</pattern>
        <template>ofcourse, today we have 10% discount on chilly pizza and pay through paytm to get 5% cashback</template>
     </category>
     
     <category>
      <pattern> who are you </pattern>
      <template>
         I am a bot and iam here to help you.
      </template>
     </category>
     
     <category>
          <pattern>Good Night</pattern>
          <template>
            Hi <get name = "username"/> Good night.<split/>Thanks for the conversation!
          </template>
     </category>
     
     <category>
          <pattern>i love you</pattern>
          <template>
            i love you too <get name = "username"/>
          </template>
     </category>
     
     <category>
      <pattern> How are you feeling today </pattern>
      
      <template>
         <think><set name = "state"> happy</set></think>
         <condition name = "state" value = "happy">
            I am happy!
         </condition>
         
         <condition name = "state" value = "sad">
            I am sad!
         </condition>
      </template>
      
     </category>
     
     <category>
          <pattern>bye</pattern>
          <template>
            Bye <get name = "username"/><split/> Thanks for the conversation💓💓💓!<split/> Hope we meet soon again.
          </template>
     </category>
     
     <category>
          <pattern>miss you</pattern>
          <template>
            miss you too <get name = "username"/><split/> Thanks for the conversation💓💓💓!<split/> Hope we meet soon again.
          </template>
     </category>



_____________________________________________________________________________________________________________

#6.  Pandorabots
---------------
---------------

For the better experience use Pandorabots , before create an account using mail .

create directories and write down the code as you want with the help of above explanations.

Run the code , so that it pop-up a chat bot.

you can communicate there .

_______________________________________________________________________________________________________________