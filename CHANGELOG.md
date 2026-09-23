# **Changelog**

All notable changes to Skales will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),

and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## v12.9.35 - Roles

**A release about the things that got in the way: a switch that switches, sub-agents that run on the model you choose, and a voice note that plays.**

Roles in Skales Code was a start button dressed as a switch: pressing it again never turned it off, and a red box stayed on screen as if something had failed. It is a switch now, its state is a quiet strip in the theme's own colours with a way to turn it off, and it names the model each role will run on. Sub-agents in the chat and in Code run on one model you pick under Settings, Chat & Code, with a live model list, so a cheap model can do the errands while the conversation keeps its own. A run on a subscription says it is included in your subscription instead of "price unknown".

Around it, the fixes you run into every day: a WhatsApp voice message arrives as a voice message you can play, WhatsApp starts once when Skales opens, a read-only conversation can read a web page, Voice opens a fresh conversation, a context window you set holds after the first answer, the notes about set-aside tool steps appear only when something was set aside, and the effort you used last is where the next chat starts.

### Added

- **An answer can be reported from Iris, Flow, Lio and the Desktop Buddy, not only from the chat.** Iris has Report answer in her right-click menu next to Copy last answer. A written Flow answer and each architect or reviewer turn in Lio open the same right-click menu a chat answer has, with Copy and Report answer; a passage you selected keeps the normal text menu. The site Lio built carries a flag above its preview, and an answer in the Buddy bubble carries a small flag underneath. All of them open the same report window as the chat and say the same thing about what is sent.

### Fixed

- **A greeting is answered without sending the tool list.** A "hi" or a "thanks" was meant to go out without tools, but the current time is attached to your message before the check, and the check read "hi" plus the time as a real request. Every greeting paid for thirty-five tools; it now costs a few thousand tokens.

- **The first message of a fresh install gets the same instructions as every message after it.** The capability list was written to disk only after the first answer had already been sent without it, so the first and second turns carried two different prompts and the second could not reuse the first from the provider's cache.

- **An imported skill can be opened when the prompt says to open it.** The skills list told the model to call read_skill, and read_skill was not among the tools it was given. It now ships whenever skills are listed.

- **A ChatGPT subscription conversation reuses its cached prompt and says how much it did.** Each request now names its conversation to the provider's prompt cache, and the share of the input served from the cache is read back, so the cost in the footer and in Analyze counts it.

- **A subscription conversation no longer turns into "price unknown" after a stopped turn.** When a run ended early, the line that settles what it spent carried no provider, so it was counted as a call without a price. It now names the provider the run used, and the footer keeps saying the conversation is included in your subscription.

- **A link you paste is read right away.** Reading a web page is always among the tools now, so an address is opened in the first step instead of after a detour. The web search tool says that an address is to be opened, not searched, and the other page and request tools sit in the web group the tool list names.

- **Skales' own documentation and your skills stay reachable when the tool list has to be cut.** On a model with a small budget the lookup for Skales' documentation and the skill reader could be cut while the instructions still pointed at them. Both are now kept on every turn that points at them.

- **Your skills are listed with what they do.** The short skill list showed only names; each skill has its one-line description again. The full instructions of a skill your message names now come after the part of the prompt the provider can reuse from its cache, so naming a skill no longer makes the rest of the conversation more expensive. The tool that opens a skill's own files ships together with the skill reader.

- **The standing rules are back in the instructions.** Never switching the companion on by itself, building plugins and skills only with their tools, offering to save a skill only while you are there, never sending you to a /mcp page, answering as Skales rather than Iris in the chat, and never claiming local models are required had moved into a document the model only reads on request. They are one line each in the instructions again.

- **Skales Code is no longer told to use a document panel it does not have.** The file instructions named the document tool on every turn, also in the Code window, which does not carry it. It is named only where it can be used.

- **Models that stumble over tools loaded on demand keep the full instructions.** GLM-4 and Kimi models already get every tool at once because they tend to describe a tool call instead of making it; they now also keep the full product text instead of an index they would have to look up.

- **Skales tells you the right place for the voice settings.** The instructions said there was no Voice tab, while the lookup and the app itself put the voice settings under Settings, Voice. They now agree, and AI providers are named by their tab, AI Providers.

- **A greeting on a ChatGPT subscription uses the conversation's prompt cache as well.** A message sent without tools left out the cache key the other messages carry.

- **A read-only conversation can open a web page to read it.** Read-only in the chat, and Plan and Ask in Skales Code, refused to open any page in the browser, so a request as plain as reading the newest GitHub issues ended with Skales asking you to paste them in. Opening an ordinary web page is now a read like any other; clicking, typing, signing in, downloading, and opening a link that does something when it is opened (signing out, unsubscribing, confirming, paying) are still refused in these modes. The tooltip of the read-only mode says so.

- **A permission card that asks every time no longer offers answers it cannot keep.** A purchase, a sign-in, an export and a click that cannot be taken back are asked about every single time, but their cards in the chat and in Skales Code still offered "for this session" and "always allow", and the next such step asked again as if nothing had been pressed. These cards now offer allow once and cancel; every other card keeps all of its answers.

- **Skales opens on the colour of its theme instead of switching to it a moment later.** The window, the start page and the first frame of the app each carried their own copy of the default theme's background, two of them a slightly different near-black, so every start showed a visible change of ground. All three now take the colour from the one table the themes are painted from.

- **A fresh installation no longer counts OpenRouter as your choice before you have made one.** The built-in defaults had OpenRouter switched on, and the first save during setup wrote that to disk. Leaving the provider step without picking anything then asked whether to keep OpenRouter instead of saying that no provider is set up, and the model list named OpenRouter on a machine without a key. OpenRouter is now switched on when you choose it, and not before.

- **WhatsApp starts once when Skales opens, and starting it no longer takes Skales down with it.** Opening the app, the first background tick and Settings could each start the bridge before the first one was answering, and the second one freed its port by stopping every process connected to that port, the Skales server included. The server restarted, the bridge started a third time next to a browser still holding its session, and the bridge could sit at "authenticated" without ever becoming ready. A start now waits for a bridge that is still starting, a port is freed only from the process listening on it, a bridge starts its client once, and one that authenticates without becoming ready writes the step it stopped at to its log.

- **A picture Skales shows in a turn you started from your phone arrives on the phone as a picture again.** Asking the computer from the phone to show you something - "send me a random picture" - brought back the answer's text and, in it, the name of a file on the computer; the picture itself stayed behind. The computer now tells the phone about every picture, clip and file the turn produced, and the phone fetches each one the way it fetches any other file from the computer, so it appears in the answer it belongs to. Only files the computer would hand over anyway are offered.

- **The theme name Skales-X stays on one line when you pick a theme.** On a narrow window the setup's theme cards split it at the hyphen and put "-X" on a line of its own; the name now stays whole there, in Settings, Appearance, and in the setup's summary.

- **A picture written straight into an answer is still there when you open the conversation again.** Saving the conversation used to drop it, and reopening showed an empty frame; an ordinary image format is now kept as a file with the conversation, in the chat and in Skales Code. A picture in a format that can carry code stays hidden, and its place now reads that it was not shown, with the model's description of it on hover. Older conversations that lost a picture say so in its place.

- **Your own messages in Skales Code read like the answers.** Lists, headings, links and pasted code are drawn instead of printed as raw characters, every line break you typed stays where it was, and a long paste shows its first lines with a button for the rest. A picture link in your own message is named rather than loaded, and a pasted web page shows as code rather than running.

- **Comments in code blocks in Skales Code are readable in every theme.** They were drawn in the faintest text colour, below the contrast text needs in light mode; they now clear it on every surface code is shown on and stay dimmer than the code around them.

- **Hover hints in the chat bar, the sidebar toolbar and the icon rail are no longer cut off or drawn twice.** The Agents button and the chat mode segments explain themselves in the app's own hint, which the narrow bar can no longer clip, and the icons of the slim rail and the sidebar toolbar show one hint instead of a clipped card on top of it.

- **The effort dial keeps its position.** A conversation you reopen, from the sidebar, History, a link or after a restart, comes back at the effort it was using, and a new conversation starts where you last put the dial instead of at the lowest setting. The Code window remembers its own dial the same way. A level carried over is only applied to a model that has an effort setting.

- **Long tool runs no longer leave a "tool steps were set aside" line after nearly every turn.** A conversation on the default model was measured against a generic window far smaller than the model's own, so tidying started at a fraction of the threshold you set, and a tidy-up that set nothing aside still wrote its line. Tidying now starts only when a request really presses the window of the model that answers, a tidy-up that only shortened results stays quiet, and each kind of fold, setting steps aside or summarising older parts, is reported once per run instead of after every step.

- **A context window you set under Override Model Limits stays the window after the first answer.** With an override for every model of a custom endpoint, the footer showed the number you set until the first reply and then fell back to the endpoint's generic default, and long conversations were folded or trimmed against that smaller number. The override now governs the footer, the trimming before a request and the automatic compaction alike, and a window a server reports no longer replaces it quietly.

- **Opening Voice starts a new conversation with the orb.** Iris reopened the last conversation every time, even after Skales was restarted, and drew its last answer on screen as if it had just been given. Each new Voice window now starts fresh; a reload of the same window stays in its conversation, and a turn that is still running or a recording that never became a turn keeps its conversation instead of being left behind. Earlier conversations stay in History and in Iris' own conversation list, and opening Iris no longer changes which conversation the chat has open.

- **A voice message sent over WhatsApp arrives as a voice message you can play.** Speech synthesis writes WAV, and WhatsApp builds a voice note only from Ogg/Opus: the file died inside WhatsApp's own page code, and the failure was booked against a WhatsApp Web build that works. Audio WhatsApp cannot play is now converted with the bundled FFmpeg before it is sent, a WAV sent without a wish goes as a voice note, and the bridge refuses unplayable audio with the reason instead of restarting itself.

- **WhatsApp keeps sending after WhatsApp Web updates itself in the background.** The bridge held a page that no longer existed, every send failed until a restart, and its recovery gave up because WhatsApp served a newer build than the one it asked for. A send now checks the page first and restarts the client on whatever build WhatsApp serves; nothing was sent through the dead page, so nothing is sent twice.

- **Roles in the Code window turns off when you press it again.** The key looked like a switch and behaved like a button: pressed on an empty composer it raised a red warning that stayed however often you pressed, and while the roles were working it could not be pressed at all. It is a real switch now. While it is on, a quiet notice above the composer says that what you send goes to the architect, the coder and the reviewer, names the model each of them will run on, says when no provider is set up for them yet, opens the role models over the window and carries its own Turn off. The choice belongs to the session, so it is still there after a reload, and a new session starts with it off. `/roles` on its own flips it; `/roles` with a task still runs that task at once.

- **One sub-agent model for Chat and Code, and it is used.** Settings, Chat & Code has a new row with a provider, a model and a Fetch button: whatever a sub-agent runs on when it has no model of its own. Pick a cheap model there and the small errands stop running on your main model or subscription; leave it empty and nothing changes. Until now the per-role models under Goals reached a sub-agent only in the optional role modes, never in the default one, and never for jobs dispatched as parallel tasks, so a model set there could change nothing at all. The new row and the Goals rows write the same setting and show the same answer.

- **A reply paid for by your subscription says so.** Answers and sub-agents running on a sign-in such as ChatGPT were labelled "price unknown" or "not reported". They now read "included in your subscription", with the API price of the same tokens beside it as a marked comparison when that price is known. They add no dollars to the session ceiling and no longer turn the session total into an estimate.

- **A sub-agent's result no longer claims a roster that was never asked.** A helper given a name such as "Researcher" reported that the name was not on the roster and that an automatic role ran instead, even when no roster was switched on, and said it twice. The note now appears only when your roster is in use, and once.

- **An agent pinned to its own model is measured against that model's window.** A resident agent that runs on a small local model while the app's default is a large one had its window, its trimming and its automatic summaries sized for the default, so a long run was not compacted in time and the local engine refused it. The window, and the model that summarises older parts of its conversation, now follow the model that actually answers.

- **"New" in the Code window starts on the effort you last set.** A new session took over the level of the session open before it, or the lowest level, instead of the dial's last position; a Code session started from your phone without a pick of its own starts there too.

- **A Studio video in WebM goes over WhatsApp as a video.** A .webm file was taken for audio, converted and delivered as a voice message without its picture; a recording sent on purpose as a voice message is still converted. AAC audio, which the bridge refused as unplayable, travels as audio again, and each converted voice note gets a name of its own, a time limit, and is removed once it has been sent.

- **Read-only, Plan and Ask keep refusing links that act, however they are spelled.** An address such as /deleteAccount or /logoutUser, a doubly encoded word, and pages on this computer or your own network (a router's reboot page, a local server) are no longer taken for an ordinary page to read.

- **Two quick changes to the role models under Goals both stay.** The second change could write the first away; they are now saved one after the other.

- **Roles on with only an attachment in the composer says that the roles need a task in words** instead of doing nothing. Closing Iris in the browser version and opening her again starts a fresh conversation, and a picture too large to send to your phone is no longer announced to it.

- **Morning greetings and stand-ups no longer appear in the middle of your chat.** A note Skales sends on its own - the morning greeting, the daily stand-up, a check-in - was put into whatever conversation was open as if it were an answer, often right between your first question of the day and its reply, and the model then read it as something it had said. These notes now wait in the notifications behind the bell, which shows a dot until you look. Only what needs you still pops up: a reminder you set, a blocked task, a meeting, a room asking for you. An approval a Telegram or WhatsApp run is waiting for still shows as a notice in the open chat. A stand-up with nothing completed and nothing blocked is no longer sent at all.

- **Skales does less work while you are only looking at it.** The mood bar redrew itself on every refresh of the screen while the window was in front; it now moves in 30 steps a second, which looks the same, and the status dots in the navigation pulse three times when something new arrives and then stay lit instead of pulsing for as long as it is unread. An idle Skales window measured about a third lighter.

- **Numbered lists keep every digit.** From the tenth item on, a numbered list in an answer showed only the last digit - "0.", "1.", "2." instead of 10, 11, 12. The list now makes room for as many digits as its numbers have.

- **A run that keeps asking for something it already has is stopped, with the reason.** A scheduled task could repeat the same search more than a thousand times, each one refused with "use the result you already have", until its step budget ran out - and every refusal was a paid model call. Background tasks, Telegram, WhatsApp, the command line and the Desktop Buddy now end such a run after a few rounds that brought nothing new, save the progress, and say what happened and how to continue; a scheduled task that ends this way is filed as not finished instead of done. Reading something that is still moving, such as the output of a running build, never counts as repeating.

- **Sub-agents can no longer start sub-agents without end.** A helper without a role of its own was allowed past the delegation depth, so a request like "run two sub-agents in parallel" could fan out into helpers starting helpers, hundreds of paid model calls in a couple of minutes. Helpers now keep the configured depth (one level by default); only the role that exists for handing work on may go one level further, and never deeper.

- **The question card in the chat looks like every other card under Flat.** Its corners and its shadow were fixed numbers no theme could reach, so under Flat it stayed rounded and lifted while everything around it was square and flat. It now takes its corners from the theme like the other cards, square under Flat and unchanged under Skales-X and Classic, and the question card on the Memory page does the same.

- **When clicks and typing on your screen are refused, Skales says why it happens even with the switch on.** macOS ties the Accessibility permission to the app's signature, so after an update, a rebuilt or an unsigned Skales the switch in System Settings can still show on while it belongs to the old app. The notice now says to remove Skales there and add it again, and that controlling the browser needs none of this.

### Changed

- **Skales opens at 90 % size.** Everyone who has never chosen a size, new installations included, starts with the whole window at 90 %, which reads calmer and shows more of each page. A size you chose under Settings, Appearance, Skales size - 100 % included - stays exactly as it is, and Reset now returns to the default instead of to a fixed number.

- **A turn carries an index of what Skales knows about itself instead of the whole of it.** Every message used to send the release notes of ten versions, the catalogue of every page, the status of every skill, every feature of the chat and the map of every setting, whether the question needed them or not. A turn on a cloud model now carries one line naming five topics (what is new, where things are, the features, the skills, and everything else the app can do), and Skales fetches the one it needs when a question asks for it, word for word as it used to stand in the prompt. An ordinary second turn on a fresh install went from about 27,000 input tokens to under 14,000. Local models and the compact prompt levels keep the full text.

- **Skales Code and Flow no longer carry the chat's product descriptions.** Reminders, triggers, scheduled jobs, the conversation history search and app navigation stay one tool-group load away there instead of being sent with every step, and the skill list, the chat's rendering notes and the calendar routing are left out. The first turn of a Code session costs 45 percent less than before, the first turn of Flow 41 percent less.

- **The largest always-loaded tool descriptions say the same thing in fewer words.** Sub-agents, the checklist, reminders, triggers, scheduled jobs and a dozen file and shell tools keep every rule they had, and the tool list of an ordinary turn is a fifth smaller. Rules that stood in two or three places now stand in one, and the rules for posting through the browser and for Computer Use travel with those tools, so they arrive when the tools do.
