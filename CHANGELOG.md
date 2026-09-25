# **Changelog**

All notable changes to Skales will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),

and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## v12.9.41 - Lantern

**A release that gives every surface the same hands, and makes a course that Moodle counts as done.**

The chat and Skales Code now have what a coding agent needs every day: they pack and unpack archives, write binary files, work on your own servers over SSH, SFTP and rsync, put every file they make where you say, write Word files and editable presentations, and voice a text or a whole course with the voice you choose, captions included. Flow becomes a canvas: every page is a frame that builds itself while the agent writes, you queue the next request while it works, click an element to change it in the file, pin comments on several and send them as one request, and compare variants side by side.

Courses are the other half. One course runtime serves SCORM 1.2 and 2004, cmi5, xAPI, AICC and Common Cartridge; Flow builds e-learning courses in their own mode; any folder can be packaged, checked and tested; and a finished course goes into Moodle from wherever you are, replacing the package in the same activity so your learners keep their progress. Plugins grow into whole applications with their own model calls, long jobs, previews, files in and out and hand-offs, which is what the free E-Learning plugin is built on.

Settings is rebuilt from the ground up. It opens as one window over whatever you are doing, with ten categories on the left and the same names as on the phone. Every switch and choice takes effect the moment you change it, nothing waits for a Save button, and nothing you or another part of Skales changed elsewhere is undone when you close it.

12.9.41 is the same release with a repaired Windows build: the Windows app starts again, and every part the app loads on demand is in the Windows package. macOS and Linux behave exactly as in 12.9.40.

### Added

- **Iris connects to current live-audio models.** OpenAI Realtime and Gemini Live now default to available models, retired preview picks return to a working default, and Gemini's short-lived token uses its documented WebSocket endpoint. Extended Thinking gets the required non-blocking tool declarations.

- **Code can ask its language server where a symbol lives.** The read-only query returns definitions, references, hover details, implementations, call hierarchies, document symbols and project-wide symbol searches with editor line numbers, using the existing server and install approval path.

- **DevKit reaches the current app capabilities.** Its CLI and authenticated API can run every available Chat tool through the shared safety gate, persist one-time approvals through restart, use Code roles and loops, run installed plugin agents, and inspect the decision model. The in-app reference reads tool and provider counts from the app itself; the docs cover phone approvals, MCP certificates and the current Chat stream.

- **Code subagents keep model-specific tool guidance.** A child's isolated prompt now carries only the tool notes for tools it can call, and a long, repeated subagent run is checked for a fresh return path.

- **One patch can change several project files together.** Chat and Code check every path and hunk before applying a unified diff, keep backups and Code diffs, offer one Undo for the patch, and report compile diagnostics for changed files.

- **The bundled DevKit has one source in this app.** Its published facts come from the running app's version, tool count and provider manifest. A missing DevKit source or stale generated facts now fails the build check.

- **An installed DevKit can be refreshed in place.** The Developer card offers the newer bundled copy, preserves the API token and extra files, and saves the prior folder as a backup. A second visit shows the current state.

- **GPT 6 tool turns use the OpenAI Responses API.** Direct OpenAI key calls for Astra, Sol and Luna keep their tools and native effort setting. The code builder can also send model-native effort to Google, OpenAI and Anthropic.

- **Coding agents can pack archives.** Code and ops subagents can create and list ZIP files. In true Unrestricted mode with full file access, edits and cleanup no longer wait for a prior file read; file backups and path protection still apply, and account identifiers still require provenance.

- **E-Learning previews use a real window and the chosen width.** The storyboard sends Desktop, Tablet or Mobile to the preview host, opens a separate window when asked, and closes it with the course preview. The editor gives the course more room and uses the plugin page kit's solid surfaces and segmented controls. Google narration offers its working voice for a sample.

- **Model pickers show every available model.** Chat, Code and Flow search the complete catalogue and keep the active provider and free models browsable without a hidden row limit.

- **Google and Anthropic discovery follows every result page.** A model on a later API page is included in the same alphabetic picker as the first page.

- **Stop from the phone reaches a private chat run.** The phone's private session id is resolved to the in-memory runner, and the idle confirmation returns under the phone's id.

- **Effort now reaches OpenAI API and Gemini models.** The composer adds Max, sends the model's native effort or thinking setting, and shows the actual rung when a model supports less. Desktop and phone share the same mapping.

- **Hugging Face model browsing can load every page.** Search results and your own models gain a Show more button, keep their alphabetical order as pages arrive, and discard stale searches when you change filters.

- **Long model lists can be searched in their dropdown.** The shared picker keeps keyboard navigation and marks the chosen model while it filters the full list.

- **OpenAI images and Realtime name the credential they need.** Studio offers current GPT Image 2.5 models and defaults to Flare. ChatGPT sign-in still works for chat; image generation and Iris live audio in Skales explain that their API endpoints require an OpenAI API key.

- **Private videos remain readable by the chat's video tool.** A video attached in Incognito can be revisited on later turns: frame descriptions and soundtrack transcription use its in-memory reference without writing a decoder copy to disk.

- **Private chats stay private across the phone and computer.** A private turn sent from Mobile uses an in-memory desktop conversation, including when the connection drops and comes back, so it never joins a saved chat or its notifications.

- **The chat and Skales Code can pack and inspect zip archives.** Skales zips a folder, a file or a list of files with patterns for what to include and leave out, and puts a folder's contents at the top of the archive, the way an LMS or a theme upload expects. It can also list what is inside an archive without unpacking it. Passwords and key files are never packed.

- **Binary files can be read and written.** Pictures, audio, fonts and archives can be copied, patched and assembled byte for byte, not only text files.

- **Skales works on your own servers over SSH.** Add a server once (password, key file, pasted key or ssh-agent, with its host key remembered), then the chat and Skales Code can run commands there and follow long ones as they run. They can also upload and download files and folders and keep a folder in sync with the server, sending only what changed. SFTP publishing profiles and SSH servers are one list.

- **Every tool that makes a file can put it where you say.** Images, voice recordings, PDFs, spreadsheets, videos and the new documents go into your project folder or any folder you name, instead of only their usual place.

- **Word files and editable presentations from the chat.** Skales writes a .docx from Markdown and builds a PowerPoint deck with real text boxes, pictures, shapes and speaker notes, and tells you about anything it could not place.

- **Any HTML page can be exported to PDF, PowerPoint or Word.** The export that Flow's buttons run now works for any folder. It renders the page the way the preview shows it, with its pictures, fonts and styles.

- **Narration with the voice you choose.** The chat, Skales Code and the plugins can voice a text or a whole course with any voice you have set up: OpenRouter's speech models and its audio models, ElevenLabs, Azure, OpenAI, the offline voice on this computer, and the others. Long texts are voiced in short parts and joined without clicks. You get mp3 or wav, subtitles whose times come from the audio, and a spoken version that can differ from the written caption. After a change, only the changed slides are voiced again. You can play samples of several voices before choosing, and the cost is shown.

- **SSH servers in Settings.** Add a server with a key file, a pasted key, a password or your ssh-agent, test the sign-in, see the remembered host key and forget it after a reinstall, and mark a server as trusted.

- **Your phone can use your servers through the paired computer.** The phone asks, and the computer runs the command or the transfer with its own server settings. Passwords and keys never travel to the phone.

- **Auto runs the new tools without asking when they stay in your project folder.** Packing, unpacking, documents, spreadsheets and exports inside the bound folder go through in Auto. So do a cut plan for the video editor and a project on the Projects page. On a server you marked as trusted, commands and downloads run without a card too. The first upload to a server in a session still asks.

- **Flow has a canvas.** Every page, variant and picture of a project is a frame on one plane, and with Versions switched on so is every earlier version. Pinch or Ctrl/Cmd and the wheel zoom, two fingers or the wheel move around, dragging an empty spot pans, and the keyboard does the same. Frames are arranged by dragging them and open in Focus, with the device widths, the presenter and the exports, on a double click. The arrangement, the zoom, the selection and the view come back after a reload or a restart.

- **Frames build themselves while the agent writes.** A frame whose file a turn is writing reloads on its own and shows that it is being written, and a page that ends in the middle is flagged once the turn is done. Only the frames you can see run as live pages, the rest show a still, so a project with twenty frames and more stays smooth.

- **You can send the next request while Flow works.** The message box stays open during a turn; what you type goes into a queue above it and runs as a turn of its own afterwards, one after another. Waiting requests can be changed, moved and removed. The queue survives a reload and a restart, and after a stop or a failed turn it pauses and says why, with a button to go on.

- **Click an element in Flow and change it in the file.** Inspect shows where an element sits, its text and its styles. Text, font, size, weight, spacing, colours, alignment, corners and pictures are written straight into the project file, with undo and redo that still work after a reload. An element the page's own script made says so and offers to mark it instead.

- **Mark elements and ask for changes in one go.** Mark places numbered pins, each with its own comment, and sends them to the agent as one request that names every marked element exactly and carries a picture of each. While a turn works the request waits in the queue.

- **Variants side by side.** Asking Flow for several variants puts them next to each other on the canvas. Taking one makes it the page, and every other variant is kept as a version.

- **Long work keeps going when you close the window or restart Skales.** Voicing a whole course, packing a package or a long render now runs as a background job that shows its progress, can be cancelled, and picks up where it stopped after a restart instead of starting over. A job that cannot continue says that it stopped and why, instead of showing a bar that never moves.

- **Plugins can be whole applications, not only forms.** A plugin page can now be made of several files, ask its own model for an answer in the shape it needs, give its agent a job, run long work that keeps going when you reload, fill the whole window as an editor, and open a preview of what it made in a frame of its own - over the page, across the window or in a window of its own.

- **A course preview can stand in for the learning platform.** A plugin's preview can run an e-learning course as a learning platform would, with buttons to leave half way, come back to where you were and start over, and a log of every call the course made.

- **Plugins hand files out and take them in, on your click.** Save as, Show in folder and Share hand a finished file to you; a file picker copies what you choose into the plugin's own folder. A page that asks without a click gets a card first.

- **A plugin's own tool can ask you for its key.** Skales draws the field, stores the key encrypted, and the plugin's page never sees it.

- **One plugin can hand something to another.** A plugin that says it accepts a kind of thing receives a copy in its inbox, after a card that names both plugins and the files.

- **The import card names the tools a plugin brings.** Before you install a package you see which tools of its own it carries, what each one does, which keys they will ask for and what it accepts from other plugins.

- **Flow builds e-learning courses.** A new E-Learning mode in the composer, and an E-Learning block with a general course template in the Templates tab, turn a brief into a course with narration, subtitles, a transcript, exercises, a quiz and a contents list; Auto recognises a course brief and picks the mode itself. The frame around the slides is always the same one, with keyboard and screen-reader support, and a course left halfway opens again on the same slide.

- **Courses go to the LMS you name, not to a standard you have to know.** The export asks where the course goes: Moodle and Totara get SCORM 1.2, corporate systems such as SAP SuccessFactors, Cornerstone, Docebo, Workday Learning, Absorb, TalentLMS, iSpring Learn, LearnUpon, ILIAS and Blackboard get SCORM 2004 4th Edition, Canvas gets an IMS Common Cartridge, and cmi5, xAPI and AICC are there for systems that ask for exactly that. You choose when a course counts as done: the last slide, every slide, a quiz score, or only when the course says so.

- **Chat and Code package, check and test courses from any folder.** Ask for a course package and Skales builds it from any folder, including one unpacked from an existing package and edited, checks it the way an LMS reads it, and runs it in an LMS stand-in with a learner who stops halfway and comes back, reporting every call the course makes. The Flow export uses the same machinery.

- **A course is voiced from its export dialog.** Pick the speech provider and the voice and voice the whole course; only slides whose text changed are voiced again, and without a speech provider the dialog shows where to set one up.

- **The export names the settings the LMS needs.** For Moodle: update the existing activity, require the status Completed, show it in the current window; for Canvas, cmi5, xAPI and AICC what those systems expect.

- **A finished course goes straight into Moodle, from wherever you are.** Ask in the chat or in Skales Code, press Publish to Moodle in Flow's export, use the button in a plugin, or ask from your phone - the phone hands the job to your desktop, and the desktop publishes it with your own Moodle connection. Skales picks the best way your Moodle offers and tells you which one it took.

- **A new version lands in the same Moodle activity, and your learners keep their progress.** Skales replaces the package inside the activity you already have instead of creating a new one. Before anything is uploaded it checks that the new package is still the same course; a package that would make Moodle treat it as a new course, and wipe everyone's progress, is refused unless you ask for a new version on purpose.

- **A new Moodle activity comes out set up the way Moodle needs it.** Only when you ask for one: shown in the current window, and counted as done when the course reports it as completed.

- **Moodle in Settings.** Settings, Accounts & Services, Moodle holds your Moodle address, your Moodle account and a web service token. Test connection shows what your Moodle can do, Get token with account fetches a token the way the Moodle app does, and the password and token stay encrypted on your computer. Several Moodle sites are possible, one of them the default.

- **Three steps for your Moodle admin.** The Moodle settings carry a short guide for whoever runs your Moodle: install the Skales Connector for Moodle, switch on its web service, create a token. After that, publishing needs no browser at all. Without the admin it still works with your own Moodle account.

- **Publishing through your own web space.** A Moodle activity that downloads its package from your server gets every new version by uploading the file there through one of your FTP or SFTP profiles. The Moodle settings say which one switch your admin sets once for this.

- **How many learners finished, asked from the chat.** With a web service token, Skales reads back how many learners started and completed a course activity.

- **Every publish into a course asks first, in every mode.** Auto and Unrestricted do not skip it, and an earlier yes does not carry over to the next publish. A plugin can only publish a package from its own folder, and the phone's publish goes through the desktop, so your Moodle password and token never leave this computer.

- **Click an element in a plugin's course preview and change it.** A plugin that shows a course or page in its preview can switch on the same Inspect and Mark that Flow has: a click names the element, and the plugin writes the change into its own files.

- **A brand kit from a website address.** The chat, Skales Code and plugins can read a site's colours, fonts and logo from its address and save the logo where you say.

- **Whisper Small and Whisper Large v3 Turbo for dictation on this computer.** Skales Local now offers four Whisper sizes. The two new ones hear more accurately, above all in languages other than English, and are meant for recordings and push-to-talk. Every size says that it understands around a hundred languages, and an install keeps only the files the app actually uses.

- **A plugin of up to 16 MB reaches your phone.** Taking a plugin from the computer to the phone used to stop at 2 MB; it now arrives in parts and is joined on the phone.

### Fixed

- **Skales starts again on Windows.** The Windows build of 12.9.40 closed at launch without a window or a message. It opens normally again.

- **Nothing is missing from the Windows installation any more.** Parts of the app that load on demand were absent from the Windows package, so scheduled jobs, the daily briefing, the operator, parts of the live chat, the Buddy chat, the AIPointer chat, Autopilot and skill generation could fail quietly in the background. Every part the app asks for is now in the package, and the build refuses to ship if one is not.

- **Opening a file in Code again reads its latest contents.** A file created after an earlier click now opens normally, loading shows its own state, and filesystem failures name their cause instead of appearing as a deleted file or an empty review.

- **Code’s model menu remains usable in very short windows.** Its height stays within the actual space beside its trigger, while the full catalogue remains reachable by wheel and keyboard after resizing.

- **Skales Local stays paused when memory is scarce.** The automatic start at launch, a settings change and a chat turn now obey the same memory-pressure hold; Settings and Chat name the reason, and a manual Start can still override it.

- **Vision fallback honours your model answers on cloud providers too.** A model marked as able to see images takes precedence over the configured reader, even when the provider has no installed-model list. Changing that answer applies to the next image turn.

- **Deleted chats leave the sidebar immediately.** Deleting the last conversation clears its cached row, and new conversations appear through repeated delete-and-create cycles without a reload.

- **The chat and Flow model groups keep every configured model.** The active choice stays visible at the top; the rest of each provider's catalogue appears alphabetically, including large custom endpoints.

- **The model row now fetches live catalogues for configured providers.** Its normal loading path reaches the same server fetch as Refresh, including direct OpenAI, while an unavailable catalogue keeps the curated fallback and names the reason.

- **ComfyUI and AIPointer model choices are alphabetical.** Checkpoints, samplers and fetched AIPointer models sort by their displayed names, regardless of letter case.

- **Fetched model lists remain complete and alphabetical.** OpenRouter no longer drops models after the 200th result, and settings lists order entries by the name shown in the picker.

- **Private videos and documents from Mobile stay in memory on Desktop.** Chunked uploads keep their privacy across retries and reconnects, and their original bytes remain available for later private turns. Video frames and soundtracks can be decoded without temporary files, including clips whose metadata sits at the end.

- **Private document and archive tools work directly from memory.** A private file can be read in pages, documents retain their structure, and zip or other supported archives can be listed and unpacked into private references. Speech transcription skips local activity and Discover events in Incognito.

- **Incognito is clear from the first message on Desktop.** The new-chat screen has the same private composer tint and notice as an active chat, and its first message crosses to the chat through a one-time memory handoff. Private PDFs, Office files, archives and video can be attached without a Workspace copy; video frames are sampled in the window, and voice transcription sends the private flag. The document panel remains below the chat header.

- **Private attachments can stay in memory without temporary files.** Incognito uploads use opaque references for any file type, keep the existing upload size limits, remain available across later turns, and are cleared when their private session is deleted. Ordinary runs cannot read them.

- **Incognito can transcribe a video soundtrack without saving the clip.** The audio demuxer reads the video from memory and streams WAV through FFmpeg pipes, keeping the existing speech provider path available.

- **Incognito sends no stored personal context and keeps document text extraction in memory.** Saved preferences, standing instructions, relationship state and previous relay context stay out of the prompt; private Office attachments can be read without a temporary file, and private prompt previews are cleared after use.

- **Incognito stays private when tools run or a conversation moves to Skales Code.** Private turns no longer emit usage events, Discover activity, presence pings or content logs. Attached and tool-produced pictures and context measurements stay in memory, including later Code turns; private crash details and session pointers are not saved. Ordinary conversations keep their existing history and diagnostics.

- **Desktop builds work without an optional SSH crypto binding.** Electron keeps its hard runtime and terminal checks, while SSH and SFTP use ssh2's JavaScript crypto when the native binding is absent. Windows and Linux builds use a supported Node version, and portable packages omit OpenSSL and its notices.

- **The Desktop window opens on a different local port.** When the usual port is occupied or a separate test profile chooses another, Electron now sends its access token to the final port and loads the app instead of showing the remote-access token screen.

- Job status, cancellation and event routes await their route parameters as required by Next.js 15.

- Opening an Extensions subpage keeps its title and Back control visible. Deep links to a specific add-on still focus that card.

- New Spanish and Portuguese extension text keeps its natural accents; the French plugin recovery notice uses the same informal address as the app.

- Old plugin, custom skill and custom widget links in chat, toasts and surface links open their Settings subpage directly, keeping the current page underneath. Their routes remain explicitly declared as legacy redirects.

- Navigation guidance and validation follow the mounted Extensions subpages and current sidebar groups; skill uploads, plugin authorship and Widget AI notices keep their existing shared-panel checks. Sidebar validation also follows the shared Add-ons subpage and its focused legacy route. Detailed navigation help names the new subpages while the always-loaded capability text stays within its existing budget.

- Desktop-only extension rows wait for the client bridge before rendering, keeping the initial Settings render consistent.

- **Settings controls keep the values you choose.** Companion and Conscious switches, the WhatsApp signature, Discord, Slack and Telegram connection details now save and reload correctly. Drafts in instructions, Brand Kit, knowledge backend, MCP and Discover ask before Settings closes. Deleted Brand Kit assets vanish immediately, and Discover reads the saved settings file.

- **Settings reports failed saves and keeps the last slider change.** AIPointer, Buddy skin and webhook failures stay visible; compaction and AIPointer sliders flush when Settings closes. Lio accepts an empty project folder, Calendar opens with Calendar Sync, and WordPress shows the same connection state as its badge.

- **A crashed plugin reopens at a safe starting view.** Skales remembers that its renderer died, clears only the last view on the next opening, and explains the recovery while keeping saved plugin work.

- The chat document panel now starts below the header even when Incognito and provider fallback banners are visible. Banner spacing aligns with the header.

- **AIPointer follows the cursor and its idle bubble responds at every app size.** Its transparent overlay and Buddy use a separate zoom host. Hover, outside clicks and screenshot selections convert between screen points and CSS pixels consistently, while Buddy keeps following the app theme and custom accent.

- **Narrated courses open safely after voicing.** The speech service now saves waveform peaks beside each audio file. E-Learning draws those peaks without decoding audio in the app window, and older recordings show a duration and cue bar.

- **Diagnostics names a dead renderer.** A renderer crash now shows its reason, exit code and page in the exported report.
- **Background job status and event routes build with Next.js 15.** The handlers resolve promised route parameters before validating or looking up the job.

- **Audio decoding works again on macOS Monterey.** The desktop runtime uses Electron 43.7.0, the last supported major line for macOS 12. Plugins, Studio scenes and widgets can decode audio normally on the new runtime, while older runtimes keep the visible error fallback. The Code terminal uses an ABI-independent native module with executable launch helpers. The browser automation build check recognizes the bundled Node 24 runtime.

- **SSH keeps native encryption on the updated desktop runtime.** A reproducible rebuild links its crypto module with OpenSSL and updates the CPU detector for Electron's ABI. The build automatically verifies both the development dependencies and the standalone copies against the real desktop runtime; the additional library's license travels in the notices.

- **Embedded audio reports a readable error instead of crashing the desktop app.** Plugins, HTML previews, Studio scenes and widgets avoid the unsafe native audio decoder. Audio playback and host-generated waveforms remain available.

- **An action you approved on a plugin page now runs.** Pressing Allow on a plugin's approval card could come back as "no longer valid" and ask again instead of doing the thing.

- **An imported plugin arrives complete.** A plugin installed from a file kept its page but lost the tools it brings, the layout of its pages and its triggers.

- **The plugin check reads the whole page.** It now understands every call a plugin page can make and reads the page's own scripts too, so a working page is no longer reported as calling something unknown, and a tool the plugin brings no longer counts as missing from its list.

- **Testing a server that signs in with a key works from the FTP card too.** The test reads the stored key and its passphrase, the same way it reads a stored password.

- **Groq speaks again.** Its old voices were retired. Skales now uses Groq's current speech model and passes on Groq's own message when the model first has to be enabled in the Groq console.

- **ElevenLabs says when the account has no credits left** instead of showing only an error number.

- **The cost of OpenRouter's speech voices is shown** instead of "unknown".

- **Unpacking a large archive no longer stops at two thousand files.** An archive is checked as a whole before anything lands on disk. Entries that would land outside the target folder, links, and files that already exist (when you ask to keep them) are each counted and named.

- **Moodle reports a Flow course as completed.** A course exported from Flow never told the LMS it was finished, so every learner stayed "incomplete" forever. It now reports completion by the rule chosen at export.

- **The course package is what the preview showed.** Libraries, fonts and anything a page loaded from the internet now travel inside the package, so a course looks the same in the LMS as it did in Flow, also without a network connection.

- **A course with several pages keeps its session.** Following a link from one page to another ended the LMS session. The pages now open inside the course, and the session lasts until the learner leaves.

- **A learner who stops halfway comes back to the same place, and quiz answers show up in the LMS reports.** Time spent, the last position, the progress and each answer are reported, and the session is closed properly when the window closes.

- **A course starts the LMS session only once.** A second start is refused by strict systems.

- **Handout PDFs, lesson videos and downloads stay in the course.** Only earlier exports of the same project are left out of a package now, never a kind of file.

- **A deck reports its slides and completes on the last one, and the start page may sit in a folder.**

- **Replacing a course in Moodle keeps every learner's progress.** A course keeps the identity of its first export in every later one, and a removed slide sends a returning learner to the slide that followed it.

- **The course package no longer names schema files it does not contain.**

- **A plugin page whose script contains certain dollar-sign sequences loads.** Such a page could come out cut in half and show nothing.

- **A plugin that packs a course for a corporate LMS keeps that LMS.** The name of the LMS was treated as a file name, so the course was packed for the default one.

- **A backup without secrets leaves the signed-in browsers at home.** The browser the agent drives and the one that publishes to Moodle keep the sessions of the sites they signed in to, so they now stay on this computer. A pasted SSH key and its passphrase are left out like a server password, and a backup with secrets carries them so the server profile signs in on another computer.

- **A plugin tool that needs no model is never reported as needing one.** On a computer with no AI provider, any plugin tool that failed was reported as "needs a model", even a course test that had run to the end and produced its full report, or a package check on a file that was missing. Only tools that do their work with a model now get that answer, and only when nothing else on the computer could do that kind of work. Every other tool reports its own result and the reason it gave.

- **Testing a course no longer fails one that was already finished when the learner left.** A course that counts as complete the moment it opens correctly clears its "suspend" flag, and the test marked that as an error. It now accepts it and explains that leaving halfway and resuming were never tried, and why. When a page has slides the course runtime does not recognise, both the packer and the test say how to mark them. A failed test now names the checks that failed. If nothing could step through a course without the Skales runtime, the test says to pass steps. The E-Learning plugin shows the name of each check and marks hints as warnings, not errors.

- **A ChatGPT request the service refuses now says why.** When the subscription turned a request down (a limit reached, too many requests at once, a request too large for the model), the chat and the helpers only said the connection had closed. They now show the reason the service gave.

- **Helpers on a ChatGPT subscription are no longer cut off while they think.** A model that reasons silently for a long stretch before its first word was stopped as if the connection had stalled.

- **A failed helper shows its whole reason.** The helpers panel wraps the reason instead of cutting it short.

- **Saving in Settings no longer undoes changes made elsewhere.** Settings used to write back everything it had loaded when it opened, so a key saved in the chat, a folder shared in Skales Code, a routine changed from the phone or a buddy picked in the chat could quietly be reset. Every change is now written on its own, field by field.

- **The active provider stays the one you chose.** Opening and saving Settings could switch it to Skales IQ; it is now read from disk and changed in one place only, whoever changes it.

- **A field you empty stays empty.** Clearing a key, an address or a choice in Settings now really clears it instead of keeping the old value.

- **Keys are no longer readable in the Settings window.** A saved key shows as saved and can be replaced or tested; the key itself stays on disk and is never handed to the window.

- **Closing Settings no longer stops what it started.** A model download, a sign-in to an MCP server, an Outlook or social sign-in and a WhatsApp pairing keep running when the window closes and are still there when it opens again.

- **Every link into Settings opens the right place.** Buttons in the chat, the tray, AIPointer, Iris and the buddy used to land on a page that no longer existed or on the top of Settings; they now open the category and the row they mean.

- **Testing a voice list or a knowledge store with a saved key tests the key.** Both used to send the placeholder instead of the key.

### Changed

- **Extensions opens each manager on its own Settings subpage.** API connectors, MCP servers, AIPointer, Add-ons, Plugins, Custom Skills, Custom Widgets, Webhooks and Lio AI appear in order. Existing routes reopen the same managers; the sidebar keeps installed plugins and widgets, and saved management pins migrate without touching installed items. Add-on names share the translated catalogue, Cockpit describes its background runner, and Guide links open their exact settings rows.

- **A change you make while a turn works on the same file is not lost.** The running turn is told about it, and if it writes over it anyway, your change is put back when the turn ends. When the element it changed is gone, putting it back becomes the first request in the queue.

- **Flow checks its own result once the queue is empty.** With requests waiting, the next one runs first and the check waits for the last result.

- **Plugin packages up to 64 MB install.** A plugin with a voiced example course, fonts and voice samples no longer hits the old 8 MB ceiling, and one file a page stores or you pick may be up to 100 MB. Downloads from the plugin directory get more time to arrive.

- **A plugin's model use counts against your money limit.** Model answers and agent runs from a plugin page count on that plugin's meter for the day and stop at the limit set under Settings > Goals.

- **A plugin writing a document or a course package into its own folder no longer asks every time.** Packing, unpacking, documents and exports that land in the plugin's own data folder run the way the same tools run in Auto inside a bound project folder. Writing into the plugin's own pages still asks, and publishing, sending and deleting always do.

- **An exported plugin package and a package built from a plugin folder come from the same writer**, so both carry the same file list, checksums and signature.

- **Auto also runs Spotify playback, new or appended Obsidian notes and a WordPress cache flush without asking.** All three are undone easily or change no content. The rest of those integrations still asks.

- **Settings is one window with ten categories.** General, AI & Models, Assistant, Memory, Voice, Channels & Devices, Accounts & Services, Extensions, Security & Privacy and System, with the same names and icons as on the phone, a search that finds every row, and a Standard view that hides the rows for experts. It opens over the page you are on and closes back to it.

- **Settings takes effect at once.** Switches, choices and sliders apply the moment you change them, text fields when you leave them. Keys, accounts and connections keep their own Connect or Save button with a clear state beside it.

- **Every account, service and messenger is one row.** The row says whether it is set up; tapping it opens its own page with the form and the test, and Back returns to the list.

- **Icons instead of emoji throughout Settings.**

### Removed

- **The Save Settings button.** Nothing in Settings waits for it any more. A provider card with a key you have not saved yet asks before the window closes.
