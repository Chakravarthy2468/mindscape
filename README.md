MindScape VR — Virtual Reality Therapy Platform
MindScape VR is a browser-based therapy platform that simulates safe, controlled environments for exposure therapy, mood enhancement, and anxiety/PTSD treatment. It features an immersive, minimal 3D mountain environment, real-time biometric simulation, adaptive session controls, and an elegant, responsive design system.

Features
Immersive 3D Mountain Scene

Layered mountains with depth, sky and clouds, snow caps, cable car, lodge, wildlife, and subtle parallax for presence.

Time-of-day and weather effects (sunrise/day/sunset/night, clear/cloudy/misty/snowy).

Therapy Flows

Assessment screen with scales, multiple-choice, and yes/no questions.

Dashboard with recommended sessions, therapy cards, progress indicators, and achievements.

VR session screen with environment, session controls, and emergency stop.

Real-time Biometrics (Simulated)

Heart rate, stress level, skin conductance with visual indicators and safe thresholds.

Safety & Accessibility

Safety Mode toggle and emergency stop.

Prefers-reduced-motion and high-contrast support.

Keyboard focus states and screen-reader-friendly utilities.

Premium UI System

Tokenized design system, gradients, glassmorphism, modern cards, and micro-interactions.

Fully responsive across desktop and mobile.

Tech Stack
HTML5

CSS3 (Design tokens, responsive grid, animations, accessibility support)

Vanilla JavaScript (modular class-based app controller, DOM-driven UI logic)

Project Structure
index.html

Screens: Welcome, Assessment, Dashboard, VR Session

Modals: Breathing Exercise, Session Complete, Settings

Overlays: Biometric panel, VR controls, Level indicators

style.css

Design tokens and semantic colors (light/dark)

Layout, components, cards, buttons, utilities

VR environment styles: sky, mountains, snow, wildlife, controls, effects

Accessibility, motion/contrast media queries

app.js

MindScapeApp class: lifecycle, screen routing, event binding

Data models: therapy scenarios, assessment questions

VR state: height level, weather, time of day, safety mode

Session actions: biometrics, breathing exercise, emergency stop, modals

Getting Started
Prerequisites

A modern browser (Chrome, Edge, Safari, Firefox) with CSS transforms/animations and ES6 support.

Local Run

Option A: Open index.html directly in the browser.

Option B: Serve with any static server:

Python: python3 -m http.server 8080

Node (serve): npx serve .

VS Code Live Server: “Open with Live Server”

Usage
Flow

Launch: Open index.html to see the Welcome screen with feature highlights.

Role:

Patient Access: Starts the assessment flow.

Therapist Portal: Jumps to dashboard (example therapist profile).

Assessment:

Answer questions to tailor recommended therapy.

Progress bar shows completion.

Dashboard:

View recommended therapy, available sessions, progress, anxiety level, achievements.

Start a session to enter VR.

VR Session:

Interact with the mountain environment.

Adjust Weather (Clear/Cloudy/Misty/Snowy), Time (Sunrise/Day/Sunset/Night), and Safety Mode.

Select Height Levels (Base Camp → Summit Peak).

Use breathing exercise, pause, end session, or emergency stop at any time.

Controls & Interactions

Height Levels: Right-side panel. Click levels to advance or retreat.

Weather & Time: Left-side VR Controls Panel.

Safety: Toggle On/Off (with prominent warning when Off).

Interactive Elements: Cable car (ride), lodge (enter), wildlife (observe eagle).

Breathing Exercise: Opens guided inhale/hold/exhale loop with tactile feedback.

Key Code Points
App Lifecycle

app.js → MindScapeApp.init(): binds events and initializes screens.

showScreen(screenId): handles screen routing.

Assessment

assessmentQuestions array defines question types and labels.

renderCurrentQuestion(), next/prev control handlers.

Dashboard

therapyScenarios array configures session types and details.

renderDashboard() populates recommended and available sessions.

VR Environment

Height: changeHeightLevel(level)

Weather: changeWeather(weather)

Time: changeTimeOfDay(time)

Safety: toggleSafetyMode(enabled)

Biometrics: startBiometricMonitoring() simulates heart rate, stress, conductance.

Modals

showModal/hideModal helpers.

Breathing exercise loop with inhale/hold/exhale cycle.

Customization
Add/Modify Scenarios: app.js → this.therapyScenarios

Tuning 3D Feel: style.css → .mountain-vr-environment, mountain layers, transforms, and transitions

UI Theme: style.css design tokens in :root and dark-mode media queries

Accessibility:

Motion reduction: @media (prefers-reduced-motion: reduce)

High contrast: @media (prefers-contrast: high)

Focus outlines and .sr-only utilities

Roadmap Ideas
Real sensor integration (Web Bluetooth/WebUSB) for biometrics.

Progress persistence (backend or IndexedDB).

Analytics and therapist dashboard with session playback/review.

Additional environments (beach, forest, city heights, aircraft cabin).

Voice guidance and multi-language support.

Troubleshooting
Blank VR environment:

Ensure index.html is served over a local server to avoid asset path or security issues with some browsers.

Controls not responding:

Check console logs; verify elements exist and event listeners are bound.

Motion sensitivity:

Enable system “Reduce Motion” to automatically minimize animations.

Contributing
Fork the repository and create feature branches.

Keep UI tokens consistent with style.css design system.

Avoid breaking existing IDs/classes used by app.js selectors.

License
This project is provided for demonstration and educational purposes. Add an explicit license file if open-sourcing (e.g., MIT/Apache-2.0).

Credits
UI/UX design system and VR environment authored in CSS with layered 3D effects.

Application logic implemented in vanilla JavaScript with a class-based architecture.
