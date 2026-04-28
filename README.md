<div align="center">

![TicTacToe XO Banner](https://placehold.co/900x200/1a1a2e/ffffff?text=TicTacToe+Project&font=montserrat)

# ❌ TicTacToe Project ⭕

### A full-featured Tic-Tac-Toe platform - AI opponent (Complex Algorithm), local multiplayer, and real-time online play, built across three years as a final matriculation project

![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![C#](https://img.shields.io/badge/C%23-Backend-239120?style=for-the-badge&logo=csharp&logoColor=white)
![ASP.NET](https://img.shields.io/badge/ASP.NET-Web_Framework-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-Realtime_DB-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![Visual Studio](https://img.shields.io/badge/Visual_Studio-IDE-5C2D91?style=for-the-badge&logo=visualstudio&logoColor=white)

</div>

---

## 📖 Table of Contents

- [Tech Stack](#-tech-stack)
- [Key Features](#-key-features)
- [Getting Started](#-getting-started)
- [Usage](#-usage)
- [Architecture](#-architecture)

---

## 🛠 Tech Stack

| Layer | Technology | Version |
|-------|-----------|---------|
| Frontend Language | JavaScript | ES6+ |
| Backend Language | C# | - |
| Web Framework | ASP.NET | - |
| Realtime Database | Firebase Realtime Database | - |
| IDE | Visual Studio | 2019+ |

---

## ✨ Key Features

- **Three Distinct Game Modes** - Choose between playing against the AI, challenging a friend on the same machine, or competing against any opponent in real time across the internet.
- **AI Algorithm (vs PC Mode)** - Features a sophisticated decision-making algorithm that evaluates board states and selects optimal moves, providing a genuinely challenging single-player experience.
- **Real-Time Online Multiplayer** - The online mode uses Firebase Realtime Database to sync every move between two remote players instantly, with no page refresh required.
- **ASP.NET Web Interface** - The game is delivered as a fully functional web application built on ASP.NET, playable directly in any modern browser without additional client installs.
- **Object-Oriented Architecture** - The entire codebase is structured around OOP principles - encapsulation, inheritance, and polymorphism - keeping game logic modular and maintainable.
- **Clean Separation of Concerns** - Game logic, UI rendering, and data persistence are split across distinct layers so each can be understood and changed independently.
- **Dual-Language Implementation** - The project leverages C# on the server side for game rules and session management, and JavaScript on the client side for interactive board rendering and Firebase communication.
- **Three-Year Academic Evolution** - Designed and built from scratch across Grades 10–12 as a final Bagrut (Israeli matriculation) project, growing from basic board logic into a fully networked, multi-mode game system.

---

## 🚀 Getting Started

### Prerequisites

- [Visual Studio](https://visualstudio.microsoft.com/) (2019 or later) with the **ASP.NET and web development** workload installed
- [.NET Framework](https://dotnet.microsoft.com/en-us/download/dotnet-framework) matching the project's target version
- A [Firebase](https://firebase.google.com/) project with **Realtime Database** enabled (required for online mode)
- A modern web browser - Chrome, Edge, or Firefox

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/GuyGuyPeres/TicTacToeProject.git
cd TicTacToeProject
```

2. **Open the solution in Visual Studio**

   Double-click `TicTacToe.sln`, or use **File → Open → Project/Solution** from inside Visual Studio.

3. **Restore NuGet packages**

   Right-click the solution in Solution Explorer and select **Restore NuGet Packages**.

4. **Configure Firebase credentials**

   Locate the Firebase configuration block in the project (typically inside `Scripts/firebase.js` or `Web.config`) and replace the placeholder values with your own Firebase project credentials:

```env
FIREBASE_API_KEY=your_api_key_here
FIREBASE_AUTH_DOMAIN=your-project-id.firebaseapp.com
FIREBASE_DATABASE_URL=https://your-project-id.firebaseio.com
FIREBASE_PROJECT_ID=your-project-id
```

> ⚠️ Never commit your Firebase credentials to source control. Keep them local or use environment-level configuration.

<details>
<summary>🔧 <strong>Troubleshooting Common Issues</strong></summary>

- **Build fails - missing packages**: Right-click the solution → *Restore NuGet Packages*, then rebuild with **Ctrl+Shift+B**.
- **Firebase connection errors in online mode**: Verify that `FIREBASE_DATABASE_URL` ends in `.firebaseio.com` with no trailing slash, and that Realtime Database is enabled (not just Firestore) in your Firebase console.
- **Game board doesn't render**: Open browser DevTools (F12) and check the Console tab for JavaScript errors - most commonly caused by missing or incorrect Firebase credentials.
- **Online mode shows no opponent / moves don't sync**: Both players must be connected to the same Firebase project and joined to the same game session ID.
- **Page loads but shows a blank screen**: Ensure the ASP.NET application built successfully and that IIS Express started on the correct port.

</details>

### Run the App

Press **F5** in Visual Studio (or **Debug → Start Debugging**). The app will launch automatically in your default browser at:

```
http://localhost:<port>/
```

---

## 💡 Usage

The application presents a main menu on load where you pick your game mode. All three modes share the same board logic and win-detection algorithm.

### Game Modes Overview

| Mode | Players | Connection |
|------|---------|-----------|
| User vs PC | 1 | Local - no internet required |
| User vs User | 2 | Local - both players on the same machine |
| User vs User (Online) | 2 | Remote - synced via Firebase in real time |

---

### ❌ User vs PC

Select **Play vs Computer** from the main menu. Choose your symbol (X or O). The AI calculates its response immediately after each of your moves. Win, lose, or draw - the result is announced and you can restart.

---

### 👥 User vs User (Local)

Select **Play vs Friend**. Player 1 and Player 2 take turns clicking cells on the shared board. The game tracks whose turn it is, highlights the winner's line, and offers a rematch when the game ends.

---

### 🌐 User vs User (Online)

Select **Play Online**.

1. **Player 1** creates a new game session - a session code is generated and displayed.
2. **Player 2** opens the game in their own browser and enters the session code to join.
3. Both boards update in real time as each player makes their move via Firebase.

> A full step-by-step walkthrough (written in Hebrew) is available in the **User Manual** PDFs included in this repository.

---

## 🏗 Architecture

### Repository Contents

> ⚠️ Source code is not included in this repository. The files below are the documentation and user manuals for the project.

```text
📁 TicTacToeProject/
├── 📄 README.md                              # Project overview (this file)
├── 📄 Full Documention (NO SOURCE CODE).pdf  # Full technical documentation (Hebrew)
├── 📄 User Manual - USER VS PC.pdf           # Step-by-step guide for vs Computer mode (Hebrew)
├── 📄 User Manual - USER VS USER.pdf         # Step-by-step guide for local multiplayer (Hebrew)
├── 📄 User Manual - USER VS USER ONLINE.pdf  # Step-by-step guide for online multiplayer (Hebrew)
└── 📄 User Manual XO ASP.NET.pdf            # Step-by-step guide for the ASP.NET version (Hebrew)
```

### Request & Game Flow

```
Player clicks a cell
    → JavaScript (game.js) captures input & validates move
        → ASP.NET Controller (MVC route) receives the action
            → C# Game Model evaluates board state & win conditions
                │
                ├─── [vs PC] AI Engine selects response move
                │
                └─── [Online] Firebase Realtime DB syncs move
                         → Opponent's browser listener fires
                             → game.js updates opponent's board UI
                │
                └─── JSON response / Razor view refresh
                         → Board re-renders with updated state
                             → Win / draw announcement if game over
```

---

<div align="center">

Made with ☕, determination, and a whole lot of X's and O's - across three years of high school.

⭐ **If this project helped you, consider giving it a star!** ⭐

Built with 💻 by [CaptainPeres](https://github.com/GuyGuyPeres)

</div>
