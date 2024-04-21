# 0.3 - (2024-04-21)
## Fn Lock time!
Who would have thought that Fn key toggle implementation can be so tricky?!

Karabiner's super powerful, but one thing that caught me off guard is that you can't capture the [from.any](https://karabiner-elements.pqrs.org/docs/json/complex-modifications-manipulator-definition/from/any/) key code and forward it. This means I couldn't use the logic that I wanted, namely setting a variable as soon as you focus on an application with default fn lock on, which would allow me to only declare the applications once (twice technically, second one to say when 'NOT' focusing on these apps).

So anyway, I had to declare all 12 Function keys 4 times, with 2 sets including all the applications per key. Not great...

It's tempting to use `file_paths` option instead of `bundle_identifiers`, which I think was the intended solution to not having to repeat the applications for every key. That way we could put all the apps we want auto fn lock on in the same folder.

However, I'm worried about any apps or scripts that references app's package contents would break, which may be much harder to fix - so I went with the uglier `bundle_identifiers` option. You can still do a search and replace to change your apps though so it's not the end of the world.
## New features
- (⇪, S, F) - fn lock toggle. Repeat to toggle back (unlike Numpad layer).
	- I went with (⇪, S, F) because it's easier than (⇪, fn) and feels sensible inside System layer
- Automatic fn lock for Frontmost Application (bundle identifiers)
	- Use [this article](https://karabiner-elements.pqrs.org/docs/json/complex-modifications-manipulator-definition/conditions/frontmost-application/) to tweak this for your own applications
- When in fn lock, hold (fn) key to use alternate key, i.e.:
	- During Fn lock, (fn+F1) = Decrease Brightness
	- When bundle identifiers in Focus, (fn+F1) = Decrease Brightness
	- When non bundle identifiers in Focus, (fn+F1) = F1
- Added fn_lock.txt to be used with xbar
### Import note!
- Default behaviour is media keys, Fn lock required to enable Function keys
- Disable 'Use F1, F2, etc. keys as standard function keys' feature in System Settings:
	-  > System Settings… > Keyboard > Keyboard Shortcuts… > Function Keys
- Disable 'Use all F1, F2, etc. keys as standard function keys' toggle in Karabiner Element's Function Keys tab. I think the config file will take care of that, but worth double checking!
## Others
- Cleaned up empty modifier keys in JSON - I thought it broke when I deleted them, but I probably just broke the syntax by leaving the commas behind. I said I'm not good at this!
# 0.2 - (2024-04-20)
## New features
- Video layer (⇪V)
	- **N**etflix, **Y**ouTube, **C**runchyroll, **D**isney+, Ne**b**ula, **P**lex,
	- UK link for **A**mazon Prime Videos I'm afraid!
- Creative layer (⇪C)
	- I use the Affinity suite because fuck Adobe's subscription model
- Develo(P)er layer (⇪P)
	- Most apps recite on the left side (VS Code, Sublime Text, Zed, Atom etc.) so this is easier to use, plus it's next to (O)pen layer for more coherence
	- Moved Sublime Text to this layer
- Gaming layer (⇪G)
	- App Store goes in here since (A) is taken by Arc in Open layer and I rarely use it
- Finder layer (⇪F)
- Added a full shortcuts page [here](Shortcuts.md)
## Fixes
- Oh you need a zero key in your numpad? Fine...
# 0.1 - (2024-04-19)

## Initial Release

I don't really publish GitHub repos, please don't sue me for bad changelog!
## Features
- Layered shortcuts using Karabiner Elements triggered by hitting and releasing the ⇪ key (capslock), followed by layer key, and finally the action afterwards.
	- This will be referred to as the **menu** key
	- All shortcuts are denoted in brackets ().
	- I use uppercase letters to denote shortcuts, you don't need to actually capitalise when using the shortcuts
	- I use the comma notation to indicate key release, e.g. (⇪, O)
	- I use + notation to indicate simultaneous key presses, e.g. (⇧+⇪)
	- ⇪ is capslock
	- ⇧ is shift
- Open layer (⇪, O)
- System layer (⇪, S)
- Raycast layer (⇪, R)
	- Requires Raycast
- Numpad layer (⇪, N)
	- Toggles on, (⇪) to exit layer
	- U, I, O = 4, 5, 6
	- J, K, L = 1, 2, 3
- When held down, ⇪ acts as hyper key (⇧^⌥⌘)
	- This allows the key to be used for custom shortcuts with other apps
	- Please remove the built in hyper key rule from Karabiner Elements for this to work
- Toggle capslock itself (⇧+⇪) - order matters
- Template included for custom layers
- xbar integration via stat.txt file
	- See README for more details