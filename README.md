Here's a simple `README.md` file for the PowerShell "keep-alive" script that toggles Scroll Lock to prevent system idle:

---

````markdown
# Keep-Alive Script (PowerShell)

This PowerShell script is designed to prevent your Windows system from going idle, locking, or triggering the screensaver by simulating periodic keyboard activity using the **Scroll Lock** key.

## 📋 Description

The script uses the `WScript.Shell` COM object to send **Scroll Lock** keypresses every 4 minutes. This simulates user presence and keeps your session active.

## ⚙️ How It Works

- Clears the console screen.
- Prints a status message: `"Keep alive w/ scroll lock…"`.
- Creates a shell object to send keyboard inputs.
- Enters an infinite loop where it:
  - Sends a `{SCROLLLOCK}` key press.
  - Waits 100 milliseconds.
  - Sends another `{SCROLLLOCK}` key press to revert the state.
  - Waits 240 seconds (4 minutes).
- Repeats this process indefinitely until stopped.

## 💻 Script

```powershell
Clear-Host

Echo "Keep alive w/ scroll lock..."

$WShell = New-Object -com "Wscript.Shell"

while ($true)
{
    $WShell.sendkeys("{SCROLLLOCK}")
    Start-Sleep -Milliseconds 100
    $WShell.sendkeys("{SCROLLLOCK}")
    Start-Sleep -Seconds 240
}
````

## 🛠 Requirements

* Windows OS
* PowerShell (default on most Windows systems)

## 🚀 How to Run

1. Open PowerShell as Administrator.
2. Paste the script into the terminal or save it as a `.ps1` file and run:

```powershell
.\keep_alive.ps1
```

3. To stop the script, press `Ctrl + C`.

## ⚠️ Disclaimer

This script is intended for **personal and ethical use only**. Please make sure to follow your organization's policies. Using this to bypass corporate security policies (e.g., auto-lock) may be considered a violation.

## 📄 License

This project is open source and free to use under the MIT License.

```

---

Let me know if you'd like to include author information, logging, or additional features in the script or README.
```
