# companion-module-obs-studio

This module will allow you to control OBS Studio using the built-in obs-websocket plugin.

## Getting Started

See [HELP.md](https://github.com/bitfocus/companion-module-obs-studio/blob/master/companion/HELP.md)

## Changelog

### v3.7.0

- New
  - Added Previous Scene Active feedback
  - Added scene_previous variable
  - Added Adjust Transition Duration action
  - Allow custom variable in Set Transition Duration action

### v3.6.0

- New
  - Added Split Record action _(requires OBS 30.2)_
  - Added Record Chapter action _(requires OBS 30.2)_
- Fix
  - Ensure feedbacks that use custom variables are re-checked if the variable changes
  - Properly throw error if unable to get initial info from obs-websocket

### v3.5.0

- New
  - Added transition_active variable
  - Set Filter Settings action
- Improved
  - Allow customization of Stream Congestion feedback colors, including a color for when streaming is not active
  - Allow custom variables in additional actions and feedbacks
- Fix
  - Grouped text sources not appearing in dropdown of text sources

### v3.4.3

- Fix
  - Module not reconnecting when OBS was reopened under specific situations on Windows

### v3.4.2

- Fix
  - "Set Source Transform" action not working
  - Error when updating input settings variables

### v3.4.1

- Fix
  - Performance improvements for Scene Collections with a large number of sources
  - More accurately update action/feedback dropdowns when scenes/sources are removed
  - Properly update scene_preview variable and Scene in Preview feedback when switching into Studio Mode
  - Properly update scene_preview and scene_active variables when switching Scene Collections

### v3.4.0

- New
  - Disk Space Remaining feedback to alert when available disk space is below specified threshold
  - free_disk_space_mb variable that returns a raw number value (no units) of MB free on disk, for use in expressions
- Improved
  - Rename 'Set Source Filter Visibility' to 'Set Filter Visibility' since it can also be used for scenes
  - Use newly available InputSettingsChanged event (requires OBS v30.1) to more accurately update changes to current_text, image_file_name, and media_file_name variables

### v3.3.0

- New
  - Preview next/previous scene actions
  - Adjust source volume by percentage action
  - VendorEvent feedback
- Improved
  - Control all filters on a source with the "Set Source Filter Visibility" action
- Fix
  - More reliable behavior when controlling Source Visibility for all sources

### v3.2.0

- Feature
  - New Custom Vendor Request action for sending commands to third party plugins
- Fix
  - Custom Command failing to run
  - Crash when the file name for an image source was invalid

### v3.1.1

- Fix
  - Upgrade script error crashing module
  - Additional fixes for Quick Transition causing transition state to get stuck

### v3.1.0

- New
  - Feedback for Studio Mode Enabled
  - Feedback for stream congestion (similar to the green/yellow/red square in the OBS UI)
  - Feedback for audio meters (similar to the audio meters in the OBS UI)
  - Feedback for audio peaking if above a certain value
- Fix
  - Quick Transition actions causing transition state to get stuck
  - Kbps variable has been restored
  - Certain variable updates (mute, media_status, and others) were not working when the source has an invalid variable name

### v3.0.1

- Fix
  - Set Preview Scene action now properly sends scene to preview instead of program
  - Possible error when executing upgrade scripts resolved

### v3.0.0

- Major
  - Rewrite to support Companion v3
- New
  - Variables for scene names based on the scene order within OBS
- Fix
  - Filter Enabled feedback now properly lists all filters

### v2.0.5

- Fix
  - All text source now appear as choices in the Set Text action dropdown on startup
- Improved
  - Allow hostnames to be used in the module configuration

### v2.0.4

- Fix
  - When using Set Scene Visibility on a group source, the sources within groups are now not affected
  - Toggle/Start/Stop Output now works properly with Virtual Camera
- Improved
  - Update obs-websocket-js to latest version
  - Use obs-websocket's Batch command for certain actions

### v2.0.3

- Fix
  - Properly detect more types of disconnections and properly update module status
  - Grouped sources can now be enabled / disabled via "Set Source Visibility" action
  - Grouped sources feedback is now accurate

### v2.0.2

- New
  - Allow Global Audio Devices to be choices for actions, feedback, and variables
- Fix
  - Show Scenes in the Open Projector action choices

### v2.0.1

- Fixes
  - Prevent issue when using more than one instance of the OBS module
  - Add filters from scenes, not just sources

### v2.0.0

- New

  - Support for obs-websocket version 5.0.0
  - New "Current Media" option on all media control actions
  - Custom variables for "Set Program Scene", "Set Preview Scene", and "Custom Command" actions
  - Ability to specify a specific scene for a source in the the "Source Visible in Program" feedback

  - New Actions:
    - Toggle Recording Pause
    - Open Source Properties Window
    - Open Source Filters Window
    - Open Source Interact Window
  - New Feedback:
    - Replay Buffer Active
  - New Variables:
    - recording_path
    - stream_service
    - base_resolution
    - output_resolution
    - target_framerate
    - replay_buffer_path

- Fixes
  - Take Screenshot action now works again
  - Recording feedback should properly reflect recording state
