===============================
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


==============================
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
DebugMaster.Feed("Player Die1", LogColor.Blue, FeedAnchor.TopLeft);
DebugMaster.Feed("Player Die2", LogColor.Yellow, FeedAnchor.TopLeft);
DebugMaster.Feed("Player Life2", LogColor.Cyan, FeedAnchor.MiddleCenter);
DebugMaster.Feed("Player Life3", LogColor.White, FeedAnchor.MiddleCenter);

Output (on screen):
🟦 Player Die1 — top left  
🟨 Player Die2 — top left  
🟦 Player Life2 — middle center  
⚪ Player Life3 — middle center


==============================
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


==============================
🎨 Style & Color Combinations
==============================

DebugMaster.Log("Test Bold", LogColor.Red, LogStyle.Bold);
DebugMaster.Log("Test Italic", LogColor.Green, LogStyle.Italic);
DebugMaster.Log("Test Strikethrough", LogColor.Blue, LogStyle.Strikethrough);
DebugMaster.Log("Test Underline", LogColor.Magenta, LogStyle.Underline);
DebugMaster.Log("Test BoldItalic", LogColor.Cyan, LogStyle.BoldItalic);

Output:
[LOG] Test Bold (Red, Bold)  
[LOG] Test Italic (Green, Italic)  
[LOG] Test Strikethrough (Blue, Strikethrough)  
[LOG] Test Underline (Magenta, Underline)  
[LOG] Test BoldItalic (Cyan, BoldItalic)
