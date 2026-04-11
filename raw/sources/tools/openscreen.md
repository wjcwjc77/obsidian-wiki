---
title: "siddharthvaddem/openscreen: Create stunning demos for free. Open-source, no subscriptions, no watermarks, and free for commercial use. An alternative to Screen Studio."
source: "https://github.com/siddharthvaddem/openscreen"
author:
published:
created: 2026-04-11
description: "Create stunning demos for free. Open-source, no subscriptions, no watermarks, and free for commercial use. An alternative to Screen Studio.  - siddharthvaddem/openscreen: Create stunning demos for free. Open-source, no subscriptions, no watermarks, and free for commercial use. An alternative to Screen Studio."
tags:
  - "tools"
---
## OpenScreen

**OpenScreen is your free, open-source alternative to Screen Studio (sort of).**

If you don't want to pay $29/month for Screen Studio but want a much simpler version that does what most people seem to need, making beautiful product demos and walkthroughs, here's a free-to-use app for you. OpenScreen does not offer all Screen Studio features, but covers the basics well!

Screen Studio is an awesome product and this is definitely not a 1:1 clone. OpenScreen is a much simpler take, just the basics for folks who want control and don't want to pay. If you need all the fancy features, your best bet is to support Screen Studio (they really do a great job, haha). But if you just want something free (no gotchas) and open, this project does the job!

OpenScreen is 100% free for personal and commercial use. Use it, modify it, distribute it. (Just be cool 😁 and give a shoutout if you feel like it!)

[![OpenScreen App Preview 3](https://github.com/siddharthvaddem/openscreen/raw/main/public/preview3.png)](https://github.com/siddharthvaddem/openscreen/blob/main/public/preview3.png) [![OpenScreen App Preview 4](https://github.com/siddharthvaddem/openscreen/raw/main/public/preview4.png)](https://github.com/siddharthvaddem/openscreen/blob/main/public/preview4.png)

## Core Features

- Record specific windows or your whole screen.
- Add automatic or manual zooms (adjustable depth levels) and customize their durarion and position.
- Record microphone and system audio.
- Crop video recordings to hide parts.
- Choose between wallpapers, solid colors, gradients or a custom background.
- Motion blur for smoother pan and zoom effects.
- Add annotations (text, arrows, images).
- Trim sections of the clip.
- Customize the speed of different segments.
- Export in different aspect ratios and resolutions.

## Installation

Download the latest installer for your platform from the [GitHub Releases](https://github.com/siddharthvaddem/openscreen/releases) page.

### macOS

If you encounter issues with macOS Gatekeeper blocking the app (since it does not come with a developer certificate), you can bypass this by running the following command in your terminal after installation:

```
xattr -rd com.apple.quarantine /Applications/Openscreen.app
```

Note: Give your terminal Full Disk Access in **System Settings > Privacy & Security** to grant you access and then run the above command.

After running this command, proceed to **System Preferences > Security & Privacy** to grant the necessary permissions for "screen recording" and "accessibility". Once permissions are granted, you can launch the app.

### Linux

Download the `.AppImage` file from the releases page. Make it executable and run:

```
chmod +x Openscreen-Linux-*.AppImage
./Openscreen-Linux-*.AppImage
```

You may need to grant screen recording permissions depending on your desktop environment.

**Note:** If the app fails to launch due to a "sandbox" error, run it with --no-sandbox:

```
./Openscreen-Linux-*.AppImage --no-sandbox
```

### Limitations

System audio capture relies on Electron's [desktopCapturer](https://www.electronjs.org/docs/latest/api/desktop-capturer) and has some platform-specific quirks:

- **macOS**: Requires macOS 13+. On macOS 14.2+ you'll be prompted to grant audio capture permission. macOS 12 and below does not support system audio (mic still works).
- **Windows**: Works out of the box.
- **Linux**: Needs PipeWire (default on Ubuntu 22.04+, Fedora 34+). Older PulseAudio-only setups may not support system audio (mic should still work).

## Built with

- Electron
- React
- TypeScript
- Vite
- PixiJS
- dnd-timeline

---

*I'm new to open source, idk what I'm doing lol. If something is wrong please raise an issue 🙏*

## Contributing

Contributions are welcome! If you’d like to help out or see what’s currently being worked on, take a look at the open issues and the [project roadmap](https://github.com/users/siddharthvaddem/projects/3) to understand the current direction of the project and find ways to contribute.

## License

This project is licensed under the [MIT License](https://github.com/siddharthvaddem/openscreen/blob/main/LICENSE). By using this software, you agree that the authors are not liable for any issues, damages, or claims arising from its use.