<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sahal Abshir · Developer & Community Manager</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Inter:wght@300;400;500;600;700&family=Space+Grotesk:wght@300;400;500;600;700&family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=DM+Serif+Display:ital@0;1&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1.5rem;
            line-height: 1.6;
            color: #e2e8f0;
            position: relative;
            overflow-y: auto;
            background: #0a0e1a;
        }

        /* ============================================================
           MOVING BACKGROUND
           ============================================================ */
        .moving-bg {
            position: fixed;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            z-index: 0;
            background: conic-gradient(
                from 0deg,
                #0f172a,
                #1e1b4b,
                #312e81,
                #4c1d95,
                #6d28d9,
                #7c3aed,
                #4c1d95,
                #312e81,
                #1e1b4b,
                #0f172a
            );
            animation: rotateBg 30s linear infinite;
        }

        @keyframes rotateBg {
            0% { transform: rotate(0deg) scale(1); }
            50% { transform: rotate(180deg) scale(1.3); }
            100% { transform: rotate(360deg) scale(1); }
        }

        /* ============================================================
           GLOWING ORBS
           ============================================================ */
        .glow-orb {
            position: fixed;
            border-radius: 50%;
            pointer-events: none;
            z-index: 0;
            filter: blur(80px);
            animation: orbFloat 18s ease-in-out infinite;
        }

        .glow-orb:nth-child(1) {
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, #3b82f6, transparent 70%);
            top: -100px;
            left: -100px;
            animation-delay: 0s;
            opacity: 0.5;
        }

        .glow-orb:nth-child(2) {
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, #8b5cf6, transparent 70%);
            bottom: -150px;
            right: -150px;
            animation-delay: 6s;
            opacity: 0.4;
        }

        .glow-orb:nth-child(3) {
            width: 350px;
            height: 350px;
            background: radial-gradient(circle, #ec4899, transparent 70%);
            top: 40%;
            left: 60%;
            animation-delay: 12s;
            opacity: 0.35;
        }

        .glow-orb:nth-child(4) {
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, #f59e0b, transparent 70%);
            top: 70%;
            left: 10%;
            animation-delay: 3s;
            opacity: 0.3;
        }

        .glow-orb:nth-child(5) {
            width: 280px;
            height: 280px;
            background: radial-gradient(circle, #10b981, transparent 70%);
            top: 10%;
            left: 50%;
            animation-delay: 9s;
            opacity: 0.3;
        }

        @keyframes orbFloat {
            0%, 100% { transform: translate(0, 0) scale(1); }
            25% { transform: translate(80px, -50px) scale(1.2); }
            50% { transform: translate(-50px, 80px) scale(0.9); }
            75% { transform: translate(40px, -30px) scale(1.1); }
        }

        /* ============================================================
           FLOATING DECORATIONS - BUTTERFLIES & MORE
           ============================================================ */
        .fly-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
            overflow: hidden;
        }

        .fly {
            position: absolute;
            font-size: 1.8rem;
            animation: flyAround 20s ease-in-out infinite;
            filter: drop-shadow(0 0 10px rgba(255, 255, 255, 0.05));
            opacity: 0.5;
        }

        .fly:nth-child(1) { top: 10%; left: 5%; animation-delay: 0s; font-size: 2rem; color: rgba(147, 197, 253, 0.25); }
        .fly:nth-child(2) { top: 20%; left: 80%; animation-delay: 3s; font-size: 1.6rem; color: rgba(196, 181, 253, 0.25); }
        .fly:nth-child(3) { top: 50%; left: 10%; animation-delay: 6s; font-size: 2.2rem; color: rgba(252, 165, 165, 0.25); }
        .fly:nth-child(4) { top: 70%; left: 75%; animation-delay: 9s; font-size: 1.5rem; color: rgba(253, 230, 138, 0.25); }
        .fly:nth-child(5) { top: 35%; left: 50%; animation-delay: 12s; font-size: 1.9rem; color: rgba(167, 243, 208, 0.25); }
        .fly:nth-child(6) { top: 85%; left: 20%; animation-delay: 15s; font-size: 1.7rem; color: rgba(251, 191, 36, 0.2); }
        .fly:nth-child(7) { top: 15%; left: 40%; animation-delay: 2s; font-size: 2.1rem; color: rgba(236, 72, 153, 0.2); }
        .fly:nth-child(8) { top: 60%; left: 60%; animation-delay: 7s; font-size: 1.4rem; color: rgba(52, 211, 153, 0.2); }
        .fly:nth-child(9) { top: 45%; left: 85%; animation-delay: 10s; font-size: 1.8rem; color: rgba(96, 165, 250, 0.2); }
        .fly:nth-child(10) { top: 90%; left: 55%; animation-delay: 4s; font-size: 1.6rem; color: rgba(244, 63, 94, 0.15); }
        .fly:nth-child(11) { top: 5%; left: 65%; animation-delay: 8s; font-size: 2rem; color: rgba(139, 92, 246, 0.2); }
        .fly:nth-child(12) { top: 75%; left: 45%; animation-delay: 13s; font-size: 1.5rem; color: rgba(251, 146, 60, 0.2); }
        .fly:nth-child(13) { top: 30%; left: 30%; animation-delay: 1s; font-size: 1.7rem; color: rgba(56, 189, 248, 0.2); }
        .fly:nth-child(14) { top: 65%; left: 15%; animation-delay: 5s; font-size: 2rem; color: rgba(232, 121, 249, 0.2); }
        .fly:nth-child(15) { top: 10%; left: 90%; animation-delay: 11s; font-size: 1.6rem; color: rgba(251, 207, 232, 0.2); }

        @keyframes flyAround {
            0% { transform: translate(0, 0) rotate(0deg) scale(1); }
            10% { transform: translate(80px, -40px) rotate(15deg) scale(1.1); }
            20% { transform: translate(-60px, 50px) rotate(-10deg) scale(0.9); }
            30% { transform: translate(100px, 20px) rotate(20deg) scale(1.15); }
            40% { transform: translate(-80px, -60px) rotate(-15deg) scale(0.85); }
            50% { transform: translate(50px, 70px) rotate(10deg) scale(1.1); }
            60% { transform: translate(-100px, -20px) rotate(-20deg) scale(0.9); }
            70% { transform: translate(60px, -50px) rotate(15deg) scale(1.05); }
            80% { transform: translate(-40px, 60px) rotate(-5deg) scale(0.95); }
            90% { transform: translate(70px, 30px) rotate(5deg) scale(1.08); }
            100% { transform: translate(0, 0) rotate(0deg) scale(1); }
        }

        /* ============================================================
           FLOATING BUBBLES
           ============================================================ */
        .bubbles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
            overflow: hidden;
        }

        .bubble {
            position: absolute;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.05), transparent 70%);
            animation: bubbleFloat 15s ease-in-out infinite;
        }

        .bubble:nth-child(1) { width: 60px; height: 60px; top: 20%; left: 10%; animation-delay: 0s; }
        .bubble:nth-child(2) { width: 40px; height: 40px; top: 60%; left: 85%; animation-delay: 3s; }
        .bubble:nth-child(3) { width: 80px; height: 80px; top: 40%; left: 40%; animation-delay: 6s; }
        .bubble:nth-child(4) { width: 50px; height: 50px; top: 80%; left: 15%; animation-delay: 9s; }
        .bubble:nth-child(5) { width: 70px; height: 70px; top: 15%; left: 70%; animation-delay: 2s; }
        .bubble:nth-child(6) { width: 30px; height: 30px; top: 50%; left: 25%; animation-delay: 5s; }
        .bubble:nth-child(7) { width: 90px; height: 90px; top: 75%; left: 55%; animation-delay: 8s; }
        .bubble:nth-child(8) { width: 45px; height: 45px; top: 30%; left: 55%; animation-delay: 11s; }

        @keyframes bubbleFloat {
            0%, 100% { transform: translate(0, 0) scale(1); }
            25% { transform: translate(60px, -80px) scale(1.2); }
            50% { transform: translate(-40px, 60px) scale(0.8); }
            75% { transform: translate(30px, -40px) scale(1.1); }
        }

        /* ============================================================
           STARS
           ============================================================ */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
            overflow: hidden;
        }

        .star {
            position: absolute;
            width: 3px;
            height: 3px;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s ease-in-out infinite;
            box-shadow: 0 0 6px rgba(255, 255, 255, 0.3);
        }

        .star:nth-child(1) { top: 10%; left: 5%; animation-delay: 0s; width: 4px; height: 4px; }
        .star:nth-child(2) { top: 20%; left: 15%; animation-delay: 0.5s; }
        .star:nth-child(3) { top: 30%; left: 25%; animation-delay: 1s; width: 5px; height: 5px; }
        .star:nth-child(4) { top: 40%; left: 35%; animation-delay: 1.5s; }
        .star:nth-child(5) { top: 50%; left: 45%; animation-delay: 2s; width: 4px; height: 4px; }
        .star:nth-child(6) { top: 60%; left: 55%; animation-delay: 2.5s; }
        .star:nth-child(7) { top: 70%; left: 65%; animation-delay: 3s; width: 5px; height: 5px; }
        .star:nth-child(8) { top: 80%; left: 75%; animation-delay: 0.3s; }
        .star:nth-child(9) { top: 15%; left: 85%; animation-delay: 0.8s; width: 4px; height: 4px; }
        .star:nth-child(10) { top: 85%; left: 10%; animation-delay: 1.8s; }
        .star:nth-child(11) { top: 45%; left: 90%; animation-delay: 2.2s; }
        .star:nth-child(12) { top: 75%; left: 40%; animation-delay: 0.2s; width: 5px; height: 5px; }
        .star:nth-child(13) { top: 25%; left: 70%; animation-delay: 1.2s; }
        .star:nth-child(14) { top: 55%; left: 12%; animation-delay: 2.8s; width: 4px; height: 4px; }
        .star:nth-child(15) { top: 90%; left: 85%; animation-delay: 1.5s; }

        @keyframes twinkle {
            0%, 100% { opacity: 0.2; transform: scale(0.8); }
            50% { opacity: 1; transform: scale(1.4); }
        }

        /* ============================================================
           PROFILE CARD
           ============================================================ */
        .profile-card {
            max-width: 1050px;
            width: 100%;
            background: rgba(255, 255, 255, 0.06);
            backdrop-filter: blur(24px);
            -webkit-backdrop-filter: blur(24px);
            border-radius: 2.5rem;
            padding: 2.5rem 3rem;
            position: relative;
            z-index: 1;
            border: 1px solid rgba(255, 255, 255, 0.06);
            box-shadow: 0 30px 80px -20px rgba(0, 0, 0, 0.6);
        }

        .flag-bg {
            position: absolute;
            top: -25px;
            right: -25px;
            width: 160px;
            height: 160px;
            opacity: 0.1;
            pointer-events: none;
            z-index: 0;
            animation: pulseFlag 4s ease-in-out infinite;
        }

        .flag-bg svg {
            width: 100%;
            height: 100%;
            transform: rotate(15deg);
        }

        .flag-bg-bottom {
            position: absolute;
            bottom: -20px;
            left: -20px;
            width: 110px;
            height: 110px;
            opacity: 0.08;
            pointer-events: none;
            z-index: 0;
            animation: pulseFlag 5s ease-in-out infinite reverse;
        }

        .flag-bg-bottom svg {
            width: 100%;
            height: 100%;
            transform: rotate(-10deg);
        }

        @keyframes pulseFlag {
            0%, 100% { opacity: 0.08; transform: scale(1); }
            50% { opacity: 0.15; transform: scale(1.05); }
        }

        @media (max-width: 640px) {
            .profile-card { padding: 1.5rem 1.2rem; border-radius: 1.8rem; }
            .flag-bg { width: 100px; height: 100px; top: -10px; right: -10px; }
            .flag-bg-bottom { width: 70px; height: 70px; }
            .glow-orb { display: none; }
            .stars { display: none; }
            .fly { display: none; }
            .bubble { display: none; }
            body { padding: 1rem; }
        }

        .profile-content {
            position: relative;
            z-index: 2;
        }

        /* ============================================================
           IDENTITY SECTION
           ============================================================ */
        .identity {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 1.5rem 2rem;
            margin-bottom: 2rem;
        }

        .avatar-wrapper {
            display: flex;
            align-items: center;
            gap: 0.8rem;
        }

        .avatar-frame {
            flex-shrink: 0;
            width: 110px;
            height: 110px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.05);
            border: 3px solid rgba(255, 255, 255, 0.08);
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 40px rgba(59, 130, 246, 0.1);
        }

        .avatar-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .avatar-frame .fallback-icon {
            font-size: 3.5rem;
            color: rgba(255, 255, 255, 0.4);
            display: none;
        }

        .avatar-frame img:not([src]),
        .avatar-frame img[src=""],
        .avatar-frame img[src*="error"] {
            display: none;
        }

        .avatar-frame img:not([src])+.fallback-icon,
        .avatar-frame img[src=""]+.fallback-icon,
        .avatar-frame img[src*="error"]+.fallback-icon {
            display: block;
        }

        .small-flag {
            font-size: 2rem;
            animation: flagWave 2s ease-in-out infinite;
            display: inline-block;
            width: 40px;
            height: 40px;
        }

        .small-flag svg {
            width: 100%;
            height: 100%;
        }

        @keyframes flagWave {
            0%, 100% { transform: rotate(-5deg) scale(1); }
            50% { transform: rotate(5deg) scale(1.1); }
        }

        .title-group h1 {
            font-size: 2.5rem;
            font-weight: 700;
            letter-spacing: -0.02em;
            background: linear-gradient(135deg, #ffffff, #94a3b8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-family: 'Playfair Display', serif;
        }

        .title-group .badge-role {
            display: inline-block;
            background: rgba(59, 130, 246, 0.15);
            padding: 0.3rem 1.4rem;
            border-radius: 40px;
            font-weight: 500;
            font-size: 0.9rem;
            color: #a5b4fc;
            border: 1px solid rgba(255, 255, 255, 0.06);
            font-family: 'Space Grotesk', sans-serif;
        }

        .title-group .badge-role i {
            margin-right: 6px;
            font-size: 0.85rem;
        }

        .quick-contact {
            margin-left: auto;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            flex-wrap: wrap;
        }

        .email-chip {
            background: rgba(255, 255, 255, 0.04);
            padding: 0.5rem 1.5rem;
            border-radius: 60px;
            border: 1px solid rgba(255, 255, 255, 0.06);
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            color: #cbd5e1;
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }

        .email-chip i {
            color: #60a5fa;
            font-size: 1rem;
        }

        .email-chip a {
            text-decoration: none;
            color: inherit;
        }

        .email-chip:hover {
            border-color: rgba(59, 130, 246, 0.3);
            background: rgba(255, 255, 255, 0.08);
            transform: translateY(-2px);
        }

        /* ============================================================
           DIVIDER
           ============================================================ */
        .divider-light {
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.06), rgba(139, 92, 246, 0.12), rgba(255, 255, 255, 0.06), transparent);
            margin: 0 0 2rem 0;
        }

        /* ============================================================
           GRID LAYOUT
           ============================================================ */
        .profile-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2.5rem;
        }

        @media (max-width: 780px) {
            .profile-grid {
                grid-template-columns: 1fr;
                gap: 1.5rem;
            }
            .quick-contact {
                margin-left: 0;
                width: 100%;
                justify-content: flex-start;
                margin-top: 0.3rem;
            }
            .avatar-wrapper {
                flex-direction: column;
                align-items: center;
            }
            .small-flag {
                font-size: 1.8rem;
                margin-left: 0;
                margin-top: 0.2rem;
                width: 35px;
                height: 35px;
            }
        }

        /* ============================================================
           ABOUT SECTION
           ============================================================ */
        .about h2 {
            font-size: 1rem;
            font-weight: 400;
            letter-spacing: 0.8px;
            text-transform: uppercase;
            color: #94a3b8;
            margin-bottom: 0.8rem;
            font-family: 'Cormorant Garamond', serif;
            font-weight: 600;
        }

        .about h2 i {
            color: #60a5fa;
            margin-right: 6px;
        }

        .about p {
            font-size: 1rem;
            color: #cbd5e1;
            line-height: 1.7;
            font-weight: 300;
        }

        .about p i {
            color: #60a5fa;
            margin-right: 4px;
        }

        .bio-highlight {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 16px;
            padding: 1rem 1.5rem;
            margin-top: 1rem;
            border: 1px solid rgba(255, 255, 255, 0.04);
        }

        .bio-highlight span {
            display: inline-block;
            background: rgba(59, 130, 246, 0.12);
            padding: 0.15rem 0.9rem;
            border-radius: 30px;
            font-size: 0.85rem;
            font-weight: 500;
            color: #a5b4fc;
            font-family: 'Space Grotesk', sans-serif;
        }

        .bio-highlight p {
            margin-top: 0.5rem;
            font-size: 0.95rem;
            color: #cbd5e1;
            font-weight: 300;
        }

        .bio-highlight p i {
            color: #60a5fa;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 0.8rem;
        }

        .project-tags span {
            background: rgba(255, 255, 255, 0.04);
            padding: 0.2rem 0.9rem;
            border-radius: 30px;
            font-size: 0.75rem;
            font-weight: 400;
            color: #94a3b8;
            border: 1px solid rgba(255, 255, 255, 0.04);
            transition: all 0.3s ease;
        }

        .project-tags span:hover {
            transform: translateY(-2px);
            border-color: rgba(139, 92, 246, 0.2);
            color: #cbd5e1;
        }

        .project-tags span i {
            color: #60a5fa;
            margin-right: 4px;
        }

        .location-badge {
            background: rgba(59, 130, 246, 0.05);
            border: 1px solid rgba(59, 130, 246, 0.08);
            border-radius: 40px;
            padding: 0.15rem 1rem;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            font-size: 0.8rem;
            color: #94a3b8;
            margin-top: 0.5rem;
            font-weight: 300;
        }

        .location-badge i {
            color: #60a5fa;
        }

        /* ============================================================
           SERVICES SECTION
           ============================================================ */
        .services-section {
            margin-top: 1.5rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.06);
        }

        .services-section h3 {
            font-size: 0.9rem;
            font-weight: 500;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            color: #94a3b8;
            margin-bottom: 1rem;
            font-family: 'Space Grotesk', sans-serif;
        }

        .services-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        @media (max-width: 480px) {
            .services-grid {
                grid-template-columns: 1fr;
            }
        }

        .service-card {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: 16px;
            padding: 1rem 1.2rem;
            transition: all 0.3s ease;
        }

        .service-card:hover {
            transform: translateY(-3px);
            border-color: rgba(139, 92, 246, 0.2);
            background: rgba(255, 255, 255, 0.05);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15);
        }

        .service-card .icon {
            font-size: 1.8rem;
            color: #60a5fa;
            margin-bottom: 0.5rem;
        }

        .service-card h4 {
            color: #e2e8f0;
            font-size: 1rem;
            font-weight: 500;
            margin-bottom: 0.3rem;
        }

        .service-card .price {
            color: #a5b4fc;
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 0.3rem;
        }

        .service-card .price span {
            color: #64748b;
            font-weight: 300;
            font-size: 0.8rem;
        }

        .service-card p {
            color: #94a3b8;
            font-size: 0.8rem;
            line-height: 1.5;
            font-weight: 300;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: linear-gradient(135deg, rgba(59, 130, 246, 0.2), rgba(139, 92, 246, 0.2));
            padding: 0.5rem 1.5rem;
            border-radius: 60px;
            border: 1px solid rgba(139, 92, 246, 0.2);
            color: #a5b4fc;
            text-decoration: none;
            font-size: 0.85rem;
            font-weight: 500;
            transition: all 0.3s ease;
            margin-top: 0.8rem;
        }

        .cta-button:hover {
            background: linear-gradient(135deg, rgba(59, 130, 246, 0.3), rgba(139, 92, 246, 0.3));
            transform: translateY(-2px);
            border-color: rgba(139, 92, 246, 0.4);
            box-shadow: 0 8px 30px rgba(139, 92, 246, 0.1);
        }

        .cta-button i {
            font-size: 0.9rem;
        }

        /* ============================================================
           DETAILS SECTION
           ============================================================ */
        .details h2 {
            font-size: 1rem;
            font-weight: 400;
            letter-spacing: 0.8px;
            text-transform: uppercase;
            color: #94a3b8;
            margin-bottom: 0.8rem;
            font-family: 'DM Serif Display', serif;
        }

        .details h2 i {
            color: #60a5fa;
            margin-right: 6px;
        }

        .info-list {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .info-item {
            display: flex;
            align-items: center;
            gap: 12px;
            background: rgba(255, 255, 255, 0.03);
            padding: 0.5rem 1rem;
            border-radius: 40px;
            border: 1px solid rgba(255, 255, 255, 0.04);
            transition: all 0.3s ease;
        }

        .info-item:hover {
            transform: translateX(4px);
            background: rgba(255, 255, 255, 0.06);
            border-color: rgba(139, 92, 246, 0.15);
        }

        .info-item i {
            width: 20px;
            color: #60a5fa;
            font-size: 1rem;
            text-align: center;
        }

        .info-item .label {
            font-weight: 400;
            color: #64748b;
            min-width: 65px;
            font-size: 0.85rem;
        }

        .info-item .value {
            font-weight: 400;
            color: #cbd5e1;
            font-size: 0.85rem;
        }

        .info-item .value a {
            color: #cbd5e1;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .info-item .value a:hover {
            color: #60a5fa;
        }

        /* ============================================================
           SOCIAL SECTION - WITH MOVING EFFECTS
           ============================================================ */
        .social-section {
            margin-top: 1rem;
        }

        .social-section h3 {
            font-size: 0.8rem;
            font-weight: 400;
            letter-spacing: 0.8px;
            text-transform: uppercase;
            color: #64748b;
            margin-bottom: 0.8rem;
            font-family: 'Space Grotesk', sans-serif;
        }

        .social-links {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem 0.8rem;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(255, 255, 255, 0.03);
            padding: 0.4rem 1.2rem;
            border-radius: 60px;
            border: 1px solid rgba(255, 255, 255, 0.04);
            text-decoration: none;
            font-weight: 400;
            color: #94a3b8;
            transition: all 0.3s ease;
            font-size: 0.85rem;
            position: relative;
            overflow: hidden;
        }

        .social-links a::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.05), transparent);
            transition: left 0.6s ease;
        }

        .social-links a:hover::before {
            left: 100%;
        }

        .social-links a i {
            font-size: 1.2rem;
            width: 1.4rem;
            text-align: center;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background: rgba(255, 255, 255, 0.08);
            border-color: rgba(255, 255, 255, 0.12);
            color: #e2e8f0;
            transform: translateY(-3px) scale(1.03);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.2);
        }

        .social-links a:hover i {
            transform: scale(1.2) rotate(-5deg);
        }

        .social-links a .fa-instagram { color: #E4405F; }
        .social-links a .fa-tiktok { color: #ffffff; }
        .social-links a .fa-linkedin-in { color: #0A66C2; }
        .social-links a .fa-github { color: #f0f6fc; }
        .social-links a .fa-whatsapp { color: #25D366; }

        .social-tag {
            margin-top: 0.8rem;
            font-size: 0.8rem;
            color: #64748b;
            background: rgba(255, 255, 255, 0.03);
            padding: 0.3rem 0.9rem;
            border-radius: 40px;
            display: inline-block;
            border: 1px solid rgba(255, 255, 255, 0.04);
            font-weight: 300;
            transition: all 0.3s ease;
        }

        .social-tag:hover {
            transform: translateY(-2px);
            border-color: rgba(139, 92, 246, 0.2);
        }

        .social-tag i {
            color: #60a5fa;
        }

        /* ============================================================
           FOOTER
           ============================================================ */
        .profile-footer {
            margin-top: 2rem;
            text-align: right;
            font-size: 0.75rem;
            color: #475569;
            border-top: 1px solid rgba(255, 255, 255, 0.04);
            padding-top: 1rem;
            font-weight: 300;
        }

        .profile-footer i {
            color: #60a5fa;
            margin: 0 4px;
            animation: heartBeat 2s ease-in-out infinite;
        }

        @keyframes heartBeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.15); }
        }

        @media (max-width: 480px) {
            .title-group h1 { font-size: 2rem; }
            .avatar-frame { width: 85px; height: 85px; }
            .info-item { flex-wrap: wrap; gap: 4px; padding: 0.4rem 0.8rem; }
            .info-item .label { min-width: 50px; font-size: 0.75rem; }
            .small-flag { font-size: 1.4rem; width: 30px; height: 30px; }
            .profile-card { padding: 1.2rem 0.8rem; }
            .about p { font-size: 0.9rem; }
            .bio-highlight { padding: 0.8rem 1rem; }
            .bio-highlight p { font-size: 0.85rem; }
        }
    </style>
</head>
<body>

    <!-- ============================================================
         BACKGROUNDS
         ============================================================ -->
    <div class="moving-bg"></div>
    <div class="glow-orb"></div>
    <div class="glow-orb"></div>
    <div class="glow-orb"></div>
    <div class="glow-orb"></div>
    <div class="glow-orb"></div>

    <!-- Flying Butterflies -->
    <div class="fly-container">
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
        <div class="fly"><i class="fas fa-butterfly"></i></div>
    </div>

    <!-- Floating Bubbles -->
    <div class="bubbles">
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
    </div>

    <!-- Stars -->
    <div class="stars">
        <span class="star"></span><span class="star"></span><span class="star"></span>
        <span class="star"></span><span class="star"></span><span class="star"></span>
        <span class="star"></span><span class="star"></span><span class="star"></span>
        <span class="star"></span><span class="star"></span><span class="star"></span>
        <span class="star"></span><span class="star"></span><span class="star"></span>
    </div>

    <!-- ============================================================
         PROFILE CARD
         ============================================================ -->
    <div class="profile-card">

        <div class="flag-bg">
            <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
                <rect width="600" height="400" fill="#4189DD"/>
                <polygon points="300,40 370,180 520,180 400,270 440,410 300,330 160,410 200,270 80,180 230,180" fill="white"/>
            </svg>
        </div>
        <div class="flag-bg-bottom">
            <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
                <rect width="600" height="400" fill="#4189DD"/>
                <polygon points="300,40 370,180 520,180 400,270 440,410 300,330 160,410 200,270 80,180 230,180" fill="white"/>
            </svg>
        </div>

        <div class="profile-content">

            <!-- HEADER -->
            <div class="identity">
                <div class="avatar-wrapper">
                    <div class="avatar-frame">
                        <img src="your-image.jpeg" alt="Sahal Abshir" onerror="this.style.display='none'; this.parentElement.querySelector('.fallback-icon').style.display='block';">
                        <i class="fas fa-user-astronaut fallback-icon"></i>
                    </div>
                    <span class="small-flag">
                        <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg">
                            <rect width="600" height="400" fill="#4189DD"/>
                            <polygon points="300,40 370,180 520,180 400,270 440,410 300,330 160,410 200,270 80,180 230,180" fill="white"/>
                        </svg>
                    </span>
                </div>
                <div class="title-group">
                    <h1>Sahal Abshir</h1>
                    <div class="badge-role">
                        <i class="fas fa-code"></i> Developer · Community Manager
                    </div>
                </div>
                <div class="quick-contact">
                    <span class="email-chip">
                        <i class="fas fa-envelope"></i>
                        <a href="mailto:sahalabshir25@gmail.com">sahalabshir25@gmail.com</a>
                    </span>
                </div>
            </div>

            <div class="divider-light"></div>

            <!-- MAIN GRID -->
            <div class="profile-grid">

                <!-- LEFT -->
                <div class="about">
                    <h2><i class="fas fa-quote-left"></i> about</h2>
                    <p>
                        <i class="fas fa-laptop-code"></i>
                        I'm <strong style="color:#e2e8f0;">Sahal Abshir</strong>, a developer and community manager from <strong style="color:#e2e8f0;">Somalia</strong>.
                        I build digital experiences — from coffee shop websites to a live soccer app — and lead communities with purpose.
                    </p>
                    <div class="bio-highlight">
                        <span><i class="fas fa-rocket"></i> what I do</span>
                        <p>
                            <i class="fas fa-check-circle"></i> Full-stack dev · React, Node, Firebase <br>
                            <i class="fas fa-users"></i> Community manager · engagement & growth <br>
                            <i class="fas fa-futbol"></i> Built <strong style="color:#e2e8f0;">LiveSoccer</strong> app + <strong style="color:#e2e8f0;">CoffeeShop</strong> web platform
                        </p>
                    </div>
                    <div class="project-tags">
                        <span><i class="fas fa-coffee"></i> CoffeeShop</span>
                        <span><i class="fas fa-futbol"></i> LiveSoccer</span>
                        <span><i class="fas fa-users"></i> Community Lead</span>
                        <span><i class="fas fa-code"></i> Full-stack</span>
                    </div>
                    <div class="location-badge">
                        <i class="fas fa-map-pin"></i> Mogadishu, Somalia · <i class="fas fa-globe-africa"></i> Somali flag
                    </div>

                    <!-- SERVICES SECTION -->
                    <div class="services-section">
                        <h3><i class="fas fa-briefcase" style="color:#60a5fa; margin-right:6px;"></i> services & pricing</h3>
                        <div class="services-grid">
                            <div class="service-card">
                                <div class="icon"><i class="fas fa-globe"></i></div>
                                <h4>Website Development</h4>
                                <div class="price">$300 <span>–</span> $1,300</div>
                                <p>Custom websites, e-commerce, portfolios, and business sites.</p>
                            </div>
                            <div class="service-card">
                                <div class="icon"><i class="fas fa-mobile-alt"></i></div>
                                <h4>App Development</h4>
                                <div class="price">$600 <span>–</span> $2,100</div>
                                <p>Mobile apps for iOS & Android, cross-platform solutions.</p>
                            </div>
                        </div>
                        <a href="mailto:sahalabshir25@gmail.com" class="cta-button">
                            <i class="fas fa-paper-plane"></i> Let's Work Together
                        </a>
                    </div>
                </div>

                <!-- RIGHT -->
                <div class="details">
                    <h2><i class="fas fa-address-card"></i> contact & info</h2>
                    <div class="info-list">
                        <div class="info-item">
                            <i class="fas fa-envelope-open-text"></i>
                            <span class="label">Email</span>
                            <span class="value"><a href="mailto:sahalabshir25@gmail.com">sahalabshir25@gmail.com</a></span>
                        </div>
                        <div class="info-item">
                            <i class="fas fa-phone-alt"></i>
                            <span class="label">Phone</span>
                            <span class="value"><a href="tel:+252610404329">+252 61 040 4329</a></span>
                        </div>
                        <div class="info-item">
                            <i class="fab fa-whatsapp" style="color:#25D366;"></i>
                            <span class="label">WhatsApp</span>
                            <span class="value"><a href="https://wa.me/252610404329" target="_blank">Message me</a></span>
                        </div>
                        <div class="info-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <span class="label">Location</span>
                            <span class="value">Mogadishu, Somalia</span>
                        </div>
                        <div class="info-item">
                            <i class="fab fa-github" style="color:#f0f6fc;"></i>
                            <span class="label">GitHub</span>
                            <span class="value"><a href="https://github.com/realpato7" target="_blank">@realpato7</a></span>
                        </div>
                    </div>

                    <div class="social-section">
                        <h3><i class="fas fa-share-alt"></i> connect · social</h3>
                        <div class="social-links">
                            <a href="https://www.instagram.com/l.zaheil_11?utm_source=qr" target="_blank">
                                <i class="fab fa-instagram"></i> instagram
                            </a>
                            <a href="https://www.tiktok.com/@sahal_66?_r=1&_t=ZS-97ddcToveVk" target="_blank">
                                <i class="fab fa-tiktok"></i> tiktok
                            </a>
                            <a href="https://www.linkedin.com/in/sahal-undefined-a65b453b5?utm_source=share_via&utm_content=profile&utm_medium=member_ios" target="_blank">
                                <i class="fab fa-linkedin-in"></i> linkedin
                            </a>
                            <a href="https://github.com/realpato7" target="_blank">
                                <i class="fab fa-github"></i> github
                            </a>
                            <a href="https://wa.me/252610404329" target="_blank">
                                <i class="fab fa-whatsapp"></i> whatsapp
                            </a>
                        </div>
                        <div class="social-tag">
                            <i class="fas fa-hashtag"></i> @sahal_abshir · building & connecting
                        </div>
                    </div>
                </div>
            </div>

            <!-- FOOTER -->
            <div class="profile-footer">
                <i class="fas fa-circle" style="font-size: 0.3rem;"></i>
                crafted with <i class="fas fa-heart" style="color: #ef4444;"></i> · Sahal Abshir
                <span style="margin-left: 1rem;"><i class="fas fa-flag" style="color:#4189DD;"></i> Somalia</span>
            </div>
        </div>
    </div>
</body>
</html>
