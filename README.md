# reaction-timer
reaction timer game from scratch using everything that learnt abut Vue.js so far - props, events, data, methods, etc. about lifecycle methods too.
this game is all about how speedy you can click that appearing box after some delay, it will show your speed and will provide rank according your socre.

## Project setup
To Setup the Vue CLI (Command Line Interface) Project 
First: Dowanload Node.js from https://nodejs.org/en/download/package-manager
Open Terminal to Check to ansure the version : node -v

Now install vue cli : npm install -g @vue/cli
To ensure the version : vue --version

Now After Installation, create New Project : vue create reaction-timer //here your project name
cd into your Project Folder, to Open that project into VS code : code .

### Compiles

Use this command to run the server : npm run serve
Able to see Landing page of vue
Remove Hello world component and related code
in this project 
App.vue - will have 2 components [Block, Results]

### Functionalities
First we have to create 2 files under components
In App.vue we are conna set template for our Reaction Timer Game
Main Functionality is -  Check if player is playing or not ,
                         if yes : then after playing "Play Now" Button one Block should be appear after some rand delay
                         here, we are setting rand delay using Math.random() and meanwhile of this delay, we are showing one loading gif to let customer know that he/she has to wait 
                         but loading gif should disapeear before the block so we are adjusting total delay and make it disapeer before 300ms
                         after customer click to the block, it should come up with the results (ranking) based on the score (speed of the clicking) 
                         Please checkout the code flow on repo and output ss attached below for more understanding.

### OUTPUT : 

![Screenshot 2024-10-10 151525](https://github.com/user-attachments/assets/804e951f-5ecd-41da-aff4-cf9f26cd665f)
![Screenshot 2024-10-10 151436](https://github.com/user-attachments/assets/ac49e831-7f21-47b8-99e4-5064320b5337)
![Screenshot 2024-10-10 151419](https://github.com/user-attachments/assets/abc053b4-02bf-49dc-b1de-c571cf348fde)
![Screenshot 2024-10-10 151455](https://github.com/user-attachments/assets/6392d716-29b8-47d9-91e9-c93731bd8a3e)
![Screenshot 2024-10-10 151512](https://github.com/user-attachments/assets/d615eecd-c325-4dbd-8528-c21712f78cc4)
