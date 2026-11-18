# Eclipse Macro - Windows app

Place EclipseMacro.exe in a writable folder and run it. On first launch it creates recordings, templates, settings.json, and stats.json beside itself. The default recording and templates are included.

Settings controls use a responsive single-column layout and all explanatory text wraps to the available width. Mission, Templates, Settings, and Credits use rounded navigation. Scrolling uses slim rounded slider tracks with draggable thumbs, and the sliders follow the selected theme color.

Settings > Appearance offers Midnight Teal, Black & Purple, White & Black, and Midnight Blue. The Credits tab shows the Discord mark and novaa.

The loot screenshot webhook posts the completion screenshot with cumulative mission totals, wins, fails (unknown results are listed separately), and runtime since the current macro run began. Webhook URLs are not bundled; enter them in Settings.

Hotkeys: F8 Start, F6 Pause, F7 Stop. The start countdown is silent and appears at the top center of the screen.

If the app has a saved recording path from a different computer, it now automatically looks for that recording by filename in its recordings folder, then falls back to freedom_outskirts.json. The download does not include a machine-specific settings file.

Startup now reports its current initialization step, catches playback worker launch/cleanup failures, and restores the pause/stop controls if the worker exits unexpectedly. Stop also cancels the countdown.

The startup status now shows the active capture/playback step. If a playback error occurs, the app shows the error instead of leaving the status stuck. The activity log records when the playback worker starts and what screen it is waiting for.

Playback startup was blocked by a stale UI reference to a removed Record button. That reference has been removed; F9 recording remains supported without a visible Record button.

Settings > Discord Notifications now includes Send hourly loot report. It sends the previous interval and since-start mission counts, tracked loot-icon counts, runtime, missions per hour, and the latest completion screenshot after each hour. It does not include PC stats or rejoin information. Loot counts cover recognized scroll, fragment, serum, and vessel icons (one detected category per completed mission). Windows OCR reads Gold and Gems from the third and fourth reward cards and sums them for both reports; a screen that could not be read is excluded and reported as a reading count. The first report is sent 60 minutes after the macro starts.

When the macro session stops, Eclipse sends a final session report to the Loot webhook with mission totals, runtime, detected loot counts, and the latest completion screenshot.

Stopping the macro also sends a final session report with totals since that run began.
