<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>M. Nafees | Professional Portfolio</title>
    <!-- FontAwesome for Premium Icons -->
    <link rel="stylesheet" href="https://cloudflare.com">
    <style>
        :root {
            --bg-dark: #0b0f19;
            --card-bg: #1e2538;
            --primary: #00f2fe;
            --secondary: #4facfe;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --whatsapp-color: #25D366;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Roboto, sans-serif; }
        body { background-color: var(--bg-dark); color: var(--text-main); line-height: 1.6; overflow-x: hidden; }

        /* Premium Glow Header */
        header { 
            background: radial-gradient(circle at top right, rgba(79, 172, 254, 0.15), transparent), var(--bg-dark);
            padding: 100px 20px 80px 20px; 
            text-align: center; 
            position: relative;
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }
        .profile-container { margin-bottom: 20px; }
        .profile-icon { font-size: 4rem; color: var(--primary); margin-bottom: 15px; animation: pulse 2s infinite; }
        header h1 { font-size: 3.5rem; margin-bottom: 15px; background: linear-gradient(to right, var(--primary), var(--secondary)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; font-weight: 800; letter-spacing: -1px; }
        
        /* JavaScript Typing Dynamic Style */
        .typing-text { font-size: 1.4rem; color: var(--text-muted); font-weight: 400; min-height: 40px; }
        .cursor { display: inline-block; width: 3px; background-color: var(--primary); animation: blink 0.8s infinite; margin-left: 5px; }

        .container { max-width: 900px; margin: 0 auto; padding: 40px 20px; }
        
        /* Modern Glass Cards */
        section { 
            background: rgba(30, 37, 56, 0.6); 
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            padding: 40px; 
            margin-bottom: 35px; 
            border-radius: 16px; 
            border: 1px solid rgba(255, 255, 255, 0.08); 
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            transition: transform 0.3s ease, border-color 0.3s ease;
        }
        section:hover { transform: translateY(-5px); border-color: rgba(0, 242, 254, 0.3); }
        
        h2 { color: var(--primary); margin-bottom: 25px; font-size: 1.8rem; display: flex; align-items: center; gap: 12px; }
        h2 i { font-size: 1.5rem; color: var(--secondary); }

        /* Tab Filter Buttons (JavaScript Powered) */
        .filter-tabs { display: flex; gap: 10px; margin-bottom: 25px; }
        .tab-btn { background: rgba(255,255,255,0.05); border: 1px solid rgba(255,255,255,0.1); color: var(--text-main); padding: 8px 18px; border-radius: 20px; cursor: pointer; font-weight: 500; transition: 0.3s; }
        .tab-btn.active, .tab-btn:hover { background: var(--primary); color: var(--bg-dark); box-shadow: 0 0 15px rgba(0, 242, 254, 0.4); border-color: var(--primary); }

        /* Modern Skills Badges */
        .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; }
        .skill-box { background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.05); padding: 20px; border-radius: 12px; text-align: center; transition: 0.3s; }
        .skill-box:hover { background: rgba(255,255,255,0.05); }
        .skill-box i { font-size: 2.2rem; margin-bottom: 12px; display: block; }
        .skill-box.wp i { color: #21759b; }
        .skill-box.py i { color: #3776ab; }
        .skill-box.db i { color: #336791; }
        .skill-box.web i { color: #e34c26; }

        /* Project Cards */
        .project-card { background: rgba(11, 15, 25, 0.7); padding: 25px; border-radius: 12px; border-left: 4px solid var(--secondary); margin-bottom: 20px; transition: 0.3s; }
        .project-card:hover { transform: scale(1.02); }
        .project-card h3 { margin-bottom: 8px; color: #fff; font-size: 1.3rem; }
        .project-tags { display: flex; gap: 8px; margin-top: 12px; }
        .tag { font-size: 0.75rem; background: rgba(79, 172, 254, 0.15); color: var(--secondary); padding: 3px 10px; border-radius: 4px; font-weight: 600; }

        /* Social Connect Buttons */
        .social-grid { display: flex; flex-wrap: wrap; gap: 15px; }
        .btn { display: inline-flex; align-items: center; gap: 10px; padding: 12px 28px; border-radius: 8px; font-weight: 600; text-decoration: none; font-size: 1rem; transition: all 0.3s ease; cursor: pointer; border: none; }
        .btn-primary { background: linear-gradient(to right, var(--primary), var(--secondary)); color: var(--bg-dark); box-shadow: 0 4px 15px rgba(0, 242, 254, 0.3); }
        .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 6px 20px rgba(0, 242, 254, 0.5); }
        .btn-secondary { background: rgba(255,255,255,0.05); color: var(--text-main); border: 1px solid rgba(255,255,255,0.1); }
        .btn-secondary:hover { background: rgba(255,255,255,0.1); transform: translateY(-3px); }

        /* Floating Interactive WhatsApp Widget */
        .whatsapp-float {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background-color: var(--whatsapp-color);
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            text-align: center;
            font-size: 30px;
            box-shadow: 0 4px 20px rgba(37, 211, 102, 0.4);
            z-index: 100;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            transition: all 0.3s ease;
            animation: bounce 2s infinite;
        }
        .whatsapp-float:hover {
            transform: scale(1.1) rotate(10deg);
            box-shadow: 0 6px 25px rgba(37, 211, 102, 0.6);
        }

        /* Animations */
        @keyframes blink { 50% { opacity: 0; } }
        @keyframes pulse { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.05); opacity: 0.9; } }
        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }

        @media(max-width: 768px) {
            header h1 { font-size: 2.5rem; }
            section { padding: 25px; }
        }
    </style>
</head>
<body>

    <!-- Floating WhatsApp Option (JavaScript Linked) -->
    <!-- APNA WHATSAPP NUMBER Upar 'phone=' ke baad likhein (Format: 923XXXXXXXXX) -->
    <a href="https://wa.me!" class="whatsapp-float" target="_blank" title="Chat on WhatsApp">
        <i class="fab fa-whatsapp"></i>
    </a>

    <header>
        <div class="profile-container">
            <i class="fa-solid fa-laptop-code profile-icon"></i>
        </div>
        <h1>Muhammad Nafees</h1>
        <!-- JavaScript typing container -->
        <div class="typing-text">I am a <span id="dynamic-text"></span><span class="cursor">|</span></div>
    </header>

    <div class="container">
        
        <!-- About Me Section -->
        <section>
            <h2><i class="fa-regular fa-user"></i> About Me</h2>
            <p>I am an innovative Full-Stack Engineer and CMS Expert specializing in modern backend architectures and pixel-perfect frontends. Proficient in automated systems and relational database modeling, I build reliable, optimized web apps engineered for performance.</p>
        </section>

        <!-- Skills Section with Luxury Badges -->
        <section>
            <h2><i class="fa-solid fa-gears"></i> Core Competencies</h2>
            <div class="skills-grid">
                <div class="skill-box py">
                    <i class="fab fa-python"></i>
                    <h3>FastAPI</h3>
                    <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 5px;">Python Web Backends</p>
                </div>
                <div class="skill-box wp">
                    <i class="fab fa-wordpress"></i>
                    <h3>WordPress</h3>
                    <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 5px;">CMS Customization</p>
                </div>
                <div class="skill-box db">
                    <i class="fa-solid fa-database"></i>
                    <h3>Databases</h3>
                    <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 5px;">PostgreSQL / MySQL</p>
                </div>
                <div class="skill-box web">
                    <i class="fa-solid fa-code"></i>
                    <h3>Frontend & Git</h3>
                    <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 5px;">HTML5, CSS3, GitHub</p>
                </div>
            </div>
        </section>

        <!-- Interactive Projects Section (JavaScript Filter) -->
        <section>
            <h2><i class="fa-solid fa-briefcase"></i> Featured Projects</h2>
            
            <!-- JS Interactive Category Filter -->
            <div class="filter-tabs">
                <button class="tab-btn active" onclick="filterProjects('all')">All</button>
                <button class="tab-btn" onclick="filterProjects('backend')">Backend / Python</button>
                <button class="tab-btn" onclick="filterProjects('cms')">WordPress / Web</button>
            </div>

            <div id="projects-container">
                <div class="project-card" data-category="backend">
                    <h3>Secure Rest API Endpoint Architecture</h3>
# mnafeesofficial1.github.io
