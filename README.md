<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width,initial-scale=1.0">
  <title>KisanFlow AI — Agricultural Marketplace Intelligence</title>
  <meta name="description"
    content="KisanFlow AI: Predict demand, connect farmers with buyers, aggregate supply, and deliver — powered by AI intelligence for Indian agriculture.">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap"
    rel="stylesheet">
  <style>
    /* ===== DESIGN TOKENS ===== */
    :root {
      --dark: #0f2818;
      --dark2: #163520;
      --green: #1b8a4a;
      --green2: #28a85f;
      --green3: #34c471;
      --green-soft: #e8f5ee;
      --green-bg: #f0f8f2;
      --gold: #d48806;
      --amber: #f0b429;
      --red: #dc4848;
      --blue: #3b82f6;
      --text: #1a2e22;
      --text2: #2d4a36;
      --muted: #5f7a68;
      --muted2: #8fa498;
      --white: #ffffff;
      --offwhite: #fafcfa;
      --border: #d4e5d8;
      --border2: #e8f0ea;
      --sage: #edf6ee;
      --sage2: #e3efe4;
      --card-bg: rgba(255, 255, 255, 0.92);
      --sidebar-w: 260px;
      --topbar-h: 64px;
      --radius: 14px;
      --radius-lg: 20px;
      --radius-sm: 10px;
      --shadow-sm: 0 2px 8px rgba(15, 40, 24, 0.06);
      --shadow: 0 4px 20px rgba(15, 40, 24, 0.08);
      --shadow-lg: 0 12px 40px rgba(15, 40, 24, 0.12);
      --shadow-xl: 0 20px 60px rgba(15, 40, 24, 0.15);
      --transition: 0.2s cubic-bezier(0.4, 0, 0.2, 1);
    }

    /* ===== RESET & BASE ===== */
    *,
    *::before,
    *::after {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      -webkit-font-smoothing: antialiased;
    }

    body {
      font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', sans-serif;
      color: var(--text);
      background: var(--green-bg);
      line-height: 1.6;
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* ===== TYPOGRAPHY ===== */
    h1 {
      font-size: 2rem;
      font-weight: 800;
      letter-spacing: -0.03em;
      line-height: 1.2;
    }

    h2 {
      font-size: 1.35rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      line-height: 1.3;
    }

    h3 {
      font-size: 1.1rem;
      font-weight: 700;
      line-height: 1.4;
    }

    p {
      color: var(--text2);
    }

    a {
      color: var(--green);
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
    }

    /* ===== AUTH / LANDING SCREEN ===== */
    .auth-topbar {
      position: absolute;
      top: 24px;
      right: 28px;
      z-index: 10;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .lang-picker-auth {
      display: flex;
      align-items: center;
      background: rgba(255, 255, 255, 0.12);
      backdrop-filter: blur(12px);
      padding: 6px 14px;
      border-radius: 999px;
      border: 1px solid rgba(255, 255, 255, 0.2);
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2);
    }

    .auth-lang-select {
      background: transparent;
      color: #ffffff;
      border: none;
      font-family: inherit;
      font-size: 0.88rem;
      font-weight: 600;
      cursor: pointer;
      outline: none;
    }

    .auth-lang-select option {
      background: #163520;
      color: #ffffff;
    }

    #authScreen {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: linear-gradient(160deg, #0f2818 0%, #163520 40%, #1b4a2e 70%, #0f2818 100%);
      position: relative;
      overflow: hidden;
      padding: 40px 20px;
    }

    #authScreen::before {
      content: '';
      position: absolute;
      top: -200px;
      right: -200px;
      width: 600px;
      height: 600px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(27, 138, 74, 0.15) 0%, transparent 70%);
      pointer-events: none;
    }

    #authScreen::after {
      content: '';
      position: absolute;
      bottom: -150px;
      left: -150px;
      width: 500px;
      height: 500px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(212, 136, 6, 0.08) 0%, transparent 70%);
      pointer-events: none;
    }

    .auth-brand {
      text-align: center;
      margin-bottom: 48px;
      position: relative;
      z-index: 1;
    }

    .auth-brand h1 {
      font-size: 2.8rem;
      color: #fff;
      margin-bottom: 8px;
      letter-spacing: -0.04em;
    }

    .auth-brand h1 span {
      color: var(--green3);
    }

    .auth-brand p {
      color: rgba(255, 255, 255, 0.65);
      font-size: 1rem;
      font-weight: 500;
    }

    .auth-brand .sih-badge {
      display: inline-block;
      margin-top: 12px;
      background: rgba(255, 255, 255, 0.08);
      border: 1px solid rgba(255, 255, 255, 0.12);
      padding: 6px 16px;
      border-radius: 999px;
      color: rgba(255, 255, 255, 0.6);
      font-size: 0.78rem;
      font-weight: 600;
      letter-spacing: 0.04em;
    }

    /* Role selection cards */
    .role-cards {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
      max-width: 720px;
      width: 100%;
      position: relative;
      z-index: 1;
    }

    .role-card {
      background: rgba(255, 255, 255, 0.06);
      backdrop-filter: blur(20px);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: var(--radius-lg);
      padding: 40px 32px;
      text-align: center;
      cursor: pointer;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      position: relative;
      overflow: hidden;
    }

    .role-card::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(27, 138, 74, 0.12) 0%, transparent 60%);
      opacity: 0;
      transition: opacity 0.3s ease;
    }

    .role-card:hover {
      border-color: rgba(52, 196, 113, 0.4);
      transform: translateY(-4px);
      box-shadow: 0 20px 60px rgba(27, 138, 74, 0.2);
    }

    .role-card:hover::before {
      opacity: 1;
    }

    .role-card .icon {
      font-size: 3rem;
      margin-bottom: 16px;
      display: block;
      position: relative;
    }

    .role-card h3 {
      color: #fff;
      font-size: 1.3rem;
      margin-bottom: 10px;
      position: relative;
    }

    .role-card p {
      color: rgba(255, 255, 255, 0.55);
      font-size: 0.88rem;
      margin-bottom: 24px;
      line-height: 1.5;
      position: relative;
    }

    .role-card .btn-role {
      display: inline-block;
      background: linear-gradient(135deg, var(--green), var(--green2));
      color: #fff;
      padding: 12px 28px;
      border-radius: 999px;
      font-weight: 700;
      font-size: 0.9rem;
      border: none;
      cursor: pointer;
      transition: all var(--transition);
      position: relative;
      box-shadow: 0 4px 16px rgba(27, 138, 74, 0.3);
    }

    .role-card .btn-role:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 24px rgba(27, 138, 74, 0.4);
    }

    /* Auth / Registration forms */
    .auth-panel {
      display: none;
      max-width: 520px;
      width: 100%;
      position: relative;
      z-index: 1;
    }

    .auth-panel.active {
      display: block;
    }

    .auth-form-card {
      background: rgba(255, 255, 255, 0.06);
      backdrop-filter: blur(24px);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: var(--radius-lg);
      padding: 36px 32px;
    }

    .auth-form-card h2 {
      color: #fff;
      margin-bottom: 6px;
      font-size: 1.45rem;
    }

    .auth-form-card .subtitle {
      color: rgba(255, 255, 255, 0.5);
      font-size: 0.88rem;
      margin-bottom: 28px;
    }

    .auth-form-card label {
      display: block;
      color: rgba(255, 255, 255, 0.7);
      font-size: 0.8rem;
      font-weight: 700;
      margin-bottom: 5px;
      margin-top: 14px;
    }

    .auth-form-card label:first-of-type {
      margin-top: 0;
    }

    .auth-form-card input,
    .auth-form-card select {
      width: 100%;
      padding: 11px 14px;
      background: rgba(255, 255, 255, 0.07);
      border: 1px solid rgba(255, 255, 255, 0.12);
      border-radius: var(--radius-sm);
      color: #fff;
      font: inherit;
      font-size: 0.92rem;
      outline: none;
      transition: all var(--transition);
    }

    .auth-form-card input::placeholder {
      color: rgba(255, 255, 255, 0.3);
    }

    .auth-form-card input:focus,
    .auth-form-card select:focus {
      border-color: var(--green2);
      box-shadow: 0 0 0 3px rgba(40, 168, 95, 0.15);
    }

    .auth-form-card select option {
      background: var(--dark);
      color: #fff;
    }

    .auth-form-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .auth-form-card .btn-submit {
      width: 100%;
      margin-top: 24px;
      padding: 13px;
      background: linear-gradient(135deg, var(--green), var(--green2));
      color: #fff;
      border: none;
      border-radius: 999px;
      font-weight: 800;
      font-size: 0.95rem;
      cursor: pointer;
      transition: all var(--transition);
      box-shadow: 0 4px 16px rgba(27, 138, 74, 0.3);
    }

    .auth-form-card .btn-submit:hover {
      transform: translateY(-1px);
      box-shadow: 0 8px 24px rgba(27, 138, 74, 0.4);
    }

    .auth-back {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      color: rgba(255, 255, 255, 0.5);
      font-size: 0.85rem;
      font-weight: 600;
      margin-bottom: 20px;
      cursor: pointer;
      transition: color var(--transition);
      background: none;
      border: none;
      font-family: inherit;
    }

    .auth-back:hover {
      color: rgba(255, 255, 255, 0.8);
    }

    .auth-login-link {
      text-align: center;
      margin-top: 18px;
      color: rgba(255, 255, 255, 0.45);
      font-size: 0.85rem;
    }

    .auth-login-link a {
      color: var(--green3);
      font-weight: 700;
      cursor: pointer;
    }

    .auth-login-link a:hover {
      text-decoration: underline;
    }

    /* ===== APP SHELL (post-auth) ===== */
    #appShell {
      display: none;
      min-height: 100vh;
    }

    #appShell.active {
      display: flex;
    }

    /* ===== SIDEBAR ===== */
    .sidebar {
      width: var(--sidebar-w);
      background: var(--dark);
      color: #fff;
      position: fixed;
      top: 0;
      left: 0;
      bottom: 0;
      z-index: 20;
      display: flex;
      flex-direction: column;
      transition: transform 0.3s ease;
      overflow-y: auto;
      overflow-x: hidden;
    }

    .sidebar-brand {
      padding: 20px 22px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.07);
    }

    .sidebar-brand h1 {
      font-size: 1.3rem;
      color: #fff;
      margin-bottom: 2px;
    }

    .sidebar-brand h1 span {
      color: var(--green3);
    }

    .sidebar-brand p {
      font-size: 0.72rem;
      color: rgba(255, 255, 255, 0.4);
      font-weight: 500;
    }

    .sidebar-nav {
      flex: 1;
      padding: 12px 10px;
      display: flex;
      flex-direction: column;
      gap: 2px;
    }

    .sidebar-nav button {
      display: flex;
      align-items: center;
      gap: 12px;
      width: 100%;
      padding: 11px 14px;
      background: transparent;
      border: none;
      border-radius: var(--radius-sm);
      color: rgba(255, 255, 255, 0.55);
      font: inherit;
      font-size: 0.88rem;
      font-weight: 600;
      cursor: pointer;
      transition: all var(--transition);
      text-align: left;
      white-space: nowrap;
    }

    .sidebar-nav button:hover {
      background: rgba(255, 255, 255, 0.06);
      color: rgba(255, 255, 255, 0.85);
    }

    .sidebar-nav button.active {
      background: rgba(27, 138, 74, 0.2);
      color: var(--green3);
    }

    .sidebar-nav button .nav-icon {
      width: 20px;
      text-align: center;
      font-size: 1rem;
      flex-shrink: 0;
    }

    .sidebar-nav .nav-section {
      font-size: 0.68rem;
      font-weight: 700;
      color: rgba(255, 255, 255, 0.25);
      text-transform: uppercase;
      letter-spacing: 0.1em;
      padding: 16px 14px 6px;
    }

    .sidebar-user {
      padding: 16px 18px;
      border-top: 1px solid rgba(255, 255, 255, 0.07);
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .sidebar-user .avatar {
      width: 36px;
      height: 36px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--green), var(--green2));
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 800;
      font-size: 0.85rem;
      color: #fff;
      flex-shrink: 0;
    }

    .sidebar-user .user-info {
      overflow: hidden;
    }

    .sidebar-user .user-info strong {
      display: block;
      font-size: 0.85rem;
      color: #fff;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }

    .sidebar-user .user-info span {
      font-size: 0.72rem;
      color: rgba(255, 255, 255, 0.4);
    }

    .sidebar-logout {
      background: none;
      border: none;
      color: rgba(255, 255, 255, 0.35);
      font-size: 0.8rem;
      font-weight: 600;
      cursor: pointer;
      margin-left: auto;
      padding: 6px 10px;
      border-radius: var(--radius-sm);
      font-family: inherit;
      transition: all var(--transition);
    }

    .sidebar-logout:hover {
      color: var(--red);
      background: rgba(220, 72, 72, 0.1);
    }

    /* Mobile sidebar toggle */
    .mobile-toggle {
      display: none;
      position: fixed;
      top: 14px;
      left: 14px;
      z-index: 25;
      background: var(--dark);
      color: #fff;
      border: none;
      border-radius: var(--radius-sm);
      width: 42px;
      height: 42px;
      font-size: 1.2rem;
      cursor: pointer;
      box-shadow: var(--shadow-lg);
    }

    .sidebar-overlay {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.5);
      z-index: 19;
    }

    /* ===== MAIN CONTENT ===== */
    .main-content {
      flex: 1;
      margin-left: var(--sidebar-w);
      min-height: 100vh;
      background: var(--green-bg);
    }

    /* Top Bar */
    .topbar {
      position: sticky;
      top: 0;
      z-index: 10;
      background: rgba(255, 255, 255, 0.85);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border2);
      padding: 0 32px;
      height: var(--topbar-h);
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
    }

    .topbar-left {
      display: flex;
      align-items: center;
      gap: 16px;
    }

    .topbar-welcome {
      font-weight: 700;
      font-size: 1rem;
      color: var(--text);
    }

    .topbar-welcome span {
      color: var(--green);
    }

    .topbar-right {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .topbar-location {
      display: flex;
      align-items: center;
      gap: 6px;
      background: var(--sage);
      border: 1px solid var(--border);
      padding: 7px 14px;
      border-radius: 999px;
      font-size: 0.82rem;
      font-weight: 600;
      color: var(--text2);
      cursor: pointer;
      transition: all var(--transition);
    }

    .topbar-location:hover {
      border-color: var(--green);
    }

    .topbar-location select {
      background: transparent;
      border: none;
      font: inherit;
      font-weight: 700;
      color: var(--green);
      cursor: pointer;
      outline: none;
      padding: 0;
      -webkit-appearance: none;
    }

    .topbar-btn {
      width: 38px;
      height: 38px;
      border-radius: 50%;
      border: 1px solid var(--border);
      background: #fff;
      color: var(--muted);
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      transition: all var(--transition);
      font-size: 1rem;
      position: relative;
    }

    .topbar-btn:hover {
      border-color: var(--green);
      color: var(--green);
    }

    .topbar-btn .badge {
      position: absolute;
      top: -2px;
      right: -2px;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: var(--red);
      color: #fff;
      font-size: 0.6rem;
      font-weight: 800;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .lang-select {
      background: #fff;
      border: 1px solid var(--border);
      border-radius: var(--radius-sm);
      padding: 7px 10px;
      font: inherit;
      font-size: 0.82rem;
      font-weight: 600;
      color: var(--text);
      cursor: pointer;
      outline: none;
      transition: border-color var(--transition);
    }

    .lang-select:hover {
      border-color: var(--green);
    }

    /* ===== PAGE CONTENT ===== */
    .page-content {
      padding: 28px 32px 60px;
      max-width: 1200px;
    }

    .page-section {
      display: none;
    }

    .page-section.active {
      display: block;
    }

    /* ===== CARDS ===== */
    .card {
      background: var(--card-bg);
      backdrop-filter: blur(8px);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 24px;
      box-shadow: var(--shadow-sm);
      transition: all var(--transition);
    }

    .card:hover {
      box-shadow: var(--shadow);
      border-color: #c6dcc9;
    }

    .card h2,
    .card h3 {
      color: var(--dark);
      margin-top: 0;
    }

    .card h2 {
      font-size: 1.2rem;
      margin-bottom: 4px;
    }

    .card h3 {
      font-size: 1.05rem;
    }

    /* ===== GRID LAYOUTS ===== */
    .grid {
      display: grid;
      gap: 18px;
    }

    .grid-2 {
      grid-template-columns: repeat(2, 1fr);
    }

    .grid-3 {
      grid-template-columns: repeat(3, 1fr);
    }

    .grid-4 {
      grid-template-columns: repeat(4, 1fr);
    }

    .grid-sidebar {
      grid-template-columns: 1.4fr 0.6fr;
    }

    /* ===== METRIC CARDS ===== */
    .metric-card {
      position: relative;
      overflow: hidden;
      padding: 20px 22px;
    }

    .metric-card .metric-icon {
      width: 42px;
      height: 42px;
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.2rem;
      margin-bottom: 14px;
    }

    .metric-card .metric-icon.green {
      background: rgba(27, 138, 74, 0.1);
      color: var(--green);
    }

    .metric-card .metric-icon.gold {
      background: rgba(212, 136, 6, 0.1);
      color: var(--gold);
    }

    .metric-card .metric-icon.blue {
      background: rgba(59, 130, 246, 0.1);
      color: var(--blue);
    }

    .metric-card .metric-icon.red {
      background: rgba(220, 72, 72, 0.1);
      color: var(--red);
    }

    .metric-card .metric-label {
      font-size: 0.78rem;
      font-weight: 700;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.04em;
      margin-bottom: 4px;
    }

    .metric-card .metric-value {
      font-size: 1.7rem;
      font-weight: 900;
      color: var(--dark);
      letter-spacing: -0.03em;
      line-height: 1.2;
    }

    .metric-card .metric-sub {
      font-size: 0.78rem;
      color: var(--muted2);
      margin-top: 4px;
    }

    .metric-card .metric-change {
      display: inline-flex;
      align-items: center;
      gap: 3px;
      font-size: 0.75rem;
      font-weight: 700;
      padding: 3px 8px;
      border-radius: 999px;
      margin-top: 6px;
    }

    .metric-change.up {
      background: rgba(27, 138, 74, 0.1);
      color: var(--green);
    }

    .metric-change.down {
      background: rgba(220, 72, 72, 0.1);
      color: var(--red);
    }

    /* ===== SECTION HEADERS ===== */
    .section-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 16px;
      gap: 12px;
    }

    .section-header h2 {
      margin: 0;
    }

    .section-header p {
      margin: 0;
      color: var(--muted);
      font-size: 0.88rem;
    }

    .section-header .section-badge {
      display: inline-flex;
      align-items: center;
      gap: 5px;
      background: var(--sage);
      border: 1px solid var(--border);
      padding: 5px 12px;
      border-radius: 999px;
      font-size: 0.72rem;
      font-weight: 700;
      color: var(--muted);
    }

    /* ===== BUTTONS ===== */
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      padding: 10px 20px;
      border: none;
      border-radius: 999px;
      font: inherit;
      font-weight: 700;
      font-size: 0.88rem;
      cursor: pointer;
      transition: all var(--transition);
      white-space: nowrap;
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--green), var(--green2));
      color: #fff;
      box-shadow: 0 4px 14px rgba(27, 138, 74, 0.2);
    }

    .btn-primary:hover {
      transform: translateY(-1px);
      box-shadow: 0 8px 22px rgba(27, 138, 74, 0.3);
    }

    .btn-secondary {
      background: #fff;
      color: var(--green);
      border: 1px solid var(--border);
    }

    .btn-secondary:hover {
      border-color: var(--green);
      background: var(--sage);
    }

    .btn-sm {
      padding: 7px 14px;
      font-size: 0.8rem;
    }

    .btn-xs {
      padding: 5px 10px;
      font-size: 0.74rem;
    }

    /* ===== PILLS / BADGES ===== */
    .pill {
      display: inline-block;
      padding: 4px 10px;
      border-radius: 999px;
      font-size: 0.72rem;
      font-weight: 800;
      border: 1px solid transparent;
    }

    .pill-green {
      background: rgba(27, 138, 74, 0.1);
      color: var(--green);
      border-color: rgba(27, 138, 74, 0.15);
    }

    .pill-gold {
      background: rgba(212, 136, 6, 0.1);
      color: var(--gold);
      border-color: rgba(212, 136, 6, 0.15);
    }

    .pill-red {
      background: rgba(220, 72, 72, 0.1);
      color: var(--red);
      border-color: rgba(220, 72, 72, 0.15);
    }

    .pill-blue {
      background: rgba(59, 130, 246, 0.1);
      color: var(--blue);
      border-color: rgba(59, 130, 246, 0.15);
    }

    .pill-muted {
      background: var(--sage);
      color: var(--muted);
      border-color: var(--border);
    }

    /* ===== FORM ELEMENTS (in-app) ===== */
    .form-group {
      margin-bottom: 14px;
    }

    .form-group label {
      display: block;
      font-size: 0.8rem;
      font-weight: 700;
      color: var(--text2);
      margin-bottom: 5px;
    }

    .form-group input,
    .form-group select,
    .form-group textarea {
      width: 100%;
      padding: 10px 14px;
      border: 1px solid var(--border);
      border-radius: var(--radius-sm);
      background: #fff;
      color: var(--text);
      font: inherit;
      font-size: 0.9rem;
      outline: none;
      transition: all var(--transition);
    }

    .form-group textarea {
      resize: vertical;
      min-height: 80px;
    }

    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus {
      border-color: var(--green2);
      box-shadow: 0 0 0 3px rgba(40, 168, 95, 0.1);
    }

    .form-row {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 12px;
    }

    .form-inline {
      display: flex;
      gap: 12px;
      align-items: end;
      flex-wrap: wrap;
    }

    .form-inline .form-group {
      flex: 1;
      min-width: 150px;
      margin-bottom: 0;
    }

    /* ===== FORECAST CARDS ===== */
    .forecast-card {
      position: relative;
      overflow: hidden;
    }

    .forecast-card .demand-level {
      position: absolute;
      top: 16px;
      right: 16px;
      padding: 4px 12px;
      border-radius: 999px;
      font-size: 0.7rem;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 0.04em;
    }

    .demand-HIGH {
      background: rgba(27, 138, 74, 0.12);
      color: var(--green);
    }

    .demand-MEDIUM {
      background: rgba(212, 136, 6, 0.12);
      color: var(--gold);
    }

    .demand-LOW {
      background: rgba(220, 72, 72, 0.12);
      color: var(--red);
    }

    .forecast-card .fc-crop {
      font-weight: 800;
      font-size: 1.1rem;
      color: var(--dark);
    }

    .forecast-card .fc-location {
      font-size: 0.82rem;
      color: var(--muted);
      margin-bottom: 14px;
    }

    .forecast-card .fc-stat {
      margin-top: 8px;
    }

    .forecast-card .fc-stat-label {
      font-size: 0.72rem;
      color: var(--muted2);
      font-weight: 600;
    }

    .forecast-card .fc-stat-value {
      font-size: 1.15rem;
      font-weight: 800;
      color: var(--dark);
    }

    .forecast-card .fc-growth {
      display: inline-flex;
      align-items: center;
      gap: 3px;
      font-size: 0.78rem;
      font-weight: 700;
      margin-top: 4px;
    }

    /* ===== HEATMAP ===== */
    .heatmap-container {
      padding: 20px;
      text-align: center;
    }

    .heatmap-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
      gap: 8px;
      margin-top: 16px;
    }

    .heatmap-cell {
      padding: 14px 10px;
      border-radius: var(--radius-sm);
      text-align: center;
      transition: all var(--transition);
      cursor: default;
    }

    .heatmap-cell .district-name {
      font-size: 0.78rem;
      font-weight: 700;
      margin-bottom: 4px;
    }

    .heatmap-cell .district-demand {
      font-size: 0.7rem;
      font-weight: 600;
    }

    .heat-high {
      background: rgba(27, 138, 74, 0.18);
      color: var(--green);
    }

    .heat-medium {
      background: rgba(212, 136, 6, 0.14);
      color: #9a6c04;
    }

    .heat-low {
      background: rgba(220, 72, 72, 0.1);
      color: var(--red);
    }

    .heat-high:hover {
      background: rgba(27, 138, 74, 0.28);
    }

    .heat-medium:hover {
      background: rgba(212, 136, 6, 0.22);
    }

    .heat-low:hover {
      background: rgba(220, 72, 72, 0.18);
    }

    /* ===== TREND CHART ===== */
    .trend-chart {
      width: 100%;
      height: 200px;
      margin-top: 12px;
    }

    /* ===== STAR RATING ===== */
    .stars {
      display: inline-flex;
      gap: 2px;
      font-size: 1.2rem;
    }

    .stars .star {
      cursor: pointer;
      color: var(--border);
      transition: color 0.15s;
      background: none;
      border: none;
      padding: 0;
      font-size: inherit;
    }

    .stars .star.filled {
      color: var(--gold);
    }

    .stars .star:hover {
      color: var(--amber);
    }

    .rating-display {
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    .rating-display .rating-num {
      font-size: 1.1rem;
      font-weight: 800;
      color: var(--dark);
    }

    .rating-display .rating-count {
      font-size: 0.78rem;
      color: var(--muted);
    }

    .stars-static {
      pointer-events: none;
    }

    .stars-static .star {
      cursor: default;
    }

    /* ===== REVIEW CARD ===== */
    .review-item {
      padding: 16px 0;
      border-bottom: 1px solid var(--border2);
    }

    .review-item:last-child {
      border-bottom: 0;
    }

    .review-header {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 8px;
    }

    .review-avatar {
      width: 34px;
      height: 34px;
      border-radius: 50%;
      background: var(--sage2);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 800;
      font-size: 0.78rem;
      color: var(--green);
      flex-shrink: 0;
    }

    .review-meta strong {
      font-size: 0.88rem;
      color: var(--dark);
      display: block;
    }

    .review-meta span {
      font-size: 0.72rem;
      color: var(--muted2);
    }

    .review-body {
      font-size: 0.88rem;
      color: var(--text2);
      margin-bottom: 8px;
      line-height: 1.5;
    }

    .review-tags {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
    }

    .review-report {
      font-size: 0.72rem;
      color: var(--muted2);
      cursor: pointer;
      background: none;
      border: none;
      font-family: inherit;
      margin-left: auto;
    }

    .review-report:hover {
      color: var(--red);
    }

    /* ===== ORDER ITEMS ===== */
    .order-item {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
      padding: 14px 0;
      border-bottom: 1px solid var(--border2);
    }

    .order-item:last-child {
      border-bottom: 0;
    }

    .order-info strong {
      display: block;
      font-size: 0.9rem;
      color: var(--dark);
    }

    .order-info span {
      font-size: 0.78rem;
      color: var(--muted);
    }

    .order-status {
      text-align: right;
    }

    /* ===== LIST ITEMS (marketplace) ===== */
    .list-item {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      padding: 13px 0;
      border-bottom: 1px solid var(--border2);
    }

    .list-item:last-child {
      border-bottom: 0;
    }

    .list-item strong {
      color: var(--dark);
    }

    /* ===== RESULT BLOCKS ===== */
    .result-block {
      margin-top: 14px;
      padding: 16px;
      border-radius: var(--radius-sm);
      background: var(--sage);
      border: 1px dashed var(--border);
      min-height: 20px;
      font-size: 0.9rem;
      line-height: 1.6;
    }

    /* ===== ALERT BLOCK ===== */
    .alert-block {
      padding: 14px 18px;
      border-radius: var(--radius-sm);
      font-size: 0.88rem;
    }

    .alert-warning {
      background: #fff8e6;
      border: 1px solid #efd48b;
      color: #6f5311;
    }

    .alert-info {
      background: rgba(59, 130, 246, 0.06);
      border: 1px solid rgba(59, 130, 246, 0.15);
      color: #2563eb;
    }

    /* ===== CHECKS (route) ===== */
    .checks {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 14px;
    }

    .checks label {
      display: flex;
      align-items: center;
      gap: 6px;
      background: var(--sage);
      padding: 8px 12px;
      border-radius: 999px;
      border: 1px solid var(--border);
      font-weight: 700;
      font-size: 0.85rem;
      cursor: pointer;
      transition: all var(--transition);
    }

    .checks label:hover {
      border-color: var(--green);
    }

    .checks input[type="checkbox"] {
      width: auto;
      accent-color: var(--green);
    }

    /* ===== SCORE ===== */
    .trust-score {
      font-size: 3rem;
      font-weight: 900;
      color: var(--green);
      margin: 10px 0;
    }

    .trust-score span {
      font-size: 1rem;
      color: var(--muted);
    }

    .progress-bar {
      height: 8px;
      background: var(--border2);
      border-radius: 999px;
      overflow: hidden;
    }

    .progress-bar i {
      display: block;
      height: 100%;
      background: linear-gradient(90deg, var(--green), var(--green3));
      border-radius: 999px;
      transition: width 0.6s ease;
    }

    /* ===== FLOW DIAGRAM ===== */
    .flow-row {
      display: flex;
      gap: 8px;
      align-items: center;
      justify-content: center;
      flex-wrap: wrap;
      padding: 12px 0;
    }

    .flow-row .flow-step {
      background: var(--sage);
      border: 1px solid var(--border);
      padding: 8px 14px;
      border-radius: 999px;
      font-weight: 700;
      font-size: 0.82rem;
    }

    .flow-row .flow-arrow {
      color: var(--gold);
      font-weight: 800;
    }

    /* ===== TOAST ===== */
    .toast-container {
      position: fixed;
      bottom: 24px;
      right: 24px;
      z-index: 100;
    }

    .toast {
      background: var(--dark);
      color: #fff;
      padding: 14px 20px;
      border-radius: var(--radius);
      box-shadow: var(--shadow-xl);
      font-size: 0.88rem;
      font-weight: 600;
      display: none;
      max-width: 360px;
    }

    .toast.show {
      display: block;
      animation: toastIn 0.3s ease;
    }

    @keyframes toastIn {
      from {
        transform: translateY(12px) scale(0.95);
        opacity: 0;
      }

      to {
        transform: none;
        opacity: 1;
      }
    }

    /* ===== FOOTER ===== */
    .app-footer {
      text-align: center;
      padding: 24px 32px;
      background: var(--offwhite);
      border-top: 1px solid var(--border2);
      font-size: 0.8rem;
      color: var(--muted);
    }

    .app-footer strong {
      color: var(--dark);
      display: block;
      margin-bottom: 4px;
      font-size: 0.9rem;
    }

    /* ===== DEMO BADGE ===== */
    .demo-badge {
      display: inline-flex;
      align-items: center;
      gap: 4px;
      background: rgba(212, 136, 6, 0.08);
      border: 1px solid rgba(212, 136, 6, 0.15);
      padding: 3px 10px;
      border-radius: 999px;
      font-size: 0.68rem;
      font-weight: 700;
      color: var(--gold);
      text-transform: uppercase;
      letter-spacing: 0.04em;
    }

    /* ===== ANIMATIONS ===== */
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(16px);
      }

      to {
        opacity: 1;
        transform: none;
      }
    }

    .animate-in {
      animation: fadeInUp 0.4s ease forwards;
    }

    .delay-1 {
      animation-delay: 0.05s;
      opacity: 0;
    }

    .delay-2 {
      animation-delay: 0.1s;
      opacity: 0;
    }

    .delay-3 {
      animation-delay: 0.15s;
      opacity: 0;
    }

    .delay-4 {
      animation-delay: 0.2s;
      opacity: 0;
    }

    /* ===== RESPONSIVE ===== */
    @media (max-width: 1024px) {
      .grid-4 {
        grid-template-columns: repeat(2, 1fr);
      }

      .grid-sidebar {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 900px) {
      .sidebar {
        transform: translateX(-100%);
      }

      .sidebar.open {
        transform: translateX(0);
      }

      .sidebar-overlay.open {
        display: block;
      }

      .mobile-toggle {
        display: flex;
      }

      .main-content {
        margin-left: 0;
      }

      .page-content {
        padding: 24px 16px 48px;
      }

      .topbar {
        padding: 0 16px;
        padding-left: 60px;
      }

      .grid-3 {
        grid-template-columns: 1fr 1fr;
      }

      .role-cards {
        grid-template-columns: 1fr;
        max-width: 380px;
      }
    }

    @media (max-width: 640px) {

      .grid-2,
      .grid-3,
      .grid-4 {
        grid-template-columns: 1fr;
      }

      .form-row {
        grid-template-columns: 1fr;
      }

      .form-inline {
        flex-direction: column;
        align-items: stretch;
      }

      .auth-form-row {
        grid-template-columns: 1fr;
      }

      .topbar-welcome {
        display: none;
      }

      h1 {
        font-size: 1.6rem;
      }

      .role-card {
        padding: 28px 20px;
      }
    }
  </style>
</head>

<body>

  <!-- ===== AUTH SCREEN ===== -->
  <div id="authScreen">
    <!-- Language Selector on Landing Page -->
    <div class="auth-topbar">
      <div class="lang-picker-auth">
        <span style="font-size:1.1rem;margin-right:6px;">🌐</span>
        <label for="authLangSelect"
          style="color:rgba(255,255,255,0.85);font-size:0.85rem;margin-right:8px;font-weight:600;cursor:pointer;"
          data-i18n="selectLanguage">Language:</label>
        <select class="auth-lang-select" id="authLangSelect" onchange="changeLang(this.value)">
          <option value="en">English</option>
          <option value="hi">हिंदी (Hindi)</option>
          <option value="kn">ಕನ್ನಡ (Kannada)</option>
          <option value="ta">தமிழ் (Tamil)</option>
          <option value="te">తెలుగు (Telugu)</option>
        </select>
      </div>
    </div>
    <div class="auth-brand">
      <h1>🌾 Kisan<span>Flow</span></h1>
      <p>Predict • Connect • Aggregate • Deliver</p>
      <div class="sih-badge">SIH 2026 — Problem Statement 26033</div>
    </div>

    <!-- Role Selection -->
    <div class="role-cards" id="roleSelection">
      <div class="role-card" onclick="showRegForm('farmer')">
        <span class="icon">🌾</span>
        <h3 data-i18n="roleFarmerTitle">Farmer / FPO</h3>
        <p data-i18n="roleFarmerDesc">Sell your produce directly to verified buyers. Get AI-powered demand forecasts and
          fair pricing.</p>
        <button class="btn-role" type="button">Register as Farmer / FPO</button>
      </div>
      <div class="role-card" onclick="showRegForm('buyer')">
        <span class="icon">🛒</span>
        <h3 data-i18n="roleBuyerTitle">Customer / Buyer</h3>
        <p data-i18n="roleBuyerDesc">Buy directly from farmers and FPOs. Access fresh produce at fair market prices.</p>
        <button class="btn-role" type="button">Register as Customer / Buyer</button>
      </div>
    </div>

    <!-- Farmer Registration -->
    <div class="auth-panel" id="farmerRegPanel">
      <button class="auth-back" onclick="showRoleSelection()" data-i18n="backToRoleSelection">← Back to role
        selection</button>
      <div class="auth-form-card">
        <h2 data-i18n="farmerRegTitle">🌾 Farmer / FPO Registration</h2>
        <p class="subtitle" data-i18n="farmerRegSubtitle">Join KisanFlow to sell your produce directly without middlemen
        </p>
        <form id="farmerRegForm" onsubmit="return registerUser(event,'farmer')">
          <div class="auth-form-row">
            <div><label>Full Name / FPO Name *</label><input name="name" placeholder="Enter your name" required></div>
            <div><label>Mobile Number *</label><input name="mobile" type="tel" placeholder="+91 98765 43210" required>
            </div>
          </div>
          <label>Email</label><input name="email" type="email" placeholder="email@example.com">
          <div class="auth-form-row">
            <div><label>District *</label><input name="district" placeholder="e.g. Mandya" required></div>
            <div><label>State *</label>
              <select name="state" required>
                <option value="Karnataka">Karnataka</option>
                <option value="Tamil Nadu">Tamil Nadu</option>
                <option value="Andhra Pradesh">Andhra Pradesh</option>
                <option value="Telangana">Telangana</option>
                <option value="Maharashtra">Maharashtra</option>
                <option value="Kerala">Kerala</option>
                <option value="Other">Other</option>
              </select>
            </div>
          </div>
          <div class="auth-form-row">
            <div><label>Type *</label>
              <select name="farmerType" required>
                <option value="Farmer">Individual Farmer</option>
                <option value="FPO">FPO (Farmer Producer Org)</option>
              </select>
            </div>
            <div><label>Preferred Language</label>
              <select name="language">
                <option value="en">English</option>
                <option value="hi">हिंदी</option>
                <option value="kn">ಕನ್ನಡ</option>
                <option value="ta">தமிழ்</option>
                <option value="te">తెలుగు</option>
              </select>
            </div>
          </div>
          <label>Crops / Products Handled</label><input name="crops" placeholder="e.g. Tomato, Onion, Potato">
          <div class="auth-form-row">
            <div><label>Available Quantity (kg)</label><input name="quantity" type="number" placeholder="e.g. 5000">
            </div>
            <div><label>Farm / FPO Details</label><input name="details" placeholder="Optional details"></div>
          </div>
          <div class="auth-form-row">
            <div><label>Password *</label><input name="password" type="password" placeholder="Min 6 characters" required
                minlength="6"></div>
            <div><label>Confirm Password *</label><input name="confirmPassword" type="password"
                placeholder="Re-enter password" required minlength="6"></div>
          </div>
          <button type="submit" class="btn-submit" data-i18n="createFarmerAccountBtn">Create Farmer Account</button>
        </form>
        <div class="auth-login-link">Already have an account? <a onclick="showLoginForm()">Sign in</a></div>
      </div>
    </div>

    <!-- Buyer Registration -->
    <div class="auth-panel" id="buyerRegPanel">
      <button class="auth-back" onclick="showRoleSelection()" data-i18n="backToRoleSelection">← Back to role
        selection</button>
      <div class="auth-form-card">
        <h2 data-i18n="customerRegTitle">🛒 Customer / Buyer Registration</h2>
        <p class="subtitle" data-i18n="customerRegSubtitle">Join KisanFlow to buy fresh produce directly from farmers
        </p>
        <form id="buyerRegForm" onsubmit="return registerUser(event,'buyer')">
          <div class="auth-form-row">
            <div><label>Full Name / Business Name *</label><input name="name" placeholder="Enter your name" required>
            </div>
            <div><label>Mobile Number *</label><input name="mobile" type="tel" placeholder="+91 98765 43210" required>
            </div>
          </div>
          <label>Email</label><input name="email" type="email" placeholder="email@example.com">
          <div class="auth-form-row">
            <div><label>Location *</label><input name="location" placeholder="e.g. Bengaluru" required></div>
            <div><label>Buyer Type *</label>
              <select name="buyerType" required>
                <option value="Consumer">Consumer</option>
                <option value="Restaurant">Restaurant</option>
                <option value="Retailer">Retailer</option>
                <option value="Bulk Buyer">Bulk Buyer</option>
              </select>
            </div>
          </div>
          <div class="auth-form-row">
            <div><label>Preferred Products</label><input name="products" placeholder="e.g. Tomato, Onion"></div>
            <div><label>Preferred Language</label>
              <select name="language">
                <option value="en">English</option>
                <option value="hi">हिंदी</option>
                <option value="kn">ಕನ್ನಡ</option>
                <option value="ta">தமிழ்</option>
                <option value="te">తెలుగు</option>
              </select>
            </div>
          </div>
          <div class="auth-form-row">
            <div><label>Password *</label><input name="password" type="password" placeholder="Min 6 characters" required
                minlength="6"></div>
            <div><label>Confirm Password *</label><input name="confirmPassword" type="password"
                placeholder="Re-enter password" required minlength="6"></div>
          </div>
          <button type="submit" class="btn-submit" data-i18n="createBuyerAccountBtn">Create Buyer Account</button>
        </form>
        <div class="auth-login-link">Already have an account? <a onclick="showLoginForm()">Sign in</a></div>
      </div>
    </div>

    <!-- Login Form -->
    <div class="auth-panel" id="loginPanel">
      <button class="auth-back" onclick="showRoleSelection()" data-i18n="backToRoleSelection">← Back to role
        selection</button>
      <div class="auth-form-card">
        <h2 data-i18n="loginTitle">Welcome Back</h2>
        <p class="subtitle" data-i18n="loginSubtitle">Sign in to your KisanFlow account</p>
        <form id="loginForm" onsubmit="return loginUser(event)">
          <label>Mobile Number or Email *</label>
          <input name="identifier" placeholder="Enter mobile or email" required>
          <label>Password *</label>
          <input name="password" type="password" placeholder="Enter password" required>
          <button type="submit" class="btn-submit" data-i18n="signInBtn">Sign In</button>
        </form>
        <div class="auth-login-link">Don't have an account? <a onclick="showRoleSelection()">Register</a></div>
      </div>
    </div>
  </div>

  <!-- ===== APP SHELL ===== -->
  <div id="appShell">
    <!-- Mobile Toggle -->
    <button class="mobile-toggle" id="mobileToggle" onclick="toggleSidebar()">☰</button>
    <div class="sidebar-overlay" id="sidebarOverlay" onclick="toggleSidebar()"></div>

    <!-- Sidebar -->
    <aside class="sidebar" id="sidebar">
      <div class="sidebar-brand">
        <h1>🌾 Kisan<span>Flow</span></h1>
        <p>AI Agricultural Marketplace</p>
      </div>

      <!-- Farmer Nav -->
      <nav class="sidebar-nav" id="farmerNav" style="display:none;">
        <div class="nav-section" data-i18n="navSectionMain">Main</div>
        <button class="active" data-page="dashboard" onclick="navigateTo('dashboard')"><span class="nav-icon">📊</span>
          <span data-i18n="navDashboard">Dashboard</span></button>
        <button data-page="myProduce" onclick="navigateTo('myProduce')"><span class="nav-icon">🌱</span> <span
            data-i18n="navMyProduce">My Produce</span></button>
        <button data-page="buyerRequests" onclick="navigateTo('buyerRequests')"><span class="nav-icon">📋</span> <span
            data-i18n="navBuyerRequests">Buyer Requests</span></button>
        <div class="nav-section" data-i18n="navSectionIntelligence">Intelligence</div>
        <button data-page="forecast" onclick="navigateTo('forecast')"><span class="nav-icon">🔮</span> <span
            data-i18n="navForecast">AI Demand Forecast</span></button>
        <button data-page="priceAdvisor" onclick="navigateTo('priceAdvisor')"><span class="nav-icon">💰</span> <span
            data-i18n="navPriceAdvisor">Price Advisor</span></button>
        <button data-page="profitSim" onclick="navigateTo('profitSim')"><span class="nav-icon">🧮</span> <span
            data-i18n="navProfitSim">Profit Simulator</span></button>
        <div class="nav-section" data-i18n="navSectionOperations">Operations</div>
        <button data-page="orders" onclick="navigateTo('orders')"><span class="nav-icon">📦</span> <span
            data-i18n="navOrders">Orders</span></button>
        <button data-page="logistics" onclick="navigateTo('logistics')"><span class="nav-icon">🚚</span> <span
            data-i18n="navLogistics">Logistics</span></button>
        <button data-page="reviews" onclick="navigateTo('reviews')"><span class="nav-icon">⭐</span> <span
            data-i18n="navReviews">Reviews & Ratings</span></button>
        <div class="nav-section" data-i18n="navSectionAccount">Account</div>
        <button data-page="profile" onclick="navigateTo('profile')"><span class="nav-icon">👤</span> <span
            data-i18n="navProfile">Profile</span></button>
      </nav>

      <!-- Buyer Nav -->
      <nav class="sidebar-nav" id="buyerNav" style="display:none;">
        <div class="nav-section" data-i18n="navSectionMain">Main</div>
        <button class="active" data-page="dashboard" onclick="navigateTo('dashboard')"><span class="nav-icon">📊</span>
          <span data-i18n="navDashboard">Dashboard</span></button>
        <button data-page="browseProduce" onclick="navigateTo('browseProduce')"><span class="nav-icon">🛒</span> <span
            data-i18n="navBrowseProduce">Browse Produce</span></button>
        <button data-page="postRequirement" onclick="navigateTo('postRequirement')"><span class="nav-icon">📝</span>
          <span data-i18n="navPostDemand">Post Requirement</span></button>
        <button data-page="findFarmers" onclick="navigateTo('findFarmers')"><span class="nav-icon">🔍</span> <span
            data-i18n="navFindFarmers">Find Farmers / FPOs</span></button>
        <div class="nav-section" data-i18n="navSectionIntelligence">Intelligence</div>
        <button data-page="forecast" onclick="navigateTo('forecast')"><span class="nav-icon">🔮</span> <span
            data-i18n="navForecast">AI Demand Forecast</span></button>
        <div class="nav-section" data-i18n="navSectionOperations">Operations</div>
        <button data-page="orders" onclick="navigateTo('orders')"><span class="nav-icon">📦</span> <span
            data-i18n="navOrders">Orders</span></button>
        <button data-page="deliveryTracking" onclick="navigateTo('deliveryTracking')"><span class="nav-icon">🚚</span>
          <span data-i18n="navDeliveryTracking">Delivery Tracking</span></button>
        <button data-page="reviews" onclick="navigateTo('reviews')"><span class="nav-icon">⭐</span> <span
            data-i18n="navReviews">Reviews</span></button>
        <button data-page="favorites" onclick="navigateTo('favorites')"><span class="nav-icon">❤️</span> <span
            data-i18n="navFavorites">Favorites</span></button>
        <div class="nav-section" data-i18n="navSectionAccount">Account</div>
        <button data-page="profile" onclick="navigateTo('profile')"><span class="nav-icon">👤</span> <span
            data-i18n="navProfile">Profile</span></button>
      </nav>

      <div class="sidebar-user" id="sidebarUser">
        <div class="avatar" id="userAvatar">U</div>
        <div class="user-info">
          <strong id="userName">User</strong>
          <span id="userRole">Farmer</span>
        </div>
        <button class="sidebar-logout" onclick="logoutUser()" data-i18n="logout">Logout</button>
      </div>
    </aside>

    <!-- Main Content -->
    <div class="main-content">
      <!-- Top Bar -->
      <header class="topbar">
        <div class="topbar-left">
          <span class="topbar-welcome" id="topbarWelcome">Welcome, <span id="topbarName">User</span></span>
        </div>
        <div class="topbar-right">
          <div class="topbar-location">
            📍 <select id="locationSelect" onchange="changeLocation()">
              <option value="Bengaluru">Bengaluru</option>
              <option value="Mysuru">Mysuru</option>
              <option value="Mandya">Mandya</option>
              <option value="Hassan">Hassan</option>
              <option value="Kolar">Kolar</option>
              <option value="Tumakuru">Tumakuru</option>
              <option value="Dharwad">Dharwad</option>
              <option value="Hubli">Hubli</option>
              <option value="Belgaum">Belgaum</option>
            </select>
          </div>
          <button class="topbar-btn" title="Notifications" onclick="toast('No new notifications')">
            🔔 <span class="badge">3</span>
          </button>
          <select class="lang-select" id="langSelect" onchange="changeLang(this.value)">
            <option value="en">English</option>
            <option value="hi">हिंदी</option>
            <option value="kn">ಕನ್ನಡ</option>
            <option value="ta">தமிழ்</option>
            <option value="te">తెలుగు</option>
          </select>
        </div>
      </header>

      <!-- Page Content Container -->
      <div class="page-content">

        <!-- ==================== DASHBOARD ==================== -->
        <div class="page-section active" id="page-dashboard">
          <!-- Welcome Hero -->
          <div class="card"
            style="background:linear-gradient(135deg,var(--dark),#1a5235);color:#fff;border:none;margin-bottom:20px;padding:28px 30px;position:relative;overflow:hidden;">
            <div style="position:absolute;right:24px;bottom:-10px;font-size:5rem;opacity:0.08;">🌾</div>
            <h2 style="color:#fff;font-size:1.5rem;margin-bottom:6px;" id="dashHeroTitle">Agricultural Marketplace
              Intelligence</h2>
            <p style="color:rgba(255,255,255,0.7);max-width:700px;margin:0;" data-i18n="heroText">Connect farmers and
              FPOs directly with consumers, restaurants and bulk buyers while using AI to reduce supply-chain
              inefficiency.</p>
          </div>

          <!-- Key Metrics -->
          <div class="grid grid-4" style="margin-bottom:20px;">
            <div class="card metric-card animate-in delay-1">
              <div class="metric-icon green">🌱</div>
              <div class="metric-label">Available Supply</div>
              <div class="metric-value" id="metricSupply">4</div>
              <div class="metric-sub">Active listings</div>
            </div>
            <div class="card metric-card animate-in delay-2">
              <div class="metric-icon blue">📋</div>
              <div class="metric-label">Buyer Demand</div>
              <div class="metric-value" id="metricDemands">2</div>
              <div class="metric-sub">Active requests</div>
            </div>
            <div class="card metric-card animate-in delay-3">
              <div class="metric-icon gold">🔮</div>
              <div class="metric-label" data-i18n="predictedDemand">Predicted Demand</div>
              <div class="metric-value" id="metricPredicted">5,200 kg</div>
              <div class="metric-sub" id="metricPredictedCrop">Tomato · Next period</div>
            </div>
            <div class="card metric-card animate-in delay-4">
              <div class="metric-icon red">📊</div>
              <div class="metric-label">Supply-Demand Gap</div>
              <div class="metric-value" id="metricGap">3,150 kg</div>
              <div class="metric-change down">⬇ Shortage</div>
            </div>
          </div>

          <!-- AI Forecast + Opportunities -->
          <div class="grid grid-sidebar" style="margin-bottom:20px;">
            <!-- AI Forecast -->
            <div class="card">
              <div class="section-header">
                <div>
                  <h2 data-i18n="forecastHeader">🔮 AI Future Demand Forecast</h2>
                  <p>Predicted crop demand by location</p>
                </div>
                <span class="demo-badge">📊 Demo Forecast Data</span>
              </div>
              <!-- Filters -->
              <div class="form-inline" style="margin-bottom:18px;">
                <div class="form-group">
                  <label>Crop</label>
                  <select id="dashForecastCrop" onchange="updateDashForecast()">
                    <option>Tomato</option>
                    <option>Onion</option>
                    <option>Potato</option>
                  </select>
                </div>
                <div class="form-group">
                  <label>Location</label>
                  <select id="dashForecastLoc" onchange="updateDashForecast()">
                    <option>All Locations</option>
                    <option>Bengaluru</option>
                    <option>Mysuru</option>
                    <option>Mandya</option>
                    <option>Hassan</option>
                    <option>Kolar</option>
                  </select>
                </div>
                <div class="form-group">
                  <label>Period</label>
                  <select id="dashForecastPeriod" onchange="updateDashForecast()">
                    <option value="7">7 Days</option>
                    <option value="15" selected>15 Days</option>
                    <option value="30">30 Days</option>
                  </select>
                </div>
              </div>
              <!-- Forecast Cards -->
              <div class="grid grid-3" id="dashForecastCards"></div>
              <!-- Trend Chart -->
              <div style="margin-top:18px;">
                <h3 style="margin-bottom:8px;">Demand Trend</h3>
                <svg class="trend-chart" id="trendChart" viewBox="0 0 600 180" preserveAspectRatio="none"></svg>
              </div>
            </div>

            <!-- Supply-Demand Opportunities -->
            <div>
              <div class="card" style="margin-bottom:18px;">
                <h3 data-i18n="highDemandNearYou">📍 High Demand Near You</h3>
                <p style="font-size:0.82rem;color:var(--muted);margin-bottom:14px;" id="nearYouLocation">Bengaluru</p>
                <div id="nearYouList"></div>
              </div>
              <div class="card">
                <h3 data-i18n="opportunities">🎯 Opportunities</h3>
                <p style="font-size:0.82rem;color:var(--muted);margin-bottom:12px;">Supply-demand matches</p>
                <div id="opportunitiesList"></div>
              </div>
            </div>
          </div>

          <!-- Recommended + Flow -->
          <div class="grid grid-2" style="margin-bottom:20px;">
            <div class="card" id="recommendedSection">
              <h3 id="recommendedTitle">🤝 Recommended Buyers</h3>
              <div id="recommendedList"></div>
            </div>
            <div class="card">
              <h3>🔄 How KisanFlow Works</h3>
              <div class="flow-row">
                <span class="flow-step" data-i18n="buyerDemand">Buyer Demand</span>
                <span class="flow-arrow">→</span>
                <span class="flow-step" data-i18n="aiForecast">AI Forecast</span>
                <span class="flow-arrow">→</span>
                <span class="flow-step" data-i18n="smartMatching">Smart Matching</span>
                <span class="flow-arrow">→</span>
                <span class="flow-step" data-i18n="aggregation">Aggregation</span>
                <span class="flow-arrow">→</span>
                <span class="flow-step" data-i18n="logistics">Logistics</span>
              </div>
              <p style="margin-top:12px;font-size:0.85rem;" data-i18n="uspText">Instead of waiting for farmers to find
                buyers, KisanFlow starts from predicted market demand and works backwards to identify, aggregate and
                deliver suitable agricultural supply.</p>
            </div>
          </div>

          <!-- Active Orders + Recent Reviews -->
          <div class="grid grid-2" style="margin-bottom:20px;">
            <div class="card">
              <h3 data-i18n="activeOrders">📦 Active Orders</h3>
              <div id="dashOrders"></div>
            </div>
            <div class="card">
              <h3 data-i18n="recentReviews">⭐ Recent Reviews</h3>
              <div id="dashReviews"></div>
            </div>
          </div>

          <!-- Logistics Status -->
          <div class="card" style="margin-bottom:20px;">
            <h3 data-i18n="smartLogisticsStatus">🚚 Smart Logistics Status</h3>
            <div id="dashLogistics"></div>
          </div>
        </div>

        <!-- ==================== MY PRODUCE (Farmer) ==================== -->
        <div class="page-section" id="page-myProduce">
          <div class="section-header">
            <div>
              <h2>🌱 My Produce Listings</h2>
              <p>Manage your supply and add new produce</p>
            </div>
          </div>
          <div class="grid grid-2">
            <div class="card">
              <h3 data-i18n="availableSupply">🌱 Available Supply</h3>
              <div id="farmerProducts"></div>
            </div>
            <div class="card">
              <h3 data-i18n="addSupply">Add Farmer / FPO Supply</h3>
              <form id="productForm" onsubmit="return addSupply(event)">
                <div class="form-group"><label data-i18n="farmerName">Farmer / FPO name</label><input name="farmer"
                    placeholder="Farmer / FPO name" required></div>
                <div class="form-row">
                  <div class="form-group"><label data-i18n="productExample">Product e.g. Tomato</label><input
                      name="product" placeholder="Product e.g. Tomato" required></div>
                  <div class="form-group"><label data-i18n="quantity">Quantity (kg)</label><input name="qty"
                      type="number" min="1" placeholder="Quantity (kg)" required></div>
                </div>
                <div class="form-row">
                  <div class="form-group"><label data-i18n="priceKg">Price per kg</label><input name="price"
                      type="number" min="0" step="0.1" placeholder="Price per kg" required></div>
                  <div class="form-group"><label data-i18n="location">Location</label><input name="location"
                      placeholder="Location" required></div>
                </div>
                <div class="form-group"><label>Quality</label><select name="quality">
                    <option>A</option>
                    <option>B</option>
                  </select></div>
                <button type="submit" class="btn btn-primary" data-i18n="addSupplyBtn">Add Supply</button>
              </form>
            </div>
          </div>
        </div>

        <!-- ==================== BUYER REQUESTS (Farmer) ==================== -->
        <div class="page-section" id="page-buyerRequests">
          <div class="section-header">
            <div>
              <h2>📋 Active Buyer Requests</h2>
              <p>Requirements posted by buyers</p>
            </div>
          </div>
          <div class="card">
            <div id="buyerRequestsList"></div>
          </div>
        </div>

        <!-- ==================== BROWSE PRODUCE (Buyer) ==================== -->
        <div class="page-section" id="page-browseProduce">
          <div class="section-header">
            <div>
              <h2>🛒 Browse Available Produce</h2>
              <p data-i18n="marketText">Direct farmer/FPO listings and reverse buyer requirements.</p>
            </div>
          </div>
          <div class="card">
            <div id="browseProducts"></div>
          </div>
        </div>

        <!-- ==================== POST REQUIREMENT (Buyer) ==================== -->
        <div class="page-section" id="page-postRequirement">
          <div class="section-header">
            <div>
              <h2>📝 Post Buyer Requirement</h2>
              <p>Tell farmers what you need</p>
            </div>
          </div>
          <div class="card">
            <form id="demandForm" onsubmit="return addDemand(event)">
              <div class="form-row">
                <div class="form-group"><label data-i18n="buyerName">Buyer name</label><input name="buyer"
                    placeholder="Buyer name" required></div>
                <div class="form-group"><label data-i18n="product">Product</label><input name="product"
                    placeholder="Product" required></div>
              </div>
              <div class="form-row">
                <div class="form-group"><label data-i18n="quantity">Quantity (kg)</label><input name="qty" type="number"
                    min="1" placeholder="Quantity (kg)" required></div>
                <div class="form-group"><label data-i18n="deliveryLocation">Delivery location</label><input
                    name="location" placeholder="Delivery location" value="Bengaluru" required></div>
              </div>
              <div class="form-row">
                <div class="form-group"><label>Quality</label><select name="quality">
                    <option>A</option>
                    <option>B</option>
                  </select></div>
                <div class="form-group"><label data-i18n="deadline">Deadline (days)</label><input name="deadline_days"
                    type="number" min="1" value="3" placeholder="Deadline (days)"></div>
              </div>
              <button type="submit" class="btn btn-primary" data-i18n="postDemandBtn">Post Demand</button>
            </form>
          </div>
        </div>

        <!-- ==================== FIND FARMERS (Buyer) ==================== -->
        <div class="page-section" id="page-findFarmers">
          <div class="section-header">
            <div>
              <h2>🔍 Find Farmers / FPOs</h2>
              <p>Reverse marketplace — find and aggregate supply</p>
            </div>
          </div>
          <div class="card" style="margin-bottom:18px;">
            <h3 data-i18n="reverseTitle">🧩 Reverse Marketplace + Smart Supply Aggregation</h3>
            <p style="margin-bottom:14px;" data-i18n="reverseText">Enter a buyer requirement. KisanFlow automatically
              finds multiple suitable farmers/FPOs and combines their supply.</p>
            <div class="form-inline">
              <div class="form-group"><label data-i18n="product">Product</label><input id="matchProduct" value="Tomato"
                  placeholder="Product"></div>
              <div class="form-group"><label data-i18n="requiredKg">Required kg</label><input id="matchQty" value="5000"
                  type="number" min="1" placeholder="Required kg"></div>
              <div class="form-group"><label data-i18n="buyerLocation">Buyer location</label><input id="matchLocation"
                  value="Bengaluru" placeholder="Buyer location"></div>
              <div class="form-group"><label>Quality</label><select id="matchQuality">
                  <option>A</option>
                  <option>B</option>
                </select></div>
              <button class="btn btn-primary" onclick="matchSupply()" data-i18n="findAggregate">Find &
                Aggregate</button>
            </div>
            <div class="result-block" id="matchResult"></div>
          </div>
          <div class="card">
            <h3 data-i18n="gapTitle">📊 Supply-Demand Gap Detector</h3>
            <p data-i18n="gapText">Detects shortage or surplus by comparing predicted demand with available supply.</p>
            <div class="result-block" id="gapResult"></div>
          </div>
        </div>

        <!-- ==================== AI DEMAND FORECAST ==================== -->
        <div class="page-section" id="page-forecast">
          <div class="section-header">
            <div>
              <h2>🔮 AI Future Demand Forecast</h2>
              <p>Location-based crop demand forecasting</p>
            </div>
            <span class="demo-badge">📊 Prototype Demo Data</span>
          </div>

          <!-- Forecast Filters -->
          <div class="card" style="margin-bottom:18px;">
            <div class="form-inline">
              <div class="form-group"><label>Crop</label>
                <select id="forecastProduct" onchange="forecast()">
                  <option>Tomato</option>
                  <option>Onion</option>
                  <option>Potato</option>
                </select>
              </div>
              <div class="form-group"><label>Location</label>
                <select id="forecastLocation" onchange="forecast()">
                  <option value="All">All Locations</option>
                  <option>Bengaluru</option>
                  <option>Mysuru</option>
                  <option>Mandya</option>
                  <option>Hassan</option>
                  <option>Kolar</option>
                </select>
              </div>
              <div class="form-group"><label>Forecast Period</label>
                <select id="forecastPeriod" onchange="forecast()">
                  <option value="7">7 Days</option>
                  <option value="15" selected>15 Days</option>
                  <option value="30">30 Days</option>
                </select>
              </div>
              <button class="btn btn-primary" onclick="forecast()" data-i18n="forecastBtn">Forecast Demand</button>
            </div>
          </div>

          <!-- Forecast Results -->
          <div class="grid grid-3" id="forecastCards" style="margin-bottom:18px;"></div>

          <!-- Trend + Heatmap -->
          <div class="grid grid-2">
            <div class="card">
              <h3>📈 Demand Trend Visualization</h3>
              <svg class="trend-chart" id="forecastTrendChart" viewBox="0 0 600 180" preserveAspectRatio="none"></svg>
              <div class="result-block" id="forecastResult"></div>
            </div>
            <div class="card heatmap-container">
              <h3>🗺️ Karnataka Demand Heatmap</h3>
              <p style="font-size:0.82rem;color:var(--muted);margin-bottom:8px;">District-level demand intensity</p>
              <div class="heatmap-grid" id="heatmapGrid"></div>
            </div>
          </div>
        </div>

        <!-- ==================== PRICE ADVISOR ==================== -->
        <div class="page-section" id="page-priceAdvisor">
          <div class="section-header">
            <div>
              <h2>💰 Explainable Price Advisor</h2>
              <p data-i18n="priceText">Get an AI-assisted price range based on predicted demand and market conditions.
              </p>
            </div>
          </div>
          <div class="card">
            <div class="form-inline" style="margin-bottom:14px;">
              <div class="form-group"><label data-i18n="product">Product</label>
                <select id="priceProduct">
                  <option>Tomato</option>
                  <option>Onion</option>
                  <option>Potato</option>
                </select>
              </div>
              <button class="btn btn-primary" onclick="priceAdvice()" data-i18n="calculatePrice">Calculate
                Price</button>
            </div>
            <div class="result-block" id="priceResult"></div>
          </div>
        </div>

        <!-- ==================== PROFIT SIMULATOR ==================== -->
        <div class="page-section" id="page-profitSim">
          <div class="section-header">
            <div>
              <h2>🧮 Farmer Profit Simulator</h2>
              <p data-i18n="profitText">Calculate estimated earnings before accepting an order.</p>
            </div>
          </div>
          <div class="grid grid-2">
            <div class="card">
              <div class="form-group"><label data-i18n="quantity">Quantity (kg)</label><input id="pQty" type="number"
                  value="500" min="1"></div>
              <div class="form-group"><label data-i18n="sellingPrice">Selling price/kg</label><input id="pPrice"
                  type="number" value="24" min="0"></div>
              <div class="form-group"><label data-i18n="transportCost">Transport cost</label><input id="pTransport"
                  type="number" value="800" min="0"></div>
              <div class="form-group"><label data-i18n="platformFee">Platform fee</label><input id="pFee" type="number"
                  value="200" min="0"></div>
              <div class="form-group"><label data-i18n="otherCost">Other cost</label><input id="pOther" type="number"
                  value="300" min="0"></div>
              <button class="btn btn-primary" onclick="profit()" data-i18n="netReturn">Calculate Net Return</button>
              <div class="result-block" id="profitResult"></div>
            </div>
            <div class="card">
              <h3 data-i18n="trustTitle">⭐ Farmer Trust Score</h3>
              <p data-i18n="trustText">The score can be calculated using fulfillment rate, quality, delivery performance
                and transaction history.</p>
              <div class="trust-score">93 <span>/100</span></div>
              <div class="progress-bar"><i style="width:93%"></i></div>
            </div>
          </div>
          <!-- Voice + Fraud -->
          <div class="grid grid-2" style="margin-top:18px;">
            <div class="card">
              <h3 data-i18n="voiceTitle">🎤 Voice + Regional Language Assistant</h3>
              <p data-i18n="voiceText">A farmer can speak instead of typing. Example: <b>"I have 500 kilos of
                  tomatoes."</b></p>
              <button class="btn btn-primary" onclick="demoVoice()" data-i18n="voiceDemo" style="margin-top:10px;">Try
                Voice Demo</button>
              <div class="result-block" id="voiceResult"></div>
            </div>
            <div class="card">
              <h3 data-i18n="fraudTitle">🛡️ Suspicious Order Detection</h3>
              <p data-i18n="fraudText">The system can identify unusual order sizes or abnormal prices and send them for
                verification.</p>
              <div class="alert-block alert-warning" data-i18n="fraudDemo" style="margin-top:10px;">⚠ Demo: A 10,000 kg
                order from a buyer whose historical average is 200 kg/week can be flagged for verification.</div>
            </div>
          </div>
        </div>

        <!-- ==================== ORDERS ==================== -->
        <div class="page-section" id="page-orders">
          <div class="section-header">
            <div>
              <h2>📦 Orders</h2>
              <p>Track and manage all your orders</p>
            </div>
          </div>
          <div class="card">
            <div id="ordersFullList"></div>
          </div>
        </div>

        <!-- ==================== LOGISTICS ==================== -->
        <div class="page-section" id="page-logistics">
          <div class="section-header">
            <div>
              <h2>🚚 Smart Logistics</h2>
              <p>Route optimization and delivery management</p>
            </div>
          </div>
          <div class="card" style="margin-bottom:18px;">
            <h3 data-i18n="routeTitle">🚚 Multi-Order Route Optimizer</h3>
            <p data-i18n="routeText">Select pickup locations. The system generates an optimized collection route.</p>
            <div class="checks" style="margin-top:14px;">
              <label><input type="checkbox" value="Mandya" checked> Mandya</label>
              <label><input type="checkbox" value="Mysuru" checked> Mysuru</label>
              <label><input type="checkbox" value="Hassan"> Hassan</label>
              <label><input type="checkbox" value="Kolar"> Kolar</label>
              <label><input type="checkbox" value="Tumakuru"> Tumakuru</label>
            </div>
            <div class="form-inline">
              <div class="form-group"><label data-i18n="destination">Destination</label><input id="destination"
                  value="Bengaluru" placeholder="Destination"></div>
              <button class="btn btn-primary" onclick="optimizeRoute()" data-i18n="optimizeRoute">Optimize
                Route</button>
            </div>
            <div class="result-block" id="routeResult"></div>
          </div>
          <div class="card">
            <h3 data-i18n="wasteTitle">🥬 Freshness / Wastage Risk</h3>
            <div class="form-inline" style="margin-top:10px;">
              <div class="form-group"><label data-i18n="product">Product</label>
                <select id="wProduct">
                  <option>Tomato</option>
                  <option>Onion</option>
                  <option>Leafy vegetables</option>
                </select>
              </div>
              <div class="form-group"><label data-i18n="distance">Distance km</label><input id="wDistance" type="number"
                  value="140" min="0"></div>
              <div class="form-group"><label data-i18n="hours">Travel hours</label><input id="wHours" type="number"
                  value="4" min="0" step=".5"></div>
              <button class="btn btn-primary" onclick="wastage()" data-i18n="assessRisk">Assess Risk</button>
            </div>
            <div class="result-block" id="wResult"></div>
          </div>
          <div class="card" style="margin-top:18px;">
            <h3 data-i18n="whyRoute">💡 Why This Route?</h3>
            <p data-i18n="routeReason">The logistics engine considers distance, delivery time, vehicle capacity,
              estimated cost and freshness risk.</p>
          </div>
        </div>

        <!-- ==================== DELIVERY TRACKING (Buyer) ==================== -->
        <div class="page-section" id="page-deliveryTracking">
          <div class="section-header">
            <div>
              <h2>🚚 Delivery Tracking</h2>
              <p>Track your order deliveries</p>
            </div>
          </div>
          <div class="card">
            <div id="deliveryList"></div>
          </div>
        </div>

        <!-- ==================== REVIEWS & RATINGS ==================== -->
        <div class="page-section" id="page-reviews">
          <div class="section-header">
            <div>
              <h2 data-i18n="reviewsHeader">⭐ Reviews & Ratings</h2>
              <p>Transaction-based reviews and ratings</p>
            </div>
          </div>
          <div class="grid grid-2">
            <!-- Rating Summary -->
            <div class="card">
              <h3 data-i18n="yourRatingTitle">Your Rating</h3>
              <div style="text-align:center;padding:20px 0;">
                <div style="font-size:3rem;font-weight:900;color:var(--dark);" id="myRatingScore">4.7</div>
                <div class="stars stars-static" id="myRatingStars"></div>
                <div style="font-size:0.85rem;color:var(--muted);margin-top:6px;" id="myReviewCount">Based on 124
                  reviews</div>
                <div style="margin-top:12px;">
                  <span class="pill pill-green">Quality: 4.8</span>
                  <span class="pill pill-blue" style="margin-left:4px;">Delivery: 4.5</span>
                </div>
              </div>
            </div>

            <!-- Write Review -->
            <div class="card">
              <h3 data-i18n="writeReviewTitle">Write a Review</h3>
              <p style="font-size:0.82rem;color:var(--muted);margin-bottom:14px;" data-i18n="rateCompletedTx">Rate a
                completed transaction</p>
              <form onsubmit="return submitReview(event)" id="reviewForm">
                <div class="form-group">
                  <label data-i18n="selectCompletedOrder">Select Completed Order</label>
                  <select name="orderId" id="reviewOrderSelect" required>
                    <option value="">-- Select an order --</option>
                  </select>
                </div>
                <div class="form-group">
                  <label data-i18n="overallRating">Overall Rating *</label>
                  <div class="stars" id="reviewStars">
                    <button type="button" class="star" data-val="1" onclick="setReviewRating(1)">★</button>
                    <button type="button" class="star" data-val="2" onclick="setReviewRating(2)">★</button>
                    <button type="button" class="star" data-val="3" onclick="setReviewRating(3)">★</button>
                    <button type="button" class="star" data-val="4" onclick="setReviewRating(4)">★</button>
                    <button type="button" class="star" data-val="5" onclick="setReviewRating(5)">★</button>
                  </div>
                </div>
                <div class="form-row">
                  <div class="form-group"><label data-i18n="qualityRating">Quality Rating</label>
                    <select name="qualityRating">
                      <option value="">Optional</option>
                      <option value="5">5 — Excellent</option>
                      <option value="4">4 — Good</option>
                      <option value="3">3 — Average</option>
                      <option value="2">2 — Below Avg</option>
                      <option value="1">1 — Poor</option>
                    </select>
                  </div>
                  <div class="form-group"><label data-i18n="deliveryRating">Delivery / Logistics Rating</label>
                    <select name="deliveryRating">
                      <option value="">Optional</option>
                      <option value="5">5 — Excellent</option>
                      <option value="4">4 — Good</option>
                      <option value="3">3 — Average</option>
                      <option value="2">2 — Below Avg</option>
                      <option value="1">1 — Poor</option>
                    </select>
                  </div>
                </div>
                <div class="form-group"><label data-i18n="yourReview">Your Review</label><textarea name="reviewText"
                    placeholder="Share your experience..." rows="3"></textarea></div>
                <button type="submit" class="btn btn-primary" data-i18n="submitReviewBtn">Submit Review</button>
              </form>
            </div>
          </div>
          <!-- All Reviews -->
          <div class="card" style="margin-top:18px;">
            <h3 data-i18n="allReviewsTitle">All Reviews</h3>
            <div id="allReviewsList"></div>
          </div>
        </div>

        <!-- ==================== FAVORITES (Buyer) ==================== -->
        <div class="page-section" id="page-favorites">
          <div class="section-header">
            <div>
              <h2>❤️ Favorites</h2>
              <p>Your saved farmers and produce</p>
            </div>
          </div>
          <div class="card">
            <div id="favoritesList">
              <p style="color:var(--muted);font-size:0.88rem;">No favorites saved yet. Browse produce to add favorites.
              </p>
            </div>
          </div>
        </div>

        <!-- ==================== PROFILE ==================== -->
        <div class="page-section" id="page-profile">
          <div class="section-header">
            <div>
              <h2>👤 Profile</h2>
              <p>Your account details</p>
            </div>
          </div>
          <div class="card" id="profileCard"></div>
        </div>

      </div>

      <!-- Footer -->
      <footer class="app-footer">
        <strong>KisanFlow AI</strong>
        <span data-i18n="footer2">Demand • Supply • Price • Logistics • AI</span>
        <br><span style="font-size:0.72rem;">SIH 2026 — Problem Statement 26033</span>
      </footer>
    </div>
  </div>

  <!-- Toast -->
  <div class="toast-container">
    <div id="toast" class="toast"></div>
  </div>

  script>
  /* =====================================================
  KISANFLOW AI — COMPLETE APPLICATION LOGIC
  All existing functionality preserved + new features
  ===================================================== */

  // ===== I18N TRANSLATIONS (FULLY PRESERVED) =====
  const T = {
  "en": {
  "tagline": "Predict • Connect • Aggregate • Deliver",
  "sihBadge": "SIH 2026 — Problem Statement 26033",
  "language": "Language",
  "selectLanguage": "Language:",
  "authSubtitle": "Agricultural Marketplace Intelligence",
  "authHeroDesc": "Connect farmers and FPOs directly with verified buyers using AI demand prediction and smart
  logistics.",
  "roleFarmerTitle": "FARMER / FPO",
  "roleFarmerDesc": "Sell your produce directly to verified buyers. Get AI-powered demand forecasts and fair pricing.",
  "registerFarmerBtn": "Register as Farmer / FPO",
  "roleBuyerTitle": "CUSTOMER / BUYER",
  "roleBuyerDesc": "Buy directly from farmers and FPOs. Access fresh produce at fair market prices.",
  "registerBuyerBtn": "Register as Customer / Buyer",
  "demoFarmerLogin": "Demo: Login as Farmer (Ramesh Patil)",
  "demoBuyerLogin": "Demo: Login as Customer (Priya Sharma)",
  "alreadyHaveAccount": "Already have an account?",
  "signInHere": "Sign In Here",
  "dontHaveAccount": "Don't have an account?",
  "registerHere": "Register Here",
  "backToRoleSelection": "← Back to role selection",
  "farmerRegTitle": "🌾 Farmer / FPO Registration",
  "farmerRegSubtitle": "Join KisanFlow to sell your produce directly without middlemen",
  "customerRegTitle": "🛒 Customer / Buyer Registration",
  "customerRegSubtitle": "Join KisanFlow to buy fresh produce directly from farmers",
  "fullNameLabel": "Full Name / FPO Name *",
  "mobileLabel": "Mobile Number *",
  "emailLabel": "Email",
  "districtLabel": "District *",
  "stateLabel": "State *",
  "entityTypeLabel": "Entity Type *",
  "preferredLangLabel": "Preferred Language",
  "cropsLabel": "Primary Crops Grown",
  "qtyLabel": "Available Quantity / Farm Size (Acres)",
  "farmDetailsLabel": "Farm / FPO Details",
  "bankUpiLabel": "Bank Account / UPI ID (for direct payouts) *",
  "passwordLabel": "Password *",
  "confirmPasswordLabel": "Confirm Password *",
  "verifyTermsFarmer": "I verify that I am a genuine farmer/FPO and agree to KisanFlow terms",
  "verifyTermsBuyer": "I agree to fair transaction practices and KisanFlow terms",
  "createFarmerAccountBtn": "Create Farmer Account",
  "createBuyerAccountBtn": "Create Buyer Account",
  "businessNameLabel": "Full Name / Business Name *",
  "buyerTypeLabel": "Buyer Type *",
  "deliveryLocationLabel": "Delivery Location / Address *",
  "pinCodeLabel": "PIN Code *",
  "contactLabel": "Contact Phone Number *",
  "gstLabel": "GST Number / Business ID (Optional for individuals)",
  "preferredProductsLabel": "Produce of Interest",
  "loginTitle": "Welcome Back",
  "loginSubtitle": "Sign in to your KisanFlow account",
  "mobileOrEmailLabel": "Mobile Number or Email *",
  "signInBtn": "Sign In",
  "dashboard": "Dashboard",
  "marketplace": "Marketplace",
  "ai": "AI Intelligence",
  "logistics": "Logistics",
  "farmerTools": "Farmer Tools",
  "heroTitle": "Demand-to-Delivery Agricultural Marketplace",
  "heroText": "Connect farmers and FPOs directly with consumers, restaurants and bulk buyers while using AI to reduce
  supply-chain inefficiency.",
  "suppliers": "Suppliers",
  "buyerDemands": "Buyer Demands",
  "tomatoDemand": "Predicted Tomato Demand",
  "nextPeriod": "Next period",
  "demandTrend": "Demand Trend",
  "aiSignal": "AI signal",
  "suggestedPrice": "Suggested Tomato Price",
  "perKg": "Per kg",
  "supplyGap": "Supply Gap",
  "currentPrediction": "Current prediction",
  "howWorks": "🔄 How KisanFlow Works",
  "buyerDemand": "Buyer Demand",
  "aiForecast": "AI Forecast",
  "smartMatching": "Smart Matching",
  "aggregation": "Aggregation",
  "coreUsp": "🎯 Core USP",
  "uspText": "Instead of waiting for farmers to find buyers, KisanFlow starts from predicted market demand and works
  backwards to identify, aggregate and deliver suitable agricultural supply.",
  "marketText": "Direct farmer/FPO listings and reverse buyer requirements.",
  "availableSupply": "🌱 Available Supply",
  "buyerBoard": "🛒 Buyer Demand Board",
  "addSupply": "Add Farmer / FPO Supply",
  "farmerName": "Farmer / FPO name",
  "productExample": "Product e.g. Tomato",
  "product": "Product",
  "quantity": "Quantity (kg)",
  "priceKg": "Price per kg",
  "location": "Location",
  "addSupplyBtn": "Add Supply",
  "postDemand": "Post Buyer Requirement",
  "buyerName": "Buyer name",
  "deliveryLocation": "Delivery location",
  "deadline": "Deadline (days)",
  "postDemandBtn": "Post Demand",
  "forecastTitle": "🔮 AI Demand Forecast",
  "forecastText": "Predict future demand using historical transactions, seasonal patterns and market signals.",
  "forecastBtn": "Forecast Demand",
  "priceTitle": "💰 Explainable Price Advisor",
  "priceText": "Get an AI-assisted price range based on predicted demand and market conditions.",
  "calculatePrice": "Calculate Price",
  "reverseTitle": "🧩 Reverse Marketplace + Smart Supply Aggregation",
  "reverseText": "Enter a buyer requirement. KisanFlow automatically finds multiple suitable farmers/FPOs and combines
  their supply.",
  "requiredKg": "Required kg",
  "buyerLocation": "Buyer location",
  "findAggregate": "Find & Aggregate",
  "gapTitle": "📊 Supply-Demand Gap Detector",
  "gapText": "Detects shortage or surplus by comparing predicted demand with available supply.",
  "wasteTitle": "🥬 Freshness / Wastage Risk",
  "distance": "Distance km",
  "hours": "Travel hours",
  "assessRisk": "Assess Risk",
  "routeTitle": "🚚 Multi-Order Route Optimizer",
  "routeText": "Select pickup locations. The system generates an optimized collection route.",
  "destination": "Destination",
  "optimizeRoute": "Optimize Route",
  "whyRoute": "💡 Why This Route?",
  "routeReason": "The logistics engine considers distance, delivery time, vehicle capacity, estimated cost and freshness
  risk.",
  "profitTitle": "🧮 Farmer Profit Simulator",
  "profitText": "Calculate estimated earnings before accepting an order.",
  "sellingPrice": "Selling price/kg",
  "transportCost": "Transport cost",
  "platformFee": "Platform fee",
  "otherCost": "Other cost",
  "netReturn": "Calculate Net Return",
  "trustTitle": "⭐ Farmer Trust Score",
  "trustText": "The score can be calculated using fulfillment rate, quality, delivery performance and transaction
  history.",
  "voiceTitle": "🎤 Voice + Regional Language Assistant",
  "voiceText": "A farmer can speak instead of typing. Example: <b>\"I have 500 kilos of tomatoes.\"</b>",
  "voiceDemo": "Try Voice Demo",
  "fraudTitle": "🛡️ Suspicious Order Detection",
  "fraudText": "The system can identify unusual order sizes or abnormal prices and send them for verification.",
  "fraudDemo": "⚠ Demo: A 10,000 kg order from a buyer whose historical average is 200 kg/week can be flagged for
  verification.",
  "footer2": "Demand • Supply • Price • Logistics • AI",
  "supplyAdded": "Supply added successfully.",
  "demandAdded": "Buyer demand posted successfully.",
  "forecastMsg": "forecast",
  "demand": "Expected demand",
  "priceRange": "Recommended range",
  "gapMsg": "Current gap",
  "aggregateMsg": "Aggregated supply",
  "shortage": "Shortage",
  "surplus": "Surplus",
  "risk": "Risk",
  "routeDone": "Optimized route",
  "estimatedDistance": "Estimated distance",
  "estimatedCost": "Estimated logistics cost",
  "net": "Estimated net return",
  "voiceReady": "Voice demo ready: 500 kg Tomato supply detected.",
  "noSupply": "No suitable supply found.",
  "invalid": "Please enter valid values.",
  "bullish": "Positive",
  "softening": "Softening",
  "low": "Low",
  "medium": "Medium",
  "high": "High",
  "navSectionMain": "Main",
  "navSectionIntelligence": "Intelligence",
  "navSectionOperations": "Operations",
  "navSectionAccount": "Account",
  "navDashboard": "Dashboard",
  "navMyProduce": "My Produce",
  "navBuyerRequests": "Buyer Requests",
  "navBrowseProduce": "Browse Produce",
  "navPostDemand": "Post Requirement",
  "navFindFarmers": "Find Farmers / FPOs",
  "navForecast": "AI Demand Forecast",
  "navPriceAdvisor": "Price Advisor",
  "navProfitSim": "Profit Simulator",
  "navOrders": "Orders",
  "navLogistics": "Logistics",
  "navDeliveryTracking": "Delivery Tracking",
  "navReviews": "Reviews & Ratings",
  "navFavorites": "Favorites",
  "navProfile": "Profile",
  "logout": "Logout",
  "roleFarmer": "Farmer 🌾",
  "roleBuyer": "Customer 🛒",
  "activeSupplyListings": "Active Supply Listings",
  "liveBuyerDemands": "Live Buyer Demands",
  "predictedDemand": "Predicted Demand",
  "highDemandNearYou": "📍 High Demand Near You",
  "opportunities": "🎯 Opportunities",
  "recommendedBuyers": "🤝 Recommended Buyers",
  "activeOrders": "📦 Active Orders",
  "recentReviews": "⭐ Recent Reviews",
  "smartLogisticsStatus": "🚚 Smart Logistics Status",
  "forecastHeader": "🔮 AI Future Demand Forecast",
  "forecastSubheader": "Predict future agricultural demand, analyze district trends, and harvest at optimal profit",
  "cropLabel": "Crop",
  "periodLabel": "Period",
  "heatmapTitle": "🗺️ Karnataka Agricultural Demand Heatmap",
  "heatmapDesc": "Real-time demand intensity, price trends, and shortage indicators across Karnataka districts",
  "trendChartTitle": "📈 Demand Trend Visualization (7-Day & 30-Day Curve)",
  "highDemandAlertsTitle": "⚡ High Demand Surge Alerts & Harvest Windows",
  "reviewsHeader": "⭐ Reviews & Ratings",
  "reviewsSubheader": "Transparent reputation system connecting verified farmers and trusted buyers",
  "yourRatingTitle": "Your Rating",
  "writeReviewTitle": "Write a Review",
  "rateCompletedTx": "Rate a completed transaction",
  "selectCompletedOrder": "Select Completed Order",
  "overallRating": "Overall Rating *",
  "qualityRating": "Quality Rating",
  "deliveryRating": "Delivery / Logistics Rating",
  "yourReview": "Your Review",
  "submitReviewBtn": "Submit Review",
  "allReviewsTitle": "All Reviews",
  "browseHeader": "🛒 Browse Fresh Produce",
  "browseSubheader": "Direct from verified farmers and FPOs at transparent farm gate prices",
  "expectedGrowth": "Expected Growth",
  "harvestInDays": "Optimal Harvest Window: 3-5 Days",
  "surgeExpected": "Expected price surge due to festival and urban demand",
  "qualityScore": "Produce Freshness",
  "orderStatus": "Status",
  "completed": "Completed",
  "inTransit": "In Transit",
  "pending": "Pending",
  "farmGatePrice": "Farm Gate Price",
  "retailPrice": "Market Retail Price",
  "directPrice": "KisanFlow Direct",
  "placeOrder": "Place Order",
  "savingsMsg": "Save up to 32% by eliminating intermediaries"
  },
  "hi": {
  "tagline": "पूर्वानुमान • कनेक्ट • एकत्रित • डिलीवर",
  "sihBadge": "SIH 2026 — समस्या विवरण 26033",
  "language": "भाषा",
  "selectLanguage": "भाषा चुनें:",
  "authSubtitle": "कृषि मार्केटप्लेस इंटेलिजेंस",
  "authHeroDesc": "AI मांग पूर्वानुमान और स्मार्ट लॉजिस्टिक्स द्वारा किसानों और FPO को सीधे सत्यापित खरीदारों से
  जोड़ें।",
  "roleFarmerTitle": "किसान / FPO",
  "roleFarmerDesc": "अपनी फसल सीधे सत्यापित खरीदारों को बेचें। AI मांग पूर्वानुमान और उचित मूल्य प्राप्त करें।",
  "registerFarmerBtn": "किसान / FPO के रूप में पंजीकरण करें",
  "roleBuyerTitle": "ग्राहक / खरीदार",
  "roleBuyerDesc": "किसानों और FPO से सीधे ताज़ा उत्पाद खरीदें। पारदर्शी और उचित बाज़ार मूल्य पाएं।",
  "registerBuyerBtn": "ग्राहक / खरीदार के रूप में पंजीकरण करें",
  "demoFarmerLogin": "डेमो: किसान लॉगिन (रमेश पाटिल)",
  "demoBuyerLogin": "डेमो: खरीदार लॉगिन (प्रिया शर्मा)",
  "alreadyHaveAccount": "क्या आपके पास पहले से खाता है?",
  "signInHere": "यहाँ साइन इन करें",
  "dontHaveAccount": "खाता नहीं है?",
  "registerHere": "पंजीकरण करें",
  "backToRoleSelection": "← भूमिका चयन पर वापस जाएं",
  "farmerRegTitle": "🌾 किसान / FPO पंजीकरण",
  "farmerRegSubtitle": "बिचौलियों के बिना अपनी उपज सीधे बेचने के लिए KisanFlow से जुड़ें",
  "customerRegTitle": "🛒 ग्राहक / खरीदार पंजीकरण",
  "customerRegSubtitle": "किसानों से सीधे ताज़ी उपज खरीदने के लिए KisanFlow से जुड़ें",
  "fullNameLabel": "पूरा नाम / FPO नाम *",
  "mobileLabel": "मोबाइल नंबर *",
  "emailLabel": "ईमेल",
  "districtLabel": "ज़िला *",
  "stateLabel": "राज्य *",
  "entityTypeLabel": "प्रकार *",
  "preferredLangLabel": "पसंदीदा भाषा",
  "cropsLabel": "मुख्य फसलें",
  "qtyLabel": "उपलब्ध मात्रा / खेत का आकार (एकड़)",
  "farmDetailsLabel": "खेत / FPO विवरण",
  "bankUpiLabel": "बैंक खाता / UPI आईडी (सीधे भुगतान के लिए) *",
  "passwordLabel": "पासवर्ड *",
  "confirmPasswordLabel": "पासवर्ड की पुष्टि करें *",
  "verifyTermsFarmer": "मैं पुष्टि करता हूँ कि मैं एक वास्तविक किसान/FPO हूँ और नियमों से सहमत हूँ",
  "verifyTermsBuyer": "मैं पारदर्शी लेनदेन और KisanFlow के नियमों से सहमत हूँ",
  "createFarmerAccountBtn": "किसान खाता बनाएं",
  "createBuyerAccountBtn": "खरीदार खाता बनाएं",
  "businessNameLabel": "पूरा नाम / व्यापार का नाम *",
  "buyerTypeLabel": "खरीदार का प्रकार *",
  "deliveryLocationLabel": "डिलीवरी का पता / स्थान *",
  "pinCodeLabel": "पिन कोड *",
  "contactLabel": "संपर्क फोन नंबर *",
  "gstLabel": "GST नंबर / बिज़नेस आईडी (व्यक्तियों के लिए वैकल्पिक)",
  "preferredProductsLabel": "रुचि के उत्पाद",
  "loginTitle": "वापसी पर स्वागत है",
  "loginSubtitle": "अपने KisanFlow खाते में साइन इन करें",
  "mobileOrEmailLabel": "मोबाइल नंबर या ईमेल *",
  "signInBtn": "साइन इन करें",
  "dashboard": "डैशबोर्ड",
  "marketplace": "मार्केटप्लेस",
  "ai": "AI इंटेलिजेंस",
  "logistics": "लॉजिस्टिक्स",
  "farmerTools": "किसान टूल्स",
  "heroTitle": "डिमांड से डिलीवरी तक कृषि मार्केटप्लेस",
  "heroText": "किसानों और FPO को उपभोक्ताओं, रेस्टोरेंट और थोक खरीदारों से सीधे जोड़ें और AI से सप्लाई चेन की अक्षमता कम
  करें।",
  "suppliers": "आपूर्तिकर्ता",
  "buyerDemands": "खरीदार की मांग",
  "tomatoDemand": "अनुमानित टमाटर मांग",
  "nextPeriod": "अगली अवधि",
  "demandTrend": "मांग का रुझान",
  "aiSignal": "AI संकेत",
  "suggestedPrice": "सुझाई गई टमाटर कीमत",
  "perKg": "प्रति किलो",
  "supplyGap": "आपूर्ति अंतर",
  "currentPrediction": "वर्तमान अनुमान",
  "howWorks": "🔄 KisanFlow कैसे काम करता है",
  "buyerDemand": "खरीदार मांग",
  "aiForecast": "AI पूर्वानुमान",
  "smartMatching": "स्मार्ट मैचिंग",
  "aggregation": "एकत्रीकरण",
  "coreUsp": "🎯 मुख्य विशेषता",
  "uspText": "किसानों के खरीदार खोजने का इंतजार करने के बजाय, KisanFlow अनुमानित बाजार मांग से शुरू करता है और उपयुक्त
  कृषि आपूर्ति को खोजकर, एकत्रित करके और पहुंचाकर काम करता है।",
  "marketText": "सीधी किसान/FPO लिस्टिंग और खरीदार की आवश्यकताएं।",
  "availableSupply": "🌱 उपलब्ध आपूर्ति",
  "buyerBoard": "🛒 खरीदार मांग बोर्ड",
  "addSupply": "किसान / FPO आपूर्ति जोड़ें",
  "farmerName": "किसान / FPO नाम",
  "productExample": "उत्पाद जैसे टमाटर",
  "product": "उत्पाद",
  "quantity": "मात्रा (किलो)",
  "priceKg": "प्रति किलो कीमत",
  "location": "स्थान",
  "addSupplyBtn": "आपूर्ति जोड़ें",
  "postDemand": "खरीदार की आवश्यकता पोस्ट करें",
  "buyerName": "खरीदार का नाम",
  "deliveryLocation": "डिलीवरी स्थान",
  "deadline": "समय सीमा (दिन)",
  "postDemandBtn": "मांग पोस्ट करें",
  "forecastTitle": "🔮 AI मांग पूर्वानुमान",
  "forecastText": "ऐतिहासिक लेनदेन, मौसमी पैटर्न और बाजार संकेतों से भविष्य की मांग का अनुमान लगाएं।",
  "forecastBtn": "मांग का पूर्वानुमान लगाएं",
  "priceTitle": "💰 समझाने योग्य मूल्य सलाहकार",
  "priceText": "अनुमानित मांग और बाजार स्थितियों के आधार पर AI-सहायित मूल्य सीमा प्राप्त करें।",
  "calculatePrice": "कीमत की गणना करें",
  "reverseTitle": "🧩 रिवर्स मार्केट + स्मार्ट सप्लाई एग्रीगेशन",
  "reverseText": "खरीदार की आवश्यकता दर्ज करें। KisanFlow उपयुक्त किसानों/FPO को खोजकर उनकी आपूर्ति को एकत्रित करता
  है।",
  "requiredKg": "आवश्यक किलो",
  "buyerLocation": "खरीदार का स्थान",
  "findAggregate": "खोजें और एकत्रित करें",
  "gapTitle": "📊 आपूर्ति-मांग अंतर",
  "gapText": "अनुमानित मांग और उपलब्ध आपूर्ति की तुलना करके कमी या अधिशेष पहचानता है।",
  "wasteTitle": "🥬 ताजगी / बर्बादी जोखिम",
  "distance": "दूरी किमी",
  "hours": "यात्रा घंटे",
  "assessRisk": "जोखिम जांचें",
  "routeTitle": "🚚 मल्टी-ऑर्डर रूट ऑप्टिमाइज़र",
  "routeText": "पिकअप स्थान चुनें। सिस्टम अनुकूलित संग्रह मार्ग बनाएगा।",
  "destination": "गंतव्य",
  "optimizeRoute": "रूट ऑप्टिमाइज़ करें",
  "whyRoute": "💡 यह रूट क्यों?",
  "routeReason": "लॉजिस्टिक्स इंजन दूरी, डिलीवरी समय, वाहन क्षमता, अनुमानित लागत और ताजगी जोखिम को ध्यान में रखता है।",
  "profitTitle": "🧮 किसान लाभ सिम्युलेटर",
  "profitText": "ऑर्डर स्वीकार करने से पहले अनुमानित कमाई की गणना करें।",
  "sellingPrice": "बिक्री कीमत/किलो",
  "transportCost": "परिवहन लागत",
  "platformFee": "प्लेटफॉर्म शुल्क",
  "otherCost": "अन्य लागत",
  "netReturn": "शुद्ध रिटर्न निकालें",
  "trustTitle": "⭐ किसान विश्वास स्कोर",
  "trustText": "स्कोर पूर्ति दर, गुणवत्ता, डिलीवरी प्रदर्शन और लेनदेन इतिहास से निकाला जा सकता है।",
  "voiceTitle": "🎤 वॉइस + क्षेत्रीय भाषा सहायक",
  "voiceText": "किसान टाइप करने के बजाय बोल सकता है। उदाहरण: <b>\"मेरे पास 500 किलो टमाटर हैं।\"</b>",
  "voiceDemo": "वॉइस डेमो आज़माएं",
  "fraudTitle": "🛡️ संदिग्ध ऑर्डर पहचान",
  "fraudText": "असामान्य ऑर्डर मात्रा या कीमत पहचानकर सत्यापन के लिए भेजी जा सकती है।",
  "fraudDemo": "⚠ डेमो: 200 किलो/सप्ताह औसत वाले खरीदार का 10,000 किलो ऑर्डर सत्यापन के लिए चिन्हित किया जा सकता है।",
  "footer2": "मांग • आपूर्ति • कीमत • लॉजिस्टिक्स • AI",
  "supplyAdded": "आपूर्ति सफलतापूर्वक जोड़ी गई।",
  "demandAdded": "खरीदार की मांग सफलतापूर्वक पोस्ट हुई।",
  "forecastMsg": "का पूर्वानुमान",
  "demand": "अपेक्षित मांग",
  "priceRange": "अनुशंसित सीमा",
  "gapMsg": "वर्तमान अंतर",
  "aggregateMsg": "एकत्रित आपूर्ति",
  "shortage": "कमी",
  "surplus": "अधिशेष",
  "risk": "जोखिम",
  "routeDone": "अनुकूलित रूट",
  "estimatedDistance": "अनुमानित दूरी",
  "estimatedCost": "अनुमानित लॉजिस्टिक्स लागत",
  "net": "अनुमानित शुद्ध रिटर्न",
  "voiceReady": "वॉइस डेमो तैयार: 500 किलो टमाटर की आपूर्ति पहचानी गई।",
  "noSupply": "उपयुक्त आपूर्ति नहीं मिली।",
  "invalid": "कृपया सही मान दर्ज करें।",
  "bullish": "सकारात्मक",
  "softening": "कमज़ोर",
  "low": "कम",
  "medium": "मध्यम",
  "high": "उच्च",
  "navSectionMain": "मुख्य",
  "navSectionIntelligence": "इंटेलिजेंस",
  "navSectionOperations": "संचालन",
  "navSectionAccount": "खाता",
  "navDashboard": "डैशबोर्ड",
  "navMyProduce": "मेरी फसल/उपज",
  "navBuyerRequests": "खरीदार अनुरोध",
  "navBrowseProduce": "उपज ब्राउज़ करें",
  "navPostDemand": "मांग पोस्ट करें",
  "navFindFarmers": "किसान / FPO खोजें",
  "navForecast": "AI मांग पूर्वानुमान",
  "navPriceAdvisor": "मूल्य सलाहकार",
  "navProfitSim": "लाभ सिम्युलेटर",
  "navOrders": "ऑर्डर्स",
  "navLogistics": "लॉजिस्टिक्स",
  "navDeliveryTracking": "डिलीवरी ट्रैकिंग",
  "navReviews": "समीक्षा और रेटिंग",
  "navFavorites": "पसंदीदा",
  "navProfile": "प्रोफ़ाइल",
  "logout": "लॉग आउट",
  "roleFarmer": "किसान 🌾",
  "roleBuyer": "ग्राहक 🛒",
  "activeSupplyListings": "सक्रिय फसल लिस्टिंग",
  "liveBuyerDemands": "सक्रिय खरीदार मांगें",
  "predictedDemand": "अनुमानित मांग",
  "highDemandNearYou": "📍 आपके पास उच्च मांग",
  "opportunities": "🎯 बाजार अवसर",
  "recommendedBuyers": "🤝 अनुशंसित खरीदार",
  "activeOrders": "📦 सक्रिय ऑर्डर्स",
  "recentReviews": "⭐ हाल की समीक्षाएं",
  "smartLogisticsStatus": "🚚 स्मार्ट लॉजिस्टिक्स स्थिति",
  "forecastHeader": "🔮 AI भविष्य मांग पूर्वानुमान",
  "forecastSubheader": "भविष्य की कृषि मांग का अनुमान लगाएं, ज़िला रुझान समझें और सही समय पर फसल काटें",
  "cropLabel": "फसल",
  "periodLabel": "अवधि",
  "heatmapTitle": "🗺️ कर्नाटक कृषि मांग हीटमैप",
  "heatmapDesc": "कर्नाटक के ज़िलों में मांग की तीव्रता, मूल्य रुझान और आपूर्ति की कमी का लाइव दृश्य",
  "trendChartTitle": "📈 मांग रुझान विश्लेषण (7-दिन और 30-दिन वक्र)",
  "highDemandAlertsTitle": "⚡ उच्च मांग अलर्ट और कटाई का सही समय",
  "reviewsHeader": "⭐ समीक्षा और रेटिंग",
  "reviewsSubheader": "सत्यापित किसानों और भरोसेमंद खरीदारों के बीच पारदर्शी प्रतिष्ठा प्रणाली",
  "yourRatingTitle": "आपकी रेटिंग",
  "writeReviewTitle": "समीक्षा लिखें",
  "rateCompletedTx": "पूर्ण लेनदेन का मूल्यांकन करें",
  "selectCompletedOrder": "पूर्ण ऑर्डर चुनें",
  "overallRating": "समग्र रेटिंग *",
  "qualityRating": "गुणवत्ता रेटिंग",
  "deliveryRating": "डिलीवरी / लॉजिस्टिक्स रेटिंग",
  "yourReview": "आपकी समीक्षा",
  "submitReviewBtn": "समीक्षा सबमिट करें",
  "allReviewsTitle": "सभी समीक्षाएं",
  "browseHeader": "🛒 ताज़ी उपज ब्राउज़ करें",
  "browseSubheader": "सत्यापित किसानों और FPO से सीधे पारदर्शी खेत मूल्य पर",
  "expectedGrowth": "अपेक्षित वृद्धि",
  "harvestInDays": "इष्टतम कटाई समय: 3-5 दिन",
  "surgeExpected": "त्यौहार और शहरी मांग के कारण मूल्य वृद्धि की संभावना",
  "qualityScore": "उत्पाद ताजगी",
  "orderStatus": "स्थिति",
  "completed": "पूर्ण",
  "inTransit": "रास्ते में",
  "pending": "लंबित",
  "farmGatePrice": "खेत की कीमत",
  "retailPrice": "बाज़ार खुदरा कीमत",
  "directPrice": "KisanFlow सीधी कीमत",
  "placeOrder": "ऑर्डर दें",
  "savingsMsg": "बिचौलियों को हटाकर 32% तक की बचत करें"
  },
  "kn": {
  "tagline": "ಮುನ್ಸೂಚನೆ • ಸಂಪರ್ಕ • ಒಟ್ಟುಗೂಡಿಕೆ • ವಿತರಣೆ",
  "sihBadge": "SIH 2026 — ಸಮಸ್ಯೆ ಹೇಳಿಕೆ 26033",
  "language": "ಭಾಷೆ",
  "selectLanguage": "ಭಾಷೆ ಆಯ್ಕೆಮಾಡಿ:",
  "authSubtitle": "ಕೃಷಿ ಮಾರುಕಟ್ಟೆ ಬುದ್ಧಿವಂತಿಕೆ",
  "authHeroDesc": "AI ಬೇಡಿಕೆ ಮುನ್ಸೂಚನೆ ಮತ್ತು ಸ್ಮಾರ್ಟ್ ಲಾಜಿಸ್ಟಿಕ್ಸ್ ಬಳಸಿ ರೈತರು ಮತ್ತು FPOಗಳನ್ನು ನೇರವಾಗಿ ಪರಿಶೀಲಿಸಿದ
  ಖರೀದಿದಾರರೊಂದಿಗೆ ಸಂಪರ್ಕಿಸಿ.",
  "roleFarmerTitle": "ರೈತ / FPO",
  "roleFarmerDesc": "ನಿಮ್ಮ ಬೆಳೆಯನ್ನು ಪರಿಶೀಲಿಸಿದ ಖರೀದಿದಾರರಿಗೆ ನೇರವಾಗಿ ಮಾರಿ. AI ಬೇಡಿಕೆ ಮುನ್ಸೂಚನೆ ಮತ್ತು ನ್ಯಾಯಯುತ ಬೆಲೆ
  ಪಡೆಯಿರಿ.",
  "registerFarmerBtn": "ರೈತ / FPO ಆಗಿ ನೋಂದಾಯಿಸಿ",
  "roleBuyerTitle": "ಗ್ರಾಹಕ / ಖರೀದಿದಾರ",
  "roleBuyerDesc": "ರೈತರು ಮತ್ತು FPOಗಳಿಂದ ನೇರವಾಗಿ ತಾಜಾ ಉತ್ಪನ್ನಗಳನ್ನು ಖರೀದಿಸಿ. ಪಾರದರ್ಶಕ ಮಾರುಕಟ್ಟೆ ಬೆಲೆ ಪಡೆಯಿರಿ.",
  "registerBuyerBtn": "ಗ್ರಾಹಕ / ಖರೀದಿದಾರರಾಗಿ ನೋಂದಾಯಿಸಿ",
  "demoFarmerLogin": "ಡೆಮೊ: ರೈತ ಲಾಗಿನ್ (ರಮೇಶ್ ಪಾಟೀಲ್)",
  "demoBuyerLogin": "ಡೆಮೊ: ಖರೀದಿದಾರ ಲಾಗಿನ್ (ಪ್ರಿಯಾ ಶರ್ಮಾ)",
  "alreadyHaveAccount": "ಈಗಾಗಲೇ ಖಾತೆ ಹೊಂದಿದ್ದೀರಾ?",
  "signInHere": "ಇಲ್ಲಿ ಸೈನ್ ಇನ್ ಮಾಡಿ",
  "dontHaveAccount": "ಖಾತೆ ಇಲ್ಲವೇ?",
  "registerHere": "ನೋಂದಾಯಿಸಿ",
  "backToRoleSelection": "← ಪಾತ್ರ ಆಯ್ಕೆಗೆ ಹಿಂತಿರುಗಿ",
  "farmerRegTitle": "🌾 ರೈತ / FPO ನೋಂದಣಿ",
  "farmerRegSubtitle": "ಮಧ್ಯವರ್ತಿಗಳಿಲ್ಲದೆ ನಿಮ್ಮ ಬೆಳೆಗಳನ್ನು ನೇರವಾಗಿ ಮಾರಾಟ ಮಾಡಲು KisanFlow ಸೇರಿ",
  "customerRegTitle": "🛒 ಗ್ರಾಹಕ / ಖರೀದಿದಾರ ನೋಂದಣಿ",
  "customerRegSubtitle": "ರೈತರಿಂದ ನೇರವಾಗಿ ತಾಜಾ ಉತ್ಪನ್ನಗಳನ್ನು ಖರೀದಿಸಲು KisanFlow ಸೇರಿ",
  "fullNameLabel": "ಪೂರ್ಣ ಹೆಸರು / FPO ಹೆಸರು *",
  "mobileLabel": "ಮೊಬೈಲ್ ಸಂಖ್ಯೆ *",
  "emailLabel": "ಇಮೇಲ್",
  "districtLabel": "ಜಿಲ್ಲೆ *",
  "stateLabel": "ರಾಜ್ಯ *",
  "entityTypeLabel": "ವಿಧ *",
  "preferredLangLabel": "ಆದ್ಯತೆಯ ಭಾಷೆ",
  "cropsLabel": "ಬೆಳೆಯುವ ಮುಖ್ಯ ಬೆಳೆಗಳು",
  "qtyLabel": "ಲಭ್ಯವಿರುವ ಪ್ರಮಾಣ / ಜಮೀನಿನ ಗಾತ್ರ (ಎಕರೆ)",
  "farmDetailsLabel": "ಜಮೀನು / FPO ವಿವರಗಳು",
  "bankUpiLabel": "ಬ್ಯಾಂಕ್ ಖಾತೆ / UPI ಐಡಿ (ನೇರ ಪಾವತಿಗೆ) *",
  "passwordLabel": "ಪಾಸ್‌ವರ್ಡ್ *",
  "confirmPasswordLabel": "ಪಾಸ್‌ವರ್ಡ್ ದೃಢೀಕರಿಸಿ *",
  "verifyTermsFarmer": "ನಾನು ನಿಜವಾದ ರೈತ/FPO ಆಗಿದ್ದೇನೆ ಮತ್ತು ನಿಯಮಗಳಿಗೆ ಸಮ್ಮತಿಸುತ್ತೇನೆ",
  "verifyTermsBuyer": "ನಾನು ನ್ಯಾಯಯುತ ವಹಿವಾಟು ಮತ್ತು KisanFlow ನಿಯಮಗಳನ್ನು ಒಪ್ಪುತ್ತೇನೆ",
  "createFarmerAccountBtn": "ರೈತ ಖಾತೆ ತೆರೆಯಿರಿ",
  "createBuyerAccountBtn": "ಖರೀದಿದಾರರ ಖಾತೆ ತೆರೆಯಿರಿ",
  "businessNameLabel": "ಪೂರ್ಣ ಹೆಸರು / ವ್ಯಾಪಾರದ ಹೆಸರು *",
  "buyerTypeLabel": "ಖರೀದಿದಾರರ ವಿಧ *",
  "deliveryLocationLabel": "ವಿತರಣಾ ವಿಳಾಸ / ಸ್ಥಳ *",
  "pinCodeLabel": "ಪಿನ್ ಕೋಡ್ *",
  "contactLabel": "ಸಂಪರ್ಕ ಫೋನ್ ಸಂಖ್ಯೆ *",
  "gstLabel": "GST ಸಂಖ್ಯೆ / ವ್ಯಾಪಾರ ಐಡಿ (ವ್ಯಕ್ತಿಗಳಿಗೆ ಐಚ್ಛಿಕ)",
  "preferredProductsLabel": "ಆಸಕ್ತಿಯ ಉತ್ಪನ್ನಗಳು",
  "loginTitle": "ಮತ್ತೆ ಸುಸ್ವಾಗತ",
  "loginSubtitle": "ನಿಮ್ಮ KisanFlow ಖಾತೆಗೆ ಸೈನ್ ಇನ್ ಮಾಡಿ",
  "mobileOrEmailLabel": "ಮೊಬೈಲ್ ಸಂಖ್ಯೆ ಅಥವಾ ಇಮೇಲ್ *",
  "signInBtn": "ಸೈನ್ ಇನ್ ಮಾಡಿ",
  "dashboard": "ಡ್ಯಾಶ್‌ಬೋರ್ಡ್",
  "marketplace": "ಮಾರುಕಟ್ಟೆ",
  "ai": "AI ಬುದ್ಧಿವಂತಿಕೆ",
  "logistics": "ಲಾಜಿಸ್ಟಿಕ್ಸ್",
  "farmerTools": "ರೈತ ಸಾಧನಗಳು",
  "heroTitle": "ಬೇಡಿಕೆಯಿಂದ ವಿತರಣೆಯವರೆಗೆ ಕೃಷಿ ಮಾರುಕಟ್ಟೆ",
  "heroText": "ರೈತರು ಮತ್ತು FPOಗಳನ್ನು ಗ್ರಾಹಕರು, ರೆಸ್ಟೋರೆಂಟ್‌ಗಳು ಮತ್ತು ದೊಡ್ಡ ಖರೀದಿದಾರರೊಂದಿಗೆ ನೇರವಾಗಿ ಸಂಪರ್ಕಿಸಿ, AI ಮೂಲಕ
  ಸರಬರಾಜು ಸರಪಳಿಯ ಅಸಮರ್ಥತೆಯನ್ನು ಕಡಿಮೆ ಮಾಡಿ.",
  "suppliers": "ಪೂರೈಕೆದಾರರು",
  "buyerDemands": "ಖರೀದಿದಾರರ ಬೇಡಿಕೆಗಳು",
  "tomatoDemand": "ಅಂದಾಜು ಟೊಮೆಟೊ ಬೇಡಿಕೆ",
  "nextPeriod": "ಮುಂದಿನ ಅವಧಿ",
  "demandTrend": "ಬೇಡಿಕೆ ಪ್ರವೃತ್ತಿ",
  "aiSignal": "AI ಸಂಕೇತ",
  "suggestedPrice": "ಸೂಚಿಸಿದ ಟೊಮೆಟೊ ಬೆಲೆ",
  "perKg": "ಪ್ರತಿ ಕೆಜಿ",
  "supplyGap": "ಪೂರೈಕೆ ಅಂತರ",
  "currentPrediction": "ಪ್ರಸ್ತುತ ಅಂದಾಜು",
  "howWorks": "🔄 KisanFlow ಹೇಗೆ ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತದೆ",
  "buyerDemand": "ಖರೀದಿದಾರರ ಬೇಡಿಕೆ",
  "aiForecast": "AI ಮುನ್ಸೂಚನೆ",
  "smartMatching": "ಸ್ಮಾರ್ಟ್ ಹೊಂದಾಣಿಕೆ",
  "aggregation": "ಒಟ್ಟುಗೂಡಿಕೆ",
  "coreUsp": "🎯 ಮುಖ್ಯ ವಿಶೇಷತೆ",
  "uspText": "ರೈತರು ಖರೀದಿದಾರರನ್ನು ಹುಡುಕುವವರೆಗೆ ಕಾಯುವ ಬದಲು, KisanFlow ಅಂದಾಜು ಮಾರುಕಟ್ಟೆ ಬೇಡಿಕೆಯಿಂದ ಪ್ರಾರಂಭಿಸಿ ಸೂಕ್ತ ಕೃಷಿ
  ಪೂರೈಕೆಯನ್ನು ಪತ್ತೆಹಚ್ಚಿ, ಒಟ್ಟುಗೂಡಿಸಿ ಮತ್ತು ವಿತರಿಸುತ್ತದೆ.",
  "marketText": "ನೇರ ರೈತ/FPO ಪಟ್ಟಿಗಳು ಮತ್ತು ಖರೀದಿದಾರರ ಅಗತ್ಯಗಳು.",
  "availableSupply": "🌱 ಲಭ್ಯವಿರುವ ಪೂರೈಕೆ",
  "buyerBoard": "🛒 ಖರೀದಿದಾರರ ಬೇಡಿಕೆ ಫಲಕ",
  "addSupply": "ರೈತ / FPO ಪೂರೈಕೆ ಸೇರಿಸಿ",
  "farmerName": "ರೈತ / FPO ಹೆಸರು",
  "productExample": "ಉತ್ಪನ್ನ ಉದಾ. ಟೊಮೆಟೊ",
  "product": "ಉತ್ಪನ್ನ",
  "quantity": "ಪ್ರಮಾಣ (ಕೆಜಿ)",
  "priceKg": "ಪ್ರತಿ ಕೆಜಿ ಬೆಲೆ",
  "location": "ಸ್ಥಳ",
  "addSupplyBtn": "ಪೂರೈಕೆ ಸೇರಿಸಿ",
  "postDemand": "ಖರೀದಿದಾರರ ಅಗತ್ಯ ಪೋಸ್ಟ್ ಮಾಡಿ",
  "buyerName": "ಖರೀದಿದಾರರ ಹೆಸರು",
  "deliveryLocation": "ವಿತರಣಾ ಸ್ಥಳ",
  "deadline": "ಗಡುವು (ದಿನಗಳು)",
  "postDemandBtn": "ಬೇಡಿಕೆ ಪೋಸ್ಟ್ ಮಾಡಿ",
  "forecastTitle": "🔮 AI ಬೇಡಿಕೆ ಮುನ್ಸೂಚನೆ",
  "forecastText": "ಐತಿಹಾಸಿಕ ವ್ಯವಹಾರಗಳು, ಋತುಮಾನ ಮಾದರಿಗಳು ಮತ್ತು ಮಾರುಕಟ್ಟೆ ಸಂಕೇತಗಳಿಂದ ಭವಿಷ್ಯದ ಬೇಡಿಕೆಯನ್ನು ಊಹಿಸಿ.",
  "forecastBtn": "ಬೇಡಿಕೆ ಊಹಿಸಿ",
  "priceTitle": "💰 ವಿವರಿಸಬಹುದಾದ ಬೆಲೆ ಸಲಹೆಗಾರ",
  "priceText": "ಅಂದಾಜು ಬೇಡಿಕೆ ಮತ್ತು ಮಾರುಕಟ್ಟೆ ಪರಿಸ್ಥಿತಿಗಳ ಆಧಾರದ ಮೇಲೆ AI ಸಹಾಯದ ಬೆಲೆ ಶ್ರೇಣಿ ಪಡೆಯಿರಿ.",
  "calculatePrice": "ಬೆಲೆ ಲೆಕ್ಕಿಸಿ",
  "reverseTitle": "🧩 ರಿವರ್ಸ್ ಮಾರುಕಟ್ಟೆ + ಸ್ಮಾರ್ಟ್ ಪೂರೈಕೆ ಒಟ್ಟುಗೂಡಿಕೆ",
  "reverseText": "ಖರೀದಿದಾರರ ಅಗತ್ಯವನ್ನು ನಮೂದಿಸಿ. KisanFlow ಸೂಕ್ತ ರೈತರು/FPOಗಳನ್ನು ಕಂಡುಹಿಡಿದು ಅವರ ಪೂರೈಕೆಯನ್ನು
  ಒಟ್ಟುಗೂಡಿಸುತ್ತದೆ.",
  "requiredKg": "ಅಗತ್ಯ ಕೆಜಿ",
  "buyerLocation": "ಖರೀದಿದಾರರ ಸ್ಥಳ",
  "findAggregate": "ಹುಡುಕಿ ಒಟ್ಟುಗೂಡಿಸಿ",
  "gapTitle": "📊 ಪೂರೈಕೆ-ಬೇಡಿಕೆ ಅಂತರ",
  "gapText": "ಅಂದಾಜು ಬೇಡಿಕೆ ಮತ್ತು ಲಭ್ಯವಿರುವ ಪೂರೈಕೆಯನ್ನು ಹೋಲಿಸಿ ಕೊರತೆ ಅಥವಾ ಹೆಚ್ಚುವರಿಯನ್ನು ಪತ್ತೆಹಚ್ಚುತ್ತದೆ.",
  "wasteTitle": "🥬 ತಾಜಾತನ / ವ್ಯರ್ಥ ಅಪಾಯ",
  "distance": "ದೂರ ಕಿಮೀ",
  "hours": "ಪ್ರಯಾಣ ಗಂಟೆಗಳು",
  "assessRisk": "ಅಪಾಯ ಅಂದಾಜಿಸಿ",
  "routeTitle": "🚚 ಬಹು-ಆರ್ಡರ್ ಮಾರ್ಗ ಆಪ್ಟಿಮೈಸರ್",
  "routeText": "ಪಿಕಪ್ ಸ್ಥಳಗಳನ್ನು ಆಯ್ಕೆಮಾಡಿ. ವ್ಯವಸ್ಥೆ ಉತ್ತಮ ಸಂಗ್ರಹ ಮಾರ್ಗವನ್ನು ರಚಿಸುತ್ತದೆ.",
  "destination": "ಗಮ್ಯಸ್ಥಾನ",
  "optimizeRoute": "ಮಾರ್ಗ ಆಪ್ಟಿಮೈಸ್ ಮಾಡಿ",
  "whyRoute": "💡 ಈ ಮಾರ್ಗ ಏಕೆ?",
  "routeReason": "ಲಾಜಿಸ್ಟಿಕ್ಸ್ ಎಂಜಿನ್ ದೂರ, ವಿತರಣಾ ಸಮಯ, ವಾಹನ ಸಾಮರ್ಥ್ಯ, ಅಂದಾಜು ವೆಚ್ಚ ಮತ್ತು ತಾಜಾತನದ ಅಪಾಯವನ್ನು
  ಪರಿಗಣಿಸುತ್ತದೆ.",
  "profitTitle": "🧮 ರೈತ ಲಾಭ ಸಿಮ್ಯುಲೇಟರ್",
  "profitText": "ಆರ್ಡರ್ ಸ್ವೀಕರಿಸುವ ಮೊದಲು ಅಂದಾಜು ಆದಾಯವನ್ನು ಲೆಕ್ಕಿಸಿ.",
  "sellingPrice": "ಮಾರಾಟ ಬೆಲೆ/ಕೆಜಿ",
  "transportCost": "ಸಾರಿಗೆ ವೆಚ್ಚ",
  "platformFee": "ಪ್ಲಾಟ್‌ಫಾರ್ಮ್ ಶುಲ್ಕ",
  "otherCost": "ಇತರೆ ವೆಚ್ಚ",
  "netReturn": "ನಿವ್ವಳ ಆದಾಯ ಲೆಕ್ಕಿಸಿ",
  "trustTitle": "⭐ ರೈತ ನಂಬಿಕೆ ಸ್ಕೋರ್",
  "trustText": "ಪೂರೈಕೆ ಪೂರ್ಣಗೊಳಿಸುವಿಕೆ, ಗುಣಮಟ್ಟ, ವಿತರಣಾ ಕಾರ್ಯಕ್ಷಮತೆ ಮತ್ತು ವ್ಯವಹಾರ ಇತಿಹಾಸದಿಂದ ಸ್ಕೋರ್ ಲೆಕ್ಕಿಸಬಹುದು.",
  "voiceTitle": "🎤 ಧ್ವನಿ + ಪ್ರಾದೇಶಿಕ ಭಾಷಾ ಸಹಾಯಕ",
  "voiceText": "ರೈತ ಟೈಪ್ ಮಾಡುವ ಬದಲು ಮಾತನಾಡಬಹುದು. ಉದಾಹರಣೆ: <b>\"ನನ್ನ ಬಳಿ 500 ಕೆಜಿ ಟೊಮೆಟೊ ಇದೆ.\"</b>",
  "voiceDemo": "ಧ್ವನಿ ಡೆಮೊ ಪ್ರಯತ್ನಿಸಿ",
  "fraudTitle": "🛡️ ಅನುಮಾನಾಸ್ಪದ ಆರ್ಡರ್ ಪತ್ತೆ",
  "fraudText": "ಅಸಾಮಾನ್ಯ ಆರ್ಡರ್ ಪ್ರಮಾಣ ಅಥವಾ ಬೆಲೆಗಳನ್ನು ಗುರುತಿಸಿ ಪರಿಶೀಲನೆಗೆ ಕಳುಹಿಸಬಹುದು.",
  "fraudDemo": "⚠ ಡೆಮೊ: ವಾರಕ್ಕೆ 200 ಕೆಜಿ ಸರಾಸರಿ ಇರುವ ಖರೀದಿದಾರರ 10,000 ಕೆಜಿ ಆರ್ಡರ್ ಪರಿಶೀಲನೆಗೆ ಗುರುತಿಸಬಹುದು.",
  "footer2": "ಬೇಡಿಕೆ • ಪೂರೈಕೆ • ಬೆಲೆ • ಲಾಜಿಸ್ಟಿಕ್ಸ್ • AI",
  "supplyAdded": "ಪೂರೈಕೆ ಯಶಸ್ವಿಯಾಗಿ ಸೇರಿಸಲಾಗಿದೆ.",
  "demandAdded": "ಖರೀದಿದಾರರ ಬೇಡಿಕೆ ಯಶಸ್ವಿಯಾಗಿ ಪೋಸ್ಟ್ ಆಗಿದೆ.",
  "forecastMsg": "ಗಾಗಿ ಮುನ್ಸೂಚನೆ",
  "demand": "ನಿರೀಕ್ಷಿತ ಬೇಡಿಕೆ",
  "priceRange": "ಶಿಫಾರಸು ಶ್ರೇಣಿ",
  "gapMsg": "ಪ್ರಸ್ತುತ ಅಂತರ",
  "aggregateMsg": "ಒಟ್ಟುಗೂಡಿಸಿದ ಪೂರೈಕೆ",
  "shortage": "ಕೊರತೆ",
  "surplus": "ಹೆಚ್ಚುವರಿ",
  "risk": "ಅಪಾಯ",
  "routeDone": "ಆಪ್ಟಿಮೈಸ್ ಮಾಡಿದ ಮಾರ್ಗ",
  "estimatedDistance": "ಅಂದಾಜು ದೂರ",
  "estimatedCost": "ಅಂದಾಜು ಲಾಜಿಸ್ಟಿಕ್ಸ್ ವೆಚ್ಚ",
  "net": "ಅಂದಾಜು ನಿವ್ವಳ ಆದಾಯ",
  "voiceReady": "ಧ್ವನಿ ಡೆಮೊ ಸಿದ್ಧ: 500 ಕೆಜಿ ಟೊಮೆಟೊ ಪೂರೈಕೆ ಪತ್ತೆಯಾಗಿದೆ.",
  "noSupply": "ಸೂಕ್ತ ಪೂರೈಕೆ ಕಂಡುಬಂದಿಲ್ಲ.",
  "invalid": "ದಯವಿಟ್ಟು ಸರಿಯಾದ ಮೌಲ್ಯಗಳನ್ನು ನಮೂದಿಸಿ.",
  "bullish": "ಏರಿಕೆ",
  "softening": "ಮಂದ",
  "low": "ಕಡಿಮೆ",
  "medium": "ಮಧ್ಯಮ",
  "high": "ಹೆಚ್ಚು",
  "navSectionMain": "ಮುಖ್ಯ",
  "navSectionIntelligence": "ಬುದ್ಧಿವಂತಿಕೆ",
  "navSectionOperations": "ಕಾರ್ಯಾಚರಣೆ",
  "navSectionAccount": "ಖಾತೆ",
  "navDashboard": "ಡ್ಯಾಶ್‌ಬೋರ್ಡ್",
  "navMyProduce": "ನನ್ನ ಬೆಳೆಗಳು",
  "navBuyerRequests": "ಖರೀದಿದಾರರ ವಿನಂತಿಗಳು",
  "navBrowseProduce": "ಉತ್ಪನ್ನಗಳನ್ನು ಬ್ರೌಸ್ ಮಾಡಿ",
  "navPostDemand": "ಬೇಡಿಕೆ ಪೋಸ್ಟ್ ಮಾಡಿ",
  "navFindFarmers": "ರೈತರು / FPO ಹುಡುಕಿ",
  "navForecast": "AI ಬೇಡಿಕೆ ಮುನ್ಸೂಚನೆ",
  "navPriceAdvisor": "ಬೆಲೆ ಸಲಹೆಗಾರ",
  "navProfitSim": "ಲಾಭ ಸಿಮ್ಯುಲೇಟರ್",
  "navOrders": "ಆರ್ಡರ್‌ಗಳು",
  "navLogistics": "ಲಾಜಿಸ್ಟಿಕ್ಸ್",
  "navDeliveryTracking": "ವಿತರಣಾ ಟ್ರ್ಯಾಕಿಂಗ್",
  "navReviews": "ವಿಮರ್ಶೆಗಳು ಮತ್ತು ರೇಟಿಂಗ್",
  "navFavorites": "ಮೆಚ್ಚಿನವುಗಳು",
  "navProfile": "ಪ್ರೊಫೈಲ್",
  "logout": "ಲಾಗ್ ಔಟ್",
  "roleFarmer": "ರೈತ 🌾",
  "roleBuyer": "ಗ್ರಾಹಕ 🛒",
  "activeSupplyListings": "ಸಕ್ರಿಯ ಬೆಳೆ ಪಟ್ಟಿಗಳು",
  "liveBuyerDemands": "ಲೈವ್ ಖರೀದಿದಾರ ಬೇಡಿಕೆಗಳು",
  "predictedDemand": "ಅಂದಾಜು ಬೇಡಿಕೆ",
  "highDemandNearYou": "📍 ನಿಮ್ಮ ಸಮೀಪದ ಹೆಚ್ಚಿನ ಬೇಡಿಕೆ",
  "opportunities": "🎯 ಮಾರುಕಟ್ಟೆ ಅವಕಾಶಗಳು",
  "recommendedBuyers": "🤝 ಶಿಫಾರಸು ಮಾಡಿದ ಖರೀದಿದಾರರು",
  "activeOrders": "📦 ಸಕ್ರಿಯ ಆರ್ಡರ್‌ಗಳು",
  "recentReviews": "⭐ ಇತ್ತೀಚಿನ ವಿಮರ್ಶೆಗಳು",
  "smartLogisticsStatus": "🚚 ಸ್ಮಾರ್ಟ್ ಲಾಜಿಸ್ಟಿಕ್ಸ್ ಸ್ಥಿತಿ",
  "forecastHeader": "🔮 AI ಭವಿಷ್ಯದ ಬೇಡಿಕೆ ಮುನ್ಸೂಚನೆ",
  "forecastSubheader": "ಭವಿಷ್ಯದ ಕೃಷಿ ಬೇಡಿಕೆಯನ್ನು ಊಹಿಸಿ, ಜಿಲ್ಲಾ ಪ್ರವೃತ್ತಿಗಳನ್ನು ವಿಶ್ಲೇಷಿಸಿ ಮತ್ತು ಗರಿಷ್ಠ ಲಾಭಕ್ಕೆ ಕೊಯ್ಲು
  ಮಾಡಿ",
  "cropLabel": "ಬೆಳೆ",
  "periodLabel": "ಅವಧಿ",
  "heatmapTitle": "🗺️ ಕರ್ನಾಟಕ ಕೃಷಿ ಬೇಡಿಕೆ ಹೀಟ್‌ಮ್ಯಾಪ್",
  "heatmapDesc": "ಕರ್ನಾಟಕದ ಜಿಲ್ಲೆಗಳಲ್ಲಿ ನೈಜ-ಸಮಯದ ಬೇಡಿಕೆ ತೀವ್ರತೆ, ಬೆಲೆ ಪ್ರವೃತ್ತಿ ಮತ್ತು ಪೂರೈಕೆ ಕೊರತೆಯ ದೃಶ್ಯಾವಳಿ",
  "trendChartTitle": "📈 ಬೇಡಿಕೆ ಪ್ರವೃತ್ತಿ ವಿಶ್ಲೇಷಣೆ (7-ದಿನ ಮತ್ತು 30-ದಿನ ವಕ್ರರೇಖೆ)",
  "highDemandAlertsTitle": "⚡ ಹೆಚ್ಚಿನ ಬೇಡಿಕೆ ಎಚ್ಚರಿಕೆಗಳು ಮತ್ತು ಕೊಯ್ಲು ಸಮಯ",
  "reviewsHeader": "⭐ ವಿಮರ್ಶೆಗಳು ಮತ್ತು ರೇಟಿಂಗ್‌ಗಳು",
  "reviewsSubheader": "ಪರಿಶೀಲಿಸಿದ ರೈತರು ಮತ್ತು ನಂಬಿಕಸ್ಥ ಖರೀದಿದಾರರ ನಡುವೆ ಪಾರದರ್ಶಕ ಪ್ರತಿಕ್ರಿಯೆ ವ್ಯವಸ್ಥೆ",
  "yourRatingTitle": "ನಿಮ್ಮ ರೇಟಿಂಗ್",
  "writeReviewTitle": "ವಿಮರ್ಶೆ ಬರೆಯಿರಿ",
  "rateCompletedTx": "ಪೂರ್ಣಗೊಂಡ ವಹಿವಾಟನ್ನು ಮೌಲ್ಯಮಾಪನ ಮಾಡಿ",
  "selectCompletedOrder": "ಪೂರ್ಣಗೊಂಡ ಆರ್ಡರ್ ಆಯ್ಕೆಮಾಡಿ",
  "overallRating": "ಒಟ್ಟಾರೆ ರೇಟಿಂಗ್ *",
  "qualityRating": "ಗುಣಮಟ್ಟ ರೇಟಿಂಗ್",
  "deliveryRating": "ವಿತರಣೆ / ಲಾಜಿಸ್ಟಿಕ್ಸ್ ರೇಟಿಂಗ್",
  "yourReview": "ನಿಮ್ಮ ವಿಮರ್ಶೆ",
  "submitReviewBtn": "ವಿಮರ್ಶೆ ಸಲ್ಲಿಸಿ",
  "allReviewsTitle": "ಎಲ್ಲಾ ವಿಮರ್ಶೆಗಳು",
  "browseHeader": "🛒 ತಾಜಾ ಉತ್ಪನ್ನಗಳನ್ನು ಬ್ರೌಸ್ ಮಾಡಿ",
  "browseSubheader": "ಪರಿಶೀಲಿಸಿದ ರೈತರಿಂದ ನೇರವಾಗಿ ಪಾರದರ್ಶಕ ಜಮೀನಿನ ಬೆಲೆಯಲ್ಲಿ",
  "expectedGrowth": "ನಿರೀಕ್ಷಿತ ಬೆಳವಣಿಗೆ",
  "harvestInDays": "ಸೂಕ್ತ ಕೊಯ್ಲು ಸಮಯ: 3-5 ದಿನಗಳು",
  "surgeExpected": "ಹಬ್ಬ ಮತ್ತು ನಗರ ಬೇಡಿಕೆಯಿಂದಾಗಿ ಬೆಲೆ ಏರಿಕೆಯ ನಿರೀಕ್ಷೆ",
  "qualityScore": "ಉತ್ಪನ್ನದ ತಾಜಾತನ",
  "orderStatus": "ಸ್ಥಿತಿ",
  "completed": "ಪೂರ್ಣಗೊಂಡಿದೆ",
  "inTransit": "ಮಾರ್ಗದಲ್ಲಿದೆ",
  "pending": "ಬಾಕಿ ಇದೆ",
  "farmGatePrice": "ಜಮೀನಿನ ನೇರ ಬೆಲೆ",
  "retailPrice": "ಮಾರುಕಟ್ಟೆ ಚಿಲ್ಲರೆ ಬೆಲೆ",
  "directPrice": "KisanFlow ನೇರ ಬೆಲೆ",
  "placeOrder": "ಆರ್ಡರ್ ಮಾಡಿ",
  "savingsMsg": "ಮಧ್ಯವರ್ತಿಗಳನ್ನು ತಪ್ಪಿಸಿ 32% ವರೆಗೆ ಉಳಿಸಿ"
  },
  "ta": {
  "tagline": "முன்கணிப்பு • இணைப்பு • ஒருங்கிணைப்பு • விநியோகம்",
  "sihBadge": "SIH 2026 — பிரச்சனை அறிக்கை 26033",
  "language": "மொழி",
  "selectLanguage": "மொழியைத் தேர்ந்தெடுக்கவும்:",
  "authSubtitle": "வேளாண் சந்தை நுண்ணறிவு",
  "authHeroDesc": "AI தேவை முன்கணிப்பு மற்றும் ஸ்மார்ட் தளவாடங்களைப் பயன்படுத்தி விவசாயிகளையும் FPOகளையும் நேரடியாக
  சரிபார்க்கப்பட்ட வாங்குபவர்களுடன் இணைக்கவும்.",
  "roleFarmerTitle": "விவசாயி / FPO",
  "roleFarmerDesc": "உங்கள் விளைபொருட்களை சரிபார்க்கப்பட்ட வாங்குபவர்களுக்கு நேரடியாக விற்கவும். AI தேவை முன்கணிப்பு
  மற்றும் நியாயமான விலையைப் பெறுங்கள்.",
  "registerFarmerBtn": "விவசாயி / FPO ஆகப் பதிவு செய்யுங்கள்",
  "roleBuyerTitle": "வாடிக்கையாளர் / வாங்குபவர்",
  "roleBuyerDesc": "விவசாயிகளிடமிருந்து நேரடியாக புதிய விளைபொருட்களை நியாயமான சந்தை விலையில் வாங்குங்கள்.",
  "registerBuyerBtn": "வாடிக்கையாளர் / வாங்குபவராக பதிவு செய்யுங்கள்",
  "demoFarmerLogin": "டெமோ: விவசாயி உள்நுழைவு (ரமேஷ் பாட்டீல்)",
  "demoBuyerLogin": "டெமோ: வாங்குபவர் உள்நுழைவு (பிரியா சர்மா)",
  "alreadyHaveAccount": "ஏற்கனவே கணக்கு உள்ளதா?",
  "signInHere": "இங்கே உள்நுழையவும்",
  "dontHaveAccount": "கணக்கு இல்லையா?",
  "registerHere": "பதிவு செய்யவும்",
  "backToRoleSelection": "← பங்குத் தேர்வுக்குத் திரும்பு",
  "farmerRegTitle": "🌾 விவசாயி / FPO பதிவு",
  "farmerRegSubtitle": "இடைத்தரகர்கள் இல்லாமல் உங்கள் விளைபொருட்களை நேரடியாக விற்க KisanFlow இல் இணையுங்கள்",
  "customerRegTitle": "🛒 வாடிக்கையாளர் / வாங்குபவர் பதிவு",
  "customerRegSubtitle": "விவசாயிகளிடமிருந்து நேரடியாக புதிய விளைபொருட்களை வாங்க KisanFlow இல் இணையுங்கள்",
  "fullNameLabel": "முழு பெயர் / FPO பெயர் *",
  "mobileLabel": "கைபேசி எண் *",
  "emailLabel": "மின்னஞ்சல்",
  "districtLabel": "மாவட்டம் *",
  "stateLabel": "மாநிலம் *",
  "entityTypeLabel": "வகை *",
  "preferredLangLabel": "விருப்பமான மொழி",
  "cropsLabel": "பயிரிடப்படும் முதன்மைப் பயிர்கள்",
  "qtyLabel": "கிடைக்கும் அளவு / பண்ணை அளவு (ஏக்கர்)",
  "farmDetailsLabel": "பண்ணை / FPO விவரங்கள்",
  "bankUpiLabel": "வங்கி கணக்கு / UPI ஐடி (நேரடி கட்டணத்திற்கு) *",
  "passwordLabel": "கடவுச்சொல் *",
  "confirmPasswordLabel": "கடவுச்சொல்லை உறுதிப்படுத்தவும் *",
  "verifyTermsFarmer": "நான் ஒரு உண்மையான விவசாயி/FPO என்பதை உறுதிசெய்து விதிமுறைகளை ஏற்கிறேன்",
  "verifyTermsBuyer": "நான் நியாயமான வர்த்தக நடைமுறைகள் மற்றும் விதிமுறைகளை ஏற்கிறேன்",
  "createFarmerAccountBtn": "விவசாயி கணக்கை உருவாக்கவும்",
  "createBuyerAccountBtn": "வாங்குபவர் கணக்கை உருவாக்கவும்",
  "businessNameLabel": "முழு பெயர் / வணிகப் பெயர் *",
  "buyerTypeLabel": "வாங்குபவர் வகை *",
  "deliveryLocationLabel": "டெலிவரி முகவரி / இருப்பிடம் *",
  "pinCodeLabel": "பின் குறியீடு *",
  "contactLabel": "தொடர்பு தொலைபேசி எண் *",
  "gstLabel": "GST எண் / வணிக ஐடி (தனிநபர்களுக்கு விருப்பத்தேர்வு)",
  "preferredProductsLabel": "விருப்பமான விளைபொருட்கள்",
  "loginTitle": "மீண்டும் வருக",
  "loginSubtitle": "உங்கள் KisanFlow கணக்கில் உள்நுழையவும்",
  "mobileOrEmailLabel": "கைபேசி எண் அல்லது மின்னஞ்சல் *",
  "signInBtn": "உள்நுழைக",
  "dashboard": "டாஷ்போர்டு",
  "marketplace": "சந்தை",
  "ai": "AI நுண்ணறிவு",
  "logistics": "தளவாடம்",
  "farmerTools": "விவசாயி கருவிகள்",
  "heroTitle": "தேவையிலிருந்து விநியோகம் வரை வேளாண் சந்தை",
  "heroText": "விவசாயிகள் மற்றும் FPOகளை நுகர்வோர், உணவகங்கள் மற்றும் மொத்த வாங்குபவர்களுடன் நேரடியாக இணைத்து, AI மூலம்
  விநியோகச் சங்கிலி செயல்திறனை மேம்படுத்துங்கள்.",
  "suppliers": "வழங்குநர்கள்",
  "buyerDemands": "வாங்குபவர் தேவைகள்",
  "tomatoDemand": "அனுமானிக்கப்பட்ட தக்காளி தேவை",
  "nextPeriod": "அடுத்த காலம்",
  "demandTrend": "தேவை போக்கு",
  "aiSignal": "AI சிக்னல்",
  "suggestedPrice": "பரிந்துரைக்கப்பட்ட தக்காளி விலை",
  "perKg": "ஒரு கிலோவிற்கு",
  "supplyGap": "வழங்கல் இடைவெளி",
  "currentPrediction": "தற்போதைய கணிப்பு",
  "howWorks": "🔄 KisanFlow எவ்வாறு செயல்படுகிறது",
  "buyerDemand": "வாங்குபவர் தேவை",
  "aiForecast": "AI முன்கணிப்பு",
  "smartMatching": "ஸ்மார்ட் பொருத்தம்",
  "aggregation": "ஒருங்கிணைப்பு",
  "coreUsp": "🎯 முக்கிய சிறப்பு",
  "uspText": "விவசாயிகள் வாங்குபவர்களைத் தேடும் முறைக்கு பதிலாக, கிசான்ஃப்ளோ கணிக்கப்பட்ட சந்தைத் தேவையிலிருந்து தொடங்கி
  பொருத்தமான வேளாண் விநியோகத்தை கண்டறிந்து, ஒருங்கிணைத்து, வழங்குகிறது.",
  "marketText": "நேரடி விவசாயி/FPO பட்டியல்கள் மற்றும் வாங்குபவர் தேவைகள்.",
  "availableSupply": "🌱 கிடைக்கும் இருப்பு",
  "buyerBoard": "🛒 வாங்குபவர் தேவை பலகை",
  "addSupply": "விவசாயி / FPO விநியோகம் சேர்க்கவும்",
  "farmerName": "விவசாயி / FPO பெயர்",
  "productExample": "பொருள் எ.கா. தக்காளி",
  "product": "பொருள்",
  "quantity": "அளவு (கிலோ)",
  "priceKg": "விலை/கிலோ",
  "location": "இருப்பிடம்",
  "addSupplyBtn": "விநியோகத்தைச் சேர்க்கவும்",
  "postDemand": "வாங்குபவர் தேவையைப் பதிவு செய்யவும்",
  "buyerName": "வாங்குபவர் பெயர்",
  "deliveryLocation": "விநியோக இடம்",
  "deadline": "காலக்கெடு (நாட்கள்)",
  "postDemandBtn": "தேவையைப் பதிவு செய்க",
  "forecastTitle": "🔮 AI தேவை முன்கணிப்பு",
  "forecastText": "வரலாற்று பரிவர்த்தனைகள் மற்றும் சந்தை சிக்னல்கள் மூலம் எதிர்கால தேவையை கணிக்கவும்.",
  "forecastBtn": "தேவையை கணிக்கவும்",
  "priceTitle": "💰 விளக்கக்கூடிய விலை ஆலோசகர்",
  "priceText": "கணிக்கப்பட்ட தேவை அடிப்படையில் AI-உதவி விலை வரம்பைப் பெறுங்கள்.",
  "calculatePrice": "விலையை கணக்கிடுங்கள்",
  "reverseTitle": "🧩 தலைகீழ் சந்தை + விநியோக ஒருங்கிணைப்பு",
  "reverseText": "வாங்குபவர் தேவையை உள்ளிடவும். KisanFlow விவசாயிகளை கண்டறிந்து விநியோகத்தை ஒருங்கிணைக்கிறது.",
  "requiredKg": "தேவையான கிலோ",
  "buyerLocation": "வாங்குபவர் இடம்",
  "findAggregate": "கண்டறிந்து ஒருங்கிணைக்கவும்",
  "gapTitle": "📊 வழங்கல்-தேவை இடைவெளி",
  "gapText": "கணிக்கப்பட்ட தேவையையும் கிடைக்கும் இருப்பையும் ஒப்பிட்டு பற்றாக்குறையைக் கண்டறியவும்.",
  "wasteTitle": "🥬 புத்துணர்ச்சி / விரயம் ஆபத்து",
  "distance": "தூரம் கி.மீ",
  "hours": "பயண நேரம்",
  "assessRisk": "ஆபத்தை மதிப்பிடுங்கள்",
  "routeTitle": "🚚 பல ஆர்டர் பாதை உகப்பாக்கி",
  "routeText": "பிக்கப் இடங்களைத் தேர்வு செய்யவும். உகந்த பாதை உருவாக்கப்படும்.",
  "destination": "இலக்கு",
  "optimizeRoute": "பாதையை உகப்பாக்குங்கள்",
  "whyRoute": "💡 இந்த பாதை ஏன்?",
  "routeReason": "தளவாட எஞ்சின் தூரம், நேரம் மற்றும் புத்துணர்ச்சி ஆபத்தை கருதுகிறது.",
  "profitTitle": "🧮 விவசாயி லாப சிமுலேட்டர்",
  "profitText": "ஆர்டரை ஏற்கும் முன் மதிப்பிடப்பட்ட வருவாயைக் கணக்கிடுங்கள்.",
  "sellingPrice": "விற்பனை விலை/கிலோ",
  "transportCost": "போக்குவரத்து செலவு",
  "platformFee": "தளக் கட்டணம்",
  "otherCost": "இதர செலவு",
  "netReturn": "நிகர வருவாயைக் கணக்கிடுங்கள்",
  "trustTitle": "⭐ விவசாயி நம்பிக்கை மதிப்பெண்",
  "trustText": "மதிப்பெண் தரம் மற்றும் விநியோக செயல்திறன் மூலம் கணக்கிடப்படுகிறது.",
  "voiceTitle": "🎤 குரல் + பிராந்திய மொழி உதவியாளர்",
  "voiceText": "விவசாயி தட்டச்சு செய்வதற்கு பதிலாக பேசலாம். எ.கா: <b>\"என்னிடம் 500 கிலோ தக்காளி உள்ளது.\"</b>",
  "voiceDemo": "குரல் டெமோ முயற்சிக்கவும்",
  "fraudTitle": "🛡️ சந்தேகத்திற்கிடமான ஆர்டர் கண்டறிதல்",
  "fraudText": "அசாதாரண ஆர்டர் அளவு சரிபார்ப்புக்கு அனுப்பப்படும்.",
  "fraudDemo": "⚠ டெமோ: வாரத்திற்கு 200 கிலோ வாங்கும் வாங்குபவரின் 10,000 கிலோ ஆர்டர் சரிபார்க்கப்படும்.",
  "footer2": "தேவை • விநியோகம் • விலை • தளவாடம் • AI",
  "supplyAdded": "விநியோகம் வெற்றிகரமாக சேர்க்கப்பட்டது.",
  "demandAdded": "வாங்குபவர் தேவை வெற்றிகரமாக பதிவிடப்பட்டது.",
  "forecastMsg": "க்கான முன்கணிப்பு",
  "demand": "எதிர்பார்க்கப்படும் தேவை",
  "priceRange": "பரிந்துரைக்கப்பட்ட வரம்பு",
  "gapMsg": "தற்போதைய இடைவெளி",
  "aggregateMsg": "ஒருங்கிணைக்கப்பட்ட விநியோகம்",
  "shortage": "பற்றாக்குறை",
  "surplus": "உபரி",
  "risk": "அபாயம்",
  "routeDone": "மேம்படுத்தப்பட்ட வழித்தடம்",
  "estimatedDistance": "மதிப்பிடப்பட்ட தூரம்",
  "estimatedCost": "மதிப்பிடப்பட்ட தளவாட செலவு",
  "net": "மதிப்பிடப்பட்ட நிகர வருமானம்",
  "voiceReady": "குரல் டெமோ தயார்: 500 கிலோ தக்காளி விநியோகம் கண்டறியப்பட்டது.",
  "noSupply": "பொருத்தமான விநியோகம் கிடைக்கவில்லை.",
  "invalid": "சரியான மதிப்புகளை உள்ளிடவும்.",
  "bullish": "நேர்மறை",
  "softening": "மெதுவான",
  "low": "குறைவு",
  "medium": "நடுத்தரம்",
  "high": "அதிகம்",
  "navSectionMain": "முதன்மை",
  "navSectionIntelligence": "நுண்ணறிவு",
  "navSectionOperations": "செயல்பாடுகள்",
  "navSectionAccount": "கணக்கு",
  "navDashboard": "டாஷ்போர்டு",
  "navMyProduce": "என் விளைபொருட்கள்",
  "navBuyerRequests": "வாங்குபவர் கோரிக்கைகள்",
  "navBrowseProduce": "பொருட்களைப் பார்க்கவும்",
  "navPostDemand": "தேவையைப் பதிவு செய்க",
  "navFindFarmers": "விவசாயிகளைத் தேடுங்கள்",
  "navForecast": "AI தேவை முன்கணிப்பு",
  "navPriceAdvisor": "விலை ஆலோசகர்",
  "navProfitSim": "லாப சிமுலேட்டர்",
  "navOrders": "ஆர்டர்கள்",
  "navLogistics": "தளவாடம்",
  "navDeliveryTracking": "டெலிவரி டிராக்கிங்",
  "navReviews": "மதிப்புரைகள் & மதிப்பீடுகள்",
  "navFavorites": "விருப்பங்கள்",
  "navProfile": "சுயவிவரம்",
  "logout": "வெளியேறு",
  "roleFarmer": "விவசாயி 🌾",
  "roleBuyer": "வாடிக்கையாளர் 🛒",
  "activeSupplyListings": "செயலில் உள்ள விளைபொருட்கள்",
  "liveBuyerDemands": "நேரடி வாங்குபவர் தேவைகள்",
  "predictedDemand": "கணிக்கப்பட்ட தேவை",
  "highDemandNearYou": "📍 உங்கள் அருகில் அதிக தேவை",
  "opportunities": "🎯 வாய்ப்புகள்",
  "recommendedBuyers": "🤝 பரிந்துரைக்கப்பட்ட வாங்குபவர்கள்",
  "activeOrders": "📦 செயலில் உள்ள ஆர்டர்கள்",
  "recentReviews": "⭐ சமீபத்திய மதிப்புரைகள்",
  "smartLogisticsStatus": "🚚 ஸ்மார்ட் தளவாட நிலை",
  "forecastHeader": "🔮 AI எதிர்கால தேவை முன்கணிப்பு",
  "forecastSubheader": "எதிர்கால வேளாண் தேவையை கணித்து உகந்த லாபத்தில் அறுவடை செய்யுங்கள்",
  "cropLabel": "பயிர்",
  "periodLabel": "காலம்",
  "heatmapTitle": "🗺️ கர்நாடக வேளாண் தேவை வரைபடம்",
  "heatmapDesc": "கர்நாடக மாவட்டங்களில் தேவை தீவிரம் மற்றும் விலை போக்கு",
  "trendChartTitle": "📈 தேவை போக்கு காட்சிப்படுத்தல் (7-நாள் & 30-நாள்)",
  "highDemandAlertsTitle": "⚡ அதிக தேவை விழிப்பூட்டல்கள் & அறுவடை காலம்",
  "reviewsHeader": "⭐ மதிப்புரைகள் & மதிப்பீடுகள்",
  "reviewsSubheader": "சரிபார்க்கப்பட்ட விவசாயிகள் மற்றும் வாங்குபவர்களுக்கான வெளிப்படையான அமைப்பு",
  "yourRatingTitle": "உங்கள் மதிப்பீடு",
  "writeReviewTitle": "மதிப்புரை எழுதுங்கள்",
  "rateCompletedTx": "பரிவர்த்தனையை மதிப்பிடவும்",
  "selectCompletedOrder": "முடிந்த ஆர்டரைத் தேர்வுசெய்க",
  "overallRating": "ஒட்டுமொத்த மதிப்பீடு *",
  "qualityRating": "தர மதிப்பீடு",
  "deliveryRating": "டெலிவரி மதிப்பீடு",
  "yourReview": "உங்கள் மதிப்புரை",
  "submitReviewBtn": "மதிப்புரையைச் சமர்ப்பிக்கவும்",
  "allReviewsTitle": "அனைத்து மதிப்புரைகள்",
  "browseHeader": "🛒 புதிய விளைபொருட்களைப் பார்க்கவும்",
  "browseSubheader": "விவசாயிகளிடமிருந்து நேரடியாக வெளிப்படையான பண்ணை விலையில்",
  "expectedGrowth": "எதிர்பார்க்கப்படும் வளர்ச்சி",
  "harvestInDays": "உகந்த அறுவடை நேரம்: 3-5 நாட்கள்",
  "surgeExpected": "பண்டிகை தேவை காரணமாக விலை உயர வாய்ப்பு",
  "qualityScore": "விளைபொருள் புத்துணர்ச்சி",
  "orderStatus": "நிலை",
  "completed": "முடிந்தது",
  "inTransit": "வழியில்",
  "pending": "நிலுவையில்",
  "farmGatePrice": "பண்ணை விலை",
  "retailPrice": "சந்தை சில்லறை விலை",
  "directPrice": "KisanFlow நேரடி விலை",
  "placeOrder": "ஆர்டர் செய்க",
  "savingsMsg": "இடைத்தரகர்களைத் தவிர்த்து 32% வரை சேமிக்கவும்"
  },
  "te": {
  "tagline": "అంచనా • అనుసంధానం • సమీకరణ • పంపిణీ",
  "sihBadge": "SIH 2026 — సమస్య ప్రకటన 26033",
  "language": "భాష",
  "selectLanguage": "భాషను ఎంచుకోండి:",
  "authSubtitle": "వ్యవసాయ మార్కెట్ ఇంటెలిజెన్స్",
  "authHeroDesc": "AI డిమాండ్ అంచనా మరియు స్మార్ట్ లాజిస్టిక్స్ ద్వారా రైతులు మరియు FPOలను నేరుగా ధృవీకరించబడిన
  కొనుగోలుదారులతో అనుసంధానించండి.",
  "roleFarmerTitle": "రైతు / FPO",
  "roleFarmerDesc": "మీ పంటలను నేరుగా ధృవీకరించబడిన కొనుగోలుదారులకు అమ్మండి. AI డిమాండ్ అంచనా మరియు సరసమైన ధర పొందండి.",
  "registerFarmerBtn": "రైతు / FPOగా నమోదు చేసుకోండి",
  "roleBuyerTitle": "కస్టమర్ / కొనుగోలుదారు",
  "roleBuyerDesc": "రైతులు మరియు FPOల నుండి నేరుగా తాజా పంటలను సరసమైన మార్కెట్ ధరలకు కొనండి.",
  "registerBuyerBtn": "కస్టమర్ / కొనుగోలుదారుగా నమోదు చేసుకోండి",
  "demoFarmerLogin": "డెమో: రైతు లాగిన్ (రమేష్ పాటిల్)",
  "demoBuyerLogin": "డెమో: కొనుగోలుదారు లాగిన్ (ప్రియా శర్మ)",
  "alreadyHaveAccount": "ఇప్పటికే ఖాతా ఉందా?",
  "signInHere": "ఇక్కడ సైన్ ఇన్ చేయండి",
  "dontHaveAccount": "ఖాతా లేదా?",
  "registerHere": "నమోదు చేసుకోండి",
  "backToRoleSelection": "← పాత్ర ఎంపికకు తిరిగి వెళ్లండి",
  "farmerRegTitle": "🌾 రైతు / FPO నమోదు",
  "farmerRegSubtitle": "దళారులు లేకుండా మీ పంటలను నేరుగా విక్రయించడానికి KisanFlow లో చేరండి",
  "customerRegTitle": "🛒 కస్టమర్ / కొనుగోలుదారు నమోదు",
  "customerRegSubtitle": "రైతుల నుండి నేరుగా తాజా పంటలను కొనుగోలు చేయడానికి KisanFlow లో చేరండి",
  "fullNameLabel": "పూర్తి పేరు / FPO పేరు *",
  "mobileLabel": "మొబైల్ నంబర్ *",
  "emailLabel": "ఇమెయిల్",
  "districtLabel": "జిల్లా *",
  "stateLabel": "రాష్ట్రం *",
  "entityTypeLabel": "రకం *",
  "preferredLangLabel": "ప్రాధాన్య భాష",
  "cropsLabel": "పండించే ప్రధాన పంటలు",
  "qtyLabel": "అందుబాటులో ఉన్న పరిమాణం / పొలం పరిమాణం (ఎకరాలు)",
  "farmDetailsLabel": "పొలం / FPO వివరాలు",
  "bankUpiLabel": "బ్యాంక్ ఖాతా / UPI ID (నేరుగా చెల్లింపు కోసం) *",
  "passwordLabel": "పాస్‌వర్డ్ *",
  "confirmPasswordLabel": "పాస్‌వర్డ్ నిర్ధారించండి *",
  "verifyTermsFarmer": "నేను నిజమైన రైతును/FPO అని ధృవీకరిస్తున్నాను మరియు నిబంధనలకు అంగీకరిస్తున్నాను",
  "verifyTermsBuyer": "నేను సరసమైన లావాదేవీ నిబంధనలకు అంగీకరిస్తున్నాను",
  "createFarmerAccountBtn": "రైతు ఖాతాను సృష్టించండి",
  "createBuyerAccountBtn": "కొనుగోలుదారు ఖాతాను సృష్టించండి",
  "businessNameLabel": "పూర్తి పేరు / వ్యాపార పేరు *",
  "buyerTypeLabel": "కొనుగోలుదారు రకం *",
  "deliveryLocationLabel": "డెలివరీ చిరునామా / ప్రాంతం *",
  "pinCodeLabel": "పిన్ కోడ్ *",
  "contactLabel": "సంప్రదింపు ఫోన్ నంబర్ *",
  "gstLabel": "GST నంబర్ / వ్యాపార ID (వ్యక్తులకు ఐచ్ఛికం)",
  "preferredProductsLabel": "ఆసక్తి ఉన్న పంటలు",
  "loginTitle": "తిరిగి స్వాగతం",
  "loginSubtitle": "మీ KisanFlow ఖాతాకు సైన్ ఇన్ చేయండి",
  "mobileOrEmailLabel": "మొబైల్ నంబర్ లేదా ఇమెయిల్ *",
  "signInBtn": "సైన్ ఇన్ చేయండి",
  "dashboard": "డాష్‌బోర్డ్",
  "marketplace": "మార్కెట్‌ప్లేస్",
  "ai": "AI ఇంటెలిజెన్స్",
  "logistics": "లాజిస్టిక్స్",
  "farmerTools": "రైతు సాధనాలు",
  "heroTitle": "డిమాండ్ నుండి డెలివరీ వరకు వ్యవసాయ మార్కెట్",
  "heroText": "రైతులు మరియు FPOలను వినియోగదారులు, రెస్టారెంట్లు మరియు భారీ కొనుగోలుదారులతో నేరుగా కలిపి, AIతో సరఫరా
  గొలుసు అసమర్థతను తగ్గించండి.",
  "suppliers": "సరఫరాదారులు",
  "buyerDemands": "కొనుగోలుదారుల డిమాండ్లు",
  "tomatoDemand": "అంచనా వేసిన టమాటా డిమాండ్",
  "nextPeriod": "తదుపరి కాలం",
  "demandTrend": "డిమాండ్ ట్రెండ్",
  "aiSignal": "AI సంకేతం",
  "suggestedPrice": "సూచించిన టమాటా ధర",
  "perKg": "కిలోకు",
  "supplyGap": "సరఫరా అంతరం",
  "currentPrediction": "ప్రస్తుత అంచనా",
  "howWorks": "🔄 KisanFlow ఎలా పనిచేస్తుంది",
  "buyerDemand": "కొనుగోలుదారు డిమాండ్",
  "aiForecast": "AI అంచనా",
  "smartMatching": "స్మార్ట్ మ్యాచ్",
  "aggregation": "సమీకరణ",
  "coreUsp": "🎯 ప్రధాన ప్రత్యేకత",
  "uspText": "రైతులు కొనుగోలుదారులను వెతకడం కోసం వేచి ఉండకుండా, కిసాన్‌ఫ్లో అంచనా మార్కెట్ డిమాండ్‌తో ప్రారంభించి తగిన
  వ్యవసాయ సరఫరాను గుర్తించి, సమీకరించి, పంపిణీ చేస్తుంది.",
  "marketText": "రైతు/FPO జాబితాలు మరియు కొనుగోలుదారుల అవసరాలు.",
  "availableSupply": "🌱 అందుబాటులో ఉన్న సరఫరా",
  "buyerBoard": "🛒 కొనుగోలుదారుల డిమాండ్ బోర్డు",
  "addSupply": "రైతు / FPO సరఫరాను జోడించండి",
  "farmerName": "రైతు / FPO పేరు",
  "productExample": "ఉత్పత్తి ఉదా. టమాటా",
  "product": "ఉత్పత్తి",
  "quantity": "పరిమాణం (కిలోలు)",
  "priceKg": "కిలో ధర",
  "location": "ప్రాంతం",
  "addSupplyBtn": "సరఫరాను జోడించండి",
  "postDemand": "కొనుగోలుదారు అవసరాన్ని పోస్ట్ చేయండి",
  "buyerName": "కొనుగోలుదారు పేరు",
  "deliveryLocation": "డెలివరీ ప్రాంతం",
  "deadline": "గడువు (రోజులు)",
  "postDemandBtn": "డిమాండ్‌ను పోస్ట్ చేయండి",
  "forecastTitle": "🔮 AI డిమాండ్ అంచనా",
  "forecastText": "చారిత్రక లావాదేవీలు మరియు మార్కెట్ సంకేతాల ద్వారా భవిష్యత్ డిమాండ్‌ను అంచనా వేయండి.",
  "forecastBtn": "డిమాండ్‌ను అంచనా వేయండి",
  "priceTitle": "💰 వివరించదగిన ధర సలహాదారు",
  "priceText": "అంచనా డిమాండ్ ఆధారంగా AI సహాయ ధర పరిధిని పొందండి.",
  "calculatePrice": "ధరను లెక్కించండి",
  "reverseTitle": "🧩 రివర్స్ మార్కెట్ + స్మార్ట్ సరఫరా సమీకరణ",
  "reverseText": "కొనుగోలుదారు అవసరాన్ని నమోదు చేయండి. KisanFlow రైతులను గుర్తించి వారి సరఫరాను సమీకరిస్తుంది.",
  "requiredKg": "అవసరమైన కిలోలు",
  "buyerLocation": "కొనుగోలుదారు ప్రాంతం",
  "findAggregate": "కనుగొని సమీకరించండి",
  "gapTitle": "📊 సరఫరా-డిమాండ్ అంతరం",
  "gapText": "అంచనా డిమాండ్ మరియు అందుబాటులో ఉన్న సరఫరాను పోల్చి కొరతను గుర్తిస్తుంది.",
  "wasteTitle": "🥬 తాజాదనం / వృధా ప్రమాదం",
  "distance": "దూరం కి.మీ",
  "hours": "ప్రయాణ గంటలు",
  "assessRisk": "ప్రమాదాన్ని అంచనా వేయండి",
  "routeTitle": "🚚 బహుళ ఆర్డర్ మార్గ ఆప్టిమైజర్",
  "routeText": "పికప్ స్థానాలను ఎంచుకోండి. సిస్టమ్ ఆప్టిమైజ్ చేసిన మార్గాన్ని సృష్టిస్తుంది.",
  "destination": "గమ్యస్థానం",
  "optimizeRoute": "మార్గాన్ని ఆప్టిమైజ్ చేయండి",
  "whyRoute": "💡 ఈ మార్గం ఎందుకు?",
  "routeReason": "లాజిస్టిక్స్ ఇంజిన్ దూరం, సమయం మరియు తాజాదనం ప్రమాదాన్ని పరిగణిస్తుంది.",
  "profitTitle": "🧮 రైతు లాభ సిమ్యులేటర్",
  "profitText": "ఆర్డర్‌ను అంగీకరించే ముందు అంచనా ఆదాయాన్ని లెక్కించండి.",
  "sellingPrice": "అమ్మకపు ధర/కిలో",
  "transportCost": "రవాణా ఖర్చు",
  "platformFee": "ప్లాట్‌ఫారమ్ రుసుము",
  "otherCost": "ఇతర ఖర్చు",
  "netReturn": "నికర రాబడిని లెక్కించండి",
  "trustTitle": "⭐ రైతు నమ్మకం స్కోర్",
  "trustText": "స్కోరు నాణ్యత మరియు డెలివరీ పనితీరు ద్వారా లెక్కించబడుతుంది.",
  "voiceTitle": "🎤 వాయిస్ + ప్రాంతీయ భాషా సహాయకుడు",
  "voiceText": "రైతు టైప్ చేయడానికి బదులుగా మాట్లాడవచ్చు. ఉదాహరణ: <b>\"నా వద్ద 500 కిలోల టమాటాలు ఉన్నాయి.\"</b>",
  "voiceDemo": "వాయిస్ డెమో ప్రయత్నించండి",
  "fraudTitle": "🛡️ అనుమానాస్పద ఆర్డర్ గుర్తింపు",
  "fraudText": "అసాధారణ ఆర్డర్ పరిమాణాలను ధృవీకరణ కోసం పంపవచ్చు.",
  "fraudDemo": "⚠ డెమో: వారానికి 200 కిలోల సగటు ఉన్న కొనుగోలుదారు నుండి 10,000 కిలోల ఆర్డర్ ధృవీకరణకు ఫ్లాగ్
  చేయబడుతుంది.",
  "footer2": "డిమాండ్ • సరఫరా • ధర • లాజిస్టిక్స్ • AI",
  "supplyAdded": "సరఫరా విజయవంతంగా జోడించబడింది.",
  "demandAdded": "కొనుగోలుదారు అవసరం విజయవంతంగా పోస్ట్ చేయబడింది.",
  "forecastMsg": "కోసం అంచనా",
  "demand": "అంచనా డిమాండ్",
  "priceRange": "సిఫార్సు పరిధి",
  "gapMsg": "ప్రస్తుత అంతరం",
  "aggregateMsg": "సమీకరించిన సరఫరా",
  "shortage": "కొరత",
  "surplus": "మిగులు",
  "risk": "ప్రమాదం",
  "routeDone": "ఆప్టిమైజ్ చేసిన రూట్",
  "estimatedDistance": "అంచనా దూరం",
  "estimatedCost": "అంచనా లాజిస్టిక్స్ ఖర్చు",
  "net": "అంచనా నికర రాబడి",
  "voiceReady": "వాయిస్ డెమో సిద్ధంగా ఉంది: 500 కిలోల టమాటా సరఫరా గుర్తించబడింది.",
  "noSupply": "తగిన సరఫరా కనుగొనబడలేదు.",
  "invalid": "దయచేసి సరైన విలువలను నమోదు చేయండి.",
  "bullish": "పాజిటివ్",
  "softening": "బలహీనంగా",
  "low": "తక్కువ",
  "medium": "మధ్యస్థ",
  "high": "అధిక",
  "navSectionMain": "ప్రధాన",
  "navSectionIntelligence": "ఇంటెలిజెన్స్",
  "navSectionOperations": "కార్యకలాపాలు",
  "navSectionAccount": "ఖాతా",
  "navDashboard": "డాష్‌బోర్డ్",
  "navMyProduce": "నా పంటలు",
  "navBuyerRequests": "కొనుగోలుదారు అభ్యర్థనలు",
  "navBrowseProduce": "పంటలను బ్రౌజ్ చేయండి",
  "navPostDemand": "అవసరాన్ని పోస్ట్ చేయండి",
  "navFindFarmers": "రైతులను శోధించండి",
  "navForecast": "AI డిమాండ్ అంచనా",
  "navPriceAdvisor": "ధర సలహాదారు",
  "navProfitSim": "లాభ సిమ్యులేటర్",
  "navOrders": "ఆర్డర్లు",
  "navLogistics": "లాజిస్టిక్స్",
  "navDeliveryTracking": "డెలివరీ ట్రాకింగ్",
  "navReviews": "సమీక్షలు & రేటింగ్‌లు",
  "navFavorites": "ఇష్టమైనవి",
  "navProfile": "ప్రొఫైల్",
  "logout": "లాగ్ అవుట్",
  "roleFarmer": "రైతు 🌾",
  "roleBuyer": "కస్టమర్ 🛒",
  "activeSupplyListings": "యాక్టివ్ పంట జాబితాలు",
  "liveBuyerDemands": "లైవ్ కొనుగోలుదారుల డిమాండ్లు",
  "predictedDemand": "అంచనా డిమాండ్",
  "highDemandNearYou": "📍 మీ సమీపంలో అధిక డిమాండ్",
  "opportunities": "🎯 మార్కెట్ అవకాశాలు",
  "recommendedBuyers": "🤝 సిఫార్సు చేసిన కొనుగోలుదారులు",
  "activeOrders": "📦 క్రియాశీల ఆర్డర్లు",
  "recentReviews": "⭐ ఇటీవలి సమీక్షలు",
  "smartLogisticsStatus": "🚚 స్మార్ట్ లాజిస్టిక్స్ స్థితి",
  "forecastHeader": "🔮 AI భవిష్యత్ డిమాండ్ అంచనా",
  "forecastSubheader": "భవిష్యత్ వ్యవసాయ డిమాండ్‌ను అంచనా వేసి సరైన లాభంతో కోత కోయండి",
  "cropLabel": "పంట",
  "periodLabel": "కాలం",
  "heatmapTitle": "🗺️ కర్ణాటక వ్యవసాయ డిమాండ్ హీట్‌మ్యాప్",
  "heatmapDesc": "కర్ణాటక జిల్లాల్లో డిమాండ్ తీవ్రత మరియు ధరల ట్రెండ్స్ ప్రత్యక్ష వీక్షణ",
  "trendChartTitle": "📈 డిమాండ్ ట్రెండ్ విజువలైజేషన్ (7-రోజులు & 30-రోజుల కర్వ్)",
  "highDemandAlertsTitle": "⚡ అధిక డిమాండ్ హెచ్చరికలు & కోత సమయం",
  "reviewsHeader": "⭐ సమీక్షలు & రేటింగ్‌లు",
  "reviewsSubheader": "రైతులు మరియు కొనుగోలుదారుల మధ్య పారదర్శక విశ్వసనీయత వ్యవస్థ",
  "yourRatingTitle": "మీ రేటింగ్",
  "writeReviewTitle": "సమీక్ష రాయండి",
  "rateCompletedTx": "పూర్తయిన లావాదేవీని రేట్ చేయండి",
  "selectCompletedOrder": "పూర్తయిన ఆర్డర్‌ను ఎంచుకోండి",
  "overallRating": "మొత్తం రేటింగ్ *",
  "qualityRating": "నాణ్యత రేటింగ్",
  "deliveryRating": "డెలివరీ రేటింగ్",
  "yourReview": "మీ సమీక్ష",
  "submitReviewBtn": "సమీక్షను సమర్పించండి",
  "allReviewsTitle": "అన్ని సమీక్షలు",
  "browseHeader": "🛒 తాజా పంటలను బ్రౌజ్ చేయండి",
  "browseSubheader": "రైతుల నుండి నేరుగా పారదర్శక పొలం ధరలకు",
  "expectedGrowth": "ఆశించిన వృద్ధి",
  "harvestInDays": "సరైన కోత సమయం: 3-5 రోజులు",
  "surgeExpected": "పండుగ మరియు నగర డిమాండ్ కారణంగా ధర పెరిగే అవకాశం",
  "qualityScore": "పంట తాజాదనం",
  "orderStatus": "స్థితి",
  "completed": "పూర్తయింది",
  "inTransit": "దారిలో ఉంది",
  "pending": "పెండింగ్‌లో ఉంది",
  "farmGatePrice": "పొలం ధర",
  "retailPrice": "మార్కెట్ రిటైల్ ధర",
  "directPrice": "KisanFlow ప్రత్యక్ష ధర",
  "placeOrder": "ఆర్డర్ చేయండి",
  "savingsMsg": "దళారులను తొలగించి 32% వరకు ఆదా చేయండి"
  }
  };

  let lang = localStorage.getItem('kisanflow_lang') || 'en';
  const t = k => (T[lang] && T[lang][k]) || T.en[k] || k;

  // ===== APPLICATION STATE (PRESERVED + EXTENDED) =====
  const state = {
  currentUser: null,
  users: [],
  supplies: [
  {farmer:'Green Valley FPO',product:'Tomato',qty:1200,price:22,location:'Mandya',quality:'A'},
  {farmer:'Mysuru Fresh',product:'Tomato',qty:850,price:23,location:'Mysuru',quality:'A'},
  {farmer:'Kolar Roots',product:'Onion',qty:1800,price:28,location:'Kolar',quality:'A'},
  {farmer:'Hassan Harvest',product:'Potato',qty:1600,price:25,location:'Hassan',quality:'B'}
  ],
  demands: [
  {buyer:'FreshMart Bengaluru',product:'Tomato',qty:3000,location:'Bengaluru',quality:'A',days:3},
  {buyer:'Hotel GreenLeaf',product:'Onion',qty:1200,location:'Bengaluru',quality:'A',days:2}
  ],
  market: {
  Tomato:{demand:5200,price:24,trend:7},
  Onion:{demand:3900,price:29,trend:3},
  Potato:{demand:3100,price:26,trend:-2}
  },
  orders: [
  {id:'ORD-001',product:'Tomato',qty:1200,buyer:'FreshMart Bengaluru',farmer:'Green Valley FPO',status:'In
  Transit',date:'2026-09-02',price:22},
  {id:'ORD-002',product:'Onion',qty:800,buyer:'Hotel GreenLeaf',farmer:'Kolar
  Roots',status:'Completed',date:'2026-09-01',price:28},
  {id:'ORD-003',product:'Potato',qty:500,buyer:'Metro Retail',farmer:'Hassan
  Harvest',status:'Completed',date:'2026-08-28',price:25},
  {id:'ORD-004',product:'Tomato',qty:600,buyer:'Fresh Kitchen',farmer:'Mysuru
  Fresh',status:'Processing',date:'2026-09-03',price:23}
  ],
  reviews: [
  {id:'R001',orderId:'ORD-002',reviewer:'Hotel GreenLeaf',reviewee:'Kolar
  Roots',rating:5,qualityRating:5,deliveryRating:4,text:'Excellent quality onions, fresh and well-packed. Will order
  again.',date:'2026-09-01',role:'buyer'},
  {id:'R002',orderId:'ORD-003',reviewer:'Metro Retail',reviewee:'Hassan
  Harvest',rating:4,qualityRating:4,deliveryRating:4,text:'Good quality potatoes. Delivery was on
  time.',date:'2026-08-29',role:'buyer'},
  {id:'R003',orderId:'ORD-002',reviewer:'Kolar Roots',reviewee:'Hotel
  GreenLeaf',rating:5,qualityRating:null,deliveryRating:null,text:'Great buyer, payment was prompt and communication was
  clear.',date:'2026-09-01',role:'farmer'},
  {id:'R004',orderId:'ORD-003',reviewer:'Hassan Harvest',reviewee:'Metro
  Retail',rating:4,qualityRating:null,deliveryRating:null,text:'Good buyer, fair
  negotiations.',date:'2026-08-30',role:'farmer'}
  ],
  selectedLocation: 'Bengaluru',
  reviewRating: 0
  };

  // Forecast demo data by location
  const forecastData = {
  Tomato: {
  Bengaluru: {demand:18500,growth:24,level:'HIGH'},
  Mysuru: {demand:8200,growth:12,level:'MEDIUM'},
  Mandya: {demand:6100,growth:8,level:'MEDIUM'},
  Hassan: {demand:4300,growth:-3,level:'LOW'},
  Kolar: {demand:5800,growth:15,level:'MEDIUM'}
  },
  Onion: {
  Bengaluru: {demand:12800,growth:11,level:'MEDIUM'},
  Mysuru: {demand:6500,growth:5,level:'MEDIUM'},
  Mandya: {demand:3200,growth:-2,level:'LOW'},
  Hassan: {demand:2800,growth:3,level:'LOW'},
  Kolar: {demand:7200,growth:18,level:'HIGH'}
  },
  Potato: {
  Bengaluru: {demand:9200,growth:-4,level:'LOW'},
  Mysuru: {demand:5100,growth:2,level:'LOW'},
  Mandya: {demand:4800,growth:6,level:'MEDIUM'},
  Hassan: {demand:6200,growth:9,level:'MEDIUM'},
  Kolar: {demand:3100,growth:-6,level:'LOW'}
  }
  };

  const heatmapDistricts = [
  'Bengaluru','Mysuru','Mandya','Hassan','Kolar','Tumakuru',
  'Dharwad','Belgaum','Hubli','Shimoga','Davangere','Raichur'
  ];

  // ===== UTILITY =====
  function esc(v) { return String(v).replace(/[&<>'"]/g, c => ({'&':'&amp;','<':'&lt;','>
      ':'&gt;',"'":'&#39;','"':'&quot;'}[c])); }
      function toast(msg) {
      const e = document.getElementById('toast');
      e.textContent = msg; e.classList.add('show');
      clearTimeout(window._toast);
      window._toast = setTimeout(() => e.classList.remove('show'), 2800);
      }
      function saveState() {
      try { localStorage.setItem('kisanflow_state',
      JSON.stringify({users:state.users,currentUser:state.currentUser,reviews:state.reviews,orders:state.orders,supplies:state.supplies,demands:state.demands}));
      } catch(e){}
      }
      function loadState() {
      try {
      const s = JSON.parse(localStorage.getItem('kisanflow_state'));
      if (s) {
      if (s.users) state.users = s.users;
      if (s.currentUser) state.currentUser = s.currentUser;
      if (s.reviews) state.reviews = s.reviews;
      if (s.orders && s.orders.length) state.orders = s.orders;
      if (s.supplies && s.supplies.length) state.supplies = s.supplies;
      if (s.demands && s.demands.length) state.demands = s.demands;
      }
      } catch(e){}
      }

      // ===== AUTH FUNCTIONS =====
      function showRoleSelection() {
      document.getElementById('roleSelection').style.display = '';
      document.querySelectorAll('.auth-panel').forEach(p => p.classList.remove('active'));
      }
      function showRegForm(role) {
      document.getElementById('roleSelection').style.display = 'none';
      document.querySelectorAll('.auth-panel').forEach(p => p.classList.remove('active'));
      document.getElementById(role === 'farmer' ? 'farmerRegPanel' : 'buyerRegPanel').classList.add('active');
      }
      function showLoginForm() {
      document.getElementById('roleSelection').style.display = 'none';
      document.querySelectorAll('.auth-panel').forEach(p => p.classList.remove('active'));
      document.getElementById('loginPanel').classList.add('active');
      }

      function registerUser(e, role) {
      e.preventDefault();
      const f = new FormData(e.target);
      const pwd = f.get('password'), cpwd = f.get('confirmPassword');
      if (pwd !== cpwd) { toast('Passwords do not match'); return false; }
      const user = {
      id: 'U' + Date.now(),
      role: role,
      name: f.get('name'),
      mobile: f.get('mobile'),
      email: f.get('email') || '',
      password: pwd,
      language: f.get('language') || 'en',
      createdAt: new Date().toISOString()
      };
      if (role === 'farmer') {
      user.district = f.get('district');
      user.state = f.get('state');
      user.farmerType = f.get('farmerType');
      user.crops = f.get('crops');
      user.quantity = f.get('quantity');
      user.details = f.get('details');
      user.location = f.get('district');
      } else {
      user.location = f.get('location');
      user.buyerType = f.get('buyerType');
      user.products = f.get('products');
      }
      state.users.push(user);
      state.currentUser = user;
      lang = user.language || 'en';
      document.getElementById('langSelect').value = lang;
      saveState();
      enterApp();
      toast('Welcome to KisanFlow, ' + user.name + '!');
      return false;
      }

      function loginUser(e) {
      e.preventDefault();
      const f = new FormData(e.target);
      const id = f.get('identifier'), pwd = f.get('password');
      const user = state.users.find(u => (u.mobile === id || u.email === id) && u.password === pwd);
      if (!user) { toast('Invalid credentials. Please try again.'); return false; }
      state.currentUser = user;
      lang = user.language || 'en';
      document.getElementById('langSelect').value = lang;
      saveState();
      enterApp();
      toast('Welcome back, ' + user.name + '!');
      return false;
      }

      function logoutUser() {
      state.currentUser = null;
      saveState();
      document.getElementById('appShell').classList.remove('active');
      document.getElementById('authScreen').style.display = '';
      showRoleSelection();
      }

      function enterApp() {
      const u = state.currentUser;
      if (!u) return;
      document.getElementById('authScreen').style.display = 'none';
      document.getElementById('appShell').classList.add('active');

      // Configure sidebar nav
      const isFarmer = u.role === 'farmer';
      document.getElementById('farmerNav').style.display = isFarmer ? '' : 'none';
      document.getElementById('buyerNav').style.display = isFarmer ? 'none' : '';

      // User info
      document.getElementById('userAvatar').textContent = u.name.charAt(0).toUpperCase();
      document.getElementById('userName').textContent = u.name;
      document.getElementById('userRole').textContent = isFarmer ? (u.farmerType || 'Farmer') : (u.buyerType ||
      'Buyer');
      document.getElementById('topbarName').textContent = u.name;
      if (u.location) {
      const sel = document.getElementById('locationSelect');
      // try to match user location
      for (let o of sel.options) { if (o.value === u.location) { sel.value = u.location; break; } }
      state.selectedLocation = sel.value;
      }

      // Dashboard title
      document.getElementById('dashHeroTitle').textContent = isFarmer ?
      'Welcome to Your Farmer Dashboard' : 'Welcome to Your Buyer Dashboard';
      document.getElementById('recommendedTitle').textContent = isFarmer ?
      '🤝 Recommended Buyers' : '🤝 Recommended Farmers / FPOs';

      navigateTo('dashboard');
      renderAll();
      }

      // ===== NAVIGATION =====
      function navigateTo(pageId) {
      document.querySelectorAll('.page-section').forEach(p => p.classList.remove('active'));
      const page = document.getElementById('page-' + pageId);
      if (page) page.classList.add('active');

      // Update sidebar active
      document.querySelectorAll('.sidebar-nav button[data-page]').forEach(b => {
      b.classList.toggle('active', b.dataset.page === pageId);
      });

      // Close mobile sidebar
      if (window.innerWidth <= 900) { document.getElementById('sidebar').classList.remove('open');
        document.getElementById('sidebarOverlay').classList.remove('open'); } // Trigger page-specific renders if
        (pageId==='dashboard' ) renderDashboard(); if (pageId==='forecast' ) { forecast(); renderHeatmap(); } if
        (pageId==='reviews' ) renderReviews(); if (pageId==='orders' ) renderOrders(); if (pageId==='myProduce' )
        renderMyProduce(); if (pageId==='buyerRequests' ) renderBuyerRequests(); if (pageId==='browseProduce' )
        renderBrowseProduce(); if (pageId==='postRequirement' ) {} if (pageId==='findFarmers' ) gap(); if
        (pageId==='profile' ) renderProfile(); if (pageId==='deliveryTracking' ) renderDeliveryTracking(); if
        (pageId==='logistics' ) {} if (pageId==='profitSim' ) { profit(); } } function toggleSidebar() {
        document.getElementById('sidebar').classList.toggle('open');
        document.getElementById('sidebarOverlay').classList.toggle('open'); } //=====i18n=====function applyI18n() {
        document.querySelectorAll('[data-i18n]').forEach(e=> {
        const k = e.dataset.i18n;
        if (k === 'voiceText' || k === 'fraudDemo') e.innerHTML = t(k);
        else e.textContent = t(k);
        });
        document.querySelectorAll('[data-i18n-placeholder]').forEach(e => e.placeholder = t(e.dataset.i18nPlaceholder));
        document.documentElement.lang = lang;

        // Sync language selects
        const s1 = document.getElementById('langSelect');
        const s2 = document.getElementById('authLangSelect');
        if (s1 && s1.value !== lang) s1.value = lang;
        if (s2 && s2.value !== lang) s2.value = lang;

        // Localize user role badge in sidebar
        const roleEl = document.getElementById('userRole');
        if (roleEl && state.currentUser) {
        roleEl.textContent = state.currentUser.role === 'farmer' ? t('roleFarmer') : t('roleBuyer');
        }
        }

        function changeLang(v) {
        lang = v;
        localStorage.setItem('kisanflow_lang', v);
        const s1 = document.getElementById('langSelect');
        const s2 = document.getElementById('authLangSelect');
        if (s1) s1.value = v;
        if (s2) s2.value = v;

        applyI18n();

        // Re-render active views if user is logged in
        if (state.currentUser) {
        renderSidebarNav();
        renderDashboard();
        renderHeatmap();
        forecast();
        renderReviews();
        renderOrders();
        renderBrowseProduce();
        renderMyProduce();
        renderBuyerRequests();
        }

        const langLabel = (s1 && s1.selectedOptions[0]?.text) || (s2 && s2.selectedOptions[0]?.text) || v;
        toast(t('language') + ': ' + langLabel);
        }
        function changeLocation() {
        state.selectedLocation = document.getElementById('locationSelect').value;
        renderDashboard();
        }

        // ===== RENDER ALL =====
        function renderAll() {
        applyI18n();
        renderDashboard();
        }

        // ===== DASHBOARD RENDER =====
        function renderDashboard() {
        // Metrics
        document.getElementById('metricSupply').textContent = state.supplies.length;
        document.getElementById('metricDemands').textContent = state.demands.length;
        const crop = document.getElementById('dashForecastCrop')?.value || 'Tomato';
        const m = state.market[crop] || state.market.Tomato;
        const totalSupply = state.supplies.filter(x => x.product.toLowerCase() === crop.toLowerCase()).reduce((a,x) => a
        + Number(x.qty), 0);
        const gapVal = m.demand - totalSupply;
        document.getElementById('metricPredicted').textContent = m.demand.toLocaleString() + ' kg';
        document.getElementById('metricPredictedCrop').textContent = crop + ' · Next period';
        document.getElementById('metricGap').textContent = Math.abs(gapVal).toLocaleString() + ' kg';
        const gapChange = document.querySelector('#page-dashboard .metric-change');
        if (gapChange) {
        gapChange.className = 'metric-change ' + (gapVal >= 0 ? 'down' : 'up');
        gapChange.textContent = gapVal >= 0 ? '⬇ ' + t('shortage') : '⬆ ' + t('surplus');
        }

        // Dashboard forecast
        updateDashForecast();

        // Near you
        renderNearYou();

        // Opportunities
        renderOpportunities();

        // Recommended
        renderRecommended();

        // Orders
        renderDashOrders();

        // Reviews
        renderDashReviews();

        // Logistics
        renderDashLogistics();
        }

        function updateDashForecast() {
        const crop = document.getElementById('dashForecastCrop')?.value || 'Tomato';
        const loc = document.getElementById('dashForecastLoc')?.value || 'All Locations';
        const period = parseInt(document.getElementById('dashForecastPeriod')?.value || '15');
        const fData = forecastData[crop] || forecastData.Tomato;
        const periodMult = period === 7 ? 0.5 : period === 30 ? 2 : 1;

        let locations = loc === 'All Locations' ? Object.keys(fData) : [loc];
        locations = locations.slice(0, 3);

        let html = '';
        locations.forEach(l => {
        const d = fData[l];
        if (!d) return;
        const adjDemand = Math.round(d.demand * periodMult);
        html += `<div class="card forecast-card">
          <span class="demand-level demand-${d.level}">${t(d.level.toLowerCase())}</span>
          <div class="fc-crop">${esc(crop)}</div>
          <div class="fc-location">📍 ${esc(l)}</div>
          <div class="fc-stat">
            <div class="fc-stat-label">Predicted Demand</div>
            <div class="fc-stat-value">${adjDemand.toLocaleString()} kg</div>
          </div>
          <div class="fc-stat">
            <div class="fc-stat-label">${t('expectedGrowth')}</div>
            <div class="fc-growth" style="color:${d.growth >= 0 ? 'var(--green)' : 'var(--red)'}">
              ${d.growth >= 0 ? '▲' : '▼'} ${Math.abs(d.growth)}%
            </div>
          </div>
        </div>`;
        });
        document.getElementById('dashForecastCards').innerHTML = html;

        // Update trend chart
        drawTrendChart('trendChart', crop);
        }

        // ===== NEAR YOU =====
        function renderNearYou() {
        const loc = state.selectedLocation;
        document.getElementById('nearYouLocation').textContent = '📍 ' + loc;
        const items = [];
        for (const crop of Object.keys(forecastData)) {
        const d = forecastData[crop][loc];
        if (d) items.push({crop, ...d});
        }
        items.sort((a,b) => b.demand - a.demand);
        document.getElementById('nearYouList').innerHTML = items.map(i =>
        `<div class="list-item">
          <strong>${esc(i.crop)}</strong>
          <span
            class="pill ${i.level==='HIGH'?'pill-green':i.level==='MEDIUM'?'pill-gold':'pill-red'}">${i.level}</span>
        </div>`
        ).join('') || '<p style="color:var(--muted);font-size:0.85rem;">No data for this location</p>';
        }

        // ===== OPPORTUNITIES =====
        function renderOpportunities() {
        const u = state.currentUser;
        let html = '';
        if (u && u.role === 'farmer') {
        state.demands.slice(0, 3).forEach(d => {
        html += `<div class="list-item">
          <div><strong>${esc(d.product)}</strong><br><span style="font-size:0.78rem;color:var(--muted)">${esc(d.buyer)}
              · ${d.qty} kg</span></div><span class="pill pill-blue">${d.days}d</span>
        </div>`;
        });
        } else {
        state.supplies.slice(0, 3).forEach(s => {
        html += `<div class="list-item">
          <div><strong>${esc(s.product)}</strong><br><span style="font-size:0.78rem;color:var(--muted)">${esc(s.farmer)}
              · ₹${s.price}/kg</span></div><span class="pill pill-green">${s.qty} kg</span>
        </div>`;
        });
        }
        document.getElementById('opportunitiesList').innerHTML = html || '<p
          style="color:var(--muted);font-size:0.85rem;">No opportunities yet</p>';
        }

        // ===== RECOMMENDED =====
        function renderRecommended() {
        const u = state.currentUser;
        let html = '';
        if (u && u.role === 'farmer') {
        state.demands.slice(0, 3).forEach(d => {
        const avgRating = getAverageRating(d.buyer);
        html += `<div class="list-item">
          <div><strong>${esc(d.buyer)}</strong><br><span style="font-size:0.78rem;color:var(--muted)">${esc(d.product)}
              · ${esc(d.location)}</span></div>
          <div style="text-align:right"><span style="color:var(--gold);font-weight:700;">⭐ ${avgRating}</span><br><span
              class="pill pill-green">${d.qty} kg needed</span></div>
        </div>`;
        });
        } else {
        state.supplies.slice(0, 3).forEach(s => {
        const avgRating = getAverageRating(s.farmer);
        html += `<div class="list-item">
          <div><strong>${esc(s.farmer)}</strong><br><span style="font-size:0.78rem;color:var(--muted)">${esc(s.product)}
              · ${esc(s.location)}</span></div>
          <div style="text-align:right"><span style="color:var(--gold);font-weight:700;">⭐ ${avgRating}</span><br><span
              class="pill pill-green">₹${s.price}/kg</span></div>
        </div>`;
        });
        }
        document.getElementById('recommendedList').innerHTML = html || '<p
          style="color:var(--muted);font-size:0.85rem;">No recommendations yet</p>';
        }

        // ===== ORDERS =====
        function renderDashOrders() {
        const html = state.orders.slice(0, 3).map(o => {
        const statusPill = o.status === 'Completed' ? 'pill-green' : o.status === 'In Transit' ? 'pill-blue' :
        'pill-gold';
        return `<div class="order-item">
          <div class="order-info"><strong>${esc(o.id)} · ${esc(o.product)}</strong><span>${esc(o.farmer)} →
              ${esc(o.buyer)} · ${o.qty} kg</span></div>
          <div class="order-status"><span class="pill ${statusPill}">${o.status}</span><br><span
              style="font-size:0.72rem;color:var(--muted)">${o.date}</span></div>
        </div>`;
        }).join('');
        document.getElementById('dashOrders').innerHTML = html || '<p style="color:var(--muted);font-size:0.85rem;">No
          active orders</p>';
        }
        function renderOrders() {
        const html = state.orders.map(o => {
        const statusPill = o.status === 'Completed' ? 'pill-green' : o.status === 'In Transit' ? 'pill-blue' :
        'pill-gold';
        const canReview = o.status === 'Completed';
        return `<div class="order-item">
          <div class="order-info"><strong>${esc(o.id)} · ${esc(o.product)}</strong><span>${esc(o.farmer)} →
              ${esc(o.buyer)} · ${o.qty} kg @ ₹${o.price}/kg = ₹${(o.qty * o.price).toLocaleString()}</span></div>
          <div class="order-status"><span class="pill ${statusPill}">${o.status}</span><br><span
              style="font-size:0.72rem;color:var(--muted)">${o.date}</span>${canReview ? '<br><button
              class="btn btn-xs btn-secondary" style="margin-top:4px" onclick="navigateTo(\'reviews\')">Write
              Review</button>' : ''}</div>
        </div>`;
        }).join('');
        document.getElementById('ordersFullList').innerHTML = html || '<p style="color:var(--muted);">No orders yet</p>
        ';
        }

        // ===== REVIEWS =====
        function renderDashReviews() {
        const html = state.reviews.slice(0, 3).map(r => renderReviewItem(r)).join('');
        document.getElementById('dashReviews').innerHTML = html || '<p style="color:var(--muted);font-size:0.85rem;">No
          reviews yet</p>';
        }
        function renderReviews() {
        // My rating
        const u = state.currentUser;
        if (u) {
        const myName = u.name;
        const myReviews = state.reviews.filter(r => r.reviewee === myName);
        const avg = myReviews.length ? (myReviews.reduce((a,r) => a + r.rating, 0) / myReviews.length).toFixed(1) : '—';
        document.getElementById('myRatingScore').textContent = avg;
        document.getElementById('myReviewCount').textContent = `Based on ${myReviews.length} review${myReviews.length
        !== 1 ? 's' : ''}`;
        // Stars
        const starCount = Math.round(parseFloat(avg) || 0);
        document.getElementById('myRatingStars').innerHTML = [1,2,3,4,5].map(i => `<span
          class="star ${i <= starCount ? 'filled' : ''}">★</span>`).join('');
        }

        // Populate review order select
        const completedOrders = state.orders.filter(o => o.status === 'Completed');
        const reviewedOrders = new Set(state.reviews.filter(r => r.reviewer === (u?.name || '')).map(r => r.orderId));
        const reviewSelect = document.getElementById('reviewOrderSelect');
        reviewSelect.innerHTML = '<option value="">-- Select a completed order --</option>';
        completedOrders.forEach(o => {
        if (!reviewedOrders.has(o.id)) {
        reviewSelect.innerHTML += `<option value="${o.id}">${o.id} · ${esc(o.product)} (${esc(o.farmer)} →
          ${esc(o.buyer)})</option>`;
        }
        });

        // All reviews
        document.getElementById('allReviewsList').innerHTML = state.reviews.map(r => renderReviewItem(r)).join('') || '
        <p style="color:var(--muted);">No reviews yet</p>';
        }

        function renderReviewItem(r) {
        const stars = [1,2,3,4,5].map(i => `<span class="star ${i <= r.rating ? 'filled' : ''}">★</span>`).join('');
        return `<div class="review-item">
          <div class="review-header">
            <div class="review-avatar">${r.reviewer.charAt(0)}</div>
            <div class="review-meta">
              <strong>${esc(r.reviewer)}</strong>
              <span>${r.date} · Order ${esc(r.orderId)}</span>
            </div>
            <div class="stars stars-static" style="margin-left:auto;">${stars}</div>
          </div>
          <div class="review-body">${esc(r.text)}</div>
          <div class="review-tags">
            ${r.qualityRating ? `<span class="pill pill-green">Quality: ${r.qualityRating}/5</span>` : ''}
            ${r.deliveryRating ? `<span class="pill pill-blue">Delivery: ${r.deliveryRating}/5</span>` : ''}
            <button class="review-report" onclick="toast('Review reported for moderation')">🚩 Report</button>
          </div>
        </div>`;
        }

        function getAverageRating(name) {
        const revs = state.reviews.filter(r => r.reviewee === name);
        if (!revs.length) return '4.5';
        return (revs.reduce((a,r) => a + r.rating, 0) / revs.length).toFixed(1);
        }

        function setReviewRating(val) {
        state.reviewRating = val;
        document.querySelectorAll('#reviewStars .star').forEach(s => {
        s.classList.toggle('filled', parseInt(s.dataset.val) <= val); }); } function submitReview(e) {
          e.preventDefault(); const f=new FormData(e.target); const orderId=f.get('orderId'); if (!orderId) {
          toast('Please select a completed order'); return false; } if (!state.reviewRating) { toast('Please select a
          rating'); return false; } const order=state.orders.find(o=> o.id === orderId);
          if (!order) { toast('Order not found'); return false; }

          // Prevent duplicate
          const u = state.currentUser;
          if (state.reviews.find(r => r.orderId === orderId && r.reviewer === (u?.name || ''))) {
          toast('You have already reviewed this order');
          return false;
          }

          const isFarmer = u?.role === 'farmer';
          const review = {
          id: 'R' + Date.now(),
          orderId: orderId,
          reviewer: u?.name || 'Anonymous',
          reviewee: isFarmer ? order.buyer : order.farmer,
          rating: state.reviewRating,
          qualityRating: parseInt(f.get('qualityRating')) || null,
          deliveryRating: parseInt(f.get('deliveryRating')) || null,
          text: f.get('reviewText') || '',
          date: new Date().toISOString().split('T')[0],
          role: u?.role || 'buyer'
          };
          state.reviews.unshift(review);
          state.reviewRating = 0;
          e.target.reset();
          document.querySelectorAll('#reviewStars .star').forEach(s => s.classList.remove('filled'));
          saveState();
          renderReviews();
          toast('Review submitted successfully!');
          return false;
          }

          // ===== LOGISTICS DASHBOARD =====
          function renderDashLogistics() {
          const inTransit = state.orders.filter(o => o.status === 'In Transit');
          const html = inTransit.map(o =>
          `<div class="order-item">
            <div class="order-info"><strong>🚚 ${esc(o.id)} · ${esc(o.product)}</strong><span>${esc(o.farmer)} →
                ${esc(o.buyer)} · ${o.qty} kg</span></div>
            <div class="order-status"><span class="pill pill-blue">In Transit</span><br><span
                style="font-size:0.72rem;color:var(--muted)">ETA: 4-6 hours</span></div>
          </div>`
          ).join('');
          document.getElementById('dashLogistics').innerHTML = html || '<p
            style="color:var(--muted);font-size:0.85rem;">No active deliveries</p>';
          }

          // ===== MY PRODUCE (Farmer) =====
          function renderMyProduce() {
          document.getElementById('farmerProducts').innerHTML = state.supplies.map(s =>
          `<div class="list-item">
            <div><strong>${esc(s.product)}</strong><br><small>${esc(s.farmer)} · ${esc(s.location)}</small></div>
            <div style="text-align:right"><span class="pill pill-green">${esc(s.quality)}</span><br><b>${s.qty} kg</b> ·
              ₹${s.price}/kg</div>
          </div>`
          ).join('') || '<p style="color:var(--muted);">No produce listed yet</p>';
          }
          function addSupply(e) {
          e.preventDefault();
          const f = new FormData(e.target);
          const item =
          {farmer:f.get('farmer'),product:f.get('product'),qty:Number(f.get('qty')),price:Number(f.get('price')),location:f.get('location'),quality:f.get('quality')};
          if (!item.farmer||!item.product||item.qty<=0||item.price<0||!item.location) { toast(t('invalid')); return
            false; } state.supplies.unshift(item); e.target.reset(); saveState(); renderMyProduce();
            toast(t('supplyAdded')); return false; } //=====BUYER REQUESTS (Farmer)=====function renderBuyerRequests() {
            document.getElementById('buyerRequestsList').innerHTML=state.demands.map(d=>
            `<div class="list-item">
              <div><strong>${esc(d.product)}</strong><br><small>${esc(d.buyer)} · ${esc(d.location)}</small></div>
              <div style="text-align:right"><span class="pill pill-blue">${esc(d.quality)}</span><br><b>${d.qty} kg</b>
                · ${d.days}d deadline</div>
            </div>`
            ).join('') || '<p style="color:var(--muted);">No buyer requests</p>';
            }

            // ===== BROWSE PRODUCE (Buyer) =====
            function renderBrowseProduce() {
            document.getElementById('browseProducts').innerHTML = state.supplies.map(s => {
            const rating = getAverageRating(s.farmer);
            return `<div class="list-item">
              <div><strong>${esc(s.product)}</strong><br><small>${esc(s.farmer)} · ${esc(s.location)} · <span
                    style="color:var(--gold)">⭐ ${rating}</span></small></div>
              <div style="text-align:right"><span class="pill pill-green">${esc(s.quality)}</span><br><b>${s.qty} kg</b>
                · ₹${s.price}/kg</div>
            </div>`;
            }).join('') || '<p style="color:var(--muted);">No produce available</p>';
            }

            // ===== POST DEMAND =====
            function addDemand(e) {
            e.preventDefault();
            const f = new FormData(e.target);
            const item =
            {buyer:f.get('buyer'),product:f.get('product'),qty:Number(f.get('qty')),location:f.get('location'),quality:f.get('quality'),days:Number(f.get('deadline_days'))||3};
            if (!item.buyer||!item.product||item.qty<=0||!item.location) { toast(t('invalid')); return false; }
              state.demands.unshift(item); e.target.reset(); saveState(); toast(t('demandAdded')); return false; }
              //=====DELIVERY TRACKING=====function renderDeliveryTracking() { const html=state.orders.filter(o=>
              o.status !== 'Completed').map(o => {
              const statusPill = o.status === 'In Transit' ? 'pill-blue' : 'pill-gold';
              return `<div class="order-item">
                <div class="order-info"><strong>📦 ${esc(o.id)} · ${esc(o.product)}</strong><span>${esc(o.farmer)} →
                    ${esc(o.buyer)} · ${o.qty} kg</span></div>
                <div class="order-status"><span class="pill ${statusPill}">${o.status}</span><br><span
                    style="font-size:0.72rem;color:var(--muted)">${o.status === 'In Transit' ? 'ETA: 4-6 hours' :
                    'Awaiting pickup'}</span></div>
              </div>`;
              }).join('');
              document.getElementById('deliveryList').innerHTML = html || '<p style="color:var(--muted);">No active
                deliveries</p>';
              }

              // ===== PROFILE =====
              function renderProfile() {
              const u = state.currentUser;
              if (!u) return;
              const rating = getAverageRating(u.name);
              const revCount = state.reviews.filter(r => r.reviewee === u.name).length;
              let html = `<div style="display:flex;gap:20px;align-items:center;margin-bottom:20px;">
                <div
                  style="width:64px;height:64px;border-radius:50%;background:linear-gradient(135deg,var(--green),var(--green2));display:flex;align-items:center;justify-content:center;font-size:1.5rem;font-weight:800;color:#fff;">
                  ${u.name.charAt(0).toUpperCase()}</div>
                <div>
                  <h2 style="margin:0;">${esc(u.name)}</h2>
                  <p style="margin:2px 0;color:var(--muted)">${u.role === 'farmer' ? (u.farmerType || 'Farmer') :
                    (u.buyerType || 'Buyer')} · ${esc(u.location || u.district || '')}</p>
                  <div class="rating-display"><span style="color:var(--gold);font-weight:700;">⭐ ${rating}/5</span><span
                      class="rating-count">(${revCount} reviews)</span></div>
                </div>
              </div>`;
              html += `<div class="grid grid-2">`;
                html += `<div>
                  <h3>Contact</h3>
                  <p>📱 ${esc(u.mobile)}</p>${u.email ? `<p>📧 ${esc(u.email)}</p>` : ''}`;
                  if (u.role === 'farmer') {
                  html += `<p>📍 ${esc(u.district || '')} , ${esc(u.state || '')}</p>`;
                  if (u.crops) html += `<p>🌾 Crops: ${esc(u.crops)}</p>`;
                  if (u.quantity) html += `<p>📦 Available: ${esc(u.quantity)} kg</p>`;
                  } else {
                  html += `<p>📍 ${esc(u.location || '')}</p>`;
                  if (u.products) html += `<p>🛒 Preferred: ${esc(u.products)}</p>`;
                  }
                  html += `
                </div>
                <div>
                  <h3>Account</h3>
                  <p>Member since: ${new Date(u.createdAt).toLocaleDateString()}</p>
                  <p>Language: ${u.language?.toUpperCase() || 'EN'}</p>
                  <p>ID: ${u.id}</p>
                </div>
              </div>`;
              document.getElementById('profileCard').innerHTML = html;
              }

              // ===== FORECAST (PRESERVED + ENHANCED) =====
              function forecast() {
              const p = document.getElementById('forecastProduct')?.value || 'Tomato';
              const loc = document.getElementById('forecastLocation')?.value || 'All';
              const period = parseInt(document.getElementById('forecastPeriod')?.value || '15');
              const m = state.market[p] || state.market.Tomato;
              const fData = forecastData[p] || forecastData.Tomato;
              const periodMult = period === 7 ? 0.5 : period === 30 ? 2 : 1;

              // Cards
              let locations = loc === 'All' ? Object.keys(fData) : [loc];
              let html = '';
              locations.forEach(l => {
              const d = fData[l];
              if (!d) return;
              const adjDemand = Math.round(d.demand * periodMult);
              html += `<div class="card forecast-card">
                <span class="demand-level demand-${d.level}">${d.level}</span>
                <div class="fc-crop">${esc(p)}</div>
                <div class="fc-location">📍 ${esc(l)}</div>
                <div class="fc-stat">
                  <div class="fc-stat-label">${t('predictedDemand')} (${period}d)</div>
                  <div class="fc-stat-value">${adjDemand.toLocaleString()} kg</div>
                </div>
                <div class="fc-stat">
                  <div class="fc-stat-label">Expected Growth</div>
                  <div class="fc-growth" style="color:${d.growth >= 0 ? 'var(--green)' : 'var(--red)'}">${d.growth >= 0
                    ? '▲' : '▼'} ${Math.abs(d.growth)}%</div>
                </div>
              </div>`;
              });
              document.getElementById('forecastCards').innerHTML = html;

              // Result text
              const factor = 1 + (Math.random() * 0.08 - 0.02);
              const d = Math.round(m.demand * factor * periodMult);
              document.getElementById('forecastResult').innerHTML =
              `<b>${p} ${t('forecastMsg')}</b><br>${t('demand')}: <strong>${d.toLocaleString()} kg</strong> (${period}
              days)<br>${t('demandTrend')}: <span class="pill ${m.trend >= 0 ? 'pill-green' : 'pill-red'}">${m.trend >=
                0 ? t('bullish') : t('softening')}</span>`;

              // Trend chart
              drawTrendChart('forecastTrendChart', p);
              renderHeatmap();
              }

              // ===== TREND CHART (SVG) =====
              function drawTrendChart(svgId, crop) {
              const svg = document.getElementById(svgId);
              if (!svg) return;
              const m = state.market[crop] || state.market.Tomato;
              const base = m.demand;
              const points = [];
              for (let i = 0; i < 12; i++) { const noise=(Math.random() - 0.5) * base * 0.15; const trend=base +
                (m.trend / 100) * base * i * 0.3; points.push(Math.max(0, Math.round(trend + noise))); } const
                maxVal=Math.max(...points) * 1.1; const w=600, h=160, pad=20; const stepX=(w - pad * 2) / (points.length
                - 1); const coords=points.map((v, i)=> ({
                x: pad + i * stepX,
                y: h - pad - ((v / maxVal) * (h - pad * 2))
                }));
                const pathD = coords.map((c, i) => `${i === 0 ? 'M' : 'L'} ${c.x} ${c.y}`).join(' ');
                const areaD = pathD + ` L ${coords[coords.length-1].x} ${h - pad} L ${coords[0].x} ${h - pad} Z`;

                svg.innerHTML = `
                <defs>
                  <linearGradient id="trendGrad${svgId}" x1="0" y1="0" x2="0" y2="1">
                    <stop offset="0%" stop-color="var(--green)" stop-opacity="0.3" />
                    <stop offset="100%" stop-color="var(--green)" stop-opacity="0.02" />
                  </linearGradient>
                </defs>
                <path d="${areaD}" fill="url(#trendGrad${svgId})" />
                <path d="${pathD}" fill="none" stroke="var(--green)" stroke-width="2.5" stroke-linecap="round"
                  stroke-linejoin="round" />
                ${coords.map(c => `
                <circle cx="${c.x}" cy="${c.y}" r="3.5" fill="var(--green)" stroke="#fff" stroke-width="1.5" />
                `).join('')}
                <line x1="${pad}" y1="${h - pad}" x2="${w - pad}" y2="${h - pad}" stroke="var(--border)"
                  stroke-width="1" />
                ${['Now','','','3d','','','6d','','','9d','','12d'].map((l, i) => l ? `<text x="${pad + i * stepX}"
                  y="${h - 4}" fill="var(--muted)" font-size="10" text-anchor="middle"
                  font-family="Inter,sans-serif">${l}</text>` : '').join('')}
                `;
                }

                // ===== HEATMAP =====
                function renderHeatmap() {
                const crop = document.getElementById('forecastProduct')?.value ||
                document.getElementById('dashForecastCrop')?.value || 'Tomato';
                const fData = forecastData[crop] || forecastData.Tomato;

                document.getElementById('heatmapGrid').innerHTML = heatmapDistricts.map(d => {
                const data = fData[d];
                let level, demand;
                if (data) {
                level = data.level;
                demand = data.demand.toLocaleString() + ' kg';
                } else {
                const hash = d.split('').reduce((a, c) => a + c.charCodeAt(0), 0);
                const pseudoDemand = Math.round(2000 + (hash % 8000));
                level = pseudoDemand > 6000 ? 'HIGH' : pseudoDemand > 3500 ? 'MEDIUM' : 'LOW';
                demand = pseudoDemand.toLocaleString() + ' kg';
                }
                const levelText = level === 'HIGH' ? t('high') : level === 'MEDIUM' ? t('medium') : t('low');
                const cls = level === 'HIGH' ? 'heat-high' : level === 'MEDIUM' ? 'heat-medium' : 'heat-low';
                return `<div class="heatmap-cell ${cls}">
                  <div class="district-name">${esc(d)}</div>
                  <div class="district-demand">${demand}</div>
                  <div style="font-size:0.75rem;font-weight:700;margin-top:2px;">${levelText}</div>
                </div>`;
                }).join('');
                }

                // ===== PRESERVED AI FUNCTIONS =====
                function priceAdvice() {
                const p = document.getElementById('priceProduct').value;
                const m = state.market[p] || state.market.Tomato;
                const lo = Math.max(1, Math.round(m.price * 0.94));
                const hi = Math.round(m.price * 1.08);
                document.getElementById('priceResult').innerHTML =
                `<b>${p}</b><br>${t('priceRange')}: <strong>₹${lo}–₹${hi}/kg</strong><br><small>${t('aiSignal')}:
                  ${m.trend >= 0 ? t('bullish') : t('softening')}</small>`;
                }

                function gap() {
                const crop = document.getElementById('dashForecastCrop')?.value || 'Tomato';
                const m = state.market[crop] || state.market.Tomato;
                const s = state.supplies.filter(x => x.product.toLowerCase() === crop.toLowerCase()).reduce((a, x) => a
                + Number(x.qty), 0);
                const g = m.demand - s;
                const el = document.getElementById('gapResult');
                if (el) el.innerHTML = `<b>${t('demand')}:</b> ${m.demand.toLocaleString()} kg<br><b>${t(g >= 0 ?
                  'shortage' : 'surplus')}:</b> ${Math.abs(g).toLocaleString()} kg<br><span
                  class="pill ${g >= 0 ? 'pill-red' : 'pill-green'}">${g >= 0 ? t('shortage') : t('surplus')}</span>`;
                }

                function matchSupply() {
                const p = document.getElementById('matchProduct').value.trim();
                const need = Number(document.getElementById('matchQty').value);
                if (!p || !need) { toast(t('invalid')); return; }
                let left = need;
                const matches = state.supplies.filter(s => s.product.toLowerCase() === p.toLowerCase())
                .sort((a, b) => a.price - b.price)
                .map(s => { const take = Math.min(left, s.qty); left -= take; return {...s, take}; })
                .filter(x => x.take > 0);
                const got = need - left;
                if (!matches.length) { document.getElementById('matchResult').textContent = t('noSupply'); return; }
                document.getElementById('matchResult').innerHTML =
                `<b>${t('aggregateMsg')}: ${got.toLocaleString()} kg</b><br>${matches.map(x => `${esc(x.farmer)} —
                ${x.take} kg @ ₹${x.price}/kg`).join('<br>')}<br><span
                  class="pill ${left > 0 ? 'pill-red' : 'pill-green'}">${left > 0 ? t('shortage') + ': ' +
                  left.toLocaleString() + ' kg' : t('buyerDemands') + ' ✓'}</span>`;
                }

                function wastage() {
                const p = document.getElementById('wProduct').value;
                const d = Number(document.getElementById('wDistance').value);
                const h = Number(document.getElementById('wHours').value);
                if (d < 0 || h < 0) { toast(t('invalid')); return; } let base=p==='Leafy vegetables' ? 35 : p==='Tomato'
                  ? 18 : 8; let score=Math.min(99, Math.round(base + d * 0.12 + h * 3)); const level=score < 25 ?
                  t('low') : score < 50 ? t('medium') : t('high'); document.getElementById('wResult').innerHTML=`<b>
                  ${t('risk')}:</b> ${score}% — <span
                    class="pill ${score < 25 ? 'pill-green' : score < 50 ? 'pill-gold' : 'pill-red'}">${level}</span><br><small>${p}:
                    ${d} km, ${h} h</small>`;
                  }

                  function optimizeRoute() {
                  const picks = [...document.querySelectorAll('.checks input:checked')].map(x => x.value);
                  const dest = document.getElementById('destination').value.trim() || 'Bengaluru';
                  if (!picks.length) { toast(t('invalid')); return; }
                  const order = ['Mandya','Mysuru','Hassan','Kolar','Tumakuru'];
                  picks.sort((a, b) => order.indexOf(a) - order.indexOf(b));
                  const km = {Mandya:110,Mysuru:145,Hassan:185,Kolar:70,Tumakuru:75};
                  const total = picks.reduce((a, x) => a + (km[x] || 100), 0);
                  const cost = Math.round(total * 18);
                  document.getElementById('routeResult').innerHTML =
                  `<b>${t('routeDone')}:</b> ${picks.join(' → ')} → ${esc(dest)}<br>${t('estimatedDistance')}: ${total}
                  km<br>${t('estimatedCost')}: ₹${cost.toLocaleString()}`;
                  }

                  function profit() {
                  const q = Number(document.getElementById('pQty').value);
                  const p = Number(document.getElementById('pPrice').value);
                  const tr = Number(document.getElementById('pTransport').value);
                  const fee = Number(document.getElementById('pFee').value);
                  const other = Number(document.getElementById('pOther').value);
                  if ([q, p, tr, fee, other].some(x => x < 0) || q <=0) { toast(t('invalid')); return; } const gross=q *
                    p, net=gross - tr - fee - other; document.getElementById('profitResult').innerHTML=`${t('net')}:
                    <strong>₹${net.toLocaleString()}</strong><br><small>Gross: ₹${gross.toLocaleString()} · Costs:
                      ₹${(tr + fee + other).toLocaleString()}</small>`;
                    }

                    function demoVoice() {
                    document.getElementById('voiceResult').innerHTML =
                    `<span class="pill pill-green">🎤</span> ${t('voiceReady')}`;
                    }

                    // ===== INITIALIZATION =====
                    (function init() {
                    loadState();
                    applyI18n();

                    // Check if user is already logged in
                    if (state.currentUser) {
                    enterApp();
                    } else {
                    document.getElementById('authScreen').style.display = '';
                    }

                    // Initialize some default renders
                    forecast();
                    priceAdvice();
                    wastage();
                    profit();
                    gap();
                    })();
                    </script>
</body>

</html>
