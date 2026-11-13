# 3D Online Chess

<img width="800" height="450" alt="1" src="https://github.com/user-attachments/assets/cd8afc53-0d14-47c0-b82f-994505f8bd1c" />
<img width="800" height="450" alt="2" src="https://github.com/user-attachments/assets/f61b219e-b6b2-4518-8f16-898ff383c645" />

### Real-time 3D multiplayer chess in the browser. Create a room, share it with a friend, and play.

[Live Demo](https://3d-online-chess.vercel.app/)
## Screenshots
### Authentication/Registration
<img width="1919" height="954" alt="image" src="https://github.com/user-attachments/assets/6f9eff74-f280-41c4-9158-66e02868907f" />

### Menu
<img width="1919" height="990" alt="image" src="https://github.com/user-attachments/assets/ba61729b-0050-4518-96de-b90e77d788c3" />

### Profile
<img width="1919" height="990" alt="image" src="https://github.com/user-attachments/assets/f9c169bb-005c-4949-b135-61090c38c192" />

### Lobby(Room) Settings
<img width="1919" height="990" alt="image" src="https://github.com/user-attachments/assets/b0b4ca53-4c27-43a3-ac23-f190c83ed32c" />

### Lobby
<img width="1917" height="988" alt="image" src="https://github.com/user-attachments/assets/c77b7f2a-3de5-47cf-a33a-62a3a73d6c84" />

## Features
- Interactive 3D chessboard: click a piece, then click a square to move
- Free camera: rotate the board by dragging, zoom with the scroll wheel
- Built-in 2D board view (top right corner) for when you prefer a classic layout
- Real-time multiplayer: create a room and share the code with a friend to play together
- User accounts with registration and login, secured by JWT access and refresh tokens
- Full chess rules with server-side move validation, so illegal moves are rejected
- User accounts persisted in MongoDB

## How to Play
1. Register or log in.
2. Click **Casual -> Create**
3. Customize your lobby settings, then click **Done**
4. Share the room code with a friend.
4. Your friend clicks **Casual -> Join**, enters the code to join.
5. When both players press **Ready** The countdown will start, and then the game will begin.
6. Click a piece, then click a square to move. Drag with the left mouse button to rotate the board, and scroll to zoom.

## Tech Stack
**Frontend:** HTML/CSS/JS, Vite, Three.js <br>
**Backend:** Node.js, Express, Socket.IO <br>
**Database:** MongoDB Atlas <br>
**Auth:** JWT (access + refresh tokens) <br>
**Hosting:** Vercel (frontend), Render(backend)

## How It Works
The server is the source of truth. When a player moves or captures a piece, the client sends the move to the server through an API request. The server checks it against the current game state in database and the rules of chess, and rejects it if it's illegal. This is used to prevent client-side modifications to the game so the user can't cheat.

Once a move is accepted, the server updates the game and uses Socket.IO (WebSocket) to push the new position to both players in the room, making each board render properly for each player

## Getting Started

### Prerequisites
- Node.js 22+ (v22.19.0)
- A MongoDB Atlas cluster (or local MongoDB)

### Installation
1. Clone the repo
   `git clone https://github.com/Yoribob/3D-Online-Chess.git`
2. Install dependencies in both folders
   `npm install`
3. Copy the env files and fill in your values
   `cp .env.example .env`
4. From the root folder, run:
   `npm run dev:backend`
   `npm run dev:frontend`

## Future Improvements
- Profile icons save on cloud instead of being stored locally
- UI improvement towards more hand-drawn style
- Ranked system

## AI Usage
AI tools were used during development for:
- Parts of the menu UI (mainly buttons and the lobby screen)
- Debugging during late-stage development, mainly deployment
- The black hole design in the 3D scene

The architecture, the rest of the 3D scene (board, pieces, camera), game logic, and backend were designed and implemented by me.


## License
This project is licensed under CC BY-NC-SA 4.0. See [LICENSE](LICENSE) for details.
