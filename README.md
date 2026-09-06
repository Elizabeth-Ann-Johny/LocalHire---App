<div align="center">

<h1>📍 LocalHire</h1>

<p><b>A hyperlocal hiring platform connecting nearby employers with workers.</b></p>

<p>Employers post jobs with location, pay, and requirements. Workers browse, apply, and chat with employers in real time — all backed by Firebase.</p>

<a href="https://flutter.dev"><img src="https://img.shields.io/badge/Flutter-02569B?style=flat&logo=flutter&logoColor=white" alt="Flutter"></a>
<a href="https://firebase.google.com"><img src="https://img.shields.io/badge/Firebase-FFCA28?style=flat&logo=firebase&logoColor=black" alt="Firebase"></a>
<a href="https://nodejs.org"><img src="https://img.shields.io/badge/Node.js-24-339933?style=flat&logo=node.js&logoColor=white" alt="Node.js"></a>
<a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License: MIT"></a>

</div>

<hr>

<h2>📖 Table of Contents</h2>

<ul>
<li><a href="#-features">Features</a></li>
<li><a href="#-tech-stack">Tech Stack</a></li>
<li><a href="#-repo-structure">Repo Structure</a></li>
<li><a href="#-getting-started">Getting Started</a></li>
<li><a href="#-documentation">Documentation</a></li>
<li><a href="#-contributing">Contributing</a></li>
<li><a href="#-license">License</a></li>
</ul>

<hr>

<h2 id="-features">✨ Features</h2>

<table>
<tr><td>🔐 <b>Auth</b></td><td>Phone/OTP login with a guided profile-completion flow</td></tr>
<tr><td>📝 <b>Job posting</b></td><td>Multi-step flow — location, category, pay, requirements, photos</td></tr>
<tr><td>🔍 <b>Job discovery</b></td><td>Browse, save, and apply to jobs</td></tr>
<tr><td>💬 <b>Real-time chat</b></td><td>In-app messaging between employers and workers</td></tr>
<tr><td>🔔 <b>Push notifications</b></td><td>Firebase Cloud Messaging, triggered by Cloud Functions</td></tr>
<tr><td>📍 <b>Location-aware search</b></td><td>Google Maps / Places integration</td></tr>
<tr><td>🛠️ <b>Admin dashboard</b></td><td>Separate Flutter app for platform moderation</td></tr>
</table>

<hr>

<h2 id="-tech-stack">🧰 Tech Stack</h2>

<p><b>Client</b><br>
<code>Flutter</code> · <code>Dart</code> · <code>google_maps_flutter</code> · <code>geolocator</code> · <code>image_picker</code> · <code>share_plus</code></p>

<p><b>Backend</b><br>
<code>Firebase Authentication</code> · <code>Cloud Firestore</code> · <code>Firebase Storage</code> · <code>Cloud Messaging</code></p>

<p><b>Serverless</b><br>
<code>Firebase Cloud Functions</code> (Node.js 24, <code>firebase-admin</code> / <code>firebase-functions</code>)</p>

<hr>

<h2 id="-repo-structure">📁 Repo Structure</h2>

<pre><code>LocalHire/
├── frontend/localhire/     # Main Flutter app (job seekers & employers)
├── admin_dashboard/        # Flutter admin app
├── functions/              # Firebase Cloud Functions (Node.js)
├── docs/                   # Project documentation
├── firebase.json           # Firebase deploy config
├── cors.json.txt           # Storage CORS rules — rename to cors.json before use
├── .firebaserc
└── LICENSE
</code></pre>

<hr>

<h2 id="-getting-started">🚀 Getting Started</h2>

<h3>Prerequisites</h3>

<ul>
<li><a href="https://docs.flutter.dev/get-started/install">Flutter SDK</a> (Dart SDK <code>^3.10.8</code>)</li>
<li><a href="https://firebase.google.com/docs/cli">Firebase CLI</a> — <code>npm install -g firebase-tools</code></li>
<li>Node.js 24 (for Cloud Functions)</li>
<li>A Firebase project with Authentication, Firestore, Storage, and Cloud Messaging enabled</li>
<li>A Google Maps / Places API key</li>
</ul>

<h3>1. Clone the repo</h3>

<pre><code>git clone https://github.com/Elizabeth-Ann-Johny/LocalHire.git
cd LocalHire
</code></pre>

<h3>2. Configure Firebase for each app</h3>

<pre><code>firebase login
cd frontend/localhire
flutterfire configure --project=&lt;your-firebase-project-id&gt;
</code></pre>

<p>Repeat inside <code>admin_dashboard/</code>. This generates <code>lib/firebase_options.dart</code> and the platform config files (<code>google-services.json</code>, <code>GoogleService-Info.plist</code>).</p>

<blockquote>⚠️ This repo currently has <code>google-services.json</code> and <code>firebase_options.dart</code> committed for convenience. If you fork this for your own Firebase backend, regenerate these with your own project rather than reusing the committed ones.</blockquote>

<h3>3. Run the mobile app</h3>

<pre><code>cd frontend/localhire
flutter pub get
flutter run
</code></pre>

<h3>4. Run the admin dashboard</h3>

<pre><code>cd admin_dashboard
flutter pub get
flutter run
</code></pre>

<h3>5. Run / deploy Cloud Functions</h3>

<pre><code>cd functions
npm install
npm run serve     # local emulator
npm run deploy     # deploy to Firebase
</code></pre>

<h3>6. Storage CORS config</h3>

<p><code>cors.json.txt</code> at the repo root holds CORS rules for Firebase Storage. Rename it to <code>cors.json</code> before applying it:</p>

<pre><code>mv cors.json.txt cors.json
gsutil cors set cors.json gs://&lt;your-storage-bucket&gt;
</code></pre>

<hr>

<h2 id="-documentation">📚 Documentation</h2>

<p>The <a href="docs">docs/</a> folder holds the project's written documentation.</p>

<hr>

<h2 id="-contributing">🤝 Contributing</h2>

<p>This is a personal/closed project and isn't currently open to outside contributions or pull requests.</p>

<hr>

<h2 id="-license">📄 License</h2>

<p>Distributed under the MIT License. See <a href="LICENSE">LICENSE</a> for details.</p>

