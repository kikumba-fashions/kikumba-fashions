<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crax - Next-Gen Social Experience</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #FF6B6B;
            --secondary: #4ECDC4;
            --accent: #FFE66D;
            --dark: #2D3047;
            --light: #F7FFF7;
            --gradient: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', sans-serif;
        }

        body {
            background: var(--light);
            color: var(--dark);
        }

        /* AI Firewall System (Level 4) */
        .firewall-alert {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--dark);
            color: white;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            display: none;
            z-index: 1000;
        }

        /* Main Layout */
        .container {
            display: grid;
            grid-template-columns: 280px 1fr 320px;
            min-height: 100vh;
            max-width: 2000px;
            margin: 0 auto;
        }

        /* Left Navigation */
        .side-nav {
            background: white;
            padding: 2rem 1.5rem;
            border-right: 1px solid #eee;
            position: sticky;
            top: 0;
            height: 100vh;
        }

        .logo {
            font-size: 2rem;
            font-weight: 800;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 2rem;
        }

        .nav-menu {
            list-style: none;
            margin: 2rem 0;
        }

        .nav-item {
            margin: 1rem 0;
            padding: 1rem;
            border-radius: 12px;
            transition: 0.3s ease;
            cursor: pointer;
        }

        .nav-item:hover {
            background: #f5f5f5;
        }

        .nav-item.active {
            background: var(--gradient);
            color: white;
        }

        /* Main Content */
        .main-content {
            padding: 2rem;
            background: #fafafa;
        }

        .story-carousel {
            display: flex;
            gap: 1.5rem;
            padding: 1rem 0;
            overflow-x: auto;
        }

        .story-card {
            min-width: 120px;
            height: 200px;
            border-radius: 16px;
            background: white;
            position: relative;
            overflow: hidden;
            flex-shrink: 0;
        }

        .create-story {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            border: 2px dashed #ddd;
        }

        /* Video Upload Section */
        .video-upload-box {
            background: white;
            border-radius: 16px;
            padding: 2rem;
            margin: 2rem 0;
            box-shadow: 0 2px 12px rgba(0,0,0,0.08);
        }

        .upload-options {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .upload-option {
            padding: 1.5rem;
            border: 2px solid #eee;
            border-radius: 12px;
            text-align: center;
            cursor: pointer;
            transition: 0.3s ease;
        }

        .upload-option:hover {
            border-color: var(--primary);
            background: #fff5f5;
        }

        /* AI Assistant */
        .ai-assistant {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 1000;
        }

        .ai-bubble {
            width: 60px;
            height: 60px;
            background: var(--gradient);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Right Sidebar */
        .right-sidebar {
            padding: 2rem 1.5rem;
            background: white;
            border-left: 1px solid #eee;
        }

        .live-streams {
            margin-top: 2rem;
        }

        .stream-card {
            background: var(--dark);
            color: white;
            border-radius: 12px;
            overflow: hidden;
            margin-bottom: 1rem;
        }

        /* Responsive Design */
        @media (max-width: 1200px) {
            .container {
                grid-template-columns: 80px 1fr;
            }
            .right-sidebar {
                display: none;
            }
        }

        @media (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
            }
            .side-nav {
                display: none;
            }
        }
    </style>
</head>
<body>
    <!-- AI Firewall Alert -->
    <div class="firewall-alert">
        <i class="fas fa-shield-alt"></i> AI Firewall Active - Threat Detected
    </div>

    <div class="container">
        <!-- Left Navigation -->
        <nav class="side-nav">
            <div class="logo">Crax</div>
            <ul class="nav-menu">
                <li class="nav-item active">
                    <i class="fas fa-home"></i> Home
                </li>
                <li class="nav-item">
                    <i class="fas fa-compass"></i> Explore
                </li>
                <li class="nav-item">
                    <i class="fas fa-video"></i> Live
                </li>
                <li class="nav-item">
                    <i class="fas fa-comments"></i> Messages
                </li>
                <li class="nav-item">
                    <i class="fas fa-user-friends"></i> Network
                </li>
            </ul>
        </nav>

        <!-- Main Content -->
        <main class="main-content">
            <!-- Stories -->
            <div class="story-carousel">
                <div class="story-card create-story">
                    <i class="fas fa-plus"></i>
                    <span>Create Story</span>
                </div>
                <!-- Story cards would be dynamically generated -->
            </div>

            <!-- Video Upload -->
            <div class="video-upload-box">
                <h2>Create New Post</h2>
                <div class="upload-options">
                    <div class="upload-option" onclick="openUpload('video')">
                        <i class="fas fa-video"></i>
                        <p>Upload Video</p>
                    </div>
                    <div class="upload-option" onclick="openUpload('live')">
                        <i class="fas fa-broadcast-tower"></i>
                        <p>Go Live</p>
                    </div>
                    <div class="upload-option" onclick="openUpload('audio')">
                        <i class="fas fa-microphone"></i>
                        <p>Audio Message</p>
                    </div>
                </div>
            </div>

            <!-- Video Feed -->
            <div class="video-feed">
                <!-- Video posts would be dynamically loaded -->
            </div>
        </main>

        <!-- Right Sidebar -->
        <aside class="right-sidebar">
            <h3>Live Now</h3>
            <div class="live-streams">
                <div class="stream-card">
                    <div class="stream-preview"></div>
                    <div class="stream-info">
                        <h4>User123 Live</h4>
                        <p>500 viewers</p>
                    </div>
                </div>
            </div>
        </aside>
    </div>

    <!-- AI Assistant -->
    <div class="ai-assistant">
        <div class="ai-bubble">
            <i class="fas fa-robot"></i>
        </div>
    </div>

    <script>
        // AI Firewall System
        const threats = ['malicious-link', 'suspicious-content', 'data-leak'];
        setInterval(() => {
            const randomThreat = threats[Math.floor(Math.random() * threats.length)];
            document.querySelector('.firewall-alert').style.display = 'block';
            setTimeout(() => {
                document.querySelector('.firewall-alert').style.display = 'none';
            }, 3000);
        }, 15000);

        // Video Upload Functionality
        function openUpload(type) {
            // AI Content Analysis
            const aiAnalysis = confirm(`Crax AI is analyzing your ${type}... Continue?`);
            if (aiAnalysis) {
                // Handle upload logic
            }
        }

        // Real-time Messaging
        class ChatSystem {
            constructor() {
                this.messages = [];
                this.aiEnabled = true;
            }

            async sendMessage(message) {
                if (this.aiEnabled) {
                    // AI Content Moderation
                    const safe = await this.analyzeMessage(message);
                    if (safe) {
                        this.messages.push(message);
                    }
                }
            }

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crax - Next-Gen Social Experience</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #FF6B6B;
            --secondary: #4ECDC4;
            --accent: #FFE66D;
            --dark: #2D3047;
            --light: #F7FFF7;
            --gradient: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', sans-serif;
        }

        body {
            background: var(--light);
            color: var(--dark);
        }

        /* AI Firewall System (Level 4) */
        .firewall-alert {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--dark);
            color: white;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            display: none;
            z-index: 1000;
        }

        /* Main Layout */
        .container {
            display: grid;
            grid-template-columns: 280px 1fr 320px;
            min-height: 100vh;
            max-width: 2000px;
            margin: 0 auto;
        }

        /* Left Navigation */
        .side-nav {
            background: white;
            padding: 2rem 1.5rem;
            border-right: 1px solid #eee;
            position: sticky;
            top: 0;
            height: 100vh;
        }

        .logo {
            font-size: 2rem;
            font-weight: 800;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 2rem;
        }

        .nav-menu {
            list-style: none;
            margin: 2rem 0;
        }

        .nav-item {
            margin: 1rem 0;
            padding: 1rem;
            border-radius: 12px;
            transition: 0.3s ease;
            cursor: pointer;
        }

        .nav-item:hover {
            background: #f5f5f5;
        }

        .nav-item.active {
            background: var(--gradient);
            color: white;
        }

        /* Main Content */
        .main-content {
            padding: 2rem;
            background: #fafafa;
        }

        .story-carousel {
            display: flex;
            gap: 1.5rem;
            padding: 1rem 0;
            overflow-x: auto;
        }

        .story-card {
            min-width: 120px;
            height: 200px;
            border-radius: 16px;
            background: white;
            position: relative;
            overflow: hidden;
            flex-shrink: 0;
        }

        .create-story {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            border: 2px dashed #ddd;
        }

        /* Video Upload Section */
        .video-upload-box {
            background: white;
            border-radius: 16px;
            padding: 2rem;
            margin: 2rem 0;
            box-shadow: 0 2px 12px rgba(0,0,0,0.08);
        }

        .upload-options {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .upload-option {
            padding: 1.5rem;
            border: 2px solid #eee;
            border-radius: 12px;
            text-align: center;
            cursor: pointer;
            transition: 0.3s ease;
        }

        .upload-option:hover {
            border-color: var(--primary);
            background: #fff5f5;
        }

        /* AI Assistant */
        .ai-assistant {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 1000;
        }

        .ai-bubble {
            width: 60px;
            height: 60px;
            background: var(--gradient);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Right Sidebar */
        .right-sidebar {
            padding: 2rem 1.5rem;
            background: white;
            border-left: 1px solid #eee;
        }

        .live-streams {
            margin-top: 2rem;
        }

        .stream-card {
            background: var(--dark);
            color: white;
            border-radius: 12px;
            overflow: hidden;
            margin-bottom: 1rem;
        }

        /* Responsive Design */
        @media (max-width: 1200px) {
            .container {
                grid-template-columns: 80px 1fr;
            }
            .right-sidebar {
                display: none;
            }
        }

        @media (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
            }
            .side-nav {
                display: none;
            }
        }
    </style>
</head>
<body>
    <!-- AI Firewall Alert -->
    <div class="firewall-alert">
        <i class="fas fa-shield-alt"></i> AI Firewall Active - Threat Detected
    </div>

    <div class="container">
        <!-- Left Navigation -->
        <nav class="side-nav">
            <div class="logo">Crax</div>
            <ul class="nav-menu">
                <li class="nav-item active">
                    <i class="fas fa-home"></i> Home
                </li>
                <li class="nav-item">
                    <i class="fas fa-compass"></i> Explore
                </li>
                <li class="nav-item">
                    <i class="fas fa-video"></i> Live
                </li>
                <li class="nav-item">
                    <i class="fas fa-comments"></i> Messages
                </li>
                <li class="nav-item">
                    <i class="fas fa-user-friends"></i> Network
                </li>
            </ul>
        </nav>

        <!-- Main Content -->
        <main class="main-content">
            <!-- Stories -->
            <div class="story-carousel">
                <div class="story-card create-story">
                    <i class="fas fa-plus"></i>
                    <span>Create Story</span>
                </div>
                <!-- Story cards would be dynamically generated -->
            </div>

            <!-- Video Upload -->
            <div class="video-upload-box">
                <h2>Create New Post</h2>
                <div class="upload-options">
                    <div class="upload-option" onclick="openUpload('video')">
                        <i class="fas fa-video"></i>
                        <p>Upload Video</p>
                    </div>
                    <div class="upload-option" onclick="openUpload('live')">
                        <i class="fas fa-broadcast-tower"></i>
                        <p>Go Live</p>
                    </div>
                    <div class="upload-option" onclick="openUpload('audio')">
                        <i class="fas fa-microphone"></i>
                        <p>Audio Message</p>
                    </div>
                </div>
            </div>

            <!-- Video Feed -->
            <div class="video-feed">
                <!-- Video posts would be dynamically loaded -->
            </div>
        </main>

        <!-- Right Sidebar -->
        <aside class="right-sidebar">
            <h3>Live Now</h3>
            <div class="live-streams">
                <div class="stream-card">
                    <div class="stream-preview"></div>
                    <div class="stream-info">
                        <h4>User123 Live</h4>
                        <p>500 viewers</p>
                    </div>
                </div>
            </div>
        </aside>
    </div>

    <!-- AI Assistant -->
    <div class="ai-assistant">
        <div class="ai-bubble">
            <i class="fas fa-robot"></i>
        </div>
    </div>

    <script>
        // AI Firewall System
        const threats = ['malicious-link', 'suspicious-content', 'data-leak'];
        setInterval(() => {
            const randomThreat = threats[Math.floor(Math.random() * threats.length)];
            document.querySelector('.firewall-alert').style.display = 'block';
            setTimeout(() => {
                document.querySelector('.firewall-alert').style.display = 'none';
            }, 3000);
        }, 15000);

        // Video Upload Functionality
        function openUpload(type) {
            // AI Content Analysis
            const aiAnalysis = confirm(`Crax AI is analyzing your ${type}... Continue?`);
            if (aiAnalysis) {
                // Handle upload logic
            }
        }

        // Real-time Messaging
        class ChatSystem {
            constructor() {
                this.messages = [];
                this.aiEnabled = true;
            }

            async sendMessage(message) {
                if (this.aiEnabled) {
                    // AI Content Moderation
                    const safe = await this.analyzeMessage(message);
                    if (safe) {
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crax - Next-Gen Social Experience</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #FF6B6B;
            --secondary: #4ECDC4;
            --accent: #FFE66D;
            --dark: #2D3047;
            --light: #F7FFF7;
            --gradient: linear-gradient(135deg, #FF6B6B 0%, #4ECDC4 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', sans-serif;
        }

        body {
            background: var(--light);
            color: var(--dark);
        }

        /* AI Firewall System (Level 4) */
        .firewall-alert {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--dark);
            color: white;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            display: none;
            z-index: 1000;
        }

        /* Main Layout */
        .container {
            display: grid;
            grid-template-columns: 280px 1fr 320px;
            min-height: 100vh;
            max-width: 2000px;
            margin: 0 auto;
        }

        /* Left Navigation */
        .side-nav {
            background: white;
            padding: 2rem 1.5rem;
            border-right: 1px solid #eee;
            position: sticky;
            top: 0;
            height: 100vh;
        }

        .logo {
            font-size: 2rem;
            font-weight: 800;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 2rem;
        }

        .nav-menu {
            list-style: none;
            margin: 2rem 0;
        }

        .nav-item {
            margin: 1rem 0;
            padding: 1rem;
            border-radius: 12px;
            transition: 0.3s ease;
            cursor: pointer;
        }

        .nav-item:hover {
            background: #f5f5f5;
        }

        .nav-item.active {
            background: var(--gradient);
            color: white;
        }

        /* Main Content */
        .main-content {
            padding: 2rem;
            background: #fafafa;
        }

        .story-carousel {
            display: flex;
            gap: 1.5rem;
            padding: 1rem 0;
            overflow-x: auto;
        }

        .story-card {
            min-width: 120px;
            height: 200px;
            border-radius: 16px;
            background: white;
            position: relative;
            overflow: hidden;
            flex-shrink: 0;
        }

        .create-story {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            border: 2px dashed #ddd;
        }

        /* Video Upload Section */
        .video-upload-box {
            background: white;
            border-radius: 16px;
            padding: 2rem;
            margin: 2rem 0;
            box-shadow: 0 2px 12px rgba(0,0,0,0.08);
        }

        .upload-options {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .upload-option {
            padding: 1.5rem;
            border: 2px solid #eee;
            border-radius: 12px;
            text-align: center;
            cursor: pointer;
            transition: 0.3s ease;
        }

        .upload-option:hover {
            border-color: var(--primary);
            background: #fff5f5;
        }

        /* AI Assistant */
        .ai-assistant {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 1000;
        }

        .ai-bubble {
            width: 60px;
            height: 60px;
            background: var(--gradient);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Right Sidebar */
        .right-sidebar {
            padding: 2rem 1.5rem;
            background: white;
            border-left: 1px solid #eee;
        }

        .live-streams {
            margin-top: 2rem;
        }

        .stream-card {
            background: var(--dark);
            color: white;
            border-radius: 12px;
            overflow: hidden;
            margin-bottom: 1rem;
        }

        /* Responsive Design */
        @media (max-width: 1200px) {
            .container {
                grid-template-columns: 80px 1fr;
            }
            .right-sidebar {
                display: none;
            }
        }

        @media (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
            }
            .side-nav {
                display: none;
            }
        }
    </style>
</head>
<body>
    <!-- AI Firewall Alert -->
    <div class="firewall-alert">
        <i class="fas fa-shield-alt"></i> AI Firewall Active - Threat Detected
    </div>

    <div class="container">
        <!-- Left Navigation -->
        <nav class="side-nav">
            <div class="logo">Crax</div>
            <ul class="nav-menu">
                <li class="nav-item active">
                    <i class="fas fa-home"></i> Home
                </li>
                <li class="nav-item">
                    <i class="fas fa-compass"></i> Explore
                </li>
                <li class="nav-item">
                    <i class="fas fa-video"></i> Live
                </li>
                <li class="nav-item">
                    <i class="fas fa-comments"></i> Messages
                </li>
                <li class="nav-item">
                    <i class="fas fa-user-friends"></i> Network
                </li>
            </ul>
        </nav>

        <!-- Main Content -->
        <main class="main-content">
            <!-- Stories -->
            <div class="story-carousel">
                <div class="story-card create-story">
                    <i class="fas fa-plus"></i>
                    <span>Create Story</span>
                </div>
                <!-- Story cards would be dynamically generated -->
            </div>

            <!-- Video Upload -->
            <div class="video-upload-box">
                <h2>Create New Post</h2>
                <div class="upload-options">
                    <div class="upload-option" onclick="openUpload('video')">
                        <i class="fas fa-video"></i>
                        <p>Upload Video</p>
                    </div>
                    <div class="upload-option" onclick="openUpload('live')">
                        <i class="fas fa-broadcast-tower"></i>
                        <p>Go Live</p>
                    </div>
                    <div class="upload-option" onclick="openUpload('audio')">
                        <i class="fas fa-microphone"></i>
                        <p>Audio Message</p>
                    </div>
                </div>
            </div>

            <!-- Video Feed -->
            <div class="video-feed">
                <!-- Video posts would be dynamically loaded -->
            </div>
        </main>

        <!-- Right Sidebar -->
        <aside class="right-sidebar">
            <h3>Live Now</h3>
            <div class="live-streams">
                <div class="stream-card">
                    <div class="stream-preview"></div>
                    <div class="stream-info">
                        <h4>User123 Live</h4>
                        <p>500 viewers</p>
                    </div>
                </div>
            </div>
        </aside>
    </div>

    <!-- AI Assistant -->
    <div class="ai-assistant">
        <div class="ai-bubble">
            <i class="fas fa-robot"></i>
        </div>
    </div>

    <script>
        // AI Firewall System
        const threats = ['malicious-link', 'suspicious-content', 'data-leak'];
        setInterval(() => {
            const randomThreat = threats[Math.floor(Math.random() * threats.length)];
            document.querySelector('.firewall-alert').style.display = 'block';
            setTimeout(() => {
                document.querySelector('.firewall-alert').style.display = 'none';
            }, 3000);
        }, 15000);

        // Video Upload Functionality
        function openUpload(type) {
            // AI Content Analysis
            const aiAnalysis = confirm(`Crax AI is analyzing your ${type}... Continue?`);
            if (aiAnalysis) {
                // Handle upload logic
            }
        }

        // Real-time Messaging
        class ChatSystem {
            constructor() {
                this.messages = [];
                this.aiEnabled = true;
            }

            async sendMessage(message) {
                if (this.aiEnabled) {
                    // AI Content Moderation
                    const safe = await this.analyzeMessage(message);
                    if (safe) {
                        this.messages.push(message);
                    }
                }
            }

            async analyzeMessage(text) {
                // Simulated AI analysis
                return !text.includes('spam');
            }
        }

        // Responsive Design Check
        window.addEventListener('resize', () => {
            if (window.innerWidth < 768) {
                document.querySelector('.side-nav').style.display = 'none';
            } else {
                document.querySelector('.side-nav').style.display = 'block';
            }
        });
    </script>
</body>
</html>this.aiEnabled0this.messages
