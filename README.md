# California-regional-elite-online-bank
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>California Regional Bank | Elite Digital Banking</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-blue: #002b5c;
            --primary-light-blue: #004080;
            --secondary-gold: #c9a96e;
            --accent-green: #00a86b;
            --crypto-purple: #8a2be2;
            --dark-bg: #0f1a2e;
            --dark-card: #1a2538;
            --light-gray: #f8f9fa;
            --medium-gray: #6c757d;
            --dark-gray: #212529;
            --white: #ffffff;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
            --info: #17a2b8;
            --shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
            --shadow-hover: 0 20px 60px rgba(0, 0, 0, 0.15);
            --radius: 16px;
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Roboto', sans-serif;
            background-color: #f5f7fa;
            color: var(--dark-gray);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        body.dark-mode {
            background-color: var(--dark-bg);
            color: var(--white);
        }
        
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Loading Screen */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--primary-blue), var(--dark-bg));
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.8s ease;
        }
        
        .loading-screen.hidden {
            opacity: 0;
            pointer-events: none;
        }
        
        .loader {
            width: 80px;
            height: 80px;
            border: 4px solid rgba(255, 255, 255, 0.2);
            border-top: 4px solid var(--secondary-gold);
            border-radius: 50%;
            animation: spin 1.5s linear infinite;
            margin-bottom: 30px;
        }
        
        .loading-text {
            color: white;
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 15px;
            text-align: center;
            font-family: 'Poppins', sans-serif;
        }
        
        .loading-subtext {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
            text-align: center;
            max-width: 500px;
            line-height: 1.6;
        }
        
        .loading-security {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 30px;
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Landing Page */
        .landing-page {
            font-family: 'Poppins', sans-serif;
        }
        
        .landing-header {
            background: linear-gradient(rgba(0, 43, 92, 0.95), rgba(0, 43, 92, 0.95)), url('https://images.unsplash.com/photo-1554224155-6726b3ff858f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 100px 0 80px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .landing-header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1616514197671-15d99ce7a6f8?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            opacity: 0.1;
            z-index: 0;
        }
        
        .landing-header > .container {
            position: relative;
            z-index: 1;
        }
        
        .landing-logo {
            position: absolute;
            top: 30px;
            left: 50px;
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 1.8rem;
            font-weight: 800;
            color: white;
            text-decoration: none;
            z-index: 2;
        }
        
        .landing-logo-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--secondary-gold), #ffd700);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
        }
        
        .landing-header h1 {
            font-size: 3.8rem;
            margin-bottom: 25px;
            font-weight: 800;
            line-height: 1.2;
            color: white;
        }
        
        .landing-header h1 span {
            background: linear-gradient(135deg, var(--secondary-gold), #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .landing-header p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto 40px;
            line-height: 1.8;
            opacity: 0.9;
            color: rgba(255, 255, 255, 0.9);
        }
        
        .landing-cta {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 30px;
            flex-wrap: wrap;
        }
        
        .btn {
            padding: 18px 36px;
            border: none;
            border-radius: var(--radius);
            font-weight: 600;
            font-size: 1rem;
            cursor: pointer;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 10px;
            text-decoration: none;
            font-family: 'Poppins', sans-serif;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--secondary-gold), #d4af37);
            color: var(--primary-blue);
            font-weight: 700;
        }
        
        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(201, 169, 110, 0.3);
        }
        
        .btn-secondary {
            background-color: transparent;
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }
        
        .btn-secondary:hover {
            background-color: rgba(255, 255, 255, 0.1);
            transform: translateY(-5px);
        }
        
        .stats-container {
            display: flex;
            justify-content: center;
            gap: 50px;
            margin-top: 60px;
            flex-wrap: wrap;
        }
        
        .stat-item {
            text-align: center;
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--secondary-gold);
            margin-bottom: 5px;
        }
        
        .stat-label {
            font-size: 1rem;
            opacity: 0.8;
            color: rgba(255, 255, 255, 0.9);
        }
        
        /* Login Page */
        .login-page {
            min-height: 100vh;
            background: linear-gradient(rgba(0, 43, 92, 0.9), rgba(0, 43, 92, 0.9)), url('https://images.unsplash.com/photo-1616514197671-15d99ce7a6f8?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 30px;
        }
        
        .login-container {
            background-color: white;
            border-radius: var(--radius);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.3);
            width: 100%;
            max-width: 480px;
            padding: 50px 40px;
            animation: fadeIn 0.8s ease;
            position: relative;
            overflow: hidden;
        }
        
        body.dark-mode .login-container {
            background-color: var(--dark-card);
        }
        
        .login-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(135deg, var(--secondary-gold), #d4af37);
        }
        
        .login-header {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .login-logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .login-logo-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary-blue), var(--primary-light-blue));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.8rem;
        }
        
        .login-header h2 {
            color: var(--primary-blue);
            font-size: 2.2rem;
            margin-bottom: 10px;
        }
        
        body.dark-mode .login-header h2 {
            color: var(--white);
        }
        
        .login-header p {
            color: var(--medium-gray);
        }
        
        .login-step {
            display: none;
        }
        
        .login-step.active {
            display: block;
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 10px;
            font-weight: 500;
            color: var(--dark-gray);
            font-size: 0.95rem;
        }
        
        body.dark-mode .form-group label {
            color: var(--white);
        }
        
        .form-control {
            width: 100%;
            padding: 16px 20px;
            border: 1px solid #e0e0e0;
            border-radius: var(--radius);
            font-size: 1rem;
            transition: var(--transition);
            background-color: white;
            color: var(--dark-gray);
        }
        
        body.dark-mode .form-control {
            background-color: rgba(255, 255, 255, 0.05);
            border-color: rgba(255, 255, 255, 0.1);
            color: var(--white);
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--primary-blue);
            box-shadow: 0 0 0 3px rgba(0, 43, 92, 0.1);
        }
        
        .password-field {
            position: relative;
        }
        
        .toggle-password {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            color: var(--medium-gray);
            cursor: pointer;
            font-size: 1.2rem;
        }
        
        .login-btn {
            width: 100%;
            padding: 18px;
            font-size: 1.1rem;
            font-weight: 600;
            margin-top: 10px;
        }
        
        .otp-container-8 {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin: 30px 0;
        }
        
        .otp-input-8 {
            width: 50px;
            height: 60px;
            text-align: center;
            font-size: 1.8rem;
            font-weight: 600;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            transition: var(--transition);
            background-color: white;
            color: var(--dark-gray);
        }
        
        body.dark-mode .otp-input-8 {
            background-color: rgba(255, 255, 255, 0.05);
            border-color: rgba(255, 255, 255, 0.1);
            color: var(--white);
        }
        
        .otp-input-8:focus {
            border-color: var(--primary-blue);
            box-shadow: 0 0 0 3px rgba(0, 43, 92, 0.1);
            outline: none;
        }
        
        .login-footer {
            text-align: center;
            margin-top: 30px;
            color: var(--medium-gray);
            font-size: 0.9rem;
        }
        
        .login-footer a {
            color: var(--primary-blue);
            text-decoration: none;
            font-weight: 500;
        }
        
        .remember-me {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 25px;
        }
        
        .remember-me input[type="checkbox"] {
            width: 18px;
            height: 18px;
            accent-color: var(--primary-blue);
        }
        
        /* Banking Platform Header */
        .banking-header {
            background-color: var(--primary-blue);
            color: white;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
        }
        
        .bank-logo {
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 1.6rem;
            font-weight: 700;
            color: white;
            text-decoration: none;
        }
        
        .bank-logo-icon {
            width: 45px;
            height: 45px;
            background: linear-gradient(135deg, var(--secondary-gold), #ffd700);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }
        
        .nav-menu {
            display: flex;
            list-style: none;
            gap: 25px;
        }
        
        .nav-menu a {
            color: rgba(255, 255, 255, 0.9);
            text-decoration: none;
            font-weight: 500;
            padding: 12px 20px;
            border-radius: var(--radius);
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .nav-menu a:hover, .nav-menu a.active {
            background-color: rgba(255, 255, 255, 0.15);
            color: white;
        }
        
        .user-menu {
            display: flex;
            align-items: center;
            gap: 20px;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            gap: 12px;
            background-color: rgba(255, 255, 255, 0.1);
            padding: 10px 20px;
            border-radius: 50px;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .user-info:hover {
            background-color: rgba(255, 255, 255, 0.15);
        }
        
        .user-avatar {
            width: 42px;
            height: 42px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--secondary-gold), var(--primary-blue));
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 1.1rem;
        }
        
        .logout-btn {
            background-color: rgba(255, 255, 255, 0.1);
            border: none;
            color: white;
            padding: 12px 24px;
            border-radius: var(--radius);
            cursor: pointer;
            font-weight: 500;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .logout-btn:hover {
            background-color: rgba(255, 255, 255, 0.2);
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Main Content */
        .banking-main {
            padding: 50px 0;
            min-height: calc(100vh - 120px);
        }
        
        .page {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        .page.active {
            display: block;
        }
        
        /* Dashboard */
        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 40px;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .welcome-section h1 {
            font-size: 2.4rem;
            margin-bottom: 10px;
            color: var(--primary-blue);
        }
        
        body.dark-mode .welcome-section h1 {
            color: var(--white);
        }
        
        .welcome-section p {
            color: var(--medium-gray);
            font-size: 1.1rem;
        }
        
        .account-status {
            background: linear-gradient(135deg, var(--accent-green), #00c853);
            color: white;
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 5px 15px rgba(0, 168, 107, 0.2);
        }
        
        /* Accounts Grid */
        .accounts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }
        
        .account-card {
            background-color: white;
            border-radius: var(--radius);
            padding: 35px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border-top: 5px solid var(--primary-blue);
            position: relative;
            overflow: hidden;
        }
        
        body.dark-mode .account-card {
            background-color: var(--dark-card);
        }
        
        .account-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
        }
        
        .account-card.gold {
            border-top-color: var(--secondary-gold);
        }
        
        .account-card.platinum {
            border-top-color: #8a8a8a;
        }
        
        .account-card.premium {
            border-top-color: var(--accent-green);
        }
        
        .account-type {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 25px;
        }
        
        .account-type h3 {
            color: var(--medium-gray);
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .account-balance {
            font-size: 2.8rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 15px;
            line-height: 1.2;
        }
        
        body.dark-mode .account-balance {
            color: var(--white);
        }
        
        .account-number {
            color: var(--medium-gray);
            font-size: 0.95rem;
            margin-bottom: 30px;
            font-family: 'Roboto Mono', monospace;
        }
        
        .account-actions {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }
        
        .btn-sm {
            padding: 12px 24px;
            font-size: 0.95rem;
            border-radius: 10px;
        }
        
        /* Quick Actions */
        .quick-actions {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 25px;
            margin-bottom: 60px;
        }
        
        .quick-action-btn {
            background-color: white;
            border-radius: var(--radius);
            padding: 35px 20px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: var(--shadow);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
            border: 1px solid rgba(0, 0, 0, 0.05);
        }
        
        body.dark-mode .quick-action-btn {
            background-color: var(--dark-card);
        }
        
        .quick-action-btn:hover {
            transform: translateY(-10px);
            background-color: var(--primary-blue);
            color: white;
            box-shadow: var(--shadow-hover);
        }
        
        .quick-action-btn:hover i {
            color: white;
        }
        
        .quick-action-btn i {
            font-size: 2.8rem;
            color: var(--primary-blue);
            transition: var(--transition);
        }
        
        .quick-action-btn span {
            font-weight: 600;
            font-size: 1.1rem;
        }
        
        /* Recent Transactions */
        .recent-transactions {
            background-color: white;
            border-radius: var(--radius);
            padding: 40px;
            box-shadow: var(--shadow);
        }
        
        body.dark-mode .recent-transactions {
            background-color: var(--dark-card);
        }
        
        .transactions-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }
        
        .transaction-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 25px 0;
            border-bottom: 1px solid #e0e0e0;
            cursor: pointer;
            transition: var(--transition);
        }
        
        body.dark-mode .transaction-item {
            border-bottom-color: rgba(255, 255, 255, 0.1);
        }
        
        .transaction-item:last-child {
            border-bottom: none;
        }
        
        .transaction-item:hover {
            background-color: rgba(0, 0, 0, 0.02);
            padding-left: 15px;
            padding-right: 15px;
            margin: 0 -15px;
            border-radius: 10px;
        }
        
        body.dark-mode .transaction-item:hover {
            background-color: rgba(255, 255, 255, 0.05);
        }
        
        .transaction-info h4 {
            margin-bottom: 8px;
            font-size: 1.1rem;
        }
        
        .transaction-date {
            color: var(--medium-gray);
            font-size: 0.95rem;
        }
        
        .transaction-amount {
            font-weight: 700;
            font-size: 1.3rem;
        }
        
        .transaction-amount.positive {
            color: var(--accent-green);
        }
        
        .transaction-amount.negative {
            color: var(--danger);
        }
        
        .transaction-status {
            font-size: 0.8rem;
            padding: 6px 15px;
            border-radius: 50px;
            font-weight: 600;
            margin-top: 10px;
            display: inline-block;
        }
        
        .status-completed {
            background-color: rgba(40, 167, 69, 0.1);
            color: var(--accent-green);
        }
        
        .status-pending {
            background-color: rgba(255, 193, 7, 0.1);
            color: var(--warning);
        }
        
        .status-processing {
            background-color: rgba(23, 162, 184, 0.1);
            color: var(--info);
        }
        
        /* Financial Health Score */
        .financial-health {
            background: linear-gradient(135deg, var(--primary-blue), var(--primary-light-blue));
            color: white;
            border-radius: var(--radius);
            padding: 40px;
            margin-bottom: 50px;
            display: flex;
            align-items: center;
            gap: 40px;
            box-shadow: var(--shadow);
        }
        
        /* Crypto Portfolio */
        .crypto-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin: 40px 0;
        }
        
        .crypto-card {
            background-color: white;
            border-radius: var(--radius);
            padding: 30px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border-left: 4px solid var(--crypto-purple);
        }
        
        body.dark-mode .crypto-card {
            background-color: var(--dark-card);
        }
        
        .crypto-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
        }
        
        .crypto-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .crypto-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--crypto-purple), #6a0dad);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: white;
        }
        
        .crypto-price {
            font-size: 1.8rem;
            font-weight: 700;
            margin: 15px 0;
            color: var(--primary-blue);
        }
        
        body.dark-mode .crypto-price {
            color: var(--white);
        }
        
        /* Fund Account Section */
        .fund-account-section {
            background-color: white;
            border-radius: var(--radius);
            padding: 40px;
            box-shadow: var(--shadow);
            margin: 40px 0;
        }
        
        body.dark-mode .fund-account-section {
            background-color: var(--dark-card);
        }
        
        /* Settings */
        .settings-container {
            display: grid;
            grid-template-columns: 280px 1fr;
            gap: 40px;
            margin-top: 40px;
        }
        
        .settings-sidebar {
            background-color: white;
            border-radius: var(--radius);
            padding: 20px 0;
            box-shadow: var(--shadow);
        }
        
        body.dark-mode .settings-sidebar {
            background-color: var(--dark-card);
        }
        
        .settings-menu-item {
            padding: 20px 30px;
            cursor: pointer;
            transition: var(--transition);
            border-left: 4px solid transparent;
            display: flex;
            align-items: center;
            gap: 15px;
            font-weight: 500;
        }
        
        .settings-menu-item:hover, .settings-menu-item.active {
            background-color: rgba(0, 43, 92, 0.05);
            border-left-color: var(--primary-blue);
        }
        
        body.dark-mode .settings-menu-item:hover, 
        body.dark-mode .settings-menu-item.active {
            background-color: rgba(0, 43, 92, 0.3);
        }
        
        .settings-content {
            background-color: white;
            border-radius: var(--radius);
            padding: 40px;
            box-shadow: var(--shadow);
        }
        
        body.dark-mode .settings-content {
            background-color: var(--dark-card);
        }
        
        .settings-section {
            display: none;
        }
        
        .settings-section.active {
            display: block;
        }
        
        .settings-item {
            padding: 25px 0;
            border-bottom: 1px solid #e0e0e0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        body.dark-mode .settings-item {
            border-bottom-color: rgba(255, 255, 255, 0.1);
        }
        
        .settings-item:last-child {
            border-bottom: none;
        }
        
        /* Form Row */
        .form-row {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }
        
        /* Alert */
        .alert {
            padding: 20px 25px;
            border-radius: var(--radius);
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .alert-success {
            background-color: rgba(0, 168, 107, 0.1);
            color: var(--accent-green);
            border-left: 4px solid var(--accent-green);
        }
        
        .alert-warning {
            background-color: rgba(255, 193, 7, 0.1);
            color: var(--warning);
            border-left: 4px solid var(--warning);
        }
        
        .alert-danger {
            background-color: rgba(220, 53, 69, 0.1);
            color: var(--danger);
            border-left: 4px solid var(--danger);
        }
        
        .alert-info {
            background-color: rgba(23, 162, 184, 0.1);
            color: var(--info);
            border-left: 4px solid var(--info);
        }
        
        /* Badge */
        .badge {
            display: inline-block;
            padding: 6px 15px;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 600;
        }
        
        .badge-success {
            background-color: rgba(0, 168, 107, 0.1);
            color: var(--accent-green);
        }
        
        .badge-warning {
            background-color: rgba(255, 193, 7, 0.1);
            color: var(--warning);
        }
        
        .badge-danger {
            background-color: rgba(220, 53, 69, 0.1);
            color: var(--danger);
        }
        
        /* Transfer Options */
        .transfer-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            margin: 40px 0;
        }
        
        .transfer-option {
            background-color: white;
            border-radius: var(--radius);
            padding: 40px 25px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: var(--shadow);
            border: 2px solid transparent;
        }
        
        body.dark-mode .transfer-option {
            background-color: var(--dark-card);
        }
        
        .transfer-option.active, .transfer-option:hover {
            border-color: var(--primary-blue);
            background-color: var(--primary-blue);
            color: white;
            transform: translateY(-10px);
        }
        
        .transfer-option i {
            font-size: 3.2rem;
            margin-bottom: 20px;
            display: block;
        }
        
        /* Modals */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .modal.active {
            display: flex;
            animation: fadeIn 0.3s ease;
        }
        
        .modal-content {
            background-color: white;
            border-radius: var(--radius);
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.3);
            width: 100%;
            max-width: 600px;
            max-height: 90vh;
            overflow-y: auto;
        }
        
        body.dark-mode .modal-content {
            background-color: var(--dark-card);
        }
        
        .modal-header {
            padding: 30px 35px;
            border-bottom: 1px solid #e0e0e0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        body.dark-mode .modal-header {
            border-bottom-color: rgba(255, 255, 255, 0.1);
        }
        
        .modal-body {
            padding: 35px;
        }
        
        .modal-close {
            background: none;
            border: none;
            font-size: 2rem;
            cursor: pointer;
            color: var(--medium-gray);
            transition: var(--transition);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .modal-close:hover {
            background-color: rgba(0, 0, 0, 0.05);
        }
        
        /* Login History Table */
        .login-history-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        
        .login-history-table th,
        .login-history-table td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid #e0e0e0;
        }
        
        body.dark-mode .login-history-table th,
        body.dark-mode .login-history-table td {
            border-bottom-color: rgba(255, 255, 255, 0.1);
        }
        
        .login-history-table th {
            background-color: rgba(0, 0, 0, 0.02);
            font-weight: 600;
            color: var(--primary-blue);
        }
        
        body.dark-mode .login-history-table th {
            background-color: rgba(255, 255, 255, 0.05);
            color: var(--white);
        }
        
        /* Funded Accounts */
        .funded-accounts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .funded-account-card {
            background-color: rgba(0, 0, 0, 0.03);
            border-radius: var(--radius);
            padding: 25px;
            transition: var(--transition);
        }
        
        body.dark-mode .funded-account-card {
            background-color: rgba(255, 255, 255, 0.05);
        }
        
        /* User Login Button */
        #user-login-btn {
            background: linear-gradient(135deg, var(--crypto-purple), #6a0dad);
            color: white;
            padding: 12px 25px;
            border-radius: var(--radius);
            text-decoration: none;
            display: inline-block;
            margin-top: 15px;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }
        
        #user-login-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(138, 43, 226, 0.2);
        }
        
        /* User Dashboard Specific Styles */
        #user-dashboard .account-card {
            cursor: default;
        }
        
        #user-dashboard .account-card:hover {
            transform: none;
        }
        
        #user-dashboard .transaction-item {
            cursor: pointer;
        }
        
        #user-dashboard .transaction-item:hover {
            background-color: rgba(0, 0, 0, 0.02);
            padding-left: 15px;
            padding-right: 15px;
            margin: 0 -15px;
            border-radius: 10px;
        }
        
        /* Logout Section */
        .logout-section {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            z-index: 3000;
            justify-content: center;
            align-items: center;
        }
        
        .logout-section.active {
            display: flex;
            animation: fadeIn 0.3s ease;
        }
        
        .logout-container {
            background: linear-gradient(135deg, var(--primary-blue), var(--dark-bg));
            border-radius: var(--radius);
            padding: 50px 40px;
            text-align: center;
            max-width: 500px;
            width: 90%;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.5);
        }
        
        .logout-icon {
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, var(--secondary-gold), #ffd700);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            margin: 0 auto 30px;
            color: var(--primary-blue);
        }
        
        .logout-message {
            color: white;
            font-size: 1.8rem;
            margin-bottom: 20px;
            font-weight: 700;
        }
        
        .logout-submessage {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
            margin-bottom: 40px;
            line-height: 1.6;
        }
        
        .logout-actions {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .logout-btn-confirm {
            background: linear-gradient(135deg, var(--accent-green), #00c853);
            color: white;
            padding: 16px 36px;
            border: none;
            border-radius: var(--radius);
            font-weight: 600;
            font-size: 1.1rem;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .logout-btn-confirm:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 168, 107, 0.3);
        }
        
        .logout-btn-cancel {
            background-color: rgba(255, 255, 255, 0.1);
            color: white;
            padding: 16px 36px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: var(--radius);
            font-weight: 600;
            font-size: 1.1rem;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .logout-btn-cancel:hover {
            background-color: rgba(255, 255, 255, 0.15);
            transform: translateY(-5px);
        }
        
        /* Toggle Switch */
        .toggle-switch {
            position: relative;
            display: inline-block;
            width: 60px;
            height: 30px;
        }
        
        .toggle-switch input {
            opacity: 0;
            width: 0;
            height: 0;
        }
        
        .toggle-slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 34px;
        }
        
        .toggle-slider:before {
            position: absolute;
            content: "";
            height: 22px;
            width: 22px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }
        
        input:checked + .toggle-slider {
            background-color: var(--accent-green);
        }
        
        input:checked + .toggle-slider:before {
            transform: translateX(30px);
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Utility Classes */
        .hidden { display: none !important; }
        .text-center { text-align: center; }
        .text-right { text-align: right; }
        .text-left { text-align: left; }
        .mb-20 { margin-bottom: 20px; }
        .mb-30 { margin-bottom: 30px; }
        .mb-40 { margin-bottom: 40px; }
        .mt-20 { margin-top: 20px; }
        .mt-30 { margin-top: 30px; }
        .mt-40 { margin-top: 40px; }
        
        /* Responsive */
        @media (max-width: 992px) {
            .nav-menu {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background-color: var(--primary-blue);
                flex-direction: column;
                padding: 20px;
                box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            }
            
            .nav-menu.active {
                display: flex;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .settings-container {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 768px) {
            .dashboard-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .accounts-grid, .quick-actions, .transfer-options, .crypto-grid {
                grid-template-columns: 1fr;
            }
            
            .form-row {
                grid-template-columns: 1fr;
            }
            
            .financial-health {
                flex-direction: column;
                text-align: center;
                gap: 30px;
            }
            
            .otp-container-8 {
                gap: 8px;
            }
            
            .otp-input-8 {
                width: 40px;
                height: 50px;
                font-size: 1.5rem;
            }
            
            .logout-actions {
                flex-direction: column;
            }
            
            .logout-btn-confirm,
            .logout-btn-cancel {
                width: 100%;
            }
        }
        
        @media (max-width: 576px) {
            .landing-header {
                padding: 80px 0 60px;
            }
            
            .landing-header h1 {
                font-size: 2.4rem;
            }
            
            .landing-logo {
                left: 20px;
                font-size: 1.5rem;
            }
            
            .otp-input-8 {
                width: 35px;
                height: 45px;
                font-size: 1.3rem;
            }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div id="loading-screen" class="loading-screen">
        <div class="loader"></div>
        <div class="loading-text">California Regional Bank</div>
        <div class="loading-subtext">Initializing Elite Quantum Banking Platform...</div>
        <div class="loading-security">
            <i class="fas fa-shield-alt"></i>
            <span>Quantum Security Protocols Activated</span>
        </div>
    </div>

    <!-- Login Page -->
    <div id="login-page" class="login-page">
        <div class="login-container">
            <div class="login-header">
                <div class="login-logo">
                    <div class="login-logo-icon">
                        <i class="fas fa-university"></i>
                    </div>
                    <div>
                        <h2>California Regional Bank</h2>
                        <p>Quantum Authentication Required</p>
                    </div>
                </div>
            </div>
            
            <div id="login-step-1" class="login-step active">
                <form id="login-form">
                    <div class="form-group">
                        <label for="username">Quantum ID / Email</label>
                        <input type="text" id="username" class="form-control" placeholder="Enter your Quantum ID or email" required>
                    </div>
                    <div class="form-group">
                        <label for="password">Encryption Key</label>
                        <div class="password-field">
                            <input type="password" id="password" class="form-control" placeholder="Enter your encryption key" required>
                            <button type="button" class="toggle-password" id="toggle-password">
                                <i class="fas fa-eye"></i>
                            </button>
                        </div>
                    </div>
                    <div class="remember-me">
                        <input type="checkbox" id="remember-me">
                        <label for="remember-me">Remember this device</label>
                    </div>
                    <button type="submit" class="btn btn-primary login-btn">
                        <i class="fas fa-fingerprint"></i> Quantum Authentication
                    </button>
                </form>
                <div class="login-footer">
                    <p>You'll receive an 8-digit quantum token via secure channel for verification.</p>
                    <p><a href="#" id="forgot-password">Forgot Encryption Key?</a></p>
                    <p><a href="#" id="create-new-account-link">Create New Premium Account</a></p>
                    <p><button id="user-login-btn">Access Your Funded Account</button></p>
                </div>
            </div>
            
            <div id="login-step-2" class="login-step">
                <div class="login-header">
                    <h3>8-Digit Quantum Token Verification</h3>
                    <p>Enter the 8-digit quantum token sent to your secure email</p>
                </div>
                <div class="otp-container-8">
                    <input type="text" maxlength="1" class="otp-input-8" id="otp1">
                    <input type="text" maxlength="1" class="otp-input-8" id="otp2">
                    <input type="text" maxlength="1" class="otp-input-8" id="otp3">
                    <input type="text" maxlength="1" class="otp-input-8" id="otp4">
                    <input type="text" maxlength="1" class="otp-input-8" id="otp5">
                    <input type="text" maxlength="1" class="otp-input-8" id="otp6">
                    <input type="text" maxlength="1" class="otp-input-8" id="otp7">
                    <input type="text" maxlength="1" class="otp-input-8" id="otp8">
                </div>
                <div style="text-align: center; margin: 25px 0;">
                    <button id="resend-otp" class="btn btn-secondary" style="padding: 10px 20px;">
                        <i class="fas fa-redo"></i> Resend Token
                    </button>
                </div>
                <button id="verify-otp-btn" class="btn btn-primary login-btn">
                    <i class="fas fa-check-circle"></i> Verify Quantum Token
                </button>
                <div class="login-footer">
                    <p>Token sent to your registered secure email address.</p>
                    <button id="back-to-login" class="btn btn-secondary" style="padding: 12px 24px; margin-top: 20px; width: 100%;">
                        <i class="fas fa-arrow-left"></i> Back to Login
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Banking Platform -->
    <div id="banking-platform" style="display: none;">
        <header class="banking-header">
            <div class="header-container">
                <div class="bank-logo">
                    <div class="bank-logo-icon">
                        <i class="fas fa-university"></i>
                    </div>
                    <span>CRB Quantum Banking</span>
                </div>
                
                <button class="mobile-menu-btn" id="mobile-menu-btn">
                    <i class="fas fa-bars"></i>
                </button>
                
                <nav>
                    <ul class="nav-menu" id="nav-menu">
                        <li><a href="#" data-page="dashboard" class="active"><i class="fas fa-home"></i> Dashboard</a></li>
                        <li><a href="#" data-page="transfer"><i class="fas fa-exchange-alt"></i> Transfer</a></li>
                        <li><a href="#" data-page="crypto"><i class="fas fa-coins"></i> Crypto</a></li>
                        <li><a href="#" data-page="fund-accounts"><i class="fas fa-hand-holding-usd"></i> Fund Accounts</a></li>
                        <li><a href="#" data-page="settings"><i class="fas fa-cog"></i> Settings</a></li>
                    </ul>
                </nav>
                
                <div class="user-menu">
                    <div class="user-info" id="user-dropdown-btn">
                        <div class="user-avatar" id="user-avatar">AD</div>
                        <span id="user-name-display">Albert Dawson</span>
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    
                    <button id="logout-btn" class="logout-btn">
                        <i class="fas fa-sign-out-alt"></i> Logout
                    </button>
                </div>
            </div>
        </header>
        
        <main class="banking-main">
            <div class="container">
                <!-- Dashboard -->
                <div id="dashboard-page" class="page active">
                    <div class="dashboard-header">
                        <div class="welcome-section">
                            <h1 id="welcome-message">Welcome back, Albert</h1>
                            <p>Your AI-powered financial dashboard for <span id="current-date">November 30, 2025</span></p>
                            <div class="account-status mt-20">
                                <i class="fas fa-shield-alt"></i>
                                <span>Quantum Secure • All Systems Operational</span>
                            </div>
                        </div>
                        <div class="account-status" style="background: linear-gradient(135deg, var(--accent-green), #00c853);">
                            <i class="fas fa-check-circle"></i>
                            <span id="account-status-display">Account Active • Elite Tier</span>
                        </div>
                    </div>
                    
                    <!-- Accounts Grid -->
                    <div class="accounts-grid">
                        <div class="account-card">
                            <div class="account-type">
                                <h3><i class="fas fa-university"></i> Quantum Checking</h3>
                            </div>
                            <div class="account-balance">$<span id="checking-balance">32,402,569.25</span></div>
                            <div class="account-number">Quantum ID: Q•••7890 • Limit: $100,000/day</div>
                            <div class="account-actions">
                                <button class="btn btn-primary btn-sm" data-page="transfer">
                                    <i class="fas fa-paper-plane"></i> Transfer
                                </button>
                                <button class="btn btn-secondary btn-sm" id="deposit-check">
                                    <i class="fas fa-download"></i> Deposit
                                </button>
                            </div>
                        </div>
                        
                        <div class="account-card gold">
                            <div class="account-type">
                                <h3><i class="fas fa-piggy-bank"></i> High-Yield Quantum Savings</h3>
                            </div>
                            <div class="account-balance">$<span id="savings-balance">12,500,000.00</span></div>
                            <div class="account-number">APY: 4.25% • Quantum ID: Q•••8910</div>
                            <div class="account-actions">
                                <button class="btn btn-primary btn-sm" data-page="transfer">
                                    <i class="fas fa-plus"></i> Add Funds
                                </button>
                            </div>
                        </div>
                        
                        <div class="account-card platinum">
                            <div class="account-type">
                                <h3><i class="fas fa-chart-network"></i> Crypto Portfolio</h3>
                            </div>
                            <div class="account-balance">$<span id="crypto-balance">187,425.50</span></div>
                            <div class="account-number">BTC: 2.5 • ETH: 15.8 • USDT: 50,000</div>
                            <div class="account-actions">
                                <button class="btn btn-primary btn-sm" data-page="crypto">
                                    <i class="fas fa-coins"></i> View Crypto
                                </button>
                                <button class="btn btn-secondary btn-sm" data-page="crypto">
                                    <i class="fas fa-exchange-alt"></i> Send Crypto
                                </button>
                            </div>
                        </div>
                    </div>
                    
                    <div class="quick-actions">
                        <div class="quick-action-btn" data-page="transfer">
                            <i class="fas fa-bolt"></i>
                            <span>Make Transfer</span>
                        </div>
                        <div class="quick-action-btn" data-page="crypto">
                            <i class="fas fa-coins"></i>
                            <span>Send Crypto</span>
                        </div>
                        <div class="quick-action-btn" data-page="fund-accounts">
                            <i class="fas fa-hand-holding-usd"></i>
                            <span>Fund Accounts</span>
                        </div>
                        <div class="quick-action-btn" data-page="settings">
                            <i class="fas fa-cog"></i>
                            <span>Account Settings</span>
                        </div>
                    </div>
                    
                    <div class="recent-transactions">
                        <div class="transactions-header">
                            <h2>Recent Transactions</h2>
                            <button class="btn btn-primary" id="view-all-transactions">
                                View All
                            </button>
                        </div>
                        <div id="recent-transactions-list">
                            <!-- Recent transactions loaded here -->
                        </div>
                    </div>
                </div>
                
                <!-- Transfer Page -->
                <div id="transfer-page" class="page">
                    <h1>Quantum Transfer Center</h1>
                    <p>Secure transfers with real-time exchange rates and blockchain verification</p>
                    
                    <div class="transfer-options">
                        <div class="transfer-option active" data-type="domestic">
                            <i class="fas fa-university"></i>
                            <h3>US Domestic Transfer</h3>
                            <p>Transfer between US banks instantly</p>
                        </div>
                        <div class="transfer-option" data-type="international">
                            <i class="fas fa-globe-americas"></i>
                            <h3>International Wire</h3>
                            <p>Send funds globally with competitive rates</p>
                        </div>
                        <div class="transfer-option" data-type="zelle">
                            <i class="fas fa-money-bill-wave"></i>
                            <h3>Zelle® Pay</h3>
                            <p>Send money to anyone with email or phone</p>
                        </div>
                    </div>
                    
                    <div id="domestic-transfer-form" class="fund-account-section">
                        <h3>US Domestic Transfer</h3>
                        <div class="form-row">
                            <div class="form-group">
                                <label>From Account</label>
                                <select class="form-control" id="from-account-domestic">
                                    <option value="checking">Quantum Checking - $32,402,569.25</option>
                                    <option value="savings">High-Yield Savings - $12,500,000.00</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label>To Bank</label>
                                <select class="form-control" id="to-bank-domestic">
                                    <option>Bank of America</option>
                                    <option>Chase Bank</option>
                                    <option>Wells Fargo</option>
                                    <option>Citibank</option>
                                    <option>Capital One</option>
                                </select>
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-group">
                                <label>Recipient Account Number</label>
                                <input type="text" class="form-control" id="recipient-account-domestic" placeholder="Enter account number">
                            </div>
                            <div class="form-group">
                                <label>Routing Number</label>
                                <input type="text" class="form-control" id="routing-number-domestic" placeholder="Enter routing number">
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-group">
                                <label>Amount ($)</label>
                                <input type="number" class="form-control" id="amount-domestic" placeholder="0.00" min="1">
                            </div>
                            <div class="form-group">
                                <label>Description</label>
                                <input type="text" class="form-control" id="description-domestic" placeholder="Payment for services">
                            </div>
                        </div>
                        <button class="btn btn-primary" id="send-domestic-transfer">
                            <i class="fas fa-paper-plane"></i> Send Transfer
                        </button>
                    </div>
                    
                    <div id="international-transfer-form" class="fund-account-section hidden">
                        <h3>International Wire Transfer</h3>
                        <div class="form-row">
                            <div class="form-group">
                                <label>From Account</label>
                                <select class="form-control" id="from-account-international">
                                    <option value="checking">Quantum Checking - $32,402,569.25</option>
                                    <option value="savings">High-Yield Savings - $12,500,000.00</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label>Currency</label>
                                <select class="form-control" id="currency-international">
                                    <option value="USD">US Dollar</option>
                                    <option value="EUR">Euro</option>
                                    <option value="GBP">British Pound</option>
                                    <option value="JPY">Japanese Yen</option>
                                    <option value="CAD">Canadian Dollar</option>
                                </select>
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-group">
                                <label>Amount</label>
                                <input type="number" class="form-control" id="amount-international" placeholder="0.00" min="1">
                            </div>
                            <div class="form-group">
                                <label>Converted Amount (USD)</label>
                                <input type="text" class="form-control" id="converted-amount-international" readonly>
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-group">
                                <label>Recipient Name</label>
                                <input type="text" class="form-control" id="recipient-name-international" placeholder="Full name">
                            </div>
                            <div class="form-group">
                                <label>SWIFT/BIC Code</label>
                                <input type="text" class="form-control" id="swift-code-international" placeholder="SWIFT/BIC code">
                            </div>
                        </div>
                        <button class="btn btn-primary" id="send-international-transfer">
                            <i class="fas fa-globe"></i> Send International Wire
                        </button>
                    </div>
                    
                    <div id="zelle-transfer-form" class="fund-account-section hidden">
                        <h3>Zelle® Payment</h3>
                        <div class="form-row">
                            <div class="form-group">
                                <label>From Account</label>
                                <select class="form-control" id="from-account-zelle">
                                    <option value="checking">Quantum Checking - $32,402,569.25</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label>Send To (Email or Phone)</label>
                                <input type="text" class="form-control" id="zelle-recipient" placeholder="Email or mobile number">
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-group">
                                <label>Amount ($)</label>
                                <input type="number" class="form-control" id="amount-zelle" placeholder="0.00" min="1">
                            </div>
                            <div class="form-group">
                                <label>Recipient Name</label>
                                <input type="text" class="form-control" id="zelle-recipient-name" placeholder="Name of recipient">
                            </div>
                        </div>
                        <button class="btn btn-primary" id="send-zelle-transfer">
                            <i class="fas fa-money-bill-wave"></i> Send with Zelle®
                        </button>
                    </div>
                </div>
                
                <!-- Crypto Page -->
                <div id="crypto-page" class="page">
                    <h1>Crypto Portfolio</h1>
                    <p>Manage your cryptocurrency investments with real-time market data</p>
                    
                    <div class="crypto-grid" id="crypto-portfolio">
                        <!-- Crypto portfolio loaded here -->
                    </div>
                    
                    <div class="fund-account-section">
                        <h3>Send Cryptocurrency</h3>
                        <div class="form-row">
                            <div class="form-group">
                                <label>Select Cryptocurrency</label>
                                <select class="form-control" id="send-crypto-coin">
                                    <option value="BTC">Bitcoin (BTC)</option>
                                    <option value="ETH">Ethereum (ETH)</option>
                                    <option value="USDT">Tether (USDT)</option>
                                    <option value="XRP">Ripple (XRP)</option>
                                    <option value="ADA">Cardano (ADA)</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label>Amount</label>
                                <input type="number" class="form-control" id="send-crypto-amount" placeholder="0.00" min="0.0001" step="0.0001">
                            </div>
                        </div>
                        <div class="form-group">
                            <label>Recipient Wallet Address</label>
                            <input type="text" class="form-control" id="crypto-recipient" placeholder="Enter wallet address (e.g., 1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa)">
                        </div>
                        <div class="form-group">
                            <label>Network Fee</label>
                            <select class="form-control" id="crypto-network-fee">
                                <option value="slow">Slow (Lower fee)</option>
                                <option value="normal" selected>Normal</option>
                                <option value="fast">Fast (Higher fee)</option>
                            </select>
                        </div>
                        <div id="crypto-transaction-details" class="mt-30 hidden">
                            <div class="alert alert-info">
                                <h4>Transaction Details</h4>
                                <p>Amount: <span id="crypto-amount-display">0</span> <span id="crypto-symbol-display">BTC</span></p>
                                <p>Network Fee: $<span id="crypto-fee-display">15.00</span></p>
                                <p>Total: $<span id="crypto-total-display">0.00</span></p>
                            </div>
                        </div>
                        <button class="btn btn-primary" id="send-crypto-btn">
                            <i class="fas fa-paper-plane"></i> Send Cryptocurrency
                        </button>
                    </div>
                    
                    <div class="alert alert-info mt-30">
                        <i class="fas fa-info-circle"></i>
                        <span>Cryptocurrency transactions are irreversible. Always verify wallet addresses before sending.</span>
                    </div>
                </div>
                
                <!-- Fund Accounts Page -->
                <div id="fund-accounts-page" class="page">
                    <h1>Fund Premium Accounts</h1>
                    <p>Fund new premium accounts created under your referral code: <strong>CRB-AD-2025</strong></p>
                    
                    <div class="fund-account-section">
                        <h3>Fund New Account</h3>
                        <div class="form-row">
                            <div class="form-group">
                                <label>From Account</label>
                                <select class="form-control" id="fund-from-account">
                                    <option value="checking">Quantum Checking - $32,402,569.25</option>
                                    <option value="savings">High-Yield Savings - $12,500,000.00</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label>New Account Quantum ID</label>
                                <input type="text" class="form-control" id="new-account-id" placeholder="Enter new account Quantum ID">
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-group">
                                <label>Amount ($)</label>
                                <input type="number" class="form-control" id="fund-amount" placeholder="0.00" min="1000">
                            </div>
                            <div class="form-group">
                                <label>Your Referral Code</label>
                                <input type="text" class="form-control" id="referral-code" value="CRB-AD-2025" readonly>
                            </div>
                        </div>
                        <div class="form-group">
                            <label>Account Holder Name</label>
                            <input type="text" class="form-control" id="new-account-name" placeholder="Enter account holder name">
                        </div>
                        <button class="btn btn-primary" id="fund-account-btn">
                            <i class="fas fa-hand-holding-usd"></i> Fund Account
                        </button>
                    </div>
                    
                    <div class="mt-40">
                        <h3>Recently Funded Accounts</h3>
                        <div class="funded-accounts-grid" id="funded-accounts-list">
                            <!-- Funded accounts list loaded here -->
                        </div>
                    </div>
                </div>
                
                <!-- Settings Page -->
                <div id="settings-page" class="page">
                    <h1>Quantum Settings</h1>
                    <p>Advanced security and privacy controls</p>
                    
                    <div class="settings-container">
                        <div class="settings-sidebar">
                            <div class="settings-menu-item active" data-section="profile">
                                <i class="fas fa-user-circle"></i> Quantum Profile
                            </div>
                            <div class="settings-menu-item" data-section="security">
                                <i class="fas fa-shield-alt"></i> Security Center
                            </div>
                            <div class="settings-menu-item" data-section="login-history">
                                <i class="fas fa-history"></i> Login History
                            </div>
                            <div class="settings-menu-item" data-section="referral">
                                <i class="fas fa-users"></i> Referral System
                            </div>
                        </div>
                        
                        <div class="settings-content">
                            <div id="profile-section" class="settings-section active">
                                <h2>Quantum Profile</h2>
                                <form id="profile-form">
                                    <div class="form-row">
                                        <div class="form-group">
                                            <label>Full Name</label>
                                            <input type="text" class="form-control" id="profile-name" value="Albert Dawson">
                                        </div>
                                        <div class="form-group">
                                            <label>Quantum ID</label>
                                            <input type="text" class="form-control" id="profile-quantum-id" value="Q-ALBERT-DAWSON-2025" readonly>
                                        </div>
                                    </div>
                                    <div class="form-row">
                                        <div class="form-group">
                                            <label>Secure Email</label>
                                            <input type="email" class="form-control" id="profile-email" value="albertdawson2020@gmail.com">
                                        </div>
                                        <div class="form-group">
                                            <label>Account Status</label>
                                            <input type="text" class="form-control" id="profile-status" value="Active • Elite Tier" readonly style="background-color: rgba(0, 168, 107, 0.1); color: var(--accent-green);">
                                        </div>
                                    </div>
                                    <div class="form-row">
                                        <div class="form-group">
                                            <label>Referral Code</label>
                                            <input type="text" class="form-control" id="profile-referral" value="CRB-AD-2025" readonly>
                                        </div>
                                        <div class="form-group">
                                            <label>Member Since</label>
                                            <input type="text" class="form-control" id="profile-member-since" value="March 15, 2022" readonly>
                                        </div>
                                    </div>
                                    <button type="submit" class="btn btn-primary">Update Quantum Profile</button>
                                </form>
                            </div>
                            
                            <div id="login-history-section" class="settings-section">
                                <h2>Login History</h2>
                                <p>Recent login activity on your account</p>
                                <div id="login-history-content">
                                    <!-- Login history loaded here -->
                                </div>
                            </div>
                            
                            <div id="referral-section" class="settings-section">
                                <h2>Referral System</h2>
                                <div class="alert alert-info">
                                    <i class="fas fa-info-circle"></i>
                                    <span>Your referral code: <strong>CRB-AD-2025</strong>. Share this code with others to earn rewards.</span>
                                </div>
                                
                                <div class="form-row">
                                    <div class="form-group">
                                        <label>Total Referrals</label>
                                        <input type="text" class="form-control" value="3" readonly>
                                    </div>
                                    <div class="form-group">
                                        <label>Total Commission Earned</label>
                                        <input type="text" class="form-control" value="$15,000" readonly style="background-color: rgba(0, 168, 107, 0.1); color: var(--accent-green);">
                                    </div>
                                </div>
                                
                                <div id="funded-users-list-container">
                                    <!-- Funded users list will be loaded here -->
                                </div>
                                
                                <h3 class="mt-30">How It Works</h3>
                                <ol style="margin-left: 20px; margin-top: 15px;">
                                    <li>Share your referral code: <strong>CRB-AD-2025</strong></li>
                                    <li>New users enter this code when creating their account</li>
                                    <li>You can fund their accounts from the "Fund Accounts" section</li>
                                    <li>Earn 1% commission on all transactions from referred accounts</li>
                                </ol>
                            </div>
                            
                            <div id="security-section" class="settings-section">
                                <h2>Security Center</h2>
                                <div class="settings-item">
                                    <div>
                                        <h4>Two-Factor Authentication</h4>
                                        <p>Add an extra layer of security to your account</p>
                                    </div>
                                    <div class="toggle-switch">
                                        <input type="checkbox" id="2fa-toggle" checked>
                                        <span class="toggle-slider"></span>
                                    </div>
                                </div>
                                <div class="settings-item">
                                    <div>
                                        <h4>Biometric Login</h4>
                                        <p>Use fingerprint or face recognition to log in</p>
                                    </div>
                                    <div class="toggle-switch">
                                        <input type="checkbox" id="biometric-toggle" checked>
                                        <span class="toggle-slider"></span>
                                    </div>
                                </div>
                                <div class="settings-item">
                                    <div>
                                        <h4>Email Notifications</h4>
                                        <p>Receive email alerts for account activity</p>
                                    </div>
                                    <div class="toggle-switch">
                                        <input type="checkbox" id="email-notifications-toggle" checked>
                                        <span class="toggle-slider"></span>
                                    </div>
                                </div>
                                
                                <div style="margin-top: 40px;">
                                    <h3>Security Actions</h3>
                                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; margin-top: 25px;">
                                        <button class="btn btn-secondary" id="change-password-btn">
                                            <i class="fas fa-key"></i> Change Password
                                        </button>
                                        <button class="btn btn-secondary" id="view-login-history-btn">
                                            <i class="fas fa-history"></i> View Login History
                                        </button>
                                        <button class="btn btn-secondary" id="contact-security-btn">
                                            <i class="fas fa-headset"></i> Contact Security
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </main>
    </div>

    <!-- Logout Section -->
    <div id="logout-section" class="logout-section">
        <div class="logout-container">
            <div class="logout-icon">
                <i class="fas fa-sign-out-alt"></i>
            </div>
            <div class="logout-message">Confirm Logout</div>
            <div class="logout-submessage">You are about to log out from your Quantum Banking account. All sensitive data will be securely encrypted.</div>
            <div class="logout-actions">
                <button id="logout-confirm-btn" class="logout-btn-confirm">
                    <i class="fas fa-check"></i> Yes, Logout
                </button>
                <button id="logout-cancel-btn" class="logout-btn-cancel">
                    <i class="fas fa-times"></i> Cancel
                </button>
            </div>
        </div>
    </div>

    <!-- New Account Application Modal -->
    <div id="new-account-modal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Create New Premium Account</h2>
                <button class="modal-close" id="new-account-close">&times;</button>
            </div>
            <div class="modal-body">
                <div class="form-row">
                    <div class="form-group">
                        <label>Full Name</label>
                        <input type="text" class="form-control" id="applicant-name" placeholder="Enter your full name" required>
                    </div>
                    <div class="form-group">
                        <label>Email Address</label>
                        <input type="email" class="form-control" id="applicant-email" placeholder="Enter your email" required>
                    </div>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label>Phone Number</label>
                        <input type="tel" class="form-control" id="applicant-phone" placeholder="Enter your phone number" required>
                    </div>
                    <div class="form-group">
                        <label>Date of Birth</label>
                        <input type="date" class="form-control" id="applicant-dob" required>
                    </div>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label>Initial Deposit ($)</label>
                        <input type="number" class="form-control" id="initial-deposit" value="10000" min="1000" required>
                    </div>
                    <div class="form-group">
                        <label>Referral Code (Optional)</label>
                        <input type="text" class="form-control" id="applicant-referral" placeholder="Enter referral code" value="CRB-AD-2025">
                    </div>
                </div>
                <!-- NEW PASSWORD SECTION -->
                <div class="form-row">
                    <div class="form-group">
                        <label>Create Password</label>
                        <div class="password-field">
                            <input type="password" class="form-control" id="applicant-password" placeholder="Create your password" required>
                            <button type="button" class="toggle-password" id="applicant-toggle-password">
                                <i class="fas fa-eye"></i>
                            </button>
                        </div>
                        <small style="color: var(--medium-gray); font-size: 0.85rem;">Minimum 8 characters with letters and numbers</small>
                    </div>
                    <div class="form-group">
                        <label>Confirm Password</label>
                        <div class="password-field">
                            <input type="password" class="form-control" id="applicant-confirm-password" placeholder="Confirm your password" required>
                            <button type="button" class="toggle-password" id="applicant-toggle-confirm-password">
                                <i class="fas fa-eye"></i>
                            </button>
                        </div>
                    </div>
                </div>
                <div class="alert alert-info">
                    <i class="fas fa-info-circle"></i>
                    <span>Your account will be created instantly. Minimum initial deposit: $1,000</span>
                </div>
                <button class="btn btn-primary" id="submit-application">
                    <i class="fas fa-check"></i> Create Premium Account
                </button>
            </div>
        </div>
    </div>

    <!-- Transfer Confirmation Modal -->
    <div id="transfer-modal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Confirm Transfer</h2>
                <button class="modal-close" id="transfer-close">&times;</button>
            </div>
            <div class="modal-body">
                <div id="transfer-details"></div>
                <div class="form-group mt-30">
                    <label>Enter 8-Digit Security Code</label>
                    <input type="text" class="form-control" id="transfer-security-code" placeholder="Enter 8-digit code" maxlength="8">
                </div>
                <button class="btn btn-primary mt-20" id="confirm-transfer-btn" style="width: 100%;">
                    <i class="fas fa-check"></i> Confirm & Execute Transfer
                </button>
            </div>
        </div>
    </div>

    <!-- JavaScript Implementation -->
    <script>
        const bankApp = {
            // Main user data
            user: {
                name: "Albert Dawson",
                username: "albertdawson2020",
                password: "myonlyworld",
                email: "albertdawson2020@gmail.com",
                otpCode: "12345678",
                isLoggedIn: false,
                quantumId: "Q-ALBERT-DAWSON-2025",
                tier: "Elite Tier",
                referralCode: "CRB-AD-2025"
            },
            
            // Account balances
            accounts: {
                checking: 32402569.25,
                savings: 12500000.00,
                crypto: 187425.50
            },
            
            // Crypto portfolio
            cryptoPortfolio: [
                { id: 1, name: "Bitcoin", symbol: "BTC", amount: 2.5, price: 42000, value: 105000, change: 3.2, icon: "fab fa-bitcoin" },
                { id: 2, name: "Ethereum", symbol: "ETH", amount: 15.8, price: 2250, value: 35550, change: 1.8, icon: "fab fa-ethereum" },
                { id: 3, name: "Tether", symbol: "USDT", amount: 50000, price: 1.00, value: 50000, change: 0.0, icon: "fas fa-coins" },
                { id: 4, name: "Ripple", symbol: "XRP", amount: 25000, price: 0.62, value: 15500, change: -0.5, icon: "fas fa-chart-line" },
                { id: 5, name: "Cardano", symbol: "ADA", amount: 50000, price: 0.45, value: 22500, change: 2.1, icon: "fas fa-coins" }
            ],
            
            // Other users (created accounts)
            otherUsers: [],
            
            // Funded accounts
            fundedAccounts: [
                { id: 1, name: "John Smith", quantumId: "Q-JOHN-SMITH-2025", amount: 10000, date: '2025-11-15', referralCode: 'CRB-AD-2025' },
                { id: 2, name: "Sarah Johnson", quantumId: "Q-SARAH-J-2025", amount: 25000, date: '2025-11-10', referralCode: 'CRB-AD-2025' }
            ],
            
            // Funded users (with their own accounts)
            fundedUsers: [],
            
            // Transactions - UPDATED WITH REQUESTED TRANSACTIONS
            transactions: [
                { id: 1, type: "transfer", description: "Transfer to Vivian Dewberry", amount: 10000, currency: "USD", date: "2025-12-20", status: "completed", time: "10:30 AM" },
                { id: 2, type: "transfer", description: "Transfer to Vivian Dewberry", amount: 1000, currency: "USD", date: "2025-11-23", status: "processing", time: "2:15 PM" },
                { id: 3, type: "transfer", description: "Funded John Smith Account", amount: 10000, currency: "USD", date: "2025-11-15", status: "completed", time: "10:30 AM" },
                { id: 4, type: "transfer", description: "Funded Sarah Johnson Account", amount: 25000, currency: "USD", date: "2025-11-10", status: "completed", time: "2:15 PM" },
                { id: 5, type: "crypto", description: "Bitcoin Purchase", amount: 50000, currency: "USD", date: "2025-11-05", status: "completed", time: "9:45 AM" },
                { id: 6, type: "transfer", description: "International Wire - EUR", amount: 50000, currency: "EUR", date: "2025-10-28", status: "processing", time: "3:20 PM" },
                { id: 7, type: "transfer", description: "Zelle to Friend", amount: 500, currency: "USD", date: "2025-10-25", status: "completed", time: "11:10 AM" }
            ],
            
            // Login history
            loginHistory: [],
            
            // Current transfer data
            currentTransfer: null,
            
            // Initialize
            init: function() {
                this.setupEventListeners();
                this.updateDate();
                this.loadSavedData();
                this.initializeLoginHistory();
                this.initializeFundedUsers();
                
                setTimeout(() => {
                    document.getElementById('loading-screen').classList.add('hidden');
                }, 2000);
            },
            
            // Setup event listeners
            setupEventListeners: function() {
                // Login form
                document.getElementById('login-form').addEventListener('submit', (e) => this.handleLogin(e));
                document.getElementById('toggle-password').addEventListener('click', () => this.togglePasswordVisibility());
                document.getElementById('verify-otp-btn').addEventListener('click', () => this.verifyOTP());
                document.getElementById('resend-otp').addEventListener('click', () => this.resendOTP());
                document.getElementById('back-to-login').addEventListener('click', () => this.backToLogin());
                document.getElementById('create-new-account-link').addEventListener('click', (e) => {
                    e.preventDefault();
                    this.showNewAccountModal();
                });
                
                // User login button
                document.getElementById('user-login-btn').addEventListener('click', (e) => {
                    e.preventDefault();
                    this.showUserLoginPage();
                });
                
                // OTP input auto-focus
                const otpInputs = document.querySelectorAll('.otp-input-8');
                otpInputs.forEach((input, index) => {
                    input.addEventListener('input', (e) => {
                        if (e.target.value.length === 1 && index < otpInputs.length - 1) {
                            otpInputs[index + 1].focus();
                        }
                    });
                    
                    input.addEventListener('keydown', (e) => {
                        if (e.key === 'Backspace' && !e.target.value && index > 0) {
                            otpInputs[index - 1].focus();
                        }
                    });
                });
                
                // Navigation
                document.querySelectorAll('.nav-menu a').forEach(link => {
                    link.addEventListener('click', (e) => {
                        e.preventDefault();
                        this.navigateToPage(link.getAttribute('data-page'));
                    });
                });
                
                document.getElementById('mobile-menu-btn').addEventListener('click', () => {
                    document.getElementById('nav-menu').classList.toggle('active');
                });
                
                // Quick actions
                document.querySelectorAll('.quick-action-btn').forEach(btn => {
                    btn.addEventListener('click', () => {
                        const page = btn.getAttribute('data-page');
                        this.navigateToPage(page);
                    });
                });
                
                // Account actions
                document.querySelectorAll('.account-actions button').forEach(btn => {
                    if (btn.getAttribute('data-page')) {
                        btn.addEventListener('click', () => {
                            this.navigateToPage(btn.getAttribute('data-page'));
                        });
                    }
                });
                
                // Transfer options
                document.querySelectorAll('.transfer-option').forEach(option => {
                    option.addEventListener('click', () => {
                        this.selectTransferType(option.getAttribute('data-type'));
                    });
                });
                
                // Transfer buttons
                document.getElementById('send-domestic-transfer').addEventListener('click', () => this.prepareTransfer('domestic'));
                document.getElementById('send-international-transfer').addEventListener('click', () => this.prepareTransfer('international'));
                document.getElementById('send-zelle-transfer').addEventListener('click', () => this.prepareTransfer('zelle'));
                
                // Crypto send
                document.getElementById('send-crypto-btn').addEventListener('click', () => this.sendCrypto());
                document.getElementById('send-crypto-amount').addEventListener('input', () => this.updateCryptoTransactionDetails());
                document.getElementById('send-crypto-coin').addEventListener('change', () => this.updateCryptoTransactionDetails());
                
                // Fund account
                document.getElementById('fund-account-btn').addEventListener('click', () => this.fundAccount());
                
                // Settings
                document.querySelectorAll('.settings-menu-item').forEach(item => {
                    item.addEventListener('click', () => {
                        const section = item.getAttribute('data-section');
                        this.showSettingsSection(section);
                    });
                });
                
                document.getElementById('view-login-history-btn').addEventListener('click', () => {
                    this.navigateToPage('settings');
                    this.showSettingsSection('login-history');
                });
                
                document.getElementById('change-password-btn').addEventListener('click', () => this.changePassword());
                document.getElementById('contact-security-btn').addEventListener('click', () => this.contactSecurity());
                
                // Profile form
                document.getElementById('profile-form').addEventListener('submit', (e) => {
                    e.preventDefault();
                    this.updateProfile();
                });
                
                // New account modal
                document.getElementById('submit-application').addEventListener('click', () => this.createNewAccount());
                document.getElementById('new-account-close').addEventListener('click', () => this.hideModal('new-account-modal'));
                
                // Transfer modal
                document.getElementById('transfer-close').addEventListener('click', () => this.hideModal('transfer-modal'));
                document.getElementById('confirm-transfer-btn').addEventListener('click', () => this.executeTransfer());
                
                // Logout
                document.getElementById('logout-btn').addEventListener('click', () => this.showLogoutConfirmation());
                document.getElementById('logout-confirm-btn').addEventListener('click', () => this.logout());
                document.getElementById('logout-cancel-btn').addEventListener('click', () => this.hideLogoutConfirmation());
                
                // View all transactions
                document.getElementById('view-all-transactions').addEventListener('click', () => {
                    this.navigateToPage('transfer');
                });
                
                // Click event for transaction items
                document.addEventListener('click', (e) => {
                    if (e.target.closest('.transaction-item')) {
                        const transactionItem = e.target.closest('.transaction-item');
                        this.showTransactionDetails(transactionItem);
                    }
                });
            },
            
            // Load saved data
            loadSavedData: function() {
                const savedData = localStorage.getItem('crbBankData');
                if (savedData) {
                    const data = JSON.parse(savedData);
                    if (data.accounts) this.accounts = data.accounts;
                    if (data.otherUsers) this.otherUsers = data.otherUsers;
                    if (data.fundedAccounts) this.fundedAccounts = data.fundedAccounts;
                    if (data.transactions) this.transactions = data.transactions;
                    if (data.user && data.user.isLoggedIn) {
                        this.user.isLoggedIn = data.user.isLoggedIn;
                        this.showBankingPlatform();
                    }
                }
            },
            
            // Initialize funded users
            initializeFundedUsers: function() {
                const savedFundedUsers = localStorage.getItem('crbFundedUsers');
                if (savedFundedUsers) {
                    this.fundedUsers = JSON.parse(savedFundedUsers);
                }
            },
            
            // Save data
            saveData: function() {
                const data = {
                    accounts: this.accounts,
                    otherUsers: this.otherUsers,
                    fundedAccounts: this.fundedAccounts,
                    transactions: this.transactions,
                    user: this.user
                };
                localStorage.setItem('crbBankData', JSON.stringify(data));
            },
            
            // Save funded users
            saveFundedUsers: function() {
                localStorage.setItem('crbFundedUsers', JSON.stringify(this.fundedUsers));
            },
            
            // Update date display
            updateDate: function() {
                const now = new Date();
                const options = { year: 'numeric', month: 'long', day: 'numeric' };
                document.getElementById('current-date').textContent = now.toLocaleDateString('en-US', options);
            },
            
            // Handle login
            handleLogin: function(e) {
                e.preventDefault();
                
                const username = document.getElementById('username').value;
                const password = document.getElementById('password').value;
                
                if ((username === this.user.username || username === this.user.email) && password === this.user.password) {
                    document.getElementById('login-step-1').classList.remove('active');
                    document.getElementById('login-step-2').classList.add('active');
                    
                    const otpCode = this.user.otpCode;
                    const otpInputs = document.querySelectorAll('.otp-input-8');
                    otpInputs.forEach((input, index) => {
                        input.value = otpCode[index] || '';
                    });
                    
                    this.addLoginHistory('Login successful');
                    this.showAlert('Quantum authentication initiated. Please enter the 8-digit token.', 'success');
                } else {
                    this.showAlert('Invalid credentials. Please check your Quantum ID/Email and Encryption Key.', 'error');
                }
            },
            
            // Verify OTP
            verifyOTP: function() {
                const otpInputs = document.querySelectorAll('.otp-input-8');
                let enteredOTP = '';
                otpInputs.forEach(input => {
                    enteredOTP += input.value;
                });
                
                if (enteredOTP.length === 8 && /^\d+$/.test(enteredOTP)) {
                    this.user.isLoggedIn = true;
                    this.saveData();
                    this.showBankingPlatform();
                    this.showAlert('Quantum authentication successful. Welcome to your elite banking dashboard!', 'success');
                } else {
                    this.showAlert('Invalid OTP. Please enter a valid 8-digit code.', 'error');
                }
            },
            
            // Resend OTP
            resendOTP: function() {
                const newOTP = Math.floor(10000000 + Math.random() * 90000000).toString();
                this.user.otpCode = newOTP;
                
                const otpInputs = document.querySelectorAll('.otp-input-8');
                otpInputs.forEach((input, index) => {
                    input.value = newOTP[index] || '';
                });
                
                this.showAlert(`New quantum token (${newOTP}) has been sent to your secure email.`, 'success');
            },
            
            // Back to login
            backToLogin: function() {
                document.getElementById('login-step-2').classList.remove('active');
                document.getElementById('login-step-1').classList.add('active');
            },
            
            // Toggle password visibility
            togglePasswordVisibility: function() {
                const passwordInput = document.getElementById('password');
                const toggleButton = document.getElementById('toggle-password');
                
                if (passwordInput.type === 'password') {
                    passwordInput.type = 'text';
                    toggleButton.innerHTML = '<i class="fas fa-eye-slash"></i>';
                } else {
                    passwordInput.type = 'password';
                    toggleButton.innerHTML = '<i class="fas fa-eye"></i>';
                }
            },
            
            // Show banking platform
            showBankingPlatform: function() {
                document.getElementById('login-page').style.display = 'none';
                document.getElementById('banking-platform').style.display = 'block';
                
                this.updateAccountBalances();
                this.loadRecentTransactions();
            },
            
            // Update account balances
            updateAccountBalances: function() {
                document.getElementById('checking-balance').textContent = this.formatCurrency(this.accounts.checking);
                document.getElementById('savings-balance').textContent = this.formatCurrency(this.accounts.savings);
                document.getElementById('crypto-balance').textContent = this.formatCurrency(this.accounts.crypto);
            },
            
            // Navigate to page
            navigateToPage: function(pageId) {
                document.querySelectorAll('.page').forEach(page => {
                    page.classList.remove('active');
                });
                
                document.querySelectorAll('.nav-menu a').forEach(link => {
                    link.classList.remove('active');
                    if (link.getAttribute('data-page') === pageId) {
                        link.classList.add('active');
                    }
                });
                
                document.getElementById(pageId + '-page').classList.add('active');
                document.getElementById('nav-menu').classList.remove('active');
                
                if (pageId === 'crypto') {
                    this.loadCryptoPortfolio();
                } else if (pageId === 'fund-accounts') {
                    this.loadFundedAccounts();
                } else if (pageId === 'settings') {
                    this.loadLoginHistory();
                    this.loadFundedUsersList();
                }
            },
            
            // Load recent transactions
            loadRecentTransactions: function() {
                const container = document.getElementById('recent-transactions-list');
                if (!container) return;
                
                const recent = this.transactions.slice(0, 5);
                container.innerHTML = '';
                
                recent.forEach(transaction => {
                    const element = document.createElement('div');
                    element.className = 'transaction-item';
                    element.innerHTML = `
                        <div class="transaction-info">
                            <h4>${transaction.description}</h4>
                            <div class="transaction-date">${this.formatDate(transaction.date)} • ${transaction.time}</div>
                            <div class="transaction-status status-${transaction.status}">${transaction.status.toUpperCase()}</div>
                        </div>
                        <div class="transaction-amount ${transaction.type === 'crypto' ? 'positive' : 'negative'}">
                            ${transaction.type === 'crypto' ? '+' : '-'}${transaction.currency} ${this.formatCurrency(transaction.amount)}
                        </div>
                    `;
                    container.appendChild(element);
                });
            },
            
            // Show transaction details
            showTransactionDetails: function(transactionElement) {
                const description = transactionElement.querySelector('.transaction-info h4').textContent;
                const amount = transactionElement.querySelector('.transaction-amount').textContent;
                const date = transactionElement.querySelector('.transaction-date').textContent;
                const status = transactionElement.querySelector('.transaction-status').textContent;
                
                const modalHtml = `
                    <div id="transaction-details-modal" class="modal active">
                        <div class="modal-content">
                            <div class="modal-header">
                                <h2>Transaction Details</h2>
                                <button class="modal-close" id="transaction-details-close">&times;</button>
                            </div>
                            <div class="modal-body">
                                <div style="margin-bottom: 20px;">
                                    <div style="font-size: 1.2rem; font-weight: 600; margin-bottom: 10px;">${description}</div>
                                    <div style="font-size: 2rem; font-weight: 700; color: var(--primary-blue); margin-bottom: 15px;">${amount}</div>
                                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px;">
                                        <div><strong>Date:</strong> ${date.split(' • ')[0]}</div>
                                        <div><strong>Time:</strong> ${date.split(' • ')[1]}</div>
                                        <div><strong>Status:</strong> <span class="badge badge-success">${status}</span></div>
                                        <div><strong>Type:</strong> ${description.includes('Funded') ? 'Account Funding' : 'Transfer'}</div>
                                    </div>
                                </div>
                                
                                <div style="background-color: rgba(0, 0, 0, 0.03); padding: 20px; border-radius: var(--radius);">
                                    <h4>Transaction Information</h4>
                                    <p>This transaction was processed through California Regional Bank's Quantum Network. All transfers are secured with 256-bit encryption and recorded on the blockchain for verification.</p>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
                
                const modalContainer = document.createElement('div');
                modalContainer.innerHTML = modalHtml;
                document.body.appendChild(modalContainer);
                
                document.getElementById('transaction-details-close').addEventListener('click', () => {
                    document.getElementById('transaction-details-modal').remove();
                });
                
                document.getElementById('transaction-details-modal').addEventListener('click', (e) => {
                    if (e.target.id === 'transaction-details-modal') {
                        document.getElementById('transaction-details-modal').remove();
                    }
                });
            },
            
            // Load crypto portfolio
            loadCryptoPortfolio: function() {
                const container = document.getElementById('crypto-portfolio');
                if (!container) return;
                
                container.innerHTML = '';
                
                this.cryptoPortfolio.forEach(crypto => {
                    const element = document.createElement('div');
                    element.className = 'crypto-card';
                    element.innerHTML = `
                        <div class="crypto-header">
                            <div class="crypto-icon">
                                <i class="${crypto.icon}"></i>
                            </div>
                            <div>
                                <h3 style="margin: 0;">${crypto.name}</h3>
                                <div style="font-size: 0.9rem; color: var(--medium-gray);">${crypto.symbol}</div>
                            </div>
                        </div>
                        <div class="crypto-price">$${this.formatCurrency(crypto.value)}</div>
                        <div style="display: flex; justify-content: space-between; margin-bottom: 10px;">
                            <div style="font-size: 0.9rem; color: var(--medium-gray);">Amount</div>
                            <div style="font-weight: 600;">${crypto.amount} ${crypto.symbol}</div>
                        </div>
                        <div style="display: flex; justify-content: space-between;">
                            <div style="font-size: 0.9rem; color: var(--medium-gray);">Price</div>
                            <div style="font-weight: 600;">$${this.formatCurrency(crypto.price)}</div>
                        </div>
                        <div style="display: flex; justify-content: space-between; margin-top: 10px;">
                            <div style="font-size: 0.9rem; color: var(--medium-gray);">24h Change</div>
                            <div style="font-weight: 600; color: ${crypto.change >= 0 ? 'var(--accent-green)' : 'var(--danger)'}">
                                ${crypto.change >= 0 ? '+' : ''}${crypto.change}%
                            </div>
                        </div>
                    `;
                    container.appendChild(element);
                });
            },
            
            // Update crypto transaction details
            updateCryptoTransactionDetails: function() {
                const amount = parseFloat(document.getElementById('send-crypto-amount').value) || 0;
                const coin = document.getElementById('send-crypto-coin').value;
                const crypto = this.cryptoPortfolio.find(c => c.symbol === coin);
                
                if (crypto && amount > 0) {
                    const fee = 15.00;
                    const total = (amount * crypto.price) + fee;
                    
                    document.getElementById('crypto-amount-display').textContent = amount;
                    document.getElementById('crypto-symbol-display').textContent = crypto.symbol;
                    document.getElementById('crypto-fee-display').textContent = this.formatCurrency(fee);
                    document.getElementById('crypto-total-display').textContent = this.formatCurrency(total);
                    document.getElementById('crypto-transaction-details').classList.remove('hidden');
                } else {
                    document.getElementById('crypto-transaction-details').classList.add('hidden');
                }
            },
            
            // Send cryptocurrency
            sendCrypto: function() {
                const coin = document.getElementById('send-crypto-coin').value;
                const amount = parseFloat(document.getElementById('send-crypto-amount').value);
                const recipient = document.getElementById('crypto-recipient').value;
                
                if (!amount || amount <= 0 || !recipient) {
                    this.showAlert('Please fill all required fields', 'error');
                    return;
                }
                
                const crypto = this.cryptoPortfolio.find(c => c.symbol === coin);
                if (!crypto) {
                    this.showAlert('Cryptocurrency not found', 'error');
                    return;
                }
                
                if (amount > crypto.amount) {
                    this.showAlert(`Insufficient ${crypto.symbol} balance`, 'error');
                    return;
                }
                
                // Update crypto balance
                crypto.amount -= amount;
                crypto.value = crypto.amount * crypto.price;
                this.accounts.crypto = this.cryptoPortfolio.reduce((sum, c) => sum + c.value, 0);
                
                // Add transaction
                const transactionId = this.transactions.length + 1;
                const transaction = {
                    id: transactionId,
                    type: 'crypto',
                    description: `Sent ${amount} ${crypto.symbol}`,
                    amount: amount * crypto.price,
                    currency: 'USD',
                    date: new Date().toISOString().split('T')[0],
                    status: 'processing',
                    time: this.getCurrentTime()
                };
                
                this.transactions.unshift(transaction);
                
                // Update UI
                this.updateAccountBalances();
                this.loadCryptoPortfolio();
                this.loadRecentTransactions();
                this.saveData();
                
                this.showAlert(`Successfully sent ${amount} ${crypto.symbol} to ${recipient.substring(0, 10)}...`, 'success');
                
                // Clear form
                document.getElementById('send-crypto-amount').value = '';
                document.getElementById('crypto-recipient').value = '';
                document.getElementById('crypto-transaction-details').classList.add('hidden');
            },
            
            // Select transfer type
            selectTransferType: function(type) {
                document.querySelectorAll('.transfer-option').forEach(option => {
                    option.classList.remove('active');
                    if (option.getAttribute('data-type') === type) {
                        option.classList.add('active');
                    }
                });
                
                document.querySelectorAll('.fund-account-section').forEach(form => {
                    form.classList.add('hidden');
                });
                
                document.getElementById(`${type}-transfer-form`).classList.remove('hidden');
            },
            
            // Prepare transfer
            prepareTransfer: function(type) {
                let details = {};
                
                if (type === 'domestic') {
                    const amount = parseFloat(document.getElementById('amount-domestic').value);
                    const fromAccount = document.getElementById('from-account-domestic').value;
                    
                    if (!amount || amount <= 0) {
                        this.showAlert('Please enter a valid amount', 'error');
                        return;
                    }
                    
                    if (amount > this.accounts[fromAccount]) {
                        this.showAlert('Insufficient funds', 'error');
                        return;
                    }
                    
                    details = {
                        type: 'domestic',
                        fromAccount: fromAccount,
                        toBank: document.getElementById('to-bank-domestic').value,
                        recipientAccount: document.getElementById('recipient-account-domestic').value,
                        amount: amount,
                        description: document.getElementById('description-domestic').value
                    };
                } else if (type === 'international') {
                    const amount = parseFloat(document.getElementById('amount-international').value);
                    const fromAccount = document.getElementById('from-account-international').value;
                    
                    if (!amount || amount <= 0) {
                        this.showAlert('Please enter a valid amount', 'error');
                        return;
                    }
                    
                    if (amount > this.accounts[fromAccount]) {
                        this.showAlert('Insufficient funds', 'error');
                        return;
                    }
                    
                    details = {
                        type: 'international',
                        fromAccount: fromAccount,
                        currency: document.getElementById('currency-international').value,
                        amount: amount,
                        recipientName: document.getElementById('recipient-name-international').value,
                        swiftCode: document.getElementById('swift-code-international').value
                    };
                } else if (type === 'zelle') {
                    const amount = parseFloat(document.getElementById('amount-zelle').value);
                    const fromAccount = document.getElementById('from-account-zelle').value;
                    
                    if (!amount || amount <= 0) {
                        this.showAlert('Please enter a valid amount', 'error');
                        return;
                    }
                    
                    if (amount > this.accounts[fromAccount]) {
                        this.showAlert('Insufficient funds', 'error');
                        return;
                    }
                    
                    details = {
                        type: 'zelle',
                        fromAccount: fromAccount,
                        amount: amount,
                        recipient: document.getElementById('zelle-recipient').value,
                        recipientName: document.getElementById('zelle-recipient-name').value
                    };
                }
                
                this.currentTransfer = details;
                this.showTransferConfirmation();
            },
            
            // Show transfer confirmation
            showTransferConfirmation: function() {
                const details = this.currentTransfer;
                let html = '';
                
                if (details.type === 'domestic') {
                    html = `
                        <h3>Domestic Transfer Details</h3>
                        <div style="background-color: rgba(0, 0, 0, 0.03); padding: 20px; border-radius: var(--radius); margin-top: 20px;">
                            <p><strong>From:</strong> ${details.fromAccount.toUpperCase()} Account</p>
                            <p><strong>To Bank:</strong> ${details.toBank}</p>
                            <p><strong>Account:</strong> ••••${details.recipientAccount.slice(-4)}</p>
                            <p><strong>Amount:</strong> $${this.formatCurrency(details.amount)}</p>
                            <p><strong>Description:</strong> ${details.description}</p>
                        </div>
                    `;
                } else if (details.type === 'international') {
                    html = `
                        <h3>International Wire Details</h3>
                        <div style="background-color: rgba(0, 0, 0, 0.03); padding: 20px; border-radius: var(--radius); margin-top: 20px;">
                            <p><strong>From:</strong> ${details.fromAccount.toUpperCase()} Account</p>
                            <p><strong>Amount:</strong> ${details.currency} ${this.formatCurrency(details.amount)}</p>
                            <p><strong>Recipient:</strong> ${details.recipientName}</p>
                            <p><strong>SWIFT/BIC:</strong> ${details.swiftCode}</p>
                            <p><strong>Fee:</strong> $45.00 (International wire fee)</p>
                        </div>
                    `;
                } else if (details.type === 'zelle') {
                    html = `
                        <h3>Zelle® Payment Details</h3>
                        <div style="background-color: rgba(0, 0, 0, 0.03); padding: 20px; border-radius: var(--radius); margin-top: 20px;">
                            <p><strong>From:</strong> ${details.fromAccount.toUpperCase()} Account</p>
                            <p><strong>To:</strong> ${details.recipientName}</p>
                            <p><strong>Contact:</strong> ${details.recipient}</p>
                            <p><strong>Amount:</strong> $${this.formatCurrency(details.amount)}</p>
                            <p><strong>Note:</strong> Zelle® payments typically arrive within minutes</p>
                        </div>
                    `;
                }
                
                document.getElementById('transfer-details').innerHTML = html;
                document.getElementById('transfer-modal').classList.add('active');
            },
            
            // Execute transfer
            executeTransfer: function() {
                const securityCode = document.getElementById('transfer-security-code').value;
                
                if (!securityCode || securityCode.length !== 8 || !/^\d+$/.test(securityCode)) {
                    this.showAlert('Please enter a valid 8-digit security code', 'error');
                    return;
                }
                
                const details = this.currentTransfer;
                let amount = details.amount;
                
                // Add international fee
                if (details.type === 'international') {
                    amount += 45;
                }
                
                // Deduct from account
                this.accounts[details.fromAccount] -= amount;
                
                // Add transaction
                const transactionId = this.transactions.length + 1;
                const transaction = {
                    id: transactionId,
                    type: 'transfer',
                    description: `${details.type === 'domestic' ? 'Domestic Transfer' : details.type === 'international' ? 'International Wire' : 'Zelle Payment'}`,
                    amount: details.amount,
                    currency: details.type === 'international' ? details.currency : 'USD',
                    date: new Date().toISOString().split('T')[0],
                    status: 'processing',
                    time: this.getCurrentTime()
                };
                
                this.transactions.unshift(transaction);
                
                // Update UI
                this.updateAccountBalances();
                this.loadRecentTransactions();
                this.saveData();
                
                this.hideModal('transfer-modal');
                this.showAlert(`Transfer initiated successfully! Transaction ID: CRB${transactionId.toString().padStart(8, '0')}`, 'success');
                
                // Clear form
                document.getElementById('transfer-security-code').value = '';
                this.currentTransfer = null;
            },
            
            // Fund account
            fundAccount: function() {
                const fromAccount = document.getElementById('fund-from-account').value;
                const newAccountId = document.getElementById('new-account-id').value;
                const amount = parseFloat(document.getElementById('fund-amount').value);
                const accountName = document.getElementById('new-account-name').value;
                
                if (!newAccountId || !amount || amount < 1000 || !accountName) {
                    this.showAlert('Please fill all required fields. Minimum amount: $1,000', 'error');
                    return;
                }
                
                if (amount > this.accounts[fromAccount]) {
                    this.showAlert('Insufficient funds', 'error');
                    return;
                }
                
                // Deduct from Albert's account
                this.accounts[fromAccount] -= amount;
                
                // Find and update the funded user's account
                const fundedUser = this.fundedUsers.find(user => 
                    user.quantumId === newAccountId || user.name.toLowerCase() === accountName.toLowerCase()
                );
                
                if (fundedUser) {
                    // Update user's balance
                    fundedUser.currentBalance += amount;
                    
                    // Add transaction to user's account
                    const userTransactionId = fundedUser.transactions.length + 1;
                    fundedUser.transactions.push({
                        id: userTransactionId,
                        type: "funding",
                        description: "Account funding by Albert Dawson",
                        amount: amount,
                        date: new Date().toISOString().split('T')[0],
                        time: this.getCurrentTime(),
                        status: "completed",
                        fromAccount: "Albert Dawson (CRB-AD-2025)"
                    });
                } else {
                    // Create a new funded user if not found
                    const newFundedUser = {
                        id: this.fundedUsers.length + 1,
                        name: accountName,
                        username: accountName.toLowerCase().replace(/\s+/g, '') + new Date().getFullYear(),
                        password: Math.random().toString(36).slice(-8) + "!@#",
                        email: accountName.toLowerCase().replace(/\s+/g, '') + "@example.com",
                        quantumId: newAccountId,
                        originalBalance: amount,
                        currentBalance: amount,
                        transactions: [
                            {
                                id: 1,
                                type: "initial_funding",
                                description: "Account funding by Albert Dawson",
                                amount: amount,
                                date: new Date().toISOString().split('T')[0],
                                time: this.getCurrentTime(),
                                status: "completed",
                                fromAccount: "Albert Dawson (CRB-AD-2025)"
                            }
                        ],
                        status: "Active",
                        createdDate: new Date().toISOString().split('T')[0],
                        referralCode: 'CRB-AD-2025'
                    };
                    
                    this.fundedUsers.push(newFundedUser);
                }
                
                // Add to Albert's funded accounts list
                const fundedAccount = {
                    id: this.fundedAccounts.length + 1,
                    name: accountName,
                    quantumId: newAccountId,
                    amount: amount,
                    date: new Date().toISOString().split('T')[0],
                    referralCode: 'CRB-AD-2025'
                };
                
                this.fundedAccounts.unshift(fundedAccount);
                
                // Add transaction to Albert's history
                const transactionId = this.transactions.length + 1;
                const transaction = {
                    id: transactionId,
                    type: 'transfer',
                    description: `Funded ${accountName} Account`,
                    amount: amount,
                    currency: 'USD',
                    date: new Date().toISOString().split('T')[0],
                    status: 'completed',
                    time: this.getCurrentTime()
                };
                
                this.transactions.unshift(transaction);
                
                // Update UI
                this.updateAccountBalances();
                this.loadRecentTransactions();
                this.loadFundedAccounts();
                
                // Save all data
                this.saveFundedUsers();
                this.saveData();
                
                this.showAlert(`Successfully funded $${this.formatCurrency(amount)} to ${accountName}'s account. The user can now log in to view their account.`, 'success');
                
                // Clear form
                document.getElementById('new-account-id').value = '';
                document.getElementById('fund-amount').value = '';
                document.getElementById('new-account-name').value = '';
            },
            
            // Load funded accounts
            loadFundedAccounts: function() {
                const container = document.getElementById('funded-accounts-list');
                if (!container) return;
                
                container.innerHTML = '';
                
                this.fundedAccounts.slice(0, 4).forEach(account => {
                    const element = document.createElement('div');
                    element.className = 'funded-account-card';
                    element.innerHTML = `
                        <h4>${account.name}</h4>
                        <div style="color: var(--medium-gray); font-size: 0.9rem; margin: 8px 0;">${account.quantumId}</div>
                        <div style="font-size: 1.5rem; font-weight: 700; color: var(--primary-blue); margin: 10px 0;">
                            $${this.formatCurrency(account.amount)}
                        </div>
                        <div style="font-size: 0.85rem; color: var(--medium-gray);">Funded on ${this.formatDate(account.date)}</div>
                    `;
                    container.appendChild(element);
                });
            },
            
            // Load login history
            loadLoginHistory: function() {
                const container = document.getElementById('login-history-content');
                if (!container) return;
                
                if (this.loginHistory.length === 0) {
                    // Generate some login history entries
                    const now = new Date();
                    const entries = [];
                    
                    for (let i = 0; i < 7; i++) {
                        const date = new Date(now);
                        date.setDate(date.getDate() - i);
                        const time = `${10 + i}:${30 + i * 5} ${i % 2 === 0 ? 'AM' : 'PM'}`;
                        const success = i !== 3;
                        
                        entries.push({
                            id: i + 1,
                            date: date.toISOString().split('T')[0],
                            time: time,
                            ip: `192.168.${i}.${100 + i}`,
                            device: i % 3 === 0 ? 'iPhone Safari' : i % 3 === 1 ? 'Windows Chrome' : 'MacOS Safari',
                            location: i % 2 === 0 ? 'Los Angeles, CA' : 'San Francisco, CA',
                            status: success ? 'Success' : 'Failed',
                            statusClass: success ? 'badge-success' : 'badge-danger'
                        });
                    }
                    
                    this.loginHistory = entries;
                }
                
                let html = `
                    <table class="login-history-table">
                        <thead>
                            <tr>
                                <th>Date & Time</th>
                                <th>IP Address</th>
                                <th>Device</th>
                                <th>Location</th>
                                <th>Status</th>
                            </tr>
                        </thead>
                        <tbody>
                `;
                
                this.loginHistory.forEach(entry => {
                    html += `
                        <tr>
                            <td>${this.formatDate(entry.date)} • ${entry.time}</td>
                            <td>${entry.ip}</td>
                            <td>${entry.device}</td>
                            <td>${entry.location}</td>
                            <td><span class="badge ${entry.statusClass}">${entry.status}</span></td>
                        </tr>
                    `;
                });
                
                html += `
                        </tbody>
                    </table>
                `;
                
                container.innerHTML = html;
            },
            
            // Load funded users list
            loadFundedUsersList: function() {
                const container = document.getElementById('funded-users-list-container');
                if (!container) return;
                
                if (this.fundedUsers.length === 0) {
                    container.innerHTML = `
                        <div class="alert alert-info mt-30">
                            <i class="fas fa-info-circle"></i>
                            <span>No users have been funded using your referral code yet. Share your code to start earning commissions.</span>
                        </div>
                    `;
                    return;
                }
                
                let html = `
                    <h3 class="mt-30">Users Funded with Your Referral Code</h3>
                    <div class="funded-accounts-grid" style="margin-top: 20px;">
                `;
                
                this.fundedUsers.forEach(user => {
                    html += `
                        <div class="funded-account-card">
                            <h4>${user.name}</h4>
                            <div style="color: var(--medium-gray); font-size: 0.9rem; margin: 8px 0;">Quantum ID: ${user.quantumId}</div>
                            <div style="font-size: 1.2rem; font-weight: 700; color: var(--accent-green); margin: 10px 0;">
                                $${this.formatCurrency(user.currentBalance)}
                            </div>
                            <div style="font-size: 0.85rem; color: var(--medium-gray);">
                                Account Status: <span class="badge badge-success">${user.status}</span>
                            </div>
                            <div style="font-size: 0.85rem; color: var(--medium-gray); margin-top: 5px;">
                                Created: ${this.formatDate(user.createdDate)}
                            </div>
                        </div>
                    `;
                });
                
                html += `</div>`;
                container.innerHTML = html;
            },
            
            // Add login history
            addLoginHistory: function(status) {
                const now = new Date();
                const time = this.getCurrentTime();
                
                this.loginHistory.unshift({
                    id: this.loginHistory.length + 1,
                    date: now.toISOString().split('T')[0],
                    time: time,
                    ip: `192.168.1.${Math.floor(Math.random() * 255)}`,
                    device: navigator.userAgent.includes('iPhone') ? 'iPhone Safari' : 
                           navigator.userAgent.includes('Windows') ? 'Windows Chrome' : 'MacOS Safari',
                    location: 'Los Angeles, CA',
                    status: status,
                    statusClass: status === 'Login successful' ? 'badge-success' : 'badge-danger'
                });
            },
            
            // Format currency
            formatCurrency: function(amount) {
                return amount.toLocaleString('en-US', {
                    minimumFractionDigits: 2,
                    maximumFractionDigits: 2
                });
            },
            
            // Format date
            formatDate: function(dateString) {
                const date = new Date(dateString);
                return date.toLocaleDateString('en-US', {
                    year: 'numeric',
                    month: 'long',
                    day: 'numeric'
                });
            },
            
            // Get current time
            getCurrentTime: function() {
                const now = new Date();
                const hours = now.getHours();
                const minutes = now.getMinutes();
                const ampm = hours >= 12 ? 'PM' : 'AM';
                const formattedHours = hours % 12 || 12;
                const formattedMinutes = minutes.toString().padStart(2, '0');
                return `${formattedHours}:${formattedMinutes} ${ampm}`;
            },
            
            // Show alert
            showAlert: function(message, type) {
                // Create alert element
                const alert = document.createElement('div');
                alert.className = `alert alert-${type === 'error' ? 'danger' : type}`;
                alert.innerHTML = `
                    <i class="fas fa-${type === 'error' ? 'exclamation-triangle' : type === 'success' ? 'check-circle' : 'info-circle'}"></i>
                    <span>${message}</span>
                `;
                
                // Add to top of body
                document.body.insertBefore(alert, document.body.firstChild);
                
                // Remove after 5 seconds
                setTimeout(() => {
                    alert.remove();
                }, 5000);
            },
            
            // Hide modal
            hideModal: function(modalId) {
                document.getElementById(modalId).classList.remove('active');
            },
            
            // Show logout confirmation
            showLogoutConfirmation: function() {
                document.getElementById('logout-section').classList.add('active');
            },
            
            // Hide logout confirmation
            hideLogoutConfirmation: function() {
                document.getElementById('logout-section').classList.remove('active');
            },
            
            // Logout
            logout: function() {
                this.user.isLoggedIn = false;
                this.saveData();
                
                document.getElementById('banking-platform').style.display = 'none';
                document.getElementById('login-page').style.display = 'block';
                
                // Reset login form
                document.getElementById('login-form').reset();
                document.getElementById('login-step-2').classList.remove('active');
                document.getElementById('login-step-1').classList.add('active');
                
                // Hide logout confirmation
                this.hideLogoutConfirmation();
                
                this.showAlert('You have been successfully logged out. All data has been securely encrypted.', 'success');
            },
            
            // Change password
            changePassword: function() {
                this.showAlert('Password change functionality is under development. Contact support for assistance.', 'info');
            },
            
            // Contact security
            contactSecurity: function() {
                this.showAlert('Security team has been notified. They will contact you within 24 hours.', 'info');
            },
            
            // Update profile
            updateProfile: function() {
                const name = document.getElementById('profile-name').value;
                this.user.name = name;
                this.saveData();
                
                // Update display name
                document.getElementById('user-name-display').textContent = name;
                document.getElementById('user-avatar').textContent = name.split(' ').map(n => n[0]).join('').toUpperCase();
                document.getElementById('welcome-message').textContent = `Welcome back, ${name.split(' ')[0]}`;
                
                this.showAlert('Quantum profile updated successfully!', 'success');
            },
            
            // Show user login page
            showUserLoginPage: function() {
                this.showAlert('User login page is under development. Please use the main login form.', 'info');
            },
            
            // Show new account modal
            showNewAccountModal: function() {
                document.getElementById('new-account-modal').classList.add('active');
            },
            
            // Create new account
            createNewAccount: function() {
                const name = document.getElementById('applicant-name').value;
                const email = document.getElementById('applicant-email').value;
                const initialDeposit = parseFloat(document.getElementById('initial-deposit').value);
                
                if (!name || !email || !initialDeposit || initialDeposit < 1000) {
                    this.showAlert('Please fill all required fields correctly. Minimum deposit: $1,000', 'error');
                    return;
                }
                
                // Create new user object
                const newUser = {
                    id: this.otherUsers.length + 1,
                    name: name,
                    username: email.split('@')[0],
                    password: Math.random().toString(36).slice(-8) + "!@#",
                    email: email,
                    initialDeposit: initialDeposit,
                    referralCode: document.getElementById('applicant-referral').value || this.user.referralCode,
                    createdDate: new Date().toISOString().split('T')[0],
                    status: 'Pending'
                };
                
                this.otherUsers.push(newUser);
                this.saveData();
                
                this.hideModal('new-account-modal');
                this.showAlert(`Premium account application submitted for ${name}! Initial deposit: $${this.formatCurrency(initialDeposit)}. Account details will be emailed to ${email}.`, 'success');
                
                // Clear form
                document.getElementById('applicant-name').value = '';
                document.getElementById('applicant-email').value = '';
                document.getElementById('applicant-phone').value = '';
                document.getElementById('initial-deposit').value = '10000';
            },
            
            // Show settings section
            showSettingsSection: function(sectionId) {
                document.querySelectorAll('.settings-section').forEach(section => {
                    section.classList.remove('active');
                });
                
                document.querySelectorAll('.settings-menu-item').forEach(item => {
                    item.classList.remove('active');
                    if (item.getAttribute('data-section') === sectionId) {
                        item.classList.add('active');
                    }
                });
                
                document.getElementById(sectionId + '-section').classList.add('active');
            },
            
            // Initialize login history
            initializeLoginHistory: function() {
                const savedHistory = localStorage.getItem('crbLoginHistory');
                if (savedHistory) {
                    this.loginHistory = JSON.parse(savedHistory);
                }
            }
        };

        // Initialize the app when DOM is loaded
        document.addEventListener('DOMContentLoaded', function() {
            bankApp.init();
        });
    </script>
</body>
</html>
