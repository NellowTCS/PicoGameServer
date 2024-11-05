**Credits:**<br/>
https://community.element14.com/challenges-projects/project14/cheerusup/b/blog/posts/basic-html-games-hosted-on-the-raspberry-pi-pico<br/>
https://gist.github.com/straker/ff00b4b49669ad3dec890306d348adc4#other-basic-games<br/>
https://github.com/maxnet/pico-webserver/blob/main/fs/index.html 

# PicoGameServer
Run a USB game server on your Raspberry Pi Pico or Pico H to play games locally on your device.


## Games Included
### Asteroids
![Screenshot 2024-11-04 3 57 17 PM](https://github.com/user-attachments/assets/b707be87-9103-4ac0-8bcd-79bbb561c81c)
#### Controls
- Arrow keys and space to fire.<br/>
#### How to Play
- Navigate your spaceship around and destroy the asteroids to earn points.
- In this game space is a torus (https://en.wikipedia.org/wiki/Torus) so when you go through walls you appear on the opposite side.<br/>

### Classic Pong
![Screenshot 2024-11-04 3 57 45 PM](https://github.com/user-attachments/assets/c2270bad-fc07-4597-9310-cf52bf48f999)
#### Controls
- W for Up; S for Down in single-player.
- W for Up for Player 1 (right side); S for Down for Player 1 (left side) and Up Arrow for Up for Player 2 (right side); Down Arrow for Down for Player 2 (left side) in 2-player mode
- or Fingers.<br/>
#### How to Play
- If you don't know how to play this I am concerned.<br/>

### Flappy Box
![Screenshot 2024-11-04 3 58 02 PM](https://github.com/user-attachments/assets/22496a01-7387-4d5f-b33c-892b0cc0968a)
#### Controls
- Space to magically increase your altitude.<br/>
#### How to Play
- Don't hit the green pillars.<br/>

### Guess The Number
![Screenshot 2024-11-04 3 58 19 PM](https://github.com/user-attachments/assets/1abc4bcb-7ad2-4ffb-a2fe-717d25cf2404)
#### Controls
- keyboard/number pad
- or Fingers.<br/>
#### How to Play
- Type in a number from 1 to 10.<br/>

### Memory Game (Concentration)
![Screenshot 2024-11-04 4 00 33 PM](https://github.com/user-attachments/assets/9bc7c6bc-c1f5-4c55-b64f-4ca9bb7dedd8)
#### Controls
- Cursor/Finger.<br/>
#### How to Play
- Press cards to flip them over.
- Remember the flipped-over cards and flip over other cards.
- repeat until you find two cards with the same letter on them.
- repeat. <br/>

### Mini Pong
![Screenshot 2024-11-04 4 00 42 PM](https://github.com/user-attachments/assets/693de55f-4200-4223-aa5f-9a3e9a4ac0b0)
#### Controls
- Left and Right Arrow keys to move the paddle left and right
- or Fingers.<br/>
#### How to Play
- This is a bit like Breakout but without having to destroy blocks.<br/>

### Reaction Time
![Screenshot 2024-11-04 4 00 55 PM](https://github.com/user-attachments/assets/0ea9d553-52b6-4a9b-aeeb-107c0746f3ea)
#### Controls
- Cursor/Finger.<br/>
#### How to Play
- Press Start Game. When the Tap or Click Me! button becomes green, press it.<br/>

### Simon 
![Screenshot 2024-11-04 4 01 07 PM](https://github.com/user-attachments/assets/9e552857-f691-468c-a2e1-873ee6bfc862)
#### Controls
- Cursor/Finger.<br/>
#### How to Play
- Simon will flash 1 of 4 lights an amount of times. Press the same colored lights in the same order to get points.<br/>

### Simple Clicker
![Screenshot 2024-11-04 4 01 16 PM](https://github.com/user-attachments/assets/f535ea2f-1880-4e31-ae4b-ee39e3fadff3)
#### Controls
- Cursor/Finger.<br/>
#### How to Play
- Simon will flash 1 of 4 lights an amount of times. Press the same colored lights in the same order to get points.<br/>

### Tic Tac Toe
![Screenshot 2024-11-04 4 01 32 PM](https://github.com/user-attachments/assets/b265a2d2-2830-4ea2-af83-e04429063d53)
#### Controls
- Cursor/Finger.<br/>
#### How to Play
- Place Xs in order to get a three in a row before O does.<br/>

### Breakout
![Screenshot 2024-11-04 4 01 47 PM](https://github.com/user-attachments/assets/b1715c93-a78d-46f1-95c6-95b9285f6b9f)
#### Controls
- Left and Right Arrow keys to move the paddle left and right.<br/>
#### How to Play
- Bounce the ball into the bricks to break them.<br/>

### Frogger
![Screenshot 2024-11-04 4 01 58 PM](https://github.com/user-attachments/assets/41b902c4-5d61-43bf-ba4e-de9f78d84e19)
#### Controls
- Arrow keys to move.

#### How to Play
- Move the frog to the other side without getting hit by anything or sinking.<br/>

### Snake 
![Screenshot 2024-11-04 4 02 51 PM](https://github.com/user-attachments/assets/d9c4b3af-ecaf-44f6-a571-9954b85fead3)
#### Controls
- Arrow keys to move.
- or Fingers.<br/>
#### How to Play
- Red stuff is fruit and this snake likes fruit. This snake doesn't like walls, however. <br/>

### Sokoban
![Screenshot 2024-11-04 4 03 03 PM](https://github.com/user-attachments/assets/c737f52b-8299-458a-9d2b-ef3a907964e9)
#### Controls
- Arrow keys to move.
#### How to Play
- Cover all circles with boxes to win.<br/>

### Tetris
![Screenshot 2024-11-04 4 03 10 PM](https://github.com/user-attachments/assets/ff7eb0f1-816b-4c05-a126-d7b19fac65ae)
#### Controls
- Up Arrow to rotate the Tetriminos.
- Down Arrow to increase gravity to make it fall faster.
- Left and Right Arrows to move where the Tetriminos falls.
#### How to Play
- Fill a line with blocks to clear it. Clear all lines that you can.<br/>

## Build Instructions
### Build dependencies

On Debian:

```
sudo apt install git build-essential cmake gcc-arm-none-eabi
```

Your Linux distribution does need to provide a recent CMake (3.13+).
If not, compile [CMake from source](https://cmake.org/download/#latest) first.

### Build instructions

```
git clone --depth 1 https://github.com/NellowTCS/PicoGameServer
cd pico-webserver
git submodule update --init
mkdir -p build
cd build
cmake ..
make
```

Copy the resulting pico_webserver.uf2 file to the Pico mass storage device manually.<br/>
Webserver will be available at http://192.168.7.1/

Content it is serving is in /fs<br/>
If you change any files there, run ./regen-fsdata.sh

