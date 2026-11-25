🎓 AttendMate

"Know exactly when you can bunk."
A beautiful, mobile-first web app designed for Indian college and university students to track, project, and plan their attendance with mathematical certainty.

📱 Features
⚡ Instant Attendance Calculation:
Real-time calculation of current percentage: 
attendance
=
attended
held
×
100
attendance=
held
attended
	​

×100
Color-coded glowing circular SVG progress ring (Mint Green for Safe, Amber for Caution, Coral Red for Shortage).
Friendly, student-oriented status messages.
🛡️ Safe Bunk Calculator:
Accurately computes how many classes you can afford to miss without dipping below your target percentage:
Safe Bunks
=
⌊
attended
target
−
held
⌋
Safe Bunks=⌊
target
attended
	​

−held⌋
🚀 Recovery Plan Calculator:
If you're below the required threshold, calculates the exact number of consecutive classes you must attend to get back to safety:
Consecutive Classes Needed
=
⌈
(
target
×
held
)
−
attended
1
−
target
⌉
Consecutive Classes Needed=⌈
1−target
(target×held)−attended
	​

⌉
🎯 Flexible Target Requirements:
Defaults to 75% (standard across Indian institutions like VTU, AKTU, Anna University, Mumbai University, IPU, etc.).
Quick presets for 60%, 65%, 70%, 75%, 80%, 85%, plus custom percentage input.
📚 Multi-Subject Tracker:
Add and manage multiple courses (e.g. Data Structures, Operating Systems, Mathematics).
Quick +1 Present and +1 Bunk action buttons on every subject card for effortless daily logging.
Overall semester weighted aggregate at the top.
🔮 "What If?" Simulator:
Interactive sliders to test "If I miss 
𝑋
X classes" or "If I attend 
𝑋
X classes".
Day-by-day simulated decision tracker.
📆 Semester-End Projection Planner:
Enter total expected classes in the semester.
Calculates remaining lectures, maximum future bunks allowed, and minimum classes you must attend.
💾 Offline Persistence & PWA Ready:
Zero server setup needed — works 100% offline via localStorage and Service Worker.
Export and import your data in JSON format.
Installable to home screen on iOS and Android.
🗂️ Project Structure
attendmate/
├── index.html            # Main responsive single-page application
├── manifest.json         # PWA Web App Manifest
├── sw.js                 # Service worker for offline caching & PWA
├── css/
│   └── styles.css        # Glassmorphism, animations, glow rings, themes
├── js/
│   ├── calculator.js     # Pure math formulas and edge case verifications
│   ├── storage.js        # LocalStorage persistence, sample data & backup
│   └── app.js            # UI state controller and event bindings
└── README.md             # Documentation & instructions
🧮 Mathematical Verification
Example 1 (Safe Zone)

A student attended 52 of 64 classes with a 75% requirement:

Current %
=
52
64
×
100
=
81.25
%
Current %=
64
52
	​

×100=81.25%
Safe skips
=
⌊
52
0.75
−
64
⌋
=
⌊
69.333
−
64
⌋
=
5
Safe skips=⌊
0.75
52
	​

−64⌋=⌊69.333−64⌋=5
Verification: Missing 5 classes 
→
52
/
(
64
+
5
)
=
75.36
%
≥
75
%
→52/(64+5)=75.36%≥75%. Missing 6 classes 
→
52
/
70
=
74.28
%
<
75
%
→52/70=74.28%<75%.
Example 2 (Shortage Recovery)

A student attended 55 of 80 classes with a 75% requirement:

Current %
=
55
80
×
100
=
68.75
%
Current %=
80
55
	​

×100=68.75%
Consecutive needed
=
⌈
(
0.75
×
80
)
−
55
1
−
0.75
⌉
=
⌈
60
−
55
0.25
⌉
=
20
Consecutive needed=⌈
1−0.75
(0.75×80)−55
	​

⌉=⌈
0.25
60−55
	​

⌉=20
Verification: Attending 20 consecutive classes 
→
(
55
+
20
)
/
(
80
+
20
)
=
75
/
100
=
75.00
%
→(55+20)/(80+20)=75/100=75.00%.
🚀 How to Run Locally

Because AttendMate is built with modern ES6 standards, you can run it with any local static HTTP server:

Option 1: Python 3 (Quickest)

Run the built-in HTTP server from the project directory:

bash
cd /Users/pankaj/.gemini/antigravity/scratch/attendmate
python3 -m http.server 3000

Then open http://localhost:3000 in your mobile browser or desktop browser.

Option 2: Node / npx (if Node is installed)
bash
npx serve /Users/pankaj/.gemini/antigravity/scratch/attendmate
Option 3: VS Code Live Server

Right-click index.html in VS Code and select "Open with Live Server".

📋 Sample Demo Data Included

Click "Demo Data" inside the app to instantly preload standard B.Tech/B.E semester courses:

Data Structures & Algorithms (Held: 42, Attended: 36, Target: 75% 
→
→ 85.7%, 6 safe bunks)
Operating Systems (Held: 38, Attended: 26, Target: 75% 
→
→ 68.4%, needs 10 consecutive classes)
Database Management Systems (Held: 36, Attended: 27, Target: 75% 
→
→ 75.0%, at limit)
Computer Networks (Held: 40, Attended: 33, Target: 75% 
→
→ 82.5%, 4 safe bunks)
Discrete Mathematics (Held: 30, Attended: 24, Target: 75% 
→
→ 80.0%, 2 safe bunks)
⚠️ Institutional Policy Disclaimer

Attendance rules, minimum criteria (e.g. medical leave condonation, lab vs theory weightage, duty leaves) differ by university, department, and course. Always confirm your college's official handbook and ERP portal.
