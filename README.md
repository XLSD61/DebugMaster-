📜 DebugMaster Usage Examples
===============================

Basic Logs
-----------
DebugMaster.Log("Game started", LogColor.Cyan, LogStyle.Bold);
DebugMaster.LogWarning("Low memory detected", LogColor.Yellow, LogStyle.Italic);
DebugMaster.LogError("Critical failure", LogColor.Red, LogStyle.BoldItalic);

Output:
[LOG] Game started (Cyan, Bold)
[WARNING] Low memory detected (Yellow, Italic)
[ERROR] Critical failure (Red, BoldItalic)

Simple Logs (no style)
-----------------------
DebugMaster.Log("Plain log message");
DebugMaster.LogWarning("Simple warning");
DebugMaster.LogError("Simple error");

Output:
[LOG] Plain log message
[WARNING] Simple warning
[ERROR] Simple error

Tagged Log
-----------
DebugMaster.Log(LogTag.Combat, "Hit landed", LogStyle.Bold);

Output:
[COMBAT] Hit landed (Bold)

Multiple String Tags
---------------------
DebugMaster.Log("[AI]", "#Navigation", "Target acquired");

Output:
[AI][#Navigation] Target acquired

Override Color by Tag
----------------------
DebugMaster.Log(LogTag.UI, LogColor.Yellow, "Button clicked");

Output:
[UI] Button clicked (Yellow)

Mixed Usage
------------
DebugMaster.Log(LogTag.Network, "@Backend", "Auth success in", 123, "ms");

Output:
[NETWORK@Backend] Auth success in 123 ms

Warnings & Errors with Tags
----------------------------
DebugMaster.LogWarning(LogTag.Performance, "Spike detected!");
DebugMaster.LogError("[Data]", "Save failed:", "UserId=", 1213121312);

Output:
⚠️ [PERFORMANCE] Spike detected!
❌ [DATA] Save failed: UserId=1213121312

🧩 Feed System (Floating Messages)
==============================

DebugMaster.Feed("Player spawned1", LogColor.Green);
DebugMaster.Feed("Player spawned2", LogColor.Red);
DebugMaster.Feed("Player ", LogColor.Blue);
DebugMaster.Feed("Player 3", LogColor.Yellow);

Output (on screen):
🟩 Player spawned1 — bottom center  
🟥 Player spawned2 — bottom center  
🟦 Player — bottom center  
🟨 Player 3 — bottom center

Feed Anchors
-------------
DebugMaster.Feed("Enemy 1 Spawn", LogColor.Blue, FeedAnchor.TopLeft);
DebugMaster.Feed("Enemy 2 Spawn", LogColor.Yellow, FeedAnchor.TopLeft);
DebugMaster.Feed("Scene Loaded ", LogColor.Cyan, FeedAnchor.MiddleCenter);
DebugMaster.Feed("Player Die", LogColor.White, FeedAnchor.MiddleCenter);

Output (on screen):
🟦 Enemy 1 Spawn — top left  
🟨 Enemy 2 Spawn — top left  
🟦 Scene Loaded — middle center  
⚪ Player Die — middle center

🧠 Debug HUD (Live Variables)
==============================

DebugMaster.DebugHUD(("HP", 100), ("Score", 5420), ("State", "Idle"));

Output (HUD Panel):
HP: 100  
Score: 5420  
State: Idle

Real-time HUD Update
---------------------
DebugMaster.DebugHUD(("HP", 100), ("Score", Time.time), ("State", "Idle"));

Output (updates continuously):
HP: 100  
Score: 42.15  
State: Idle

🎨 Style & Color Combinations
==============================

DebugMaster.Log("Normal Log: Player joined the lobby. ID = " + 1 + " Ping = " + 32f);
---------------------
DebugMaster.Log("Red Log: Connection timeout detected. Retries = " + 3 + " Delay = " + 2.5f, LogColor.Red);
---------------------
DebugMaster.Log("Blue Log: Fetching leaderboard data... Rank = " + 12 + " Score = " + 1420f, LogColor.Blue);
---------------------
DebugMaster.Log("Green Log: Player HP restored. Amount = " + 25 + " Time = " + 10.2f, LogColor.Green);
---------------------
DebugMaster.Log("Magenta Log: Achievement unlocked! Code = " + 101 + " Reward = " + 50f, LogColor.Magenta);
---------------------
DebugMaster.Log("Yellow Log: Loading assets... Progress = " + 87 + "% Time = " + 4.3f, LogColor.Yellow);
---------------------
DebugMaster.Log("Cyan Log: Session initialized successfully. PlayerID = " + 5 + " Latency = " + 15.7f, LogColor.Cyan);
---------------------
DebugMaster.Log("Bold Log: Player leveled up! Level = " + 2 + " XP = " + 350f, LogColor.Red, LogStyle.Bold);
---------------------
DebugMaster.Log("Italic Log: Quest in progress. Step = " + 3 + " Distance = " + 42.5f, LogColor.Green, LogStyle.Italic);
---------------------
DebugMaster.Log("Strikethrough Log: Deprecated API used. Version = " + 1 + " Delay = " + 0.8f, LogColor.Blue, LogStyle.Strikethrough);
---------------------
DebugMaster.Log("Underline Log: UI Element hovered. ElementID = " + 45 + " Duration = " + 1.2f, LogColor.Magenta, LogStyle.Underline);
---------------------
DebugMaster.Log("BoldItalic Log: Critical event triggered! Code = " + 9001 + " Time = " + 5.6f, LogColor.Cyan, LogStyle.BoldItalic);
---------------------
Output:
[LOG] Normal Log: Player joined the lobby. ID = 1 Ping = 32.0  
[LOG] Red Log: Connection timeout detected. Retries = 3 Delay = 2.5 (Red)  
[LOG] Blue Log: Fetching leaderboard data... Rank = 12 Score = 1420.0 (Blue)  
[LOG] Green Log: Player HP restored. Amount = 25 Time = 10.2 (Green)  
[LOG] Magenta Log: Achievement unlocked! Code = 101 Reward = 50.0 (Magenta)  
[LOG] Yellow Log: Loading assets... Progress = 87% Time = 4.3 (Yellow)  
[LOG] Cyan Log: Session initialized successfully. PlayerID = 5 Latency = 15.7 (Cyan)  

[LOG] Bold Log: Player leveled up! Level = 2 XP = 350.0 (Red, Bold)  
[LOG] Italic Log: Quest in progress. Step = 3 Distance = 42.5 (Green, Italic)  
[LOG] Strikethrough Log: Deprecated API used. Version = 1 Delay = 0.8 (Blue, Strikethrough)  
[LOG] Underline Log: UI Element hovered. ElementID = 45 Duration = 1.2 (Magenta, Underline)  
[LOG] BoldItalic Log: Critical event triggered! Code = 9001 Time = 5.6 (Cyan, BoldItalic)
