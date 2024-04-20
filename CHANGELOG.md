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