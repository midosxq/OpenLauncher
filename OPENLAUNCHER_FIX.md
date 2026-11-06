🚨 OPENLAUNCHER — FULL PROJECT CORRECTION & IMPLEMENTATION ORDER

READ THIS CAREFULLY. THIS IS NOT A SUGGESTION.

Claude, your previous implementation is NOT acceptable.

The latest build only shows a noticeable change in the Game Detail screen, which now looks somewhat like Steam. However, most of the features and designs that were explicitly requested are still missing.

The Mapper has not been implemented. The Welcome Screen is missing. The intro video is missing. The About OpenLauncher page is missing. The Change Cover button is still present.

This is not what was requested.

STOP making random UI changes. STOP implementing only the easiest parts. STOP treating placeholders as completed features.

Your responsibility is to FIX the EXISTING PROJECT and implement the actual requirements.

Do not make excuses. Do not silently skip features. Do not replace requested functionality with dummy screens.

---

1. FIRST: AUDIT THE EXISTING PROJECT

Before modifying anything:

1. Inspect the current repository structure.
2. Inspect the existing Android source code and application architecture.
3. Inspect the existing UI, navigation, services, resources, and build configuration.
4. Identify which features are actually implemented, partially implemented, or completely missing.
5. Check the existing "assets/" directory.

ZIP FILE RULES

- "branding.zip" is the correct branding archive.
- Inspect and extract "branding.zip" to identify the developer photo, developer information, and branding assets.
- Do not confuse "branding.zip" with the old "source.zip".
- Keep "source.zip" temporarily as a reference during the audit.
- Do not blindly delete or bundle the old "source.zip".
- Determine whether its contents are still required before deciding to remove it.
- Never replace the current project with an unrelated old implementation.

Preserve working functionality. Fix broken or incomplete functionality.

2. IMPLEMENT THE MISSING FEATURES

A. Mapper System — CRITICAL PRIORITY

The Mapper is one of the main features of OpenLauncher.

It must be implemented as an actual functional system, NOT just a visual interface.

Requirements:

- Keyboard mapping.
- Mouse mapping.
- Gamepad mapping.
- Mapper service integration.
- Mapping editor.
- Save and load mapping configurations.
- Per-game mapping configuration.
- Mouse camera sensitivity settings ("camX" and "camY", maximum 100.0).
- Cursor refresh/blink functionality, separate from Lock Cursor.
- Mouse button actions, including rapid-tap / Crazy Tap functionality.
- Mapping must only run when the selected Launch Type is "Launch with Mapper Services".

Preserve the previously agreed mapper interface:

- No floating ball.
- Mapper activation through a keyboard shortcut or configured keyboard button.
- Bottom-center floating toolbar.
- Draggable rectangular Windows 10/11-inspired appearance.
- No maximize button.
- Small circular controls with X close buttons.
- Settings/Menu label.

Do not claim Mapper is implemented if only its interface exists.

B. Welcome Screen

Implement the agreed first-launch screen.

Design:

- Centered OpenLauncher logo.
- Text: "Welcome to OpenLauncher"
- Slogan: "Your Games. Your Control."
- Subtle animated Pure Black + Purple wave background.
- "Get Started" button.

Rules:

- Display only on the first launch.
- Continue to setup after Get Started.
- Do not include a language selector.
- Language selection belongs in Settings.

C. Intro Video

Implement the 5-second intro video.

Startup logic MUST follow this sequence:

FIRST INSTALL:

1. Show Welcome Screen.
2. User presses Get Started.
3. Run the setup process.
4. Complete setup.
5. Do not play the intro before setup is completed.

SUBSEQUENT LAUNCHES:

1. Play the 5-second intro.
2. Open Game Library.

If setup is incomplete, continue setup without playing the intro.

If the user clears application data, treat the application as a fresh installation.

Do not substitute the video with a static logo or an empty delay.

D. About OpenLauncher

Implement the missing About page.

Use "assets/branding.zip" as the source of the fixed developer profile and branding assets.

Requirements:

- Developer photograph.
- Developer information.
- Clickable GitHub shortcut.
- Clickable YouTube shortcut.
- Clickable Discord shortcut.
- Clickable TikTok shortcut.
- WhatsApp Channel shortcut.

Important:

- WhatsApp must open a WhatsApp Channel link, NOT a group or personal chat.
- Developer identity must not be editable by users.
- Do not invent profile information or social URLs.
- Extract the actual information from "branding.zip".

E. Game Library and Game Detail

Keep the improved Steam-inspired Game Detail design, but complete the functionality.

Requirements:

- Game Library remains the main application screen.
- Do not introduce a Home label.
- Game cards must be clickable.
- Game Detail must display the game cover, description, and action controls.
- Support Add Manually for games that are not automatically detected.
- Support custom covers through the agreed manual game-management workflow.
- Remove the unwanted Change Cover button from the interface.
- Preserve per-game Launch Type settings.

Launch Type options:

1. Launch Only.
2. Launch with Mapper Services.

Save the selected option per game and preserve it until the user changes it.

Mouse and mapper settings must only apply to games using Launch with Mapper Services.

3. PRESERVE THE EXISTING SIDEBAR

The agreed sidebar structure:

1. Game Library
2. Game Configuration
3. Devices
4. Highlights
5. Settings
6. Activation

Activation must appear directly below Settings while activation is incomplete.

Hide Activation after successful activation and persist that state across normal restarts.

If permissions or access become invalid, provide a way to reactivate.

Do not arbitrarily rename or remove these sections.

4. PRESERVE THE VISUAL IDENTITY

OpenLauncher must use its agreed visual identity:

- Pure Black + Purple.
- PC-like fullscreen launcher.
- Epic Games Launcher-inspired Game Library.
- Steam-inspired Game Detail.
- Purple Wave effects.
- Focus Glow.
- Smooth but lightweight animations.
- No generic console-style launcher redesign.

Do not redesign the entire application into a different product.

5. PERFORMANCE AND COMPATIBILITY

Preserve the agreed performance requirements:

- Android 11–16.
- Minimum target: 2 GB RAM.
- 8-core CPU target.
- No GMS dependency.
- Adaptive performance mode by default.
- Battery priority: Balanced.

Priorities:

1. Stability.
2. Responsiveness.
3. RAM efficiency.
4. Visual quality.

Optimize animations and effects without sacrificing mapper reliability.

6. ACCESS AND ACTIVATION

Preserve the agreed access methods:

- Root access.
- Shizuku.
- ADB / Wireless Debugging.
- Bugjaeger where supported.

Root devices should work automatically when the required permissions are available.

Non-root activation must provide clear instructions and actual permission verification.

Do not show activation as successful merely because a button was pressed.

7. STRICT IMPLEMENTATION RULES

These rules are mandatory.

- Do not create fake functionality.
- Do not leave important features as TODO comments.
- Do not replace real services with mock implementations.
- Do not create buttons that do nothing.
- Do not remove working features.
- Do not arbitrarily change agreed designs.
- Do not rewrite unrelated modules.
- Do not waste time exploring unrelated files.
- Do not repeatedly inspect the same files without a reason.
- Reuse existing architecture wherever possible.
- Make focused, efficient changes.
- Do not ask for permission for every small implementation decision.

If a feature genuinely cannot be implemented because of a technical limitation, explain exactly why and provide the best technically valid implementation.

8. BUILD.YML REQUIREMENTS

The final GitHub Actions workflow must be located at:

".github/workflows/build.yml"

You are responsible for creating or correcting this file.

Requirements:

- Use the repository's actual Android project structure.
- Use the correct Gradle configuration.
- Build the actual application.
- Handle dependencies correctly.
- Produce the installable APK.
- Upload the APK as a GitHub Actions artifact.
- Avoid unnecessary workflow complexity.

Do not assume that a successful workflow means the requested features have been implemented.

9. FINAL VERIFICATION — MANDATORY

Before declaring completion, verify each feature.

Feature| Required result
Game Library| Functional
Game Detail| Functional
Mapper UI| Implemented
Mapper Service| Functional
Keyboard Mapping| Functional
Mouse Mapping| Functional
Gamepad Mapping| Functional
Welcome Screen| Implemented
Setup Flow| Functional
5-second Intro| Functional
About OpenLauncher| Implemented
branding.zip assets| Integrated
WhatsApp Channel| Correct shortcut
Change Cover button| Removed
Launch Type| Persistent per game
Activation| Functional
Adaptive Performance| Implemented
GitHub build.yml| Functional

Do not mark a feature complete just because its screen exists.

Verify the actual code paths and runtime behavior wherever possible.

If hardware-dependent functionality cannot be tested in the build environment, explicitly report that limitation instead of pretending it passed.

10. FINAL REPORT

When finished, provide:

1. What was missing in the previous implementation.
2. What files were changed.
3. What features were implemented.
4. What existing features were preserved.
5. What features remain incomplete and why.
6. Build result.
7. APK artifact location.

FINAL WARNING

The previous result was not acceptable because it focused mainly on Game Detail while ignoring multiple previously agreed requirements.

Do not repeat that mistake.

I want the OpenLauncher that was actually specified, not a simplified version of your own interpretation.

Work efficiently. Avoid unnecessary exploration and unrelated refactoring. Prioritize actual implementation over lengthy explanations.

Do not declare the project complete until the required features have been implemented and verified.

THE OBJECTIVE IS TO FINISH OPENLAUNCHER PROPERLY, NOT JUST TO MAKE AN APK THAT BUILDS.
