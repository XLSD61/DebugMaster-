# 📜 DebugMaster Usage Examples 🚀

This is a comprehensive guide to **DebugMaster**, demonstrating advanced logging, in-game feedback, real-time variable monitoring, and settings configuration for Unity.

---

# 📘 Integration Guide — Adding DebugMaster to Your Unity Project

This guide explains how to integrate **DebugMaster** into your scripts for runtime text animation and effects.

---

## **🧩 Step 1 — Import the DebugMaster Toolkit**

Before using any DebugMaster feature, ensure the **DebugMaster** package is imported into your Unity project.  
It should be located under:


---

## **📚 Step 2 — Add the Namespace**

To access all TextMaster features and effects inside your C# scripts,  
include the following namespace at the top of your file:

```csharp
using DebugMasterTool;
```

---

## **🌟 CORE CONSOLE LOGS**

### Basic Logs with Color and Style

| Code Example | Description | Expected Console Output |
| :--- | :--- | :--- |
| `DebugMaster.Log("Game started", LogColor.Cyan, LogStyle.Bold);` | Base log, Cyan, **Bold** | 🟦 `[LOG] Game started (Cyan, Bold)` |
| `DebugMaster.LogWarning("Low memory detected", LogColor.Yellow, LogStyle.Italic);` | Warning, Yellow, *Italic* | 🟨 `[WARNING] Low memory detected (Yellow, Italic)` |
| `DebugMaster.LogError("Critical failure", LogColor.Red, LogStyle.BoldItalic);` | Error, Red, **Bold-Italic** | 🟥 `[ERROR] Critical failure (Red, BoldItalic)` |

---

### Simple Logs (No Style)

| Code Example | Description | Expected Console Output |
| :--- | :--- | :--- |
| `DebugMaster.Log("Plain log message");` | Normal log | `[LOG] Plain log message` |
| `DebugMaster.LogWarning("Simple warning");` | Warning log | `[WARNING] Simple warning` |
| `DebugMaster.LogError("Simple error");` | Error log | `[ERROR] Simple error` |

---

### Tagged Logs

| Code Example | Description | Expected Console Output |
| :--- | :--- | :--- |
| `DebugMaster.Log(LogTag.Combat, "Hit landed", LogStyle.Bold);` | Tagged log with style | `[COMBAT] Hit landed (Bold)` |
| `DebugMaster.Log("[AI]", "#Navigation", "Target acquired");` | Multiple string tags | `[AI][#Navigation] Target acquired` |
| `DebugMaster.Log(LogTag.UI, LogColor.Yellow, "Button clicked");` | Override color by tag | `[UI] Button clicked (Yellow)` |
| `DebugMaster.Log(LogTag.Network, "@Backend", "Auth success in", 123, "ms");` | Mixed usage | `[NETWORK@Backend] Auth success in 123 ms` |

---

### Warnings & Errors with Tags

| Code Example | Description | Expected Console Output |
| :--- | :--- | :--- |
| `DebugMaster.LogWarning(LogTag.Performance, "Spike detected!");` | Tagged warning | ⚠️ `[PERFORMANCE] Spike detected!` |
| `DebugMaster.LogError("[Data]", "Save failed:", "UserId=", 1213121312);` | Tagged error | ❌ `[DATA] Save failed: UserId=1213121312` |

---

## **🧩 FEED SYSTEM (Floating Messages)**

### Basic Feeds

| Code Example | Anchor | Example On-Screen Output |
| :--- | :--- | :--- |
| `DebugMaster.Feed("Player spawned1", LogColor.Green);` | Bottom Center (default) | 🟩 Player spawned1 |
| `DebugMaster.Feed("Player spawned2", LogColor.Red);` | Bottom Center | 🟥 Player spawned2 |
| `DebugMaster.Feed("Player ", LogColor.Blue);` | Bottom Center | 🟦 Player |
| `DebugMaster.Feed("Player 3", LogColor.Yellow);` | Bottom Center | 🟨 Player 3 |

### Feed Anchors

| Code Example | Anchor | Example On-Screen Output |
| :--- | :--- | :--- |
| `DebugMaster.Feed("Enemy 1 Spawn", LogColor.Blue, FeedAnchor.TopLeft);` | Top Left | 🟦 Enemy 1 Spawn |
| `DebugMaster.Feed("Enemy 2 Spawn", LogColor.Yellow, FeedAnchor.TopLeft);` | Top Left | 🟨 Enemy 2 Spawn |
| `DebugMaster.Feed("Scene Loaded ", LogColor.Cyan, FeedAnchor.MiddleCenter);` | Middle Center | 🟦 Scene Loaded |
| `DebugMaster.Feed("Player Die", LogColor.White, FeedAnchor.MiddleCenter);` | Middle Center | ⚪ Player Die |

---

## **🧠 DEBUG HUD (Live Variables)**

### Static HUD

| Code Example | Description | Expected HUD Output |
| :--- | :--- | :--- |
| `DebugMaster.DebugHUD(("HP", 100), ("Score", 5420), ("State", "Idle"));` | Show values on HUD | HP: 100<br>Score: 5420<br>State: Idle |

### Real-time HUD

| Code Example | Description | Expected HUD Output |
| :--- | :--- | :--- |
| `DebugMaster.DebugHUD(("HP", 100), ("Score", Time.time), ("State", "Idle"));` | Updates continuously | HP: 100<br>Score: 42.15<br>State: Idle |

---

## **🎨 STYLE & COLOR COMBINATIONS**

### Color Only

| Code Example | Output |
| :--- | :--- |
| `DebugMaster.Log("Normal Log: Player joined the lobby. ID = 1 Ping = 32f");` | 🟦 `[LOG] Normal Log: Player joined the lobby. ID = 1 Ping = 32.0` |
| `DebugMaster.Log("Red Log: Connection timeout detected. Retries = 3 Delay = 2.5f", LogColor.Red);` | 🟥 `[LOG] Red Log: Connection timeout detected. Retries = 3 Delay = 2.5 (Red)` |
| `DebugMaster.Log("Blue Log: Fetching leaderboard data... Rank = 12 Score = 1420f", LogColor.Blue);` | 🟦 `[LOG] Blue Log: Fetching leaderboard data... Rank = 12 Score = 1420.0 (Blue)` |
| `DebugMaster.Log("Green Log: Player HP restored. Amount = 25 Time = 10.2f", LogColor.Green);` | 🟩 `[LOG] Green Log: Player HP restored. Amount = 25 Time = 10.2 (Green)` |
| `DebugMaster.Log("Magenta Log: Achievement unlocked! Code = 101 Reward = 50f", LogColor.Magenta);` | 🟪 `[LOG] Magenta Log: Achievement unlocked! Code = 101 Reward = 50.0 (Magenta)` |
| `DebugMaster.Log("Yellow Log: Loading assets... Progress = 87% Time = 4.3f", LogColor.Yellow);` | 🟨 `[LOG] Yellow Log: Loading assets... Progress = 87% Time = 4.3 (Yellow)` |
| `DebugMaster.Log("Cyan Log: Session initialized successfully. PlayerID = 5 Latency = 15.7f", LogColor.Cyan);` | 🟦 `[LOG] Cyan Log: Session initialized successfully. PlayerID = 5 Latency = 15.7 (Cyan)` |

### Color + Style

| Code Example | Output |
| :--- | :--- |
| `DebugMaster.Log("Bold Log: Player leveled up! Level = 2 XP = 350f", LogColor.Red, LogStyle.Bold);` | 🟥 `[LOG] Bold Log: Player leveled up! Level = 2 XP = 350.0 (Red, Bold)` |
| `DebugMaster.Log("Italic Log: Quest in progress. Step = 3 Distance = 42.5f", LogColor.Green, LogStyle.Italic);` | 🟩 `[LOG] Italic Log: Quest in progress. Step = 3 Distance = 42.5 (Green, Italic)` |
| `DebugMaster.Log("Strikethrough Log: Deprecated API used. Version = 1 Delay = 0.8f", LogColor.Blue, LogStyle.Strikethrough);` | 🟦 `[LOG] Strikethrough Log: Deprecated API used. Version = 1 Delay = 0.8 (Blue, Strikethrough)` |
| `DebugMaster.Log("Underline Log: UI Element hovered. ElementID = 45 Duration = 1.2f", LogColor.Magenta, LogStyle.Underline);` | 🟪 `[LOG] Underline Log: UI Element hovered. ElementID = 45 Duration = 1.2 (Magenta, Underline)` |
| `DebugMaster.Log("BoldItalic Log: Critical event triggered! Code = 9001 Time = 5.6f", LogColor.Cyan, LogStyle.BoldItalic);` | 🟦 `[LOG] BoldItalic Log: Critical event triggered! Code = 9001 Time = 5.6 (Cyan, BoldItalic)` |

---

## **⚙️ SETTINGS USAGE**

**Location:** `Assets/Resources/DebugMasterSettings.asset`  

| Property | Description | Default |
| :--- | :--- | :--- |
| `useTagColors` | If true, colorize by first tag when no explicit color is provided | `true` |
| `includeCallerInfo` | Prefix logs with caller info (Class:Line) | `true` |
| `includeFrameCount` | Include Unity frame count in prefix | `false` |
| `wrapTagsWithBrackets` | Wrap tags in `[TAG]` format | `true` |
| `callerFormat` | Format tokens for caller info | `"{class}:{line}"` |
| `timestampFormat` | Timestamp format when enabled | `"HH:mm:ss"` |
| `resourceAssetName` | Name used by `Resources.Load` for settings | `"DebugMasterSettings"` |
| `isVisible` | Show Time Scale overlay slider/buttons | `false` |
| `playModeOnly` | Overlay visible only in Play Mode | `false` |

### Example Usage:

```csharp
// Load settings automatically
var settings = Resources.Load<DebugMasterSettings>("DebugMasterSettings");

// Access properties
Debug.Log(settings.useTagColors);       // true
Debug.Log(settings.includeCallerInfo);  // true
Debug.Log(settings.timestampFormat);    // "HH:mm:ss"
