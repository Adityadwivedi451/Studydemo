<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>STUDYMINE - Neural Adventure</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
            user-select: none;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow-x: hidden;
            background: #0a0a0a;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from { transform: translateY(100%); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes glow {
            0%, 100% { box-shadow: 0 0 20px rgba(139, 92, 246, 0.5); }
            50% { box-shadow: 0 0 40px rgba(139, 92, 246, 0.8); }
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-10px); }
            75% { transform: translateX(10px); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        /* Screen Container */
        .screen {
            min-height: 100vh;
            display: none;
            animation: fadeIn 0.5s ease-out;
        }

        .screen.active {
            display: flex;
        }

        /* Splash Screen */
        #splash {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            flex-direction: column;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .stars {
            position: absolute;
            width: 100%;
            height: 100%;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        .logo-title {
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(45deg, #06ffa5, #a855f7, #ec4899);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: pulse 2s infinite;
            z-index: 10;
            text-shadow: 0 0 30px rgba(168, 85, 247, 0.5);
        }

        .loading-text {
            color: #94a3b8;
            margin-top: 20px;
            font-size: 1.2rem;
            z-index: 10;
        }

        /* Intro Screen */
        #intro {
            background: linear-gradient(135deg, #4c1d95 0%, #7c3aed 50%, #ec4899 100%);
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 2rem;
        }

        .intro-emoji {
            font-size: 6rem;
            animation: bounce 2s infinite;
            margin-bottom: 2rem;
        }

        .intro-title {
            font-size: 3rem;
            font-weight: bold;
            color: white;
            text-align: center;
            margin-bottom: 1.5rem;
        }

        .intro-text {
            font-size: 1.3rem;
            color: #e9d5ff;
            text-align: center;
            max-width: 600px;
            line-height: 1.8;
            margin-bottom: 3rem;
        }

        .btn-primary {
            padding: 1rem 3rem;
            font-size: 1.3rem;
            font-weight: bold;
            color: white;
            background: linear-gradient(135deg, #10b981, #059669);
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            box-shadow: 0 10px 30px rgba(16, 185, 129, 0.3);
        }

        .btn-primary:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 40px rgba(16, 185, 129, 0.5);
        }

        .btn-primary:active {
            transform: scale(0.95);
        }

        /* Character Creation */
        #createCharacter {
            background: linear-gradient(135deg, #1e293b 0%, #4c1d95 50%, #7c3aed 100%);
            align-items: center;
            justify-content: center;
            padding: 2rem;
        }

        .char-container {
            background: rgba(30, 41, 59, 0.8);
            backdrop-filter: blur(20px);
            border: 2px solid rgba(168, 85, 247, 0.3);
            border-radius: 24px;
            padding: 2rem;
            max-width: 600px;
            width: 100%;
            animation: slideUp 0.5s ease-out;
        }

        .char-title {
            font-size: 2rem;
            font-weight: bold;
            color: white;
            text-align: center;
            margin-bottom: 2rem;
        }

        .input-group {
            margin-bottom: 1.5rem;
        }

        .input-label {
            display: block;
            color: #cbd5e1;
            margin-bottom: 0.5rem;
            font-size: 1rem;
        }

        .input-field {
            width: 100%;
            padding: 1rem;
            background: rgba(15, 23, 42, 0.5);
            border: 2px solid rgba(168, 85, 247, 0.5);
            border-radius: 12px;
            color: white;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .input-field:focus {
            outline: none;
            border-color: #a855f7;
        }

        .aura-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1rem;
            margin-top: 1rem;
        }

        .aura-card {
            padding: 1.5rem;
            background: rgba(15, 23, 42, 0.3);
            border: 2px solid rgba(71, 85, 105, 1);
            border-radius: 16px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
        }

        .aura-card:hover {
            border-color: rgba(168, 85, 247, 0.5);
            transform: translateY(-5px);
        }

        .aura-card.selected {
            border-color: #a855f7;
            background: rgba(168, 85, 247, 0.2);
        }

        .aura-emoji {
            font-size: 3rem;
            margin-bottom: 0.5rem;
        }

        .aura-name {
            font-weight: bold;
            color: white;
            margin-bottom: 0.3rem;
        }

        .aura-effect {
            font-size: 0.85rem;
            color: #94a3b8;
        }

        /* Home Screen */
        #home {
            background: linear-gradient(135deg, #1e293b 0%, #4c1d95 50%, #7c3aed 100%);
            flex-direction: column;
            min-height: 100vh;
            padding-bottom: 80px;
        }

        .top-bar {
            background: rgba(30, 41, 59, 0.8);
            backdrop-filter: blur(20px);
            border-bottom: 2px solid rgba(168, 85, 247, 0.3);
            padding: 1rem;
        }

        .top-bar-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .player-info h2 {
            color: white;
            font-size: 1.5rem;
            margin-bottom: 0.3rem;
        }

        .player-subtitle {
            color: #c4b5fd;
            font-size: 0.9rem;
        }

        .settings-btn {
            background: none;
            border: none;
            color: #94a3b8;
            cursor: pointer;
            font-size: 1.5rem;
            padding: 0.5rem;
            border-radius: 8px;
            transition: all 0.3s;
        }

        .settings-btn:hover {
            background: rgba(168, 85, 247, 0.2);
            color: #a855f7;
        }

        .settings-btn.strict-active {
            color: #ef4444;
            animation: pulse 2s infinite;
        }

        .xp-bar-container {
            max-width: 1200px;
            margin: 1rem auto;
            padding: 0 1rem;
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .xp-icon {
            font-size: 1.5rem;
        }

        .xp-bar {
            flex: 1;
            height: 24px;
            background: rgba(30, 41, 59, 0.8);
            border: 2px solid rgba(168, 85, 247, 0.3);
            border-radius: 12px;
            overflow: hidden;
            position: relative;
        }

        .xp-fill {
            height: 100%;
            background: linear-gradient(90deg, #a855f7, #ec4899);
            transition: width 0.5s ease-out;
            box-shadow: 0 0 20px rgba(168, 85, 247, 0.5);
        }

        .xp-text {
            color: white;
            font-weight: bold;
            font-size: 0.9rem;
        }

        .content-area {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem;
            flex: 1;
        }

        .guardian-msg {
            background: linear-gradient(135deg, rgba(88, 28, 135, 0.5), rgba(219, 39, 119, 0.5));
            backdrop-filter: blur(20px);
            border: 2px solid rgba(168, 85, 247, 0.3);
            border-radius: 16px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            display: flex;
            gap: 1rem;
            animation: slideUp 0.5s ease-out;
        }

        .guardian-emoji {
            font-size: 3rem;
        }

        .guardian-text {
            flex: 1;
        }

        .guardian-label {
            color: #c4b5fd;
            font-size: 0.85rem;
            margin-bottom: 0.5rem;
        }

        .guardian-message {
            color: white;
            font-style: italic;
            line-height: 1.6;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .stat-card {
            background: rgba(30, 41, 59, 0.8);
            backdrop-filter: blur(20px);
            border: 2px solid rgba(168, 85, 247, 0.2);
            border-radius: 12px;
            padding: 1rem;
            text-align: center;
            transition: transform 0.3s;
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .stat-emoji {
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }

        .stat-value {
            font-size: 1.5rem;
            font-weight: bold;
            color: #fbbf24;
            margin-bottom: 0.3rem;
        }

        .stat-label {
            color: #94a3b8;
            font-size: 0.85rem;
        }

        .section-card {
            background: rgba(30, 41, 59, 0.8);
            backdrop-filter: blur(20px);
            border: 2px solid rgba(168, 85, 247, 0.3);
            border-radius: 16px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .section-title {
            font-size: 1.5rem;
            font-weight: bold;
            color: white;
            margin-bottom: 1rem;
        }

        .world-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
        }

        .world-card {
            padding: 1.5rem;
            border-radius: 16px;
            transition: transform 0.3s;
            position: relative;
            overflow: hidden;
        }

        .world-card:hover {
            transform: scale(1.05);
        }

        .world-emoji {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }

        .world-name {
            color: white;
            font-weight: bold;
            font-size: 1.1rem;
            margin-bottom: 1rem;
        }

        .mission-btns {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .mission-btn {
            padding: 0.75rem;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            border-radius: 8px;
            color: white;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }

        .mission-btn:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }

        .skill-bar-container {
            margin-bottom: 1rem;
        }

        .skill-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 0.5rem;
        }

        .skill-name {
            color: #c4b5fd;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .skill-level {
            color: white;
            font-weight: bold;
        }

        .skill-bar {
            height: 12px;
            background: rgba(71, 85, 105, 1);
            border-radius: 6px;
            overflow: hidden;
        }

        .skill-fill {
            height: 100%;
            transition: width 0.5s ease-out;
            border-radius: 6px;
        }

        /* Mission Screen */
        #mission {
            background: linear-gradient(135deg, #1e293b 0%, #4c1d95 50%, #7c3aed 100%);
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .mission-particles {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #a855f7;
            border-radius: 50%;
            animation: float 3s infinite;
        }

        .power-word {
            position: absolute;
            top: 20%;
            left: 50%;
            transform: translateX(-50%);
            font-size: 3rem;
            font-weight: 900;
            background: linear-gradient(45deg, #fbbf24, #ef4444, #ec4899);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: pulse 0.5s ease-out;
            z-index: 100;
            text-shadow: 0 0 30px rgba(251, 191, 36, 0.5);
        }

        .emoji-pop {
            position: absolute;
            top: 30%;
            right: 20%;
            font-size: 5rem;
            animation: bounce 1s ease-out;
            z-index: 100;
        }

        .hp-bar-top {
            position: absolute;
            top: 2rem;
            left: 2rem;
            right: 2rem;
            display: flex;
            align-items: center;
            gap: 1rem;
            z-index: 50;
        }

        .hp-icon {
            font-size: 1.5rem;
        }

        .hp-bar {
            flex: 1;
            height: 16px;
            background: rgba(30, 41, 59, 0.8);
            border: 2px solid rgba(16, 185, 129, 0.3);
            border-radius: 8px;
            overflow: hidden;
        }

        .hp-fill {
            height: 100%;
            background: linear-gradient(90deg, #10b981, #059669);
            transition: width 0.3s;
            box-shadow: 0 0 20px rgba(16, 185, 129, 0.5);
        }

        .hp-text {
            color: white;
            font-weight: bold;
        }

        .timer-circle-container {
            position: relative;
            z-index: 10;
            margin-bottom: 2rem;
        }

        .timer-circle {
            width: 250px;
            height: 250px;
        }

        .timer-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
        }

        .timer-time {
            font-size: 3.5rem;
            font-weight: 900;
            color: white;
            text-shadow: 0 0 30px rgba(168, 85, 247, 0.5);
        }

        .timer-label {
            color: #c4b5fd;
            margin-top: 0.5rem;
        }

        .combo-meter {
            background: rgba(30, 41, 59, 0.8);
            backdrop-filter: blur(20px);
            border: 2px solid rgba(168, 85, 247, 0.3);
            border-radius: 16px;
            padding: 1rem 2rem;
            z-index: 10;
            animation: glow 2s infinite;
        }

        .combo-label {
            color: #fbbf24;
            font-weight: bold;
            font-size: 0.85rem;
            margin-bottom: 0.5rem;
            text-align: center;
        }

        .combo-value {
            font-size: 2.5rem;
            font-weight: 900;
            background: linear-gradient(45deg, #fbbf24, #f97316);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-align: center;
        }

        .mission-info {
            text-align: center;
            color: #cbd5e1;
            margin-top: 1rem;
            z-index: 10;
        }

        .strict-warning {
            color: #ef4444;
            font-weight: bold;
            margin-top: 0.5rem;
            animation: pulse 2s infinite;
        }

        .guardian-bottom {
            position: absolute;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            text-align: center;
            z-index: 10;
        }

        .guardian-bottom-emoji {
            font-size: 4rem;
            margin-bottom: 0.5rem;
        }

        .guardian-quote {
            color: #94a3b8;
            font-style: italic;
        }

        /* Reward Screen */
        #reward {
            background: linear-gradient(135deg, #1e293b 0%, #7c3aed 50%, #ec4899 100%);
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .reward-particles {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .reward-particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #fbbf24;
            border-radius: 50%;
            animation: float 2s infinite;
        }

        .reward-content {
            text-align: center;
            z-index: 10;
            animation: slideUp 0.5s ease-out;
        }

        .reward-emoji {
            font-size: 6rem;
            animation: bounce 2s infinite;
            margin-bottom: 1rem;
        }

        .reward-title {
            font-size: 3rem;
            font-weight: 900;
            background: linear-gradient(45deg, #fbbf24, #ec4899, #a855f7);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 2rem;
        }

        .reward-stats {
            background: rgba(30, 41, 59, 0.8);
            backdrop-filter: blur(20px);
            border: 2px solid rgba(251, 191, 36, 0.3);
            border-radius: 16px;
            padding: 2rem;
            margin-bottom: 2rem;
        }

        .reward-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
        }

        .reward-item {
            text-align: center;
        }

        .reward-item-emoji {
            font-size: 3rem;
            margin-bottom: 0.5rem;
        }

        .reward-item-value {
            
