<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>ScriLogic | ตรรกะสัมบูรณ์ | Cyber Audit System</title>
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&family=Space+Grotesk:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #0a0c0f;
      font-family: 'Inter', 'Space Grotesk', sans-serif;
      color: #eef5ff;
      line-height: 1.5;
      scroll-behavior: smooth;
      overflow-x: hidden;
    }

    /* Animated gradient overlay */
    body::before {
      content: '';
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle at 20% 30%, rgba(20, 60, 55, 0.25) 0%, #050708 90%);
      pointer-events: none;
      z-index: -2;
    }

    body::after {
      content: '';
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0MCIgaGVpZ2h0PSI0MCIgdmlld0JveD0iMCAwIDQwIDQwIj48cGF0aCBkPSJNMjAgMjBhMjAgMjAgMCAwIDEgMjAgMjAgMjAgMjAgMCAwIDEtMjAgMjAgMjAgMjAgMCAwIDEtMjAtMjAgMjAgMjAgMCAwIDEgMjAtMjB6IiBmaWxsPSIjMjI0NDQwIiBmaWxsLW9wYWNpdHk9IjAuMDMiLz48L3N2Zz4=');
      background-repeat: repeat;
      opacity: 0.15;
      pointer-events: none;
      z-index: -1;
    }

    /* Custom cursor glow */
    .glow-cursor {
      position: fixed;
      width: 500px;
      height: 500px;
      background: radial-gradient(circle, rgba(60, 200, 180, 0.06) 0%, rgba(0,0,0,0) 70%);
      border-radius: 50%;
      pointer-events: none;
      z-index: 9999;
      transform: translate(-50%, -50%);
      transition: transform 0.08s ease;
    }

    .container {
      max-width: 1300px;
      margin: 0 auto;
      padding: 1.5rem 2.5rem 4rem;
      position: relative;
      z-index: 2;
    }

    /* ===== LOGO SECTION (ใหม่) ===== */
    .logo-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      margin-bottom: 2rem;
      padding-bottom: 1rem;
      border-bottom: 1px solid rgba(70, 180, 150, 0.3);
      flex-wrap: wrap;
      gap: 1rem;
    }
    .logo-main {
      display: flex;
      flex-direction: column;
      gap: 0.2rem;
    }
    .logo-main h2 {
      font-size: 1.8rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, #FFFFFF 20%, #8ce0d0 70%, #4ad0b0 100%);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      font-family: 'Space Grotesk', monospace;
    }
    .logo-tagline {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.7rem;
      letter-spacing: 1.5px;
      color: #6aa9a0;
      border-left: 2px solid #3bc0aa;
      padding-left: 10px;
    }
    .logo-badge {
      display: flex;
      align-items: center;
      gap: 10px;
      background: rgba(20, 45, 45, 0.5);
      backdrop-filter: blur(8px);
      padding: 0.4rem 1rem;
      border-radius: 60px;
      border: 1px solid rgba(70, 200, 170, 0.4);
    }
    .logo-badge i {
      color: #4effda;
      font-size: 0.9rem;
    }
    .logo-badge span {
      font-size: 0.7rem;
      font-family: 'JetBrains Mono', monospace;
      color: #b0e0d0;
    }

    /* Hero section */
    .hero {
      text-align: center;
      padding: 1rem 0 1.5rem;
    }

    .badge-wrapper {
      display: flex;
      justify-content: center;
      margin-bottom: 2rem;
    }

    .status-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.7rem;
      background: rgba(10, 30, 28, 0.65);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(70, 210, 180, 0.5);
      border-radius: 100px;
      padding: 0.6rem 1.8rem;
      font-family: 'JetBrains Mono', monospace;
      font-weight: 500;
      font-size: 0.85rem;
      letter-spacing: 1px;
      box-shadow: 0 0 20px rgba(50, 210, 170, 0.2);
      transition: all 0.4s ease;
    }

    .status-badge:hover {
      border-color: #4effd0;
      box-shadow: 0 0 30px rgba(78, 255, 208, 0.3);
      transform: scale(1.02);
    }

    .glow-dot {
      width: 10px;
      height: 10px;
      background: #2effbc;
      border-radius: 50%;
      box-shadow: 0 0 12px #2effbc;
      animation: pulseGlow 2s infinite;
    }

    @keyframes pulseGlow {
      0% { opacity: 0.5; transform: scale(0.8); box-shadow: 0 0 0 0 #2effbc80; }
      70% { opacity: 1; transform: scale(1.3); box-shadow: 0 0 0 8px #2effbc00; }
      100% { opacity: 0.6; transform: scale(0.9); box-shadow: 0 0 0 0 transparent; }
    }

    .hero h1 {
      font-size: clamp(3rem, 9vw, 5.8rem);
      font-weight: 800;
      letter-spacing: -0.03em;
      background: linear-gradient(145deg, #FFFFFF 20%, #a0f0e0 50%, #3bc0aa 85%);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      text-shadow: 0 5px 20px rgba(0,40,30,0.4);
      margin-bottom: 1.2rem;
      line-height: 1.2;
    }

    .hero .subhead {
      font-size: clamp(1rem, 4.5vw, 1.4rem);
      font-weight: 400;
      color: #c0e0ec;
      max-width: 760px;
      margin: 0 auto 2rem auto;
      font-family: 'Space Grotesk', monospace;
      background: rgba(20, 40, 40, 0.4);
      backdrop-filter: blur(4px);
      padding: 0.8rem 1.8rem;
      border-radius: 60px;
      border: 1px solid rgba(70, 170, 150, 0.3);
    }

    /* Slider premium */
    .slider-container {
      max-width: 1000px;
      margin: 2rem auto 2rem auto;
      border-radius: 32px;
      overflow: hidden;
      box-shadow: 0 30px 50px -20px rgba(0,0,0,0.8), 0 0 0 1px rgba(70, 210, 180, 0.4) inset, 0 0 30px rgba(0,255,200,0.1);
      transition: box-shadow 0.5s ease;
    }

    .slider-container:hover {
      box-shadow: 0 35px 55px -20px rgba(0,0,0,0.9), 0 0 0 2px rgba(80, 230, 200, 0.6) inset, 0 0 45px rgba(0,255,200,0.2);
    }

    .slider-frame {
      position: relative;
      width: 100%;
      padding-top: 56.25%;
      overflow: hidden;
      background: #030608;
    }

    .slide {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      opacity: 0;
      transform: scale(1.08);
      transition: opacity 1.2s cubic-bezier(0.2, 0.9, 0.3, 1.1), transform 1.6s cubic-bezier(0.2, 0.9, 0.3, 1.1);
      pointer-events: none;
    }

    .slide.active {
      opacity: 1;
      transform: scale(1);
      pointer-events: auto;
      z-index: 2;
    }

    /* Premium image placeholders */
    .slide-1 { background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxOTIwIDEwODAiPjxkZWZzPjxsaW5lYXJHcmFkaWVudCBpZD0iYTEiIHgxPSIwJSIgeTE9IjAlIiB4Mj0iMTAwJSIgeTI9IjEwMCUiPjxzdG9wIG9mZnNldD0iMCUiIHN0b3AtY29sb3I9IiMwYzJhMjAiLz48c3RvcCBvZmZzZXQ9IjEwMCUiIHN0b3AtY29sb3I9IiMwMTEyMTgiLz48L2xpbmVhckdyYWRpZW50PjwvZGVmcz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSJ1cmwoI2ExKSIvPjxjaXJjbGUgY3g9Ijk2MCIgY3k9IjU0MCIgcj0iMjUwIiBmaWxsPSJub25lIiBzdHJva2U9IiM0MGVjZDAiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWRhc2hhcnJheT0iMTAgMjAiLz48Y2lyY2xlIGN4PSI5NjAiIGN5PSI1NDAiIHI9IjE4MCIgZmlsbD0iIzI4YzBjMCIgb3BhY2l0eT0iMC4wNSIvPjxwYXRoIGQ9Ik0zMDAgMjAwTDE2MjAgODAwIiBzdHJva2U9IiM2MGVmYzAiIHN0cm9rZS13aWR0aD0iMS41IiBzdHJva2UtbGluZWNhcD0icm91bmQiLz48L3N2Zz4='); }
    .slide-2 { background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxOTIwIDEwODAiPjxkZWZzPjxsaW5lYXJHcmFkaWVudCBpZD0iYjEiIHgxPSIwJSIgeTE9IjAlIiB4Mj0iMCUiIHkyPSIxMDAlIj48c3RvcCBvZmZzZXQ9IjAlIiBzdHlsZT0ic3RvcC1jb2xvcjojMDQyYzI2Ii8+PHN0b3Agb2Zmc2V0PSIxMDAlIiBzdHlsZT0ic3RvcC1jb2xvcjojMDEwMjA0Ii8+PC9saW5lYXJHcmFkaWVudD48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgZmlsbD0idXJsKCNiMSkiLz48cG9seWdvbiBwb2ludHM9IjQwMCwzMDAgMTUwMCw0MDAgMTIwMCw3MDAgMjAwLDYwMCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjM2RlMGMwIiBzdHJva2Utd2lkdGg9IjIiLz48Y2lyY2xlIGN4PSI4MDAiIGN5PSI0NTAiIHI9IjMwIiBmaWxsPSIjMDBmZmQwIiBmaWxsLW9wYWNpdHk9IjAuMyIvPjwvc3ZnPg=='); }
    .slide-3 { background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxOTIwIDEwODAiPjxkZWZzPjxsaW5lYXJHcmFkaWVudCBpZD0iYzEiIHgxPSIwJSIgeTE9IjUwJSIgeDI9IjEwMCUiIHkyPSI1MCUiPjxzdG9wIG9mZnNldD0iMCUiIHN0eWxlPSJzdG9wLWNvbG9yOiMwYzFkMjAiLz48c3RvcCBvZmZzZXQ9IjEwMCUiIHN0eWxlPSJzdG9wLWNvbG9yOiMwMTBhMTIiLz48L2xpbmVhckdyYWRpZW50PjwvZGVmcz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSJ1cmwoI2MxKSIvPjxjaXJjbGUgY3g9IjUwMCIgY3k9IjU0MCIgcj0iMjAwIiBmaWxsPSJub25lIiBzdHJva2U9IiM0MGVkYzAiIHN0cm9rZS13aWR0aD0iMiIvPjwvc3ZnPg=='); }
    .slide-4 { background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxOTIwIDEwODAiPjxkZWZzPjxsaW5lYXJHcmFkaWVudCBpZD0iZDEiIHgxPSIwJSIgeTE9IjAlIiB4Mj0iMTAwJSIgeTI9IjEwMCUiPjxzdG9wIG9mZnNldD0iMCUiIHN0b3AtY29sb3I6IiMwMjFhMjAiLz48c3RvcCBvZmZzZXQ9IjEwMCUiIHN0b3AtY29sb3I6IiMwMDAiLz48L2xpbmVhckdyYWRpZW50PjwvZGVmcz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSJ1cmwoI2QxKSIvPjxwYXRoIGQ9Ik0yMDAgODAwTDk2MCAzMDBMMTcyMCA4MDAiIHN0cm9rZT0iIzVjZTBlMCIgc3Ryb2tlLXdpZHRoPSIyIi8+PC9zdmc+'); }

    .slider-dots {
      display: flex;
      justify-content: center;
      gap: 16px;
      margin-top: 24px;
      margin-bottom: 10px;
    }
    .dot {
      width: 10px;
      height: 10px;
      background: #2a5a5a;
      border-radius: 50%;
      cursor: pointer;
      transition: all 0.3s
