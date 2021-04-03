Well, let us cut to the chase and let’s start coding!
First, this is a simple command line application. We start by prompting the user to send a message.<br>
message = input('Human: ')<br>
Then we need to create a method or a function to send a reply. We will call this function getReply(). We will pass the message as a parameter for this function because the response of our application will depend on the user’s message.<br>
def getReply(message):<br>
    print('Bot: ' + message)<br>
This function just sends back whatever message the user entered. Don’t worry, we can do better. This is where the nested if-else statements will come in handy. The idea is, the application will look for some keywords and send a reply depending on our if-else statements. Let’s make our getReply function a little better.<br>
def getReply(message):<br>
    if 'who' in message and 'you' in message:<br>
        reply = "Hi, I'm Chandler."<br>
    else:<br>
        reply = "Blah blah blah"<br>
    print('Bot: ' + reply)<br>
Now our chatbot has some identity. My chatbot is based on my favorite Friends character Chandler Bing. He’s funny and so I want my chatbot to be funny. Back to our function, yes this is a little bit better than before. The application will look for the words who and you in the message. If both words appear in the message, let’s say the message is who are you?, the chatbot will introduce himself otherwise blah blah blah. Now, let’s make it more interesting.<br>
I will create a list named jokes.<br>
jokes = ["Alright! I took the quiz and it turns out I do put career over men.",
         "Yes, on a scale of one to 10, 10 being the dumbest a person can look, you are definitely 19",
         "I'm not great at advice. Can I interest you with a sarcastic comment?",
         "Ok, you have to stop the Q-tip when there's resistance!",
         "What do you know? You're a door. You only like knock knock jokes.",
         "Until I was 25, I thought that the only response to 'I love you' was 'Oh, crap!'"]<br>
(Well, Medium kinda’ messed up the formatting.)<br>
I want ChanBot (Chandler Bot, I didn’t really have to explain that, right?) to randomly select from the jokes list whenever the word joke appears in the user’s message. To do this, we need to make our if-else statement a little bit more complicated. Let’s make an if-else-if statement.<br>
def getReply(message):<br>
    if 'who' in message and 'you' in message:<br>
        reply = "Hello, I'm Chandler.<br>
    elif 'joke' in message:<br>
        reply = random.choice(jokes)<br>
    else:<br>
        reply = "Blah blah blah"<br>
    print('Bot: ' + reply)<br>
random.choice(jokes) tells our application to randomly select an item from the list jokes.<br>
Note: Do not forget to import random on top of our code.<br>
import random<br>
...<br>
Well that’s pretty much it but there’s one more thing missing. We want to have a long conversation so let’s put our code around a while loop so we can keep talking to ChanBot as long as we don’t say bye.<br>
while ('bye' not in message):<br>
    message = input('Human: ')<br>
    getReply(message)<br>
Here’s the complete code:<br>
import random<br>
jokes = ["Alright! I took the quiz and it turns out I do put career over men.",
         "Yes, on a scale of one to 10, 10 being the dumbest a person can look, you are definitely 19",
         "I'm not great at advice. Can I interest you with a sarcastic comment?",
         "Ok, you have to stop the Q-tip when there's resistance!",
         "What do you know? You're a door. You only like knock knock jokes.",
         "Until I was 25, I thought that the only response to 'I love you' was 'Oh, crap!'"]<br>
def getReply(message):<br>
    if 'who' in message and 'you' in message:<br>
        reply = "Hello, I'm Chandler."<br>
    elif 'joke' in message:<br>
        reply = random.choice(jokes)<br>
    else:<br>
        reply = "Blah blah blah"<br>
    print('Bot: ' + reply)<br>
while ('bye' not in message):<br>
    message = input('Human: ')<br>
    getReply(message)<br>
That’s it! Our very simple chatbot application. You can make it more interesting by putting more if-else statements. The more complicated the decision tree the better!
