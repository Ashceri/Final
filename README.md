# Final
var currentScene = 0;

//Emily's Variables
var ballx = 198;
var bally = 198;
var player1X = 389;//x and y of player 1s paddle
var player1Y= 170;
var player2X = 0;
var player2Y= 170;
var speedX = round(random(-5, 5));//speed of ball is random 
var speedY = round(random(-5, 5));
var keys= [];
var keyPressed = function(){// will help make the paddles move when the key is pressed
    keys[keyCode] = true;
};
var keyReleased = function(){//will make the paddles stop moving once I relase the key
    keys[keyCode] = false;
};
var upkey = UP;
var downkey = DOWN;
var Wkey = 87;//used javascript key code chart to find out the number assignment of the key W is 87
var Skey = 83;//used javascript key code

var player1Score=0;
var player2Score=0;





//button
var drawSPButton = function(){
    fill(255,16,250);
    rect(81, 235, 191, 46, 10);
    fill(5, 5, 5);
    textSize(21);
    text("Single Player", 174, 260);
};
var drawMButton = function(){
    fill(255,16,250);
    rect(81, 297, 191, 46, 10);
    fill(5, 5, 5);
    textSize(21);
    text("Multiplayer", 174, 318);
};
var drawMStartButton = function(){
    fill(255,16,250);
    rect(94, 349, 191, 46, 10);
    fill(5, 5, 5);
    textSize(21);
    text("Start Game", 190, 373);
};

//bitmojiEm
var drawBitmojiA = function(bitmojiObject) { 
    noStroke();
    
fill(79, 60, 26);
    ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*10),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*33),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);//bottom layer of hair
    ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*13),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*32),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
    ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*23),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*15),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
    ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*27),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*15),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
    ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*27),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
    ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*33),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
    ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*32),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*24),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
    ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*37),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*24),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
    ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*35),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*48),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
    ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*40),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*48),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
     ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*4),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*48),bitmojiObject.bitmojiHeight/150*45,bitmojiObject.bitmojiHeight/150*45);
fill(247, 226, 163);
rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*16),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*46),bitmojiObject.bitmojiHeight/150*25,bitmojiObject.bitmojiHeight/150*46,bitmojiObject.bitmojiHeight/150*4);//neck
    fill(247, 226, 163);
ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*4),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*5),bitmojiObject.bitmojiHeight/150*68,bitmojiObject.bitmojiHeight/150*100);//head
fill(79, 60, 26);
 ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*9),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*40),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20);//top layer of hair
 ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*7),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*40),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20);
 ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*22),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*28),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20);
 ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*25),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*31),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20);
 ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*33),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*16),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20);
 ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*38),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*16),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20);
 ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*46),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*2),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20);
 ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*38),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*4),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20);
 fill(3, 3, 3);
 rect(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*9),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*62),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);//shirt
 fill(bitmojiObject.shirtColor);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*35),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*62),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*2),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*80),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*24),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*80),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*12),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*90),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*20),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*62),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*14);
 rect(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*19),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*80),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*46),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*63),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*45),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*80),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*2);
 rect(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*19),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*93),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*1),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*93),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*17),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*93),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*13),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*93),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*33),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*93),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*45),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*93),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 rect(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*31),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*79),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*5);
 
fill(51, 140, 15);
ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*19), bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*3),bitmojiObject.bitmojiHeight/150*10,bitmojiObject.bitmojiHeight/150*8);//left eye
ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*10),bitmojiObject.bitmojiY-3,bitmojiObject.bitmojiHeight/150*10,bitmojiObject.bitmojiHeight/150*8);//right eye
fill(3, 3, 3);
ellipse(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*19), bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*3),bitmojiObject.bitmojiHeight/150*-3,bitmojiObject.bitmojiHeight/150*5);//left pupil
ellipse(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*10),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*3),bitmojiObject.bitmojiHeight/150*-3,bitmojiObject.bitmojiHeight/150*5);//right pupil
fill(247, 226, 163);//nose
arc(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*6), bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*9), bitmojiObject.bitmojiHeight/150*16, bitmojiObject.bitmojiHeight/150*12, bitmojiObject.bitmojiHeight/150*-73, bitmojiObject.bitmojiHeight/150*88);
fill(247, 153, 153);
arc(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*6),bitmojiObject.bitmojiY+(bitmojiObject.bitmojiHeight/150*24),bitmojiObject.bitmojiHeight/150*34,bitmojiObject.bitmojiHeight/150*11,-20,212);//mouth
fill(102, 52, 16);
arc(bitmojiObject.bitmojiX+(bitmojiObject.bitmojiHeight/150*11),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*12),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*10,-166,-1);//eyebrowsR
arc(bitmojiObject.bitmojiX-(bitmojiObject.bitmojiHeight/150*20),bitmojiObject.bitmojiY-(bitmojiObject.bitmojiHeight/150*12),bitmojiObject.bitmojiHeight/150*20,bitmojiObject.bitmojiHeight/150*10,-162,-1);//eyebrowL
fill(247, 226, 163);
};


//bitmojiash
var drawBitmojiB = function (x,y,h)
{
  

//neck
fill(198, 136, 99);
rect(x-10,y+41,23,24);

//face
fill(198, 136, 99);
ellipse(x,y,77,88);

//eyes
fill(56,16, 28);
ellipse(x-17, y-9, 20, 20);
ellipse(x+15, y-9, 20, 20);

//hair
fill(23, 17, 03);
ellipse(x-38,y-19,20,20);
ellipse(x-35,y-31,20,20);
ellipse(x-24,y-37,20,20);
ellipse(x-9,y-43,20,20);
ellipse(x+8,y-44,20,20);
ellipse(x+23,y-37,20,20);
ellipse(x+37,y-25,20,20);
ellipse(x-43,y-4,20,20);
ellipse(x-43,y+8,20,20);
ellipse(x-39,y+21,20,20);
ellipse(x-36,y+32,20,20);
ellipse(x-46,y+34,20,20);
ellipse(x-29,y+46,20,20);
ellipse(x-46,y+48,20,20);
ellipse(x+37,y+34,20,20);
ellipse(x+42,y-10,20,20);
ellipse(x+42,y+4,20,20);
ellipse(x+38,y+19,20,20);
ellipse(x+36,y+44,20,20);
ellipse(x+51,y+45,20,20);
ellipse(x+52,y+34,20,20);
ellipse(x+54,y+19,20,20);
ellipse(x+52,y+3,20,20);
ellipse(x+51,y-9,20,20);
ellipse(x+52,y-25,20,20);
ellipse(x+39,y-41,20,20);
ellipse(x+49,y-33,20,20);
ellipse(x+29,y-47,20,20);
ellipse(x+19,y-51,20,20);
ellipse(x+6,y-54,20,20);
ellipse(x-8,y-48,20,20);
ellipse(x-20,y-47,20,20);
ellipse(x-31,y-47,20,20);
ellipse(x-42,y-38,20,20);
ellipse(x-45,y-23,20,20);
ellipse(x-49,y+8,20,20);
ellipse(x-47,y+21,20,20);
ellipse(x-50,y-10,20,20);

//lips
fill(130, 0, 0);
arc(x,y+24,30,15,18,218);

//nose
line(x+12,y+12,x-2,y+3);
line(x+10,y+13,x-4,y+13);

//body
fill(255, 189, 242);
quad(x+48, y+89, x+49, y+56, x-46, y+56, x-47, y+87);

fill(0, 0, 0);
text("ACV", x-11, y+66, 257, 15); 


 };



 
 //intro screen
var introScreen = function() {
    fill(0, 0, 0);
    rect(0, 0, 400, 400);
    //bitmojiem
    drawBitmojiA({	
bitmojiX:66,
bitmojiY:49,
bitmojiHeight:120,
shirtColor:color(252, 237, 70)});
    //bitmojiash
    drawBitmojiB(300, 50, 100);
    textSize(40);
    fill(255, 255, 255);
    textAlign(CENTER, CENTER);
    text("Air Hockey", 200, 160);
    drawSPButton();
    drawMButton();
};

//Emily's Code
var instructions = function(){
    currentScene = 1;
    background(0, 0, 0);
    textSize(30);
    fill(255,16,250);
    text("INSTRUCTIONS", 193, 67);
    textSize(20);
    text("Player 1 (Right) use Up and Down arrows", 193, 120);
    text("Player 2 (Left) use W and S arrows", 193, 150);
    drawMStartButton();
};
var MultiHockeyTable = function(){
    currentScene = 2;
    //background 
    strokeWeight(5);
stroke(255,16,250);
background(0, 0, 0);
line(363, 55, 36, 55);
line(38, 356, 37, 55);
line(363, 356, 363, 55);
line(363, 356, 38, 356);
fill(0, 0, 0);
ellipse(400, 200, 140, 140);
ellipse(1, 201, 140, 140);
line(200, 357, 199, 56);
ellipse(200, 200, 130, 130);
//paddles
rect(player2X, player2Y, 10, 50);
rect(player1X, player1Y, 10, 50);
//ball
ellipse(ballx, bally, 10, 10);
//score
textSize(30);
fill(247, 242, 242);
text(player1Score, 358, 206);
text(player2Score, 15, 206);

if(keys[upkey]){
   player1Y -= 4; //makes the paddle move up 4 pixles per sec
}
if(keys[downkey]){
    player1Y += 4;//makes the paddle move down 4 pixles per sec
}
if(keys[Wkey]){
    player2Y -= 4;//moves up 4 pixels per sec
}
if(keys[Skey]){
    player2Y += 4;//moves down 4 pixels per sec
}

ballx += speedX; //assigns a speed to the ball
bally +=speedX;

if(bally >400 || bally < 0){//ball reads when it hits the top and bottom wall and bounces off
    speedY = -speedY;
}
if(ballx < 10 && bally > player2Y && bally < (player2Y +100)){//reads when the ball hits the peramiters of player 2 paddle even if the paddle moves and bounces off
    speedX = -speedX;
}
if(ballx > 380 && bally > player1Y && bally < (player1Y + 100) && ballx < 390){//reads when the ball hits the player 1s paddle and bounces off
    speedX = -speedX;
}
if(ballx < 0){//gives player 1 a point when player 1 scores
    player1Score += 1;
    ballx = 195;
    bally = 195;
    speedX = round(random(-5,5));
    speedY = round(random(-5,5));
}
if (ballx > 400){//gives player 2 a point when player 2 scores
    player2Score += 1;
    ballx = 195;
    bally = 195;
    speedX = round(random(-5,5));
    speedY = round(random(-5,5));
}
};
draw = function() {//makes sure that the ball and paddles move by drawing it every second
     if (currentScene ===2){
    MultiHockeyTable();
}
};



//Ashleys Code
    var hockeyTableSP =function(){
        //varibales
var user= width/2;
var compUser = width/2;
var userScore = 0;
var compUserScore = 0;
var ball;
var gameStarted = false;
var t = 0;
var pauseTime = 60;
var playerSpeed = 3;
var ballSpeed = 2.5;
var paddleHeight = 40;
var paddleWidth = 35;

//ball funtion
var Ball = function(position, speed) {
    this.position = position;
    this.speed = speed || ballSpeed;
    
    this.radius = 12;
    
    this.resetVelocity = function() {
        this.theta = random(0, 360);
        this.velocity = new PVector(
        this.speed*cos(this.theta), -this.speed*sin(this.theta));
        compUser = width/2;
    };
    this.resetVelocity();
    
    this.draw = function() {
        fill(255, 255, 255);
        noStroke();
        ellipse(this.position.x, this.position.y,
        this.radius*2, this.radius*2);
    };
    
    this.collideWithPaddle = function(x, y) {
        if (this.position.x - this.radius < x + paddleWidth/2 &&
        this.position.x + this.radius > x - paddleWidth/2) {
            if (dist(0, this.position.y, 0, y) <
            paddleHeight/2 + this.radius) {
                if (this.position.x > x) {
                    this.position.x = x + 
                    this.radius + paddleWidth/2;
                }
                else if (this.position.x < x) {
                    this.position.x = x - 
                    this.radius - paddleWidth/2;
                }
                this.velocity.mult(new PVector(-1, 1));
            }
        }
    };
    
    this.update = function() {
        //ball hits the wall
        if (this.position.x < 0) {
            compUserScore++;
            this.position = new PVector(width/2, height/2);
            gameStarted = false;
            this.resetVelocity();
        }
        else if (this.position.x > width) {
            userScore++;
            this.position = new PVector(width/2, height/2);
            gameStarted = false;
            this.resetVelocity();
        }
        if (this.position.y < 0) {
            this.position.y = 0;
            this.velocity.mult(new PVector(1, -1));
        }
        else if (this.position.y > height) {
            this.position.y = height;
            this.velocity.mult(new PVector(1, -1));
        }
        
        //ball hits paddle
        this.collideWithPaddle(20, user);
        this.collideWithPaddle(width-20, compUser);
        
        this.position.add(this.velocity);
    };
};

ball = new Ball(new PVector(width/2, height/2));

var drawScores = function() {
    var s;
    
    fill(255, 255, 255);
    textSize(20);
    
    s = "You: " + userScore;
    text(s, width*0.25-textWidth(s)/2, 25);
    s = "Player 2: " + compUserScore;
    text(s, width*0.75-textWidth(s)/2, 25);
};

var updatePlayer2 = function() {
    if (abs(compUser-ball.position.y) < playerSpeed){
        compUser = ball.position.y;
    }
    else if (compUser-ball.position.y >= playerSpeed) {
        compUser -= playerSpeed;
    }
    else if (compUser-ball.position.y <= playerSpeed) {
        compUser += playerSpeed;
    }
    
};

//Move the player up
var movePlayerUp = function() {
    user -= playerSpeed;
};

//Move the player down
var movePlayerDown = function() {
    user += playerSpeed;
};

var drawPlayers = function() {
     user = constrain(user, 0, 400);
    
    
    rectMode(CENTER);
    fill(255, 255, 255);
    rect(20, user, paddleWidth, paddleHeight);
    rect(width-20, compUser, paddleWidth, paddleHeight);
};

draw = function() {
    //User key controls
    if(keyIsPressed) {
    if(keyCode === UP) {
        movePlayerUp();
    }
    else if (keyCode === DOWN) {
        movePlayerDown();
    }
}

//background screen
strokeWeight(5);
stroke(255,16,250);
background(0, 0, 0);
line(363, 55, 36, 55);
line(38, 356, 37, 55);
line(363, 356, 363, 55);
line(363, 356, 38, 356);
fill(0, 0, 0);
ellipse(400, 200, 140, 140);
ellipse(1, 201, 140, 140);
line(200, 357, 199, 56);
ellipse(200, 200, 130, 130);

    updatePlayer2();
    drawPlayers();
    drawScores();
    
    //ball
    ball.draw();
    
    if (!gameStarted) {
        t++;
        if (t >= pauseTime) {
            t = 0;
            gameStarted = true;
        }
        return;
    }
    
    ball.update();
};

        
};


    
var mouseClicked = function ()
{
    if 
        (mouseX >= 81 && mouseX <=272 && mouseY>= 235 && mouseY <=281)
        {hockeyTableSP();}
    if
    (mouseX>= 81 && mouseX <= 272 && mouseY >=297 && mouseY <=343)
    {instructions();}
    if
    (mouseX >=94 && mouseX <=285 && mouseY >= 349 && mouseY <=395)
    {MultiHockeyTable();}
};
introScreen();

 
    
    
    

 
 
