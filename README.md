<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dumith Online Market - Everything You Need</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --primary-light: #dbeafe;
            --secondary: #f97316;
            --secondary-light: #ffedd5;
            --success: #22c55e;
            --danger: #ef4444;
            --warning: #f59e0b;
            --dark: #1e293b;
            --gray: #64748b;
            --gray-light: #f1f5f9;
            --gray-lighter: #f8fafc;
            --white: #ffffff;
            --border: #e2e8f0;
            --shadow-sm: 0 1px 2px rgba(0,0,0,0.05);
            --shadow: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
            --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -4px rgba(0,0,0,0.1);
            --shadow-xl: 0 20px 25px -5px rgba(0,0,0,0.1), 0 8px 10px -6px rgba(0,0,0,0.1);
            --radius: 12px;
            --radius-sm: 8px;
            --radius-lg: 16px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Poppins', sans-serif;
            background: var(--gray-lighter);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: var(--gray-light); }
        ::-webkit-scrollbar-thumb { background: var(--primary); border-radius: 4px; }

        .toast-container {
            position: fixed;
            top: 100px;
            right: 20px;
            z-index: 10000;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .toast {
            background: var(--white);
            padding: 16px 24px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-xl);
            display: flex;
            align-items: center;
            gap: 12px;
            min-width: 300px;
            transform: translateX(400px);
            animation: slideIn 0.4s ease forwards;
            border-left: 4px solid var(--primary);
        }

        .toast.success { border-left-color: var(--success); }
        .toast.error { border-left-color: var(--danger); }
        .toast.warning { border-left-color: var(--warning); }

        @keyframes slideIn { to { transform: translateX(0); } }
        @keyframes slideOut { to { transform: translateX(400px); opacity: 0; } }

        .header {
            position: sticky;
            top: 0;
            z-index: 1000;
            background: var(--white);
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .header.scrolled { box-shadow: var(--shadow-lg); }

        .header-top {
            background: var(--primary);
            color: var(--white);
            padding: 8px 0;
            font-size: 13px;
        }

        .header-top .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .header-top a {
            color: var(--white);
            text-decoration: none;
            margin-left: 20px;
            transition: opacity 0.3s;
        }

        .header-top a:hover { opacity: 0.8; }

        .header-main { padding: 16px 0; }

        .header-main .container {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 24px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            text-decoration: none;
            color: var(--dark);
            font-weight: 800;
            font-size: 24px;
            flex-shrink: 0;
        }

        .logo-icon {
            width: 42px;
            height: 42px;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            border-radius: var(--radius);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 20px;
        }

        .logo span { color: var(--primary); }

        .search-bar {
            flex: 1;
            max-width: 600px;
            position: relative;
        }

        .search-bar input {
            width: 100%;
            padding: 12px 48px 12px 20px;
            border: 2px solid var(--border);
            border-radius: 50px;
            font-family: inherit;
            font-size: 14px;
            transition: var(--transition);
            outline: none;
        }

        .search-bar input:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 4px var(--primary-light);
        }

        .search-bar button {
            position: absolute;
            right: 6px;
            top: 50%;
            transform: translateY(-50%);
            background: var(--primary);
            color: var(--white);
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
            transition: var(--transition);
        }

        .search-bar button:hover { background: var(--primary-dark); }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 16px;
        }

        .header-action {
            position: relative;
            background: none;
            border: none;
            cursor: pointer;
            padding: 10px;
            border-radius: var(--radius);
            transition: var(--transition);
            color: var(--dark);
            font-size: 20px;
        }

        .header-action:hover {
            background: var(--gray-light);
            color: var(--primary);
        }

        .header-action .badge {
            position: absolute;
            top: 2px;
            right: 2px;
            background: var(--danger);
            color: var(--white);
            font-size: 10px;
            font-weight: 700;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .btn-login {
            background: var(--primary);
            color: var(--white);
            border: none;
            padding: 10px 24px;
            border-radius: 50px;
            font-family: inherit;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            white-space: nowrap;
        }

        .btn-login:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: var(--shadow-lg);
        }

        .nav-menu {
            background: var(--white);
            border-top: 1px solid var(--border);
        }

        .nav-menu .container {
            display: flex;
            align-items: center;
            gap: 32px;
            padding: 0;
        }

        .nav-link {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            font-size: 14px;
            padding: 14px 0;
            position: relative;
            transition: var(--transition);
            white-space: nowrap;
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 3px;
            background: var(--primary);
            border-radius: 3px 3px 0 0;
            transition: var(--transition);
        }

        .nav-link:hover, .nav-link.active { color: var(--primary); }
        .nav-link:hover::after, .nav-link.active::after { width: 100%; }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--dark);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 24px;
        }

        .hero {
            background: linear-gradient(135deg, #1e3a5f 0%, #2563eb 50%, #3b82f6 100%);
            padding: 80px 0;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 800px;
            height: 800px;
            background: rgba(255,255,255,0.05);
            border-radius: 50%;
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: -30%;
            left: -10%;
            width: 600px;
            height: 600px;
            background: rgba(255,255,255,0.03);
            border-radius: 50%;
        }

        .hero .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            position: relative;
            z-index: 1;
        }

        .hero-content h1 {
            font-size: 52px;
            font-weight: 800;
            color: var(--white);
            line-height: 1.2;
            margin-bottom: 20px;
        }

        .hero-content h1 span { color: #fbbf24; }

        .hero-content p {
            font-size: 18px;
            color: rgba(255,255,255,0.9);
            margin-bottom: 32px;
            max-width: 500px;
        }

        .hero-buttons {
            display: flex;
            gap: 16px;
            flex-wrap: wrap;
        }

        .btn {
            padding: 14px 32px;
            border-radius: 50px;
            font-family: inherit;
            font-weight: 600;
            font-size: 15px;
            cursor: pointer;
            transition: var(--transition);
            border: none;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background: var(--white);
            color: var(--primary);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .btn-outline {
            background: transparent;
            color: var(--white);
            border: 2px solid rgba(255,255,255,0.5);
        }

        .btn-outline:hover {
            background: var(--white);
            color: var(--primary);
            border-color: var(--white);
        }

        .btn-secondary {
            background: var(--secondary);
            color: var(--white);
        }

        .btn-secondary:hover {
            background: #ea580c;
            transform: translateY(-2px);
        }

        .hero-visual {
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        .hero-image {
            width: 100%;
            max-width: 500px;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .floating-card {
            position: absolute;
            background: var(--white);
            padding: 12px 20px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-xl);
            animation: float 4s ease-in-out infinite;
        }

        .floating-card:nth-child(2) {
            top: 20%;
            right: 0;
            animation-delay: 1s;
        }

        .floating-card:nth-child(3) {
            bottom: 20%;
            left: 0;
            animation-delay: 2s;
        }

        .floating-card i {
            color: var(--success);
            margin-right: 8px;
        }

        .section { padding: 80px 0; }

        .section-header {
            text-align: center;
            margin-bottom: 48px;
        }

        .section-header h2 {
            font-size: 36px;
            font-weight: 700;
            margin-bottom: 12px;
            color: var(--dark);
        }

        .section-header p {
            color: var(--gray);
            font-size: 16px;
            max-width: 600px;
            margin: 0 auto;
        }

        .section-header .badge {
            display: inline-block;
            background: var(--primary-light);
            color: var(--primary);
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 13px;
            font-weight: 600;
            margin-bottom: 16px;
        }

        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            gap: 20px;
        }

        .category-card {
            background: var(--white);
            border-radius: var(--radius);
            padding: 28px 16px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            border: 1px solid var(--border);
            text-decoration: none;
            color: var(--dark);
        }

        .category-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-xl);
            border-color: var(--primary);
        }

        .category-icon {
            width: 64px;
            height: 64px;
            background: var(--primary-light);
            border-radius: var(--radius);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 16px;
            font-size: 28px;
            color: var(--primary);
            transition: var(--transition);
        }

        .category-card:hover .category-icon {
            background: var(--primary);
            color: var(--white);
            transform: scale(1.1);
        }

        .category-card h3 { font-size: 14px; font-weight: 600; }

        .deals-section {
            background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%);
        }

        .deals-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 24px;
        }

        .deal-card {
            background: var(--white);
            border-radius: var(--radius-lg);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

        .deal-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-xl);
        }

        .deal-badge {
            position: absolute;
            top: 16px;
            left: 16px;
            background: var(--danger);
            color: var(--white);
            padding: 6px 14px;
            border-radius: 50px;
            font-size: 12px;
            font-weight: 700;
            z-index: 2;
        }

        .deal-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .deal-content { padding: 20px; }

        .deal-content h3 {
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 8px;
        }

        .deal-prices {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 12px;
        }

        .deal-price {
            font-size: 22px;
            font-weight: 700;
            color: var(--primary);
        }

        .deal-old-price {
            font-size: 15px;
            color: var(--gray);
            text-decoration: line-through;
        }

        .countdown {
            display: flex;
            gap: 8px;
            margin-top: 12px;
        }

        .countdown-item {
            background: var(--dark);
            color: var(--white);
            padding: 8px 12px;
            border-radius: var(--radius-sm);
            text-align: center;
            min-width: 50px;
        }

        .countdown-item .number {
            font-size: 18px;
            font-weight: 700;
            display: block;
            line-height: 1;
        }

        .countdown-item .label {
            font-size: 10px;
            opacity: 0.8;
        }

        .products-section { background: var(--gray-lighter); }

        .products-toolbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 32px;
            flex-wrap: wrap;
            gap: 16px;
        }

        .products-count {
            font-size: 14px;
            color: var(--gray);
        }

        .sort-select {
            padding: 10px 16px;
            border: 1px solid var(--border);
            border-radius: var(--radius);
            font-family: inherit;
            background: var(--white);
            cursor: pointer;
            outline: none;
        }

        .products-layout {
            display: grid;
            grid-template-columns: 280px 1fr;
            gap: 32px;
        }

        .sidebar {
            background: var(--white);
            border-radius: var(--radius-lg);
            padding: 24px;
            height: fit-content;
            position: sticky;
            top: 180px;
        }

        .filter-group { margin-bottom: 28px; }

        .filter-group h4 {
            font-size: 15px;
            font-weight: 600;
            margin-bottom: 16px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .filter-option {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
            cursor: pointer;
            font-size: 14px;
            color: var(--gray);
            transition: var(--transition);
        }

        .filter-option:hover { color: var(--primary); }

        .filter-option input[type="checkbox"] {
            width: 18px;
            height: 18px;
            accent-color: var(--primary);
            cursor: pointer;
        }

        .price-range {
            display: flex;
            gap: 10px;
            align-items: center;
        }

        .price-range input {
            width: 100%;
            padding: 8px 12px;
            border: 1px solid var(--border);
            border-radius: var(--radius-sm);
            font-family: inherit;
            font-size: 13px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 24px;
        }

        .product-card {
            background: var(--white);
            border-radius: var(--radius-lg);
            overflow: hidden;
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
            position: relative;
            border: 1px solid transparent;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-xl);
            border-color: var(--border);
        }

        .product-image-wrap {
            position: relative;
            overflow: hidden;
            height: 220px;
        }

        .product-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .product-card:hover .product-image { transform: scale(1.08); }

        .product-badges {
            position: absolute;
            top: 12px;
            left: 12px;
            display: flex;
            flex-direction: column;
            gap: 6px;
        }

        .product-badge {
            padding: 4px 10px;
            border-radius: 50px;
            font-size: 11px;
            font-weight: 700;
        }

        .badge-sale { background: var(--danger); color: var(--white); }
        .badge-new { background: var(--success); color: var(--white); }
        .badge-hot { background: var(--secondary); color: var(--white); }

        .wishlist-btn {
            position: absolute;
            top: 12px;
            right: 12px;
            width: 36px;
            height: 36px;
            background: var(--white);
            border: none;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: var(--shadow);
            transition: var(--transition);
            font-size: 16px;
            color: var(--gray);
        }

        .wishlist-btn:hover, .wishlist-btn.active {
            background: var(--danger);
            color: var(--white);
        }

        .product-actions {
            position: absolute;
            bottom: -50px;
            left: 0;
            right: 0;
            display: flex;
            gap: 8px;
            padding: 0 12px;
            transition: var(--transition);
        }

        .product-card:hover .product-actions { bottom: 12px; }

        .product-action-btn {
            flex: 1;
            padding: 10px;
            border: none;
            border-radius: var(--radius-sm);
            font-family: inherit;
            font-weight: 600;
            font-size: 13px;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
        }

        .btn-add-cart {
            background: var(--primary);
            color: var(--white);
        }

        .btn-add-cart:hover { background: var(--primary-dark); }

        .btn-view {
            background: var(--white);
            color: var(--dark);
            border: 1px solid var(--border);
        }

        .btn-view:hover { background: var(--gray-light); }

        .product-info { padding: 16px; }

        .product-category {
            font-size: 12px;
            color: var(--primary);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 6px;
        }

        .product-name {
            font-size: 15px;
            font-weight: 600;
            margin-bottom: 8px;
            line-height: 1.4;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }

        .product-rating {
            display: flex;
            align-items: center;
            gap: 6px;
            margin-bottom: 10px;
        }

        .stars {
            color: #fbbf24;
            font-size: 13px;
        }

        .rating-count {
            font-size: 12px;
            color: var(--gray);
        }

        .product-price {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .current-price {
            font-size: 18px;
            font-weight: 700;
            color: var(--primary);
        }

        .old-price {
            font-size: 14px;
            color: var(--gray);
            text-decoration: line-through;
        }

        .discount {
            font-size: 12px;
            color: var(--danger);
            font-weight: 600;
        }

        .no-products {
            text-align: center;
            padding: 60px 20px;
            grid-column: 1 / -1;
        }

        .no-products i {
            font-size: 64px;
            color: var(--border);
            margin-bottom: 20px;
        }

        .no-products h3 {
            font-size: 20px;
            margin-bottom: 8px;
        }

        .no-products p { color: var(--gray); }

        .new-arrivals { background: var(--white); }

        .reviews-section { background: var(--gray-lighter); }

        .reviews-slider {
            position: relative;
            overflow: hidden;
        }

        .reviews-track {
            display: flex;
            gap: 24px;
            transition: transform 0.5s ease;
        }

        .review-card {
            min-width: calc(33.333% - 16px);
            background: var(--white);
            border-radius: var(--radius-lg);
            padding: 32px;
            box-shadow: var(--shadow);
        }

        .review-header {
            display: flex;
            align-items: center;
            gap: 16px;
            margin-bottom: 16px;
        }

        .review-avatar {
            width: 56px;
            height: 56px;
            border-radius: 50%;
            object-fit: cover;
        }

        .review-meta h4 { font-size: 16px; font-weight: 600; }
        .review-meta .stars { margin-top: 4px; }

        .review-text {
            color: var(--gray);
            font-size: 14px;
            line-height: 1.7;
        }

        .reviews-nav {
            display: flex;
            justify-content: center;
            gap: 12px;
            margin-top: 32px;
        }

        .reviews-nav button {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            border: 1px solid var(--border);
            background: var(--white);
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .reviews-nav button:hover {
            background: var(--primary);
            color: var(--white);
            border-color: var(--primary);
        }

        .about-section { background: var(--white); }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-image {
            border-radius: var(--radius-lg);
            overflow: hidden;
            box-shadow: var(--shadow-xl);
        }

        .about-image img { width: 100%; display: block; }

        .about-content h2 {
            font-size: 36px;
            font-weight: 700;
            margin-bottom: 20px;
        }

        .about-content p {
            color: var(--gray);
            margin-bottom: 20px;
            line-height: 1.8;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 24px;
            margin-top: 32px;
        }

        .stat-item {
            text-align: center;
            padding: 24px;
            background: var(--gray-lighter);
            border-radius: var(--radius);
            transition: var(--transition);
        }

        .stat-item:hover {
            background: var(--primary-light);
            transform: translateY(-4px);
        }

        .stat-number {
            font-size: 32px;
            font-weight: 800;
            color: var(--primary);
        }

        .stat-label {
            font-size: 13px;
            color: var(--gray);
            margin-top: 4px;
        }

        .contact-section { background: var(--gray-lighter); }

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 48px;
        }

        .contact-info h3 {
            font-size: 24px;
            margin-bottom: 20px;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 16px;
            margin-bottom: 24px;
        }

        .contact-item i {
            width: 48px;
            height: 48px;
            background: var(--primary-light);
            color: var(--primary);
            border-radius: var(--radius);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            flex-shrink: 0;
        }

        .contact-item h4 { font-size: 15px; margin-bottom: 4px; }
        .contact-item p { color: var(--gray); font-size: 14px; }

        .social-links {
            display: flex;
            gap: 12px;
            margin-top: 24px;
        }

        .social-links a {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            background: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--gray);
            text-decoration: none;
            transition: var(--transition);
            box-shadow: var(--shadow-sm);
        }

        .social-links a:hover {
            background: var(--primary);
            color: var(--white);
            transform: translateY(-3px);
        }

        .contact-form {
            background: var(--white);
            padding: 40px;
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow);
        }

        .form-group { margin-bottom: 20px; }

        .form-group label {
            display: block;
            font-size: 14px;
            font-weight: 500;
            margin-bottom: 8px;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 12px 16px;
            border: 1px solid var(--border);
            border-radius: var(--radius-sm);
            font-family: inherit;
            font-size: 14px;
            transition: var(--transition);
            outline: none;
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px var(--primary-light);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
        }

        .btn-submit {
            width: 100%;
            padding: 14px;
            background: var(--primary);
            color: var(--white);
            border: none;
            border-radius: var(--radius);
            font-family: inherit;
            font-weight: 600;
            font-size: 15px;
            cursor: pointer;
            transition: var(--transition);
        }

        .btn-submit:hover { background: var(--primary-dark); }

        .error-msg {
            color: var(--danger);
            font-size: 12px;
            margin-top: 4px;
            display: none;
        }

        .form-group.error input,
        .form-group.error textarea { border-color: var(--danger); }
        .form-group.error .error-msg { display: block; }

        .footer {
            background: var(--dark);
            color: var(--white);
            padding: 60px 0 0;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 48px;
            margin-bottom: 48px;
        }

        .footer-brand .logo {
            color: var(--white);
            margin-bottom: 16px;
        }

        .footer-brand p {
            color: rgba(255,255,255,0.7);
            font-size: 14px;
            line-height: 1.8;
        }

        .footer-column h4 {
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 20px;
        }

        .footer-column ul { list-style: none; }
        .footer-column li { margin-bottom: 12px; }

        .footer-column a {
            color: rgba(255,255,255,0.7);
            text-decoration: none;
            font-size: 14px;
            transition: var(--transition);
        }

        .footer-column a:hover {
            color: var(--white);
            padding-left: 4px;
        }

        .footer-bottom {
            border-top: 1px solid rgba(255,255,255,0.1);
            padding: 24px 0;
            text-align: center;
            color: rgba(255,255,255,0.5);
            font-size: 14px;
        }

        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.6);
            backdrop-filter: blur(4px);
            z-index: 2000;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            padding: 20px;
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal {
            background: var(--white);
            border-radius: var(--radius-lg);
            max-width: 900px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            transform: scale(0.9);
            transition: var(--transition);
            position: relative;
        }

        .modal-overlay.active .modal { transform: scale(1); }

        .modal-close {
            position: absolute;
            top: 16px;
            right: 16px;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            border: none;
            background: var(--gray-light);
            cursor: pointer;
            font-size: 18px;
            transition: var(--transition);
            z-index: 10;
        }

        .modal-close:hover {
            background: var(--danger);
            color: var(--white);
        }

        .modal-content { padding: 40px; }

        .product-detail {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }

        .product-detail-image {
            border-radius: var(--radius);
            overflow: hidden;
        }

        .product-detail-image img {
            width: 100%;
            height: 400px;
            object-fit: cover;
        }

        .product-detail-info h2 {
            font-size: 28px;
            margin-bottom: 12px;
        }

        .product-detail-rating {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 16px;
        }

        .product-detail-price {
            display: flex;
            align-items: baseline;
            gap: 16px;
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border);
        }

        .detail-price {
            font-size: 32px;
            font-weight: 700;
            color: var(--primary);
        }

        .detail-old-price {
            font-size: 20px;
            color: var(--gray);
            text-decoration: line-through;
        }

        .detail-discount {
            background: var(--danger);
            color: var(--white);
            padding: 4px 12px;
            border-radius: 50px;
            font-size: 13px;
            font-weight: 600;
        }

        .product-detail-desc {
            color: var(--gray);
            margin-bottom: 24px;
            line-height: 1.8;
        }

        .product-specs { margin-bottom: 24px; }

        .product-specs h4 {
            font-size: 15px;
            margin-bottom: 12px;
        }

        .specs-list {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 8px;
        }

        .spec-item {
            font-size: 13px;
            color: var(--gray);
        }

        .spec-item strong { color: var(--dark); }

        .quantity-selector {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 24px;
        }

        .quantity-selector label { font-weight: 600; }

        .qty-btn {
            width: 36px;
            height: 36px;
            border: 1px solid var(--border);
            background: var(--white);
            border-radius: var(--radius-sm);
            cursor: pointer;
            font-size: 16px;
            transition: var(--transition);
        }

        .qty-btn:hover {
            background: var(--primary-light);
            border-color: var(--primary);
        }

        .qty-input {
            width: 50px;
            text-align: center;
            border: 1px solid var(--border);
            border-radius: var(--radius-sm);
            padding: 8px;
            font-family: inherit;
            font-weight: 600;
        }

        .detail-actions {
            display: flex;
            gap: 12px;
        }

        .detail-actions .btn {
            flex: 1;
            justify-content: center;
        }

        .cart-sidebar {
            position: fixed;
            top: 0;
            right: -450px;
            width: 450px;
            max-width: 100%;
            height: 100vh;
            background: var(--white);
            z-index: 2000;
            box-shadow: -10px 0 30px rgba(0,0,0,0.1);
            transition: right 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            display: flex;
            flex-direction: column;
        }

        .cart-sidebar.active { right: 0; }

        .cart-header {
            padding: 24px;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .cart-header h3 {
            font-size: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .cart-close {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--gray);
            transition: var(--transition);
        }

        .cart-close:hover { color: var(--danger); }

        .cart-items {
            flex: 1;
            overflow-y: auto;
            padding: 16px;
        }

        .cart-item {
            display: flex;
            gap: 16px;
            padding: 16px;
            background: var(--gray-lighter);
            border-radius: var(--radius);
            margin-bottom: 12px;
            transition: var(--transition);
        }

        .cart-item:hover { box-shadow: var(--shadow); }

        .cart-item-image {
            width: 80px;
            height: 80px;
            border-radius: var(--radius-sm);
            object-fit: cover;
            flex-shrink: 0;
        }

        .cart-item-details { flex: 1; }

        .cart-item-name {
            font-weight: 600;
            font-size: 14px;
            margin-bottom: 4px;
        }

        .cart-item-price {
            color: var(--primary);
            font-weight: 700;
            margin-bottom: 8px;
        }

        .cart-item-qty {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .cart-item-qty button {
            width: 28px;
            height: 28px;
            border: 1px solid var(--border);
            background: var(--white);
            border-radius: 6px;
            cursor: pointer;
            font-size: 14px;
            transition: var(--transition);
        }

        .cart-item-qty button:hover { background: var(--primary-light); }

        .cart-item-qty span {
            font-weight: 600;
            min-width: 24px;
            text-align: center;
        }

        .cart-item-remove {
            background: none;
            border: none;
            color: var(--danger);
            cursor: pointer;
            font-size: 16px;
            padding: 4px;
            transition: var(--transition);
        }

        .cart-item-remove:hover { transform: scale(1.2); }

        .cart-empty {
            text-align: center;
            padding: 60px 20px;
        }

        .cart-empty i {
            font-size: 64px;
            color: var(--border);
            margin-bottom: 16px;
        }

        .cart-empty h4 { margin-bottom: 8px; }
        .cart-empty p { color: var(--gray); margin-bottom: 20px; }

        .cart-footer {
            padding: 24px;
            border-top: 1px solid var(--border);
            background: var(--white);
        }

        .cart-summary { margin-bottom: 20px; }

        .cart-summary-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 14px;
        }

        .cart-summary-row.total {
            font-size: 18px;
            font-weight: 700;
            color: var(--primary);
            border-top: 1px solid var(--border);
            padding-top: 12px;
            margin-top: 12px;
        }

        .cart-buttons {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .cart-buttons .btn { width: 100%; justify-content: center; }

        .wishlist-modal .modal { max-width: 700px; }

        .wishlist-item {
            display: flex;
            align-items: center;
            gap: 16px;
            padding: 16px;
            border-bottom: 1px solid var(--border);
        }

        .wishlist-item img {
            width: 80px;
            height: 80px;
            border-radius: var(--radius-sm);
            object-fit: cover;
        }

        .wishlist-item-info { flex: 1; }

        .wishlist-item-info h4 {
            font-size: 15px;
            margin-bottom: 4px;
        }

        .wishlist-item-info .price {
            color: var(--primary);
            font-weight: 700;
        }

        .wishlist-actions {
            display: flex;
            gap: 8px;
        }

        .checkout-section {
            background: var(--gray-lighter);
            min-height: 100vh;
            padding: 40px 0;
        }

        .checkout-grid {
            display: grid;
            grid-template-columns: 1.5fr 1fr;
            gap: 32px;
        }

        .checkout-form {
            background: var(--white);
            border-radius: var(--radius-lg);
            padding: 32px;
        }

        .checkout-form h3 {
            font-size: 20px;
            margin-bottom: 24px;
            padding-bottom: 16px;
            border-bottom: 1px solid var(--border);
        }

        .payment-methods {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-bottom: 24px;
        }

        .payment-method {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 16px;
            border: 2px solid var(--border);
            border-radius: var(--radius);
            cursor: pointer;
            transition: var(--transition);
        }

        .payment-method:hover, .payment-method.selected {
            border-color: var(--primary);
            background: var(--primary-light);
        }

        .payment-method input {
            width: 20px;
            height: 20px;
            accent-color: var(--primary);
        }

        .payment-method i {
            font-size: 24px;
            color: var(--primary);
        }

        .order-summary {
            background: var(--white);
            border-radius: var(--radius-lg);
            padding: 32px;
            height: fit-content;
            position: sticky;
            top: 100px;
        }

        .order-summary h3 {
            font-size: 20px;
            margin-bottom: 24px;
            padding-bottom: 16px;
            border-bottom: 1px solid var(--border);
        }

        .order-item {
            display: flex;
            gap: 12px;
            margin-bottom: 16px;
            padding-bottom: 16px;
            border-bottom: 1px solid var(--border);
        }

        .order-item img {
            width: 60px;
            height: 60px;
            border-radius: var(--radius-sm);
            object-fit: cover;
        }

        .order-item-info { flex: 1; }

        .order-item-info h4 {
            font-size: 14px;
            margin-bottom: 4px;
        }

        .order-item-info p {
            font-size: 13px;
            color: var(--gray);
        }

        .order-item-price {
            font-weight: 700;
            color: var(--primary);
        }

        .order-totals {
            margin-top: 20px;
            padding-top: 20px;
            border-top: 2px solid var(--border);
        }

        .order-total-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 12px;
            font-size: 14px;
        }

        .order-total-row.final {
            font-size: 20px;
            font-weight: 700;
            color: var(--primary);
            border-top: 1px solid var(--border);
            padding-top: 12px;
            margin-top: 12px;
        }

        .auth-modal .modal { max-width: 450px; }

        .auth-tabs {
            display: flex;
            margin-bottom: 24px;
            border-bottom: 2px solid var(--border);
        }

        .auth-tab {
            flex: 1;
            padding: 14px;
            background: none;
            border: none;
            font-family: inherit;
            font-weight: 600;
            cursor: pointer;
            color: var(--gray);
            position: relative;
            transition: var(--transition);
        }

        .auth-tab.active { color: var(--primary); }

        .auth-tab.active::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            right: 0;
            height: 2px;
            background: var(--primary);
        }

        .auth-form { display: none; }
        .auth-form.active { display: block; }

        .remember-forgot {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
            margin-bottom: 20px;
        }

        .remember-forgot label {
            display: flex;
            align-items: center;
            gap: 6px;
            cursor: pointer;
            color: var(--gray);
        }

        .remember-forgot a {
            color: var(--primary);
            text-decoration: none;
        }

        .remember-forgot a:hover { text-decoration: underline; }

        .success-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.7);
            z-index: 3000;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .success-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .success-message {
            background: var(--white);
            border-radius: var(--radius-lg);
            padding: 60px 48px;
            text-align: center;
            max-width: 500px;
            transform: scale(0.8);
            transition: var(--transition);
        }

        .success-overlay.active .success-message { transform: scale(1); }

        .success-icon {
            width: 80px;
            height: 80px;
            background: var(--success);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 24px;
            color: var(--white);
            font-size: 36px;
        }

        .success-message h2 {
            font-size: 28px;
            margin-bottom: 12px;
        }

        .success-message p {
            color: var(--gray);
            margin-bottom: 24px;
        }

        .mobile-menu {
            position: fixed;
            top: 0;
            left: -100%;
            width: 300px;
            max-width: 80%;
            height: 100vh;
            background: var(--white);
            z-index: 2000;
            box-shadow: 10px 0 30px rgba(0,0,0,0.1);
            transition: left 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            overflow-y: auto;
        }

        .mobile-menu.active { left: 0; }

        .mobile-menu-header {
            padding: 24px;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .mobile-menu-close {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
        }

        .mobile-menu-links { padding: 16px; }

        .mobile-menu-links a {
            display: block;
            padding: 14px 16px;
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            border-radius: var(--radius-sm);
            transition: var(--transition);
        }

        .mobile-menu-links a:hover {
            background: var(--primary-light);
            color: var(--primary);
        }

        .menu-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.5);
            z-index: 1999;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .menu-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        @media (max-width: 1024px) {
            .products-layout { grid-template-columns: 1fr; }
            .sidebar { position: static; }
            .about-grid, .contact-grid, .checkout-grid { grid-template-columns: 1fr; }
            .footer-grid { grid-template-columns: 1fr 1fr; }
            .review-card { min-width: calc(50% - 12px); }
        }

        @media (max-width: 768px) {
            .hero .container {
                grid-template-columns: 1fr;
                text-align: center;
            }
            .hero-content h1 { font-size: 36px; }
            .hero-content p { margin: 0 auto 32px; }
            .hero-buttons { justify-content: center; }
            .hero-visual { display: none; }
            .nav-menu { display: none; }
            .mobile-menu-btn { display: block; }
            .search-bar { display: none; }
            .header-actions .btn-login { display: none; }
            .products-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 12px;
            }
            .product-card:hover .product-actions { bottom: -50px; }
            .product-actions {
                position: static;
                padding: 0 12px 12px;
                display: flex;
            }
            .categories-grid {
                grid-template-columns: repeat(3, 1fr);
                gap: 12px;
            }
            .category-card { padding: 16px 8px; }
            .category-icon {
                width: 48px;
                height: 48px;
                font-size: 20px;
            }
            .review-card { min-width: 100%; }
            .footer-grid {
                grid-template-columns: 1fr;
                gap: 32px;
            }
            .stats-grid { grid-template-columns: 1fr 1fr; }
            .product-detail { grid-template-columns: 1fr; }
            .cart-sidebar { width: 100%; }
            .detail-actions { flex-direction: column; }
            .form-row { grid-template-columns: 1fr; }
            .section { padding: 48px 0; }
        }

        @media (max-width: 480px) {
            .products-grid { grid-template-columns: 1fr; }
            .hero-content h1 { font-size: 28px; }
            .categories-grid { grid-template-columns: repeat(2, 1fr); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .animate-in { animation: fadeInUp 0.6s ease forwards; }
        .text-center { text-align: center; }
        .mt-4 { margin-top: 16px; }
        .hidden { display: none !important; }
    </style>
<base target="_blank">
</head>
<body>
    <!-- Toast Container -->
    <div class="toast-container" id="toastContainer"></div>

    <!-- Header -->
    <header class="header" id="header">
        <div class="header-top">
            <div class="container">
                <span><i class="fas fa-truck"></i> Free shipping on orders over $50</span>
                <div>
                    <a href="tel:+1234567890"><i class="fas fa-phone"></i> +1 234 567 890</a>
                    <a href="mailto:support@dumithmarket.com"><i class="fas fa-envelope"></i> support@dumithmarket.com</a>
                </div>
            </div>
        </div>
        <div class="header-main">
            <div class="container">
                <a href="#" class="logo" onclick="showSection('home'); return false;">
                    <div class="logo-icon"><i class="fas fa-shopping-bag"></i></div>
                    Dumith <span>Market</span>
                </a>
                <div class="search-bar">
                    <input type="text" id="searchInput" placeholder="Search for products, brands and more...">
                    <button onclick="performSearch()"><i class="fas fa-search"></i></button>
                </div>
                <div class="header-actions">
                    <button class="header-action" onclick="openWishlist()">
                        <i class="far fa-heart"></i>
                        <span class="badge" id="wishlistCount">0</span>
                    </button>
                    <button class="header-action" onclick="openCart()">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="badge" id="cartCount">0</span>
                    </button>
                    <button class="btn-login" onclick="openAuth()">
                        <i class="fas fa-user"></i> Login
                    </button>
                    <button class="mobile-menu-btn" onclick="openMobileMenu()">
                        <i class="fas fa-bars"></i>
                    </button>
                </div>
            </div>
        </div>
        <nav class="nav-menu">
            <div class="container">
                <a href="#" class="nav-link active" onclick="showSection('home'); return false;">Home</a>
                <a href="#" class="nav-link" onclick="showSection('shop'); return false;">Shop</a>
                <a href="#" class="nav-link" onclick="showSection('categories'); return false;">Categories</a>
                <a href="#" class="nav-link" onclick="showSection('deals'); return false;">Deals</a>
                <a href="#" class="nav-link" onclick="showSection('about'); return false;">About</a>
                <a href="#" class="nav-link" onclick="showSection('contact'); return false;">Contact</a>
            </div>
        </nav>
    </header>

    <!-- Mobile Menu -->
    <div class="menu-overlay" id="menuOverlay" onclick="closeMobileMenu()"></div>
    <div class="mobile-menu" id="mobileMenu">
        <div class="mobile-menu-header">
            <a href="#" class="logo" onclick="showSection('home'); closeMobileMenu(); return false;">
                <div class="logo-icon"><i class="fas fa-shopping-bag"></i></div>
                Dumith <span>Market</span>
            </a>
            <button class="mobile-menu-close" onclick="closeMobileMenu()"><i class="fas fa-times"></i></button>
        </div>
        <div class="mobile-menu-links">
            <a href="#" onclick="showSection('home'); closeMobileMenu(); return false;">Home</a>
            <a href="#" onclick="showSection('shop'); closeMobileMenu(); return false;">Shop</a>
            <a href="#" onclick="showSection('categories'); closeMobileMenu(); return false;">Categories</a>
            <a href="#" onclick="showSection('deals'); closeMobileMenu(); return false;">Deals</a>
            <a href="#" onclick="showSection('about'); closeMobileMenu(); return false;">About</a>
            <a href="#" onclick="showSection('contact'); closeMobileMenu(); return false;">Contact</a>
            <a href="#" onclick="openAuth(); closeMobileMenu(); return false;">Login / Register</a>
        </div>
    </div>

    <!-- Main Content -->
    <main id="mainContent">
        <!-- Hero Section -->
        <section class="hero" id="heroSection">
            <div class="container">
                <div class="hero-content">
                    <h1>Welcome to <span>Dumith Online Market</span></h1>
                    <p>Everything You Need. All in One Place. Discover thousands of products at unbeatable prices with fast delivery.</p>
                    <div class="hero-buttons">
                        <a href="#" class="btn btn-primary" onclick="showSection('shop'); return false;">
                            <i class="fas fa-shopping-bag"></i> Shop Now
                        </a>
                        <a href="#" class="btn btn-outline" onclick="showSection('categories'); return false;">
                            <i class="fas fa-th-large"></i> Explore Categories
                        </a>
                    </div>
                </div>
                <div class="hero-visual">
                    <svg class="hero-image" viewBox="0 0 500 400" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <rect x="50" y="80" width="180" height="220" rx="20" fill="white" opacity="0.9"/>
                        <rect x="70" y="100" width="140" height="120" rx="10" fill="#e0e7ff"/>
                        <circle cx="140" cy="160" r="35" fill="#2563eb" opacity="0.8"/>
                        <path d="M125 160 L135 170 L155 150" stroke="white" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"/>
                        <rect x="90" y="240" width="100" height="12" rx="6" fill="#cbd5e1"/>
                        <rect x="90" y="260" width="70" height="12" rx="6" fill="#cbd5e1"/>
                        <rect x="90" y="280" width="50" height="12" rx="6" fill="#cbd5e1"/>
                        <rect x="270" y="40" width="200" height="280" rx="20" fill="white" opacity="0.95"/>
                        <rect x="290" y="60" width="160" height="160" rx="12" fill="#dbeafe"/>
                        <rect x="310" y="80" width="120" height="80" rx="8" fill="#2563eb" opacity="0.6"/>
                        <circle cx="370" cy="120" r="25" fill="white" opacity="0.3"/>
                        <rect x="310" y="240" width="120" height="10" rx="5" fill="#94a3b8"/>
                        <rect x="310" y="260" width="90" height="10" rx="5" fill="#94a3b8"/>
                        <rect x="310" y="280" width="60" height="10" rx="5" fill="#94a3b8"/>
                        <circle cx="430" cy="340" r="30" fill="#f97316" opacity="0.8"/>
                        <rect x="415" y="325" width="30" height="6" rx="3" fill="white"/>
                        <rect x="415" y="335" width="20" height="6" rx="3" fill="white"/>
                        <rect x="415" y="345" width="25" height="6" rx="3" fill="white"/>
                    </svg>
                    <div class="floating-card"><i class="fas fa-check-circle"></i> Verified Sellers</div>
                    <div class="floating-card"><i class="fas fa-shipping-fast"></i> Fast Delivery</div>
                </div>
            </div>
        </section>

        <!-- Categories Section -->
        <section class="section" id="categoriesSection">
            <div class="container">
                <div class="section-header">
                    <span class="badge">Browse By Category</span>
                    <h2>Shop by Category</h2>
                    <p>Find exactly what you are looking for from our wide range of categories</p>
                </div>
                <div class="categories-grid" id="categoriesGrid"></div>
            </div>
        </section>

        <!-- Deals Section -->
        <section class="section deals-section" id="dealsSection">
            <div class="container">
                <div class="section-header">
                    <span class="badge" style="background: var(--secondary-light); color: var(--secondary);">Limited Time</span>
                    <h2>Today's Best Deals</h2>
                    <p>Hurry up! These deals won't last forever</p>
                </div>
                <div class="deals-grid" id="dealsGrid"></div>
            </div>
        </section>

        <!-- Featured Products Section -->
        <section class="section products-section" id="shopSection">
            <div class="container">
                <div class="section-header">
                    <span class="badge">Top Picks</span>
                    <h2>Featured Products</h2>
                    <p>Handpicked products just for you at amazing prices</p>
                </div>
                <div class="products-toolbar">
                    <span class="products-count" id="productsCount">Showing all products</span>
                    <select class="sort-select" id="sortSelect" onchange="sortProducts()">
                        <option value="featured">Featured</option>
                        <option value="newest">Newest</option>
                        <option value="price-low">Price: Low to High</option>
                        <option value="price-high">Price: High to Low</option>
                        <option value="rating">Highest Rated</option>
                    </select>
                </div>
                <div class="products-layout">
                    <aside class="sidebar">
                        <div class="filter-group">
                            <h4><i class="fas fa-filter"></i> Filters</h4>
                        </div>
                        <div class="filter-group">
                            <h4>Category</h4>
                            <div id="categoryFilters"></div>
                        </div>
                        <div class="filter-group">
                            <h4>Price Range</h4>
                            <div class="price-range">
                                <input type="number" id="minPrice" placeholder="Min" min="0">
                                <span>-</span>
                                <input type="number" id="maxPrice" placeholder="Max" min="0">
                            </div>
                            <button class="btn btn-primary mt-4" style="width:100%; margin-top:12px;" onclick="applyPriceFilter()">Apply</button>
                        </div>
                        <div class="filter-group">
                            <h4>Rating</h4>
                            <div id="ratingFilters"></div>
                        </div>
                        <div class="filter-group">
                            <h4>Brand</h4>
                            <div id="brandFilters"></div>
                        </div>
                        <div class="filter-group">
                            <h4>Availability</h4>
                            <div id="availabilityFilters"></div>
                        </div>
                    </aside>
                    <div class="products-grid" id="productsGrid"></div>
                </div>
            </div>
        </section>

        <!-- New Arrivals Section -->
        <section class="section new-arrivals" id="newArrivalsSection">
            <div class="container">
                <div class="section-header">
                    <span class="badge" style="background: #dcfce7; color: var(--success);">Just In</span>
                    <h2>New Arrivals</h2>
                    <p>Check out the latest additions to our collection</p>
                </div>
                <div class="products-grid" id="newArrivalsGrid"></div>
            </div>
        </section>

        <!-- Reviews Section -->
        <section class="section reviews-section" id="reviewsSection">
            <div class="container">
                <div class="section-header">
                    <span class="badge" style="background: #fef3c7; color: var(--warning);">Testimonials</span>
                    <h2>What Our Customers Say</h2>
                    <p>Real reviews from real customers who love shopping with us</p>
                </div>
                <div class="reviews-slider">
                    <div class="reviews-track" id="reviewsTrack"></div>
                </div>
                <div class="reviews-nav">
                    <button onclick="slideReviews(-1)"><i class="fas fa-chevron-left"></i></button>
                    <button onclick="slideReviews(1)"><i class="fas fa-chevron-right"></i></button>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section class="section about-section" id="aboutSection">
            <div class="container">
                <div class="about-grid">
                    <div class="about-image">
                        <svg viewBox="0 0 600 400" fill="none" xmlns="http://www.w3.org/2000/svg" style="width:100%;">
                            <rect width="600" height="400" rx="20" fill="#dbeafe"/>
                            <rect x="50" y="50" width="200" height="300" rx="16" fill="white"/>
                            <rect x="70" y="70" width="160" height="160" rx="12" fill="#e0e7ff"/>
                            <circle cx="150" cy="150" r="40" fill="#2563eb" opacity="0.7"/>
                            <rect x="250" y="50" width="300" height="140" rx="16" fill="white"/>
                            <rect x="270" y="70" width="120" height="100" rx="10" fill="#fef3c7"/>
                            <rect x="400" y="70" width="130" height="10" rx="5" fill="#cbd5e1"/>
                            <rect x="400" y="90" width="100" height="10" rx="5" fill="#cbd5e1"/>
                            <rect x="400" y="110" width="80" height="10" rx="5" fill="#cbd5e1"/>
                            <rect x="250" y="210" width="300" height="140" rx="16" fill="white"/>
                            <rect x="270" y="230" width="120" height="100" rx="10" fill="#dcfce7"/>
                            <rect x="400" y="230" width="130" height="10" rx="5" fill="#cbd5e1"/>
                            <rect x="400" y="250" width="100" height="10" rx="5" fill="#cbd5e1"/>
                            <rect x="400" y="270" width="80" height="10" rx="5" fill="#cbd5e1"/>
                        </svg>
                    </div>
                    <div class="about-content">
                        <h2>About Dumith Online Market</h2>
                        <p>Dumith Online Market is a modern online shopping platform designed to make shopping simple, convenient, and affordable. We bring together thousands of products from trusted sellers around the world.</p>
                        <p>Our mission is to provide an exceptional shopping experience with fast delivery, secure payments, and outstanding customer service. Whether you are looking for the latest electronics, trendy fashion, or everyday essentials, we have got you covered.</p>
                        <div class="stats-grid">
                            <div class="stat-item">
                                <div class="stat-number">10K+</div>
                                <div class="stat-label">Products</div>
                            </div>
                            <div class="stat-item">
                                <div class="stat-number">5K+</div>
                                <div class="stat-label">Happy Customers</div>
                            </div>
                            <div class="stat-item">
                                <div class="stat-number">1K+</div>
                                <div class="stat-label">Sellers</div>
                            </div>
                            <div class="stat-item">
                                <div class="stat-number">24/7</div>
                                <div class="stat-label">Customer Support</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="section contact-section" id="contactSection">
            <div class="container">
                <div class="section-header">
                    <span class="badge" style="background: #fce7f3; color: #db2777;">Get In Touch</span>
                    <h2>Contact Us</h2>
                    <p>We would love to hear from you. Reach out to us anytime.</p>
                </div>
                <div class="contact-grid">
                    <div class="contact-info">
                        <h3>Contact Information</h3>
                        <div class="contact-item">
                            <i class="fas fa-envelope"></i>
                            <div>
                                <h4>Email</h4>
                                <p>support@dumithmarket.com</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-phone"></i>
                            <div>
                                <h4>Phone</h4>
                                <p>+1 234 567 890</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <div>
                                <h4>Location</h4>
                                <p>123 Market Street, Commerce City, CC 10001</p>
                            </div>
                        </div>
                        <div class="social-links">
                            <a href="#"><i class="fab fa-facebook-f"></i></a>
                            <a href="#"><i class="fab fa-twitter"></i></a>
                            <a href="#"><i class="fab fa-instagram"></i></a>
                            <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        </div>
                    </div>
                    <form class="contact-form" id="contactForm" onsubmit="submitContact(event)">
                        <div class="form-row">
                            <div class="form-group">
                                <label>Your Name</label>
                                <input type="text" id="contactName" placeholder="John Doe">
                                <span class="error-msg">Please enter your name</span>
                            </div>
                            <div class="form-group">
                                <label>Your Email</label>
                                <input type="email" id="contactEmail" placeholder="john@example.com">
                                <span class="error-msg">Please enter a valid email</span>
                            </div>
                        </div>
                        <div class="form-group">
                            <label>Phone Number</label>
                            <input type="tel" id="contactPhone" placeholder="+1 234 567 890">
                        </div>
                        <div class="form-group">
                            <label>Message</label>
                            <textarea id="contactMessage" placeholder="How can we help you?"></textarea>
                            <span class="error-msg">Please enter your message</span>
                        </div>
                        <button type="submit" class="btn-submit">Send Message</button>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <!-- Checkout Section (Hidden by default) -->
    <section class="checkout-section hidden" id="checkoutSection">
        <div class="container">
            <div class="section-header">
                <h2>Checkout</h2>
                <p>Complete your order by filling in the details below</p>
            </div>
            <div class="checkout-grid">
                <div class="checkout-form">
                    <h3><i class="fas fa-user"></i> Customer Information</h3>
                    <div class="form-row">
                        <div class="form-group">
                            <label>Full Name *</label>
                            <input type="text" id="checkoutName" placeholder="John Doe">
                        </div>
                        <div class="form-group">
                            <label>Email *</label>
                            <input type="email" id="checkoutEmail" placeholder="john@example.com">
                        </div>
                    </div>
                    <div class="form-group">
                        <label>Phone Number *</label>
                        <input type="tel" id="checkoutPhone" placeholder="+1 234 567 890">
                    </div>

                    <h3 style="margin-top:32px;"><i class="fas fa-map-marker-alt"></i> Delivery Address</h3>
                    <div class="form-group">
                        <label>Address *</label>
                        <input type="text" id="checkoutAddress" placeholder="123 Main Street">
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label>City *</label>
                            <input type="text" id="checkoutCity" placeholder="New York">
                        </div>
                        <div class="form-group">
                            <label>Postal Code *</label>
                            <input type="text" id="checkoutPostal" placeholder="10001">
                        </div>
                    </div>
                    <div class="form-group">
                        <label>Country *</label>
                        <select id="checkoutCountry">
                            <option value="">Select Country</option>
                            <option value="US">United States</option>
                            <option value="UK">United Kingdom</option>
                            <option value="CA">Canada</option>
                            <option value="AU">Australia</option>
                            <option value="DE">Germany</option>
                            <option value="FR">France</option>
                            <option value="JP">Japan</option>
                            <option value="IN">India</option>
                            <option value="LK">Sri Lanka</option>
                            <option value="Other">Other</option>
                        </select>
                    </div>

                    <h3 style="margin-top:32px;"><i class="fas fa-credit-card"></i> Payment Method</h3>
                    <div class="payment-methods">
                        <label class="payment-method selected" onclick="selectPayment(this)">
                            <input type="radio" name="payment" value="cod" checked>
                            <i class="fas fa-money-bill-wave"></i>
                            <div>
                                <strong>Cash on Delivery</strong>
                                <p style="font-size:13px; color:var(--gray); margin:0;">Pay when you receive your order</p>
                            </div>
                        </label>
                        <label class="payment-method" onclick="selectPayment(this)">
                            <input type="radio" name="payment" value="card">
                            <i class="fas fa-credit-card"></i>
                            <div>
                                <strong>Credit / Debit Card</strong>
                                <p style="font-size:13px; color:var(--gray); margin:0;">Visa, Mastercard, Amex</p>
                            </div>
                        </label>
                        <label class="payment-method" onclick="selectPayment(this)">
                            <input type="radio" name="payment" value="online">
                            <i class="fas fa-mobile-alt"></i>
                            <div>
                                <strong>Online Payment</strong>
                                <p style="font-size:13px; color:var(--gray); margin:0;">PayPal, Apple Pay, Google Pay</p>
                            </div>
                        </label>
                    </div>

                    <button class="btn btn-primary" style="width:100%; justify-content:center;" onclick="placeOrder()">
                        <i class="fas fa-check-circle"></i> Place Order
                    </button>
                    <button class="btn btn-outline" style="width:100%; justify-content:center; margin-top:12px; color:var(--dark); border-color:var(--border);" onclick="showSection('shop')">
                        <i class="fas fa-arrow-left"></i> Continue Shopping
                    </button>
                </div>
                <div class="order-summary">
                    <h3>Order Summary</h3>
                    <div id="orderItems"></div>
                    <div class="order-totals">
                        <div class="order-total-row">
                            <span>Subtotal</span>
                            <span id="orderSubtotal">$0.00</span>
                        </div>
                        <div class="order-total-row">
                            <span>Shipping</span>
                            <span id="orderShipping">$0.00</span>
                        </div>
                        <div class="order-total-row">
                            <span>Tax</span>
                            <span id="orderTax">$0.00</span>
                        </div>
                        <div class="order-total-row final">
                            <span>Total</span>
                            <span id="orderTotal">$0.00</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer" id="footer">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-brand">
                    <a href="#" class="logo" onclick="showSection('home'); return false;">
                        <div class="logo-icon"><i class="fas fa-shopping-bag"></i></div>
                        Dumith <span>Market</span>
                    </a>
                    <p>Your one-stop destination for all your shopping needs. Quality products, great prices, and exceptional service.</p>
                </div>
                <div class="footer-column">
                    <h4>Quick Links</h4>
                    <ul>
                        <li><a href="#" onclick="showSection('home'); return false;">Home</a></li>
                        <li><a href="#" onclick="showSection('shop'); return false;">Shop</a></li>
                        <li><a href="#" onclick="showSection('categories'); return false;">Categories</a></li>
                        <li><a href="#" onclick="showSection('deals'); return false;">Deals</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h4>Customer Service</h4>
                    <ul>
                        <li><a href="#" onclick="showSection('about'); return false;">About Us</a></li>
                        <li><a href="#" onclick="showSection('contact'); return false;">Contact Us</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Terms of Service</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h4>My Account</h4>
                    <ul>
                        <li><a href="#" onclick="openAuth(); return false;">Login / Register</a></li>
                        <li><a href="#" onclick="openCart(); return false;">My Cart</a></li>
                        <li><a href="#" onclick="openWishlist(); return false;">My Wishlist</a></li>
                        <li><a href="#" onclick="showSection('shop'); return false;">Order History</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2024 Dumith Online Market. All rights reserved. Built with care.</p>
            </div>
        </div>
    </footer>

    <!-- Cart Sidebar -->
    <div class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h3><i class="fas fa-shopping-cart"></i> Shopping Cart</h3>
            <button class="cart-close" onclick="closeCart()"><i class="fas fa-times"></i></button>
        </div>
        <div class="cart-items" id="cartItems"></div>
        <div class="cart-footer">
            <div class="cart-summary">
                <div class="cart-summary-row">
                    <span>Subtotal</span>
                    <span id="cartSubtotal">$0.00</span>
                </div>
                <div class="cart-summary-row">
                    <span>Shipping</span>
                    <span id="cartShipping">$0.00</span>
                </div>
                <div class="cart-summary-row total">
                    <span>Total</span>
                    <span id="cartTotal">$0.00</span>
                </div>
            </div>
            <div class="cart-buttons">
                <button class="btn btn-primary" onclick="proceedToCheckout()">
                    <i class="fas fa-credit-card"></i> Checkout
                </button>
                <button class="btn btn-outline" style="color:var(--dark); border-color:var(--border);" onclick="closeCart()">
                    <i class="fas fa-arrow-left"></i> Continue Shopping
                </button>
                <button class="btn btn-outline" style="color:var(--danger); border-color:var(--danger);" onclick="clearCart()">
                    <i class="fas fa-trash"></i> Clear Cart
                </button>
            </div>
        </div>
    </div>

    <!-- Product Detail Modal -->
    <div class="modal-overlay" id="productModal">
        <div class="modal">
            <button class="modal-close" onclick="closeProductModal()"><i class="fas fa-times"></i></button>
            <div class="modal-content" id="productModalContent"></div>
        </div>
    </div>

    <!-- Wishlist Modal -->
    <div class="modal-overlay wishlist-modal" id="wishlistModal">
        <div class="modal">
            <button class="modal-close" onclick="closeWishlistModal()"><i class="fas fa-times"></i></button>
            <div class="modal-content">
                <h2 style="margin-bottom:24px;"><i class="fas fa-heart" style="color:var(--danger);"></i> My Wishlist</h2>
                <div id="wishlistItems"></div>
            </div>
        </div>
    </div>

    <!-- Auth Modal -->
    <div class="modal-overlay auth-modal" id="authModal">
        <div class="modal">
            <button class="modal-close" onclick="closeAuth()"><i class="fas fa-times"></i></button>
            <div class="modal-content">
                <div class="auth-tabs">
                    <button class="auth-tab active" onclick="switchAuthTab('login')">Login</button>
                    <button class="auth-tab" onclick="switchAuthTab('register')">Register</button>
                </div>
                <form class="auth-form active" id="loginForm" onsubmit="handleLogin(event)">
                    <div class="form-group">
                        <label>Email Address</label>
                        <input type="email" id="loginEmail" placeholder="you@example.com" required>
                    </div>
                    <div class="form-group">
                        <label>Password</label>
                        <input type="password" id="loginPassword" placeholder="Enter your password" required>
                    </div>
                    <div class="remember-forgot">
                        <label><input type="checkbox"> Remember Me</label>
                        <a href="#">Forgot Password?</a>
                    </div>
                    <button type="submit" class="btn-submit">Login</button>
                    <p class="text-center mt-4" style="color:var(--gray); font-size:14px;">Don't have an account? <a href="#" onclick="switchAuthTab('register'); return false;" style="color:var(--primary); text-decoration:none; font-weight:600;">Register</a></p>
                </form>
                <form class="auth-form" id="registerForm" onsubmit="handleRegister(event)">
                    <div class="form-group">
                        <label>Full Name</label>
                        <input type="text" id="regName" placeholder="John Doe" required>
                    </div>
                    <div class="form-group">
                        <label>Email Address</label>
                        <input type="email" id="regEmail" placeholder="you@example.com" required>
                    </div>
                    <div class="form-group">
                        <label>Password</label>
                        <input type="password" id="regPassword" placeholder="Create a password" required>
                    </div>
                    <div class="form-group">
                        <label>Confirm Password</label>
                        <input type="password" id="regConfirm" placeholder="Confirm your password" required>
                    </div>
                    <button type="submit" class="btn-submit">Create Account</button>
                    <p class="text-center mt-4" style="color:var(--gray); font-size:14px;">Already have an account? <a href="#" onclick="switchAuthTab('login'); return false;" style="color:var(--primary); text-decoration:none; font-weight:600;">Login</a></p>
                </form>
            </div>
        </div>
    </div>

    <!-- Success Overlay -->
    <div class="success-overlay" id="successOverlay">
        <div class="success-message">
            <div class="success-icon"><i class="fas fa-check"></i></div>
            <h2>Thank You!</h2>
            <p>Thank you for shopping with Dumith Online Market! Your order has been placed successfully.</p>
            <button class="btn btn-primary" onclick="closeSuccess()">Continue Shopping</button>
        </div>
    </div>

    <script>
        // ============================================
        // DUMITH ONLINE MARKET - COMPLETE JAVASCRIPT
        // ============================================

        // --- Product Database ---
        const products = [
            {
                id: 1, name: "iPhone 15 Pro Max", category: "Mobile Phones", brand: "Apple",
                price: 1199, oldPrice: 1299, rating: 4.8, reviews: 2450,
                image: "https://images.unsplash.com/photo-1696446701796-da61225697cc?w=400&h=400&fit=crop",
                badge: "hot", description: "The most powerful iPhone ever with A17 Pro chip, titanium design, and advanced camera system.",
                specs: { "Display": "6.7" Super Retina XDR", "Chip": "A17 Pro", "Storage": "256GB", "Camera": "48MP Main" },
                inStock: true, isNew: true
            },
            {
                id: 2, name: "Samsung Galaxy S24 Ultra", category: "Mobile Phones", brand: "Samsung",
                price: 1299, oldPrice: 1399, rating: 4.7, reviews: 1890,
                image: "https://images.unsplash.com/photo-1610945265078-3858a0828671?w=400&h=400&fit=crop",
                badge: "sale", description: "Experience the future with Galaxy AI, 200MP camera, and S Pen integration.",
                specs: { "Display": "6.8" Dynamic AMOLED", "Chip": "Snapdragon 8 Gen 3", "Storage": "512GB", "Camera": "200MP Main" },
                inStock: true, isNew: true
            },
            {
                id: 3, name: "HP Pavilion Laptop", category: "Computers & Laptops", brand: "HP",
                price: 799, oldPrice: 999, rating: 4.5, reviews: 876,
                image: "https://images.unsplash.com/photo-1496181133206-80ce9b88a853?w=400&h=400&fit=crop",
                badge: "sale", description: "Powerful performance for work and play with Intel Core i7 and 16GB RAM.",
                specs: { "Display": "15.6" FHD", "Processor": "Intel Core i7", "RAM": "16GB", "Storage": "512GB SSD" },
                inStock: true, isNew: false
            },
            {
                id: 4, name: "Sony WH-1000XM5", category: "Electronics", brand: "Sony",
                price: 348, oldPrice: 399, rating: 4.6, reviews: 3200,
                image: "https://images.unsplash.com/photo-1618366712010-f4ae9c647dcb?w=400&h=400&fit=crop",
                badge: "hot", description: "Industry-leading noise cancellation with exceptional sound quality.",
                specs: { "Type": "Over-ear", "Battery": "30 hours", "Weight": "250g", "Connectivity": "Bluetooth 5.2" },
                inStock: true, isNew: false
            },
            {
                id: 5, name: "Apple Watch Series 9", category: "Electronics", brand: "Apple",
                price: 399, oldPrice: 429, rating: 4.7, reviews: 1540,
                image: "https://images.unsplash.com/photo-1546868871-7041f2a55e12?w=400&h=400&fit=crop",
                badge: "new", description: "Advanced health features, brighter display, and powerful S9 chip.",
                specs: { "Display": "45mm Always-On", "Chip": "S9 SiP", "Battery": "18 hours", "Water Resistance": "50m" },
                inStock: true, isNew: true
            },
            {
                id: 6, name: "Nike Air Max 270", category: "Shoes", brand: "Nike",
                price: 150, oldPrice: 180, rating: 4.4, reviews: 2100,
                image: "https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=400&h=400&fit=crop",
                badge: "sale", description: "Iconic style with maximum Air cushioning for all-day comfort.",
                specs: { "Type": "Running", "Upper": "Mesh", "Sole": "Rubber", "Weight": "300g" },
                inStock: true, isNew: false
            },
            {
                id: 7, name: "JBL Flip 6 Speaker", category: "Electronics", brand: "JBL",
                price: 129, oldPrice: 149, rating: 4.5, reviews: 980,
                image: "https://images.unsplash.com/photo-1608043152269-423dbba4e7e1?w=400&h=400&fit=crop",
                badge: "hot", description: "Bold sound for every adventure with 12 hours of playtime.",
                specs: { "Power": "30W", "Battery": "12 hours", "Waterproof": "IP67", "Weight": "550g" },
                inStock: true, isNew: false
            },
            {
                id: 8, name: "Ergonomic Office Chair", category: "Furniture", brand: "Herman Miller",
                price: 499, oldPrice: 699, rating: 4.6, reviews: 432,
                image: "https://images.unsplash.com/photo-1505843490538-5133c6c7d0e1?w=400&h=400&fit=crop",
                badge: "sale", description: "Premium ergonomic design for maximum comfort during long work hours.",
                specs: { "Material": "Mesh", "Adjustable": "Height, Armrest", "Weight Capacity": "150kg", "Warranty": "12 years" },
                inStock: true, isNew: false
            },
            {
                id: 9, name: "NutriBullet Pro Blender", category: "Home & Kitchen", brand: "NutriBullet",
                price: 89, oldPrice: 119, rating: 4.3, reviews: 5600,
                image: "https://images.unsplash.com/photo-1570222094114-d054a817e56b?w=400&h=400&fit=crop",
                badge: "hot", description: "900-watt power for smooth blends, nut butters, and more.",
                specs: { "Power": "900W", "Capacity": "32oz", "Speeds": "1", "Dishwasher Safe": "Yes" },
                inStock: true, isNew: false
            },
            {
                id: 10, name: "Canon EOS R6 Camera", category: "Electronics", brand: "Canon",
                price: 2499, oldPrice: 2799, rating: 4.8, reviews: 320,
                image: "https://images.unsplash.com/photo-1516035069371-29a1b244cc32?w=400&h=400&fit=crop",
                badge: "new", description: "Professional full-frame mirrorless camera with 20fps burst shooting.",
                specs: { "Sensor": "20MP Full Frame", "Video": "4K 60fps", "ISO": "100-102400", "Weight": "680g" },
                inStock: true, isNew: true
            },
            {
                id: 11, name: "Levi's Denim Jacket", category: "Fashion", brand: "Levi's",
                price: 89, oldPrice: 120, rating: 4.2, reviews: 780,
                image: "https://images.unsplash.com/photo-1551028719-00167b16eac5?w=400&h=400&fit=crop",
                badge: "sale", description: "Classic denim jacket with modern fit and premium quality.",
                specs: { "Material": "100% Cotton", "Fit": "Regular", "Care": "Machine Wash", "Origin": "Imported" },
                inStock: true, isNew: false
            },
            {
                id: 12, name: "Dyson V15 Vacuum", category: "Home & Kitchen", brand: "Dyson",
                price: 699, oldPrice: 799, rating: 4.7, reviews: 890,
                image: "https://images.unsplash.com/photo-1558317374-067fb5f30001?w=400&h=400&fit=crop",
                badge: "hot", description: "Laser detect technology reveals microscopic dust for a deeper clean.",
                specs: { "Suction": "230AW", "Battery": "60 minutes", "Weight": "3.1kg", "Bin Capacity": "0.77L" },
                inStock: true, isNew: true
            },
            {
                id: 13, name: "Adidas Ultraboost 22", category: "Shoes", brand: "Adidas",
                price: 180, oldPrice: 190, rating: 4.5, reviews: 1200,
                image: "https://images.unsplash.com/photo-1587563871167-1ee9c731aefb?w=400&h=400&fit=crop",
                badge: "new", description: "Ultimate energy return with Primeknit+ upper for adaptive fit.",
                specs: { "Type": "Running", "Upper": "Primeknit+", "Midsole": "Boost", "Weight": "310g" },
                inStock: true, isNew: true
            },
            {
                id: 14, name: "MacBook Air M3", category: "Computers & Laptops", brand: "Apple",
                price: 1099, oldPrice: 1199, rating: 4.9, reviews: 2100,
                image: "https://images.unsplash.com/photo-1517336714731-489689fd1ca8?w=400&h=400&fit=crop",
                badge: "new", description: "Supercharged by M3 chip with up to 18 hours of battery life.",
                specs: { "Display": "13.6" Liquid Retina", "Chip": "Apple M3", "RAM": "8GB", "Storage": "256GB" },
                inStock: true, isNew: true
            },
            {
                id: 15, name: "Ray-Ban Aviator Sunglasses", category: "Accessories", brand: "Ray-Ban",
                price: 154, oldPrice: 180, rating: 4.6, reviews: 3400,
                image: "https://images.unsplash.com/photo-1572635196237-14b3f281503f?w=400&h=400&fit=crop",
                badge: "sale", description: "Timeless aviator style with premium UV protection lenses.",
                specs: { "Frame": "Metal", "Lens": "Glass", "UV Protection": "100%", "Case": "Included" },
                inStock: true, isNew: false
            },
            {
                id: 16, name: "Organic Green Tea Set", category: "Grocery", brand: "Twinings",
                price: 24, oldPrice: 32, rating: 4.3, reviews: 560,
                image: "https://images.unsplash.com/photo-1564890369478-c89ca6d9cde9?w=400&h=400&fit=crop",
                badge: "sale", description: "Premium organic green tea collection with 6 unique flavors.",
                specs: { "Quantity": "60 bags", "Type": "Organic", "Origin": "Japan", "Caffeine": "Low" },
                inStock: true, isNew: false
            },
            {
                id: 17, name: "Wilson Tennis Racket", category: "Sports", brand: "Wilson",
                price: 199, oldPrice: 249, rating: 4.4, reviews: 320,
                image: "https://images.unsplash.com/photo-1622279457486-62dcc4a431d6?w=400&h=400&fit=crop",
                badge: "hot", description: "Professional grade racket with enhanced power and control.",
                specs: { "Weight": "300g", "Head Size": "100 sq in", "String Pattern": "16x19", "Grip": "4 3/8" },
                inStock: true, isNew: false
            },
            {
                id: 18, name: "L'Oreal Paris Serum", category: "Beauty", brand: "L'Oreal",
                price: 35, oldPrice: 45, rating: 4.2, reviews: 2100,
                image: "https://images.unsplash.com/photo-1620916566398-39f1143ab7be?w=400&h=400&fit=crop",
                badge: "sale", description: "Revitalift anti-aging serum with hyaluronic acid for youthful skin.",
                specs: { "Volume": "30ml", "Type": "Serum", "Skin Type": "All", "Cruelty Free": "Yes" },
                inStock: true, isNew: false
            },
            {
                id: 19, name: "Logitech MX Master 3S", category: "Accessories", brand: "Logitech",
                price: 99, oldPrice: 119, rating: 4.8, reviews: 4500,
                image: "https://images.unsplash.com/photo-1527864550417-7fd91fc51a46?w=400&h=400&fit=crop",
                badge: "hot", description: "Ultra-fast scrolling, 8K DPI, and ergonomic design for productivity.",
                specs: { "DPI": "8000", "Buttons": "7", "Battery": "70 days", "Connection": "Bluetooth/USB" },
                inStock: true, isNew: false
            },
            {
                id: 20, name: "Yoga Mat Premium", category: "Sports", brand: "Liforme",
                price: 120, oldPrice: 140, rating: 4.7, reviews: 890,
                image: "https://images.unsplash.com/photo-1601925260368-ae2f83cf8b7f?w=400&h=400&fit=crop",
                badge: "new", description: "Eco-friendly yoga mat with alignment markers and superior grip.",
                specs: { "Material": "Natural Rubber", "Thickness": "4.2mm", "Size": "185x68cm", "Weight": "2.5kg" },
                inStock: true, isNew: true
            }
        ];

        // --- Categories Data ---
        const categories = [
            { name: "Electronics", icon: "fas fa-tv" },
            { name: "Mobile Phones", icon: "fas fa-mobile-alt" },
            { name: "Computers & Laptops", icon: "fas fa-laptop" },
            { name: "Fashion", icon: "fas fa-tshirt" },
            { name: "Shoes", icon: "fas fa-shoe-prints" },
            { name: "Beauty", icon: "fas fa-spa" },
            { name: "Home & Kitchen", icon: "fas fa-home" },
            { name: "Furniture", icon: "fas fa-couch" },
            { name: "Sports", icon: "fas fa-running" },
            { name: "Accessories", icon: "fas fa-glasses" },
            { name: "Grocery", icon: "fas fa-shopping-basket" },
            { name: "Other", icon: "fas fa-ellipsis-h" }
        ];

        // --- Reviews Data ---
        const reviews = [
            { name: "Sarah Johnson", avatar: "https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=100&h=100&fit=crop", rating: 5, text: "Absolutely love shopping here! The products are top quality and delivery was super fast. Will definitely be coming back for more." },
            { name: "Michael Chen", avatar: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=100&h=100&fit=crop", rating: 5, text: "Best online marketplace I have used. Great prices, excellent customer service, and the website is so easy to navigate." },
            { name: "Emily Davis", avatar: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=100&h=100&fit=crop", rating: 4, text: "Found everything I needed in one place. The deals section is amazing - saved so much on my last purchase!" },
            { name: "James Wilson", avatar: "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=100&h=100&fit=crop", rating: 5, text: "The product quality exceeded my expectations. Packaging was secure and shipping was faster than promised. Highly recommend!" },
            { name: "Aisha Patel", avatar: "https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=100&h=100&fit=crop", rating: 5, text: "Dumith Market has become my go-to for all online shopping. The wishlist feature and cart persistence are game changers!" },
            { name: "David Kim", avatar: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=100&h=100&fit=crop", rating: 4, text: "Great variety of products at competitive prices. The filtering system makes it so easy to find exactly what I want." }
        ];

        // --- State Management ---
        let cart = JSON.parse(localStorage.getItem('dumith_cart')) || [];
        let wishlist = JSON.parse(localStorage.getItem('dumith_wishlist')) || [];
        let currentFilters = { categories: [], minPrice: 0, maxPrice: Infinity, rating: 0, brands: [], inStock: null };
        let currentSort = 'featured';
        let reviewSlideIndex = 0;

        // --- Initialization ---
        document.addEventListener('DOMContentLoaded', () => {
            renderCategories();
            renderDeals();
            renderProducts();
            renderNewArrivals();
            renderReviews();
            renderFilters();
            updateCartCount();
            updateWishlistCount();
            startCountdown();
            initScrollHeader();
            initSearchListener();
        });

        // --- Header Scroll Effect ---
        function initScrollHeader() {
            window.addEventListener('scroll', () => {
                document.getElementById('header').classList.toggle('scrolled', window.scrollY > 50);
            });
        }

        // --- Search ---
        function initSearchListener() {
            document.getElementById('searchInput').addEventListener('input', (e) => {
                const query = e.target.value.toLowerCase();
                if (query.length > 0) {
                    showSection('shop');
                }
                renderProducts(query);
            });
        }

        function performSearch() {
            const query = document.getElementById('searchInput').value.toLowerCase();
            showSection('shop');
            renderProducts(query);
        }

        // --- Section Navigation ---
        function showSection(section) {
            const sections = ['heroSection', 'categoriesSection', 'dealsSection', 'shopSection', 'newArrivalsSection', 'reviewsSection', 'aboutSection', 'contactSection', 'checkoutSection'];
            sections.forEach(s => {
                const el = document.getElementById(s);
                if (el) el.classList.add('hidden');
            });

            const footer = document.getElementById('footer');
            const headerTop = document.querySelector('.header-top');

            if (section === 'home') {
                ['heroSection', 'categoriesSection', 'dealsSection', 'shopSection', 'newArrivalsSection', 'reviewsSection', 'aboutSection', 'contactSection'].forEach(s => {
                    const el = document.getElementById(s);
                    if (el) el.classList.remove('hidden');
                });
                footer.classList.remove('hidden');
                headerTop.classList.remove('hidden');
                window.scrollTo({ top: 0, behavior: 'smooth' });
            } else if (section === 'shop') {
                document.getElementById('shopSection').classList.remove('hidden');
                footer.classList.remove('hidden');
                headerTop.classList.remove('hidden');
                document.getElementById('shopSection').scrollIntoView({ behavior: 'smooth' });
            } else if (section === 'categories') {
                document.getElementById('categoriesSection').classList.remove('hidden');
                footer.classList.remove('hidden');
                headerTop.classList.remove('hidden');
                document.getElementById('categoriesSection').scrollIntoView({ behavior: 'smooth' });
            } else if (section === 'deals') {
                document.getElementById('dealsSection').classList.remove('hidden');
                footer.classList.remove('hidden');
                headerTop.classList.remove('hidden');
                document.getElementById('dealsSection').scrollIntoView({ behavior: 'smooth' });
            } else if (section === 'about') {
                document.getElementById('aboutSection').classList.remove('hidden');
                footer.classList.remove('hidden');
                headerTop.classList.remove('hidden');
                document.getElementById('aboutSection').scrollIntoView({ behavior: 'smooth' });
            } else if (section === 'contact') {
                document.getElementById('contactSection').classList.remove('hidden');
                footer.classList.remove('hidden');
                headerTop.classList.remove('hidden');
                document.getElementById('contactSection').scrollIntoView({ behavior: 'smooth' });
            } else if (section === 'checkout') {
                document.getElementById('checkoutSection').classList.remove('hidden');
                footer.classList.add('hidden');
                headerTop.classList.add('hidden');
                window.scrollTo({ top: 0, behavior: 'smooth' });
                renderCheckoutSummary();
            }

            // Update nav links
            document.querySelectorAll('.nav-link').forEach(link => link.classList.remove('active'));
            const activeLink = document.querySelector(`.nav-link[onclick*="'${section}'"]`);
            if (activeLink) activeLink.classList.add('active');
        }

        // --- Categories ---
        function renderCategories() {
            const grid = document.getElementById('categoriesGrid');
            grid.innerHTML = categories.map(cat => `
                <div class="category-card" onclick="filterByCategory('${cat.name}')">
                    <div class="category-icon"><i class="${cat.icon}"></i></div>
                    <h3>${cat.name}</h3>
                </div>
            `).join('');
        }

        function filterByCategory(category) {
            currentFilters.categories = [category];
            showSection('shop');
            renderProducts();
            document.querySelectorAll('#categoryFilters input').forEach(cb => {
                cb.checked = cb.value === category;
            });
        }

        // --- Deals ---
        function renderDeals() {
            const deals = products.filter(p => p.badge === 'sale').slice(0, 4);
            const grid = document.getElementById('dealsGrid');
            grid.innerHTML = deals.map(product => `
                <div class="deal-card">
                    <span class="deal-badge">-${Math.round((1 - product.price / product.oldPrice) * 100)}%</span>
                    <img src="${product.image}" alt="${product.name}" class="deal-image">
                    <div class="deal-content">
                        <h3>${product.name}</h3>
                        <div class="deal-prices">
                            <span class="deal-price">$${product.price}</span>
                            <span class="deal-old-price">$${product.oldPrice}</span>
                        </div>
                        <div class="countdown" id="countdown-${product.id}">
                            <div class="countdown-item"><span class="number" id="hours-${product.id}">04</span><span class="label">HRS</span></div>
                            <div class="countdown-item"><span class="number" id="mins-${product.id}">32</span><span class="label">MIN</span></div>
                            <div class="countdown-item"><span class="number" id="secs-${product.id}">15</span><span class="label">SEC</span></div>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        function startCountdown() {
            setInterval(() => {
                products.filter(p => p.badge === 'sale').forEach(product => {
                    const hoursEl = document.getElementById(`hours-${product.id}`);
                    const minsEl = document.getElementById(`mins-${product.id}`);
                    const secsEl = document.getElementById(`secs-${product.id}`);
                    if (!hoursEl) return;

                    let h = parseInt(hoursEl.textContent);
                    let m = parseInt(minsEl.textContent);
                    let s = parseInt(secsEl.textContent);

                    s--;
                    if (s < 0) { s = 59; m--; }
                    if (m < 0) { m = 59; h--; }
                    if (h < 0) { h = 23; }

                    hoursEl.textContent = String(h).padStart(2, '0');
                    minsEl.textContent = String(m).padStart(2, '0');
                    secsEl.textContent = String(s).padStart(2, '0');
                });
            }, 1000);
        }

        // --- Products ---
        function getFilteredProducts(searchQuery = '') {
            let filtered = [...products];

            // Search filter
            if (searchQuery) {
                filtered = filtered.filter(p =>
                    p.name.toLowerCase().includes(searchQuery) ||
                    p.category.toLowerCase().includes(searchQuery) ||
                    p.brand.toLowerCase().includes(searchQuery)
                );
            }

            // Category filter
            if (currentFilters.categories.length > 0) {
                filtered = filtered.filter(p => currentFilters.categories.includes(p.category));
            }

            // Price filter
            if (currentFilters.minPrice > 0) {
                filtered = filtered.filter(p => p.price >= currentFilters.minPrice);
            }
            if (currentFilters.maxPrice < Infinity) {
                filtered = filtered.filter(p => p.price <= currentFilters.maxPrice);
            }

            // Rating filter
            if (currentFilters.rating > 0) {
                filtered = filtered.filter(p => p.rating >= currentFilters.rating);
            }

            // Brand filter
            if (currentFilters.brands.length > 0) {
                filtered = filtered.filter(p => currentFilters.brands.includes(p.brand));
            }

            // Availability filter
            if (currentFilters.inStock !== null) {
                filtered = filtered.filter(p => p.inStock === currentFilters.inStock);
            }

            // Sort
            switch (currentSort) {
                case 'price-low': filtered.sort((a, b) => a.price - b.price); break;
                case 'price-high': filtered.sort((a, b) => b.price - a.price); break;
                case 'rating': filtered.sort((a, b) => b.rating - a.rating); break;
                case 'newest': filtered.sort((a, b) => (b.isNew ? 1 : 0) - (a.isNew ? 1 : 0)); break;
            }

            return filtered;
        }

        function renderProducts(searchQuery = '') {
            const filtered = getFilteredProducts(searchQuery);
            const grid = document.getElementById('productsGrid');
            const countEl = document.getElementById('productsCount');

            countEl.textContent = `Showing ${filtered.length} product${filtered.length !== 1 ? 's' : ''}`;

            if (filtered.length === 0) {
                grid.innerHTML = `
                    <div class="no-products">
                        <i class="fas fa-search"></i>
                        <h3>No products found</h3>
                        <p>Try adjusting your filters or search query</p>
                    </div>
                `;
                return;
            }

            grid.innerHTML = filtered.map(product => createProductCard(product)).join('');
        }

        function createProductCard(product) {
            const discount = product.oldPrice ? Math.round((1 - product.price / product.oldPrice) * 100) : 0;
            const inWishlist = wishlist.includes(product.id);

            return `
                <div class="product-card">
                    <div class="product-image-wrap">
                        <img src="${product.image}" alt="${product.name}" class="product-image" loading="lazy">
                        <div class="product-badges">
                            ${product.badge === 'sale' ? `<span class="product-badge badge-sale">-${discount}%</span>` : ''}
                            ${product.isNew ? `<span class="product-badge badge-new">NEW</span>` : ''}
                            ${product.badge === 'hot' ? `<span class="product-badge badge-hot">HOT</span>` : ''}
                        </div>
                        <button class="wishlist-btn ${inWishlist ? 'active' : ''}" onclick="toggleWishlist(${product.id})">
                            <i class="${inWishlist ? 'fas' : 'far'} fa-heart"></i>
                        </button>
                        <div class="product-actions">
                            <button class="product-action-btn btn-add-cart" onclick="addToCart(${product.id})">
                                <i class="fas fa-cart-plus"></i> Add
                            </button>
                            <button class="product-action-btn btn-view" onclick="openProductDetail(${product.id})">
                                <i class="fas fa-eye"></i> View
                            </button>
                        </div>
                    </div>
                    <div class="product-info">
                        <div class="product-category">${product.category}</div>
                        <h3 class="product-name">${product.name}</h3>
                        <div class="product-rating">
                            <span class="stars">${'★'.repeat(Math.floor(product.rating))}${product.rating % 1 >= 0.5 ? '½' : ''}</span>
                            <span class="rating-count">(${product.reviews.toLocaleString()})</span>
                        </div>
                        <div class="product-price">
                            <span class="current-price">$${product.price}</span>
                            ${product.oldPrice ? `<span class="old-price">$${product.oldPrice}</span>` : ''}
                            ${discount > 0 ? `<span class="discount">-${discount}%</span>` : ''}
                        </div>
                    </div>
                </div>
            `;
        }

        function renderNewArrivals() {
            const newProducts = products.filter(p => p.isNew).slice(0, 4);
            const grid = document.getElementById('newArrivalsGrid');
            grid.innerHTML = newProducts.map(product => createProductCard(product)).join('');
        }

        // --- Filters ---
        function renderFilters() {
            // Category filters
            const catFilters = document.getElementById('categoryFilters');
            const uniqueCategories = [...new Set(products.map(p => p.category))];
            catFilters.innerHTML = uniqueCategories.map(cat => `
                <label class="filter-option">
                    <input type="checkbox" value="${cat}" onchange="toggleCategoryFilter('${cat}')">
                    ${cat}
                </label>
            `).join('');

            // Rating filters
            const ratingFilters = document.getElementById('ratingFilters');
            ratingFilters.innerHTML = [4, 3, 2, 1].map(r => `
                <label class="filter-option">
                    <input type="radio" name="rating" value="${r}" onchange="setRatingFilter(${r})">
                    ${'★'.repeat(r)} & Up
                </label>
            `).join('');

            // Brand filters
            const brandFilters = document.getElementById('brandFilters');
            const uniqueBrands = [...new Set(products.map(p => p.brand))];
            brandFilters.innerHTML = uniqueBrands.map(brand => `
                <label class="filter-option">
                    <input type="checkbox" value="${brand}" onchange="toggleBrandFilter('${brand}')">
                    ${brand}
                </label>
            `).join('');

            // Availability filters
            const availFilters = document.getElementById('availabilityFilters');
            availFilters.innerHTML = `
                <label class="filter-option">
                    <input type="radio" name="stock" value="true" onchange="setStockFilter(true)">
                    In Stock
                </label>
                <label class="filter-option">
                    <input type="radio" name="stock" value="false" onchange="setStockFilter(false)">
                    Out of Stock
                </label>
            `;
        }

        function toggleCategoryFilter(category) {
            const idx = currentFilters.categories.indexOf(category);
            if (idx > -1) currentFilters.categories.splice(idx, 1);
            else currentFilters.categories.push(category);
            renderProducts();
        }

        function applyPriceFilter() {
            const min = parseFloat(document.getElementById('minPrice').value) || 0;
            const max = parseFloat(document.getElementById('maxPrice').value) || Infinity;
            currentFilters.minPrice = min;
            currentFilters.maxPrice = max;
            renderProducts();
        }

        function setRatingFilter(rating) {
            currentFilters.rating = rating;
            renderProducts();
        }

        function toggleBrandFilter(brand) {
            const idx = currentFilters.brands.indexOf(brand);
            if (idx > -1) currentFilters.brands.splice(idx, 1);
            else currentFilters.brands.push(brand);
            renderProducts();
        }

        function setStockFilter(inStock) {
            currentFilters.inStock = inStock;
            renderProducts();
        }

        function sortProducts() {
            currentSort = document.getElementById('sortSelect').value;
            renderProducts();
        }

        // --- Product Detail Modal ---
        function openProductDetail(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            const discount = product.oldPrice ? Math.round((1 - product.price / product.oldPrice) * 100) : 0;
            const inWishlist = wishlist.includes(productId);

            document.getElementById('productModalContent').innerHTML = `
                <div class="product-detail">
                    <div class="product-detail-image">
                        <img src="${product.image}" alt="${product.name}">
                    </div>
                    <div class="product-detail-info">
                        <div class="product-category">${product.category}</div>
                        <h2>${product.name}</h2>
                        <div class="product-detail-rating">
                            <span class="stars">${'★'.repeat(Math.floor(product.rating))}</span>
                            <span>${product.rating} (${product.reviews.toLocaleString()} reviews)</span>
                        </div>
                        <div class="product-detail-price">
                            <span class="detail-price">$${product.price}</span>
                            ${product.oldPrice ? `<span class="detail-old-price">$${product.oldPrice}</span>` : ''}
                            ${discount > 0 ? `<span class="detail-discount">-${discount}% OFF</span>` : ''}
                        </div>
                        <p class="product-detail-desc">${product.description}</p>
                        <div class="product-specs">
                            <h4>Specifications</h4>
                            <div class="specs-list">
                                ${Object.entries(product.specs).map(([k, v]) => `<div class="spec-item"><strong>${k}:</strong> ${v}</div>`).join('')}
                            </div>
                        </div>
                        <div class="quantity-selector">
                            <label>Quantity:</label>
                            <button class="qty-btn" onclick="adjustDetailQty(-1)">-</button>
                            <input type="number" class="qty-input" id="detailQty" value="1" min="1" max="10">
                            <button class="qty-btn" onclick="adjustDetailQty(1)">+</button>
                        </div>
                        <div class="detail-actions">
                            <button class="btn btn-primary" onclick="addToCartFromDetail(${product.id})">
                                <i class="fas fa-cart-plus"></i> Add to Cart
                            </button>
                            <button class="btn btn-secondary" onclick="buyNow(${product.id})">
                                <i class="fas fa-bolt"></i> Buy Now
                            </button>
                            <button class="btn btn-outline" style="color:${inWishlist ? 'var(--danger)' : 'var(--dark)'}; border-color:${inWishlist ? 'var(--danger)' : 'var(--border)'}" onclick="toggleWishlist(${product.id})">
                                <i class="${inWishlist ? 'fas' : 'far'} fa-heart"></i>
                            </button>
                        </div>
                        <p style="margin-top:16px; font-size:13px; color:var(--gray);">
                            <i class="fas fa-store"></i> Sold by <strong>${product.brand} Official Store</strong> &nbsp;|&nbsp;
                            <i class="fas fa-check-circle"></i> ${product.inStock ? 'In Stock' : 'Out of Stock'}
                        </p>
                    </div>
                </div>
            `;

            document.getElementById('productModal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeProductModal() {
            document.getElementById('productModal').classList.remove('active');
            document.body.style.overflow = '';
        }

        function adjustDetailQty(delta) {
            const input = document.getElementById('detailQty');
            let val = parseInt(input.value) + delta;
            if (val < 1) val = 1;
            if (val > 10) val = 10;
            input.value = val;
        }

        function addToCartFromDetail(productId) {
            const qty = parseInt(document.getElementById('detailQty').value) || 1;
            for (let i = 0; i < qty; i++) {
                addToCart(productId, false);
            }
            closeProductModal();
            showToast(`${qty} item(s) added to cart`, 'success');
        }

        function buyNow(productId) {
            addToCart(productId);
            closeProductModal();
            openCart();
        }

        // --- Cart ---
        function addToCart(productId, showNotification = true) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            const existingItem = cart.find(item => item.id === productId);
            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({ ...product, quantity: 1 });
            }

            saveCart();
            updateCartCount();
            renderCartItems();
            if (showNotification) showToast('Product added to cart', 'success');
        }

        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            saveCart();
            updateCartCount();
            renderCartItems();
            showToast('Product removed from cart', 'warning');
        }

        function updateCartQty(productId, delta) {
            const item = cart.find(item => item.id === productId);
            if (!item) return;

            item.quantity += delta;
            if (item.quantity <= 0) {
                removeFromCart(productId);
                return;
            }

            saveCart();
            updateCartCount();
            renderCartItems();
        }

        function clearCart() {
            cart = [];
            saveCart();
            updateCartCount();
            renderCartItems();
            showToast('Cart cleared', 'warning');
        }

        function saveCart() {
            localStorage.setItem('dumith_cart', JSON.stringify(cart));
        }

        function updateCartCount() {
            const count = cart.reduce((sum, item) => sum + item.quantity, 0);
            document.getElementById('cartCount').textContent = count;
        }

        function renderCartItems() {
            const container = document.getElementById('cartItems');
            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="cart-empty">
                        <i class="fas fa-shopping-cart"></i>
                        <h4>Your cart is empty</h4>
                        <p>Add some products to get started</p>
                        <button class="btn btn-primary" onclick="closeCart(); showSection('shop');">
                            Start Shopping
                        </button>
                    </div>
                `;
                document.getElementById('cartSubtotal').textContent = '$0.00';
                document.getElementById('cartShipping').textContent = '$0.00';
                document.getElementById('cartTotal').textContent = '$0.00';
                return;
            }

            container.innerHTML = cart.map(item => `
                <div class="cart-item">
                    <img src="${item.image}" alt="${item.name}" class="cart-item-image">
                    <div class="cart-item-details">
                        <div class="cart-item-name">${item.name}</div>
                        <div class="cart-item-price">$${item.price}</div>
                        <div class="cart-item-qty">
                            <button onclick="updateCartQty(${item.id}, -1)">-</button>
                            <span>${item.quantity}</span>
                            <button onclick="updateCartQty(${item.id}, 1)">+</button>
                        </div>
                    </div>
                    <button class="cart-item-remove" onclick="removeFromCart(${item.id})">
                        <i class="fas fa-trash"></i>
                    </button>
                </div>
            `).join('');

            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const shipping = subtotal > 50 ? 0 : 9.99;
            const total = subtotal + shipping;

            document.getElementById('cartSubtotal').textContent = `$${subtotal.toFixed(2)}`;
            document.getElementById('cartShipping').textContent = shipping === 0 ? 'FREE' : `$${shipping.toFixed(2)}`;
            document.getElementById('cartTotal').textContent = `$${total.toFixed(2)}`;
        }

        function openCart() {
            renderCartItems();
            document.getElementById('cartSidebar').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeCart() {
            document.getElementById('cartSidebar').classList.remove('active');
            document.body.style.overflow = '';
        }

        function proceedToCheckout() {
            if (cart.length === 0) {
                showToast('Your cart is empty', 'error');
                return;
            }
            closeCart();
            showSection('checkout');
        }

        // --- Wishlist ---
        function toggleWishlist(productId) {
            const idx = wishlist.indexOf(productId);
            if (idx > -1) {
                wishlist.splice(idx, 1);
                showToast('Removed from wishlist', 'warning');
            } else {
                wishlist.push(productId);
                showToast('Added to wishlist', 'success');
            }
            saveWishlist();
            updateWishlistCount();
            renderProducts();
            renderNewArrivals();

            // Update wishlist modal if open
            if (document.getElementById('wishlistModal').classList.contains('active')) {
                renderWishlistItems();
            }
        }

        function saveWishlist() {
            localStorage.setItem('dumith_wishlist', JSON.stringify(wishlist));
        }

        function updateWishlistCount() {
            document.getElementById('wishlistCount').textContent = wishlist.length;
        }

        function openWishlist() {
            renderWishlistItems();
            document.getElementById('wishlistModal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeWishlistModal() {
            document.getElementById('wishlistModal').classList.remove('active');
            document.body.style.overflow = '';
        }

        function renderWishlistItems() {
            const container = document.getElementById('wishlistItems');
            if (wishlist.length === 0) {
                container.innerHTML = `
                    <div class="text-center" style="padding:40px;">
                        <i class="far fa-heart" style="font-size:48px; color:var(--border);"></i>
                        <h4 style="margin-top:16px;">Your wishlist is empty</h4>
                        <p style="color:var(--gray);">Save items you love for later</p>
                        <button class="btn btn-primary mt-4" onclick="closeWishlistModal(); showSection('shop');">
                            Browse Products
                        </button>
                    </div>
                `;
                return;
            }

            container.innerHTML = wishlist.map(id => {
                const product = products.find(p => p.id === id);
                if (!product) return '';
                return `
                    <div class="wishlist-item">
                        <img src="${product.image}" alt="${product.name}">
                        <div class="wishlist-item-info">
                            <h4>${product.name}</h4>
                            <span class="price">$${product.price}</span>
                        </div>
                        <div class="wishlist-actions">
                            <button class="btn btn-primary" style="padding:8px 16px; font-size:13px;" onclick="addToCart(${product.id}); toggleWishlist(${product.id});">
                                <i class="fas fa-cart-plus"></i> Move to Cart
                            </button>
                            <button class="btn btn-outline" style="padding:8px 16px; font-size:13px; color:var(--danger); border-color:var(--danger);" onclick="toggleWishlist(${product.id})">
                                <i class="fas fa-trash"></i>
                            </button>
                        </div>
                    </div>
                `;
            }).join('');
        }

        // --- Checkout ---
        function renderCheckoutSummary() {
            const container = document.getElementById('orderItems');
            container.innerHTML = cart.map(item => `
                <div class="order-item">
                    <img src="${item.image}" alt="${item.name}">
                    <div class="order-item-info">
                        <h4>${item.name}</h4>
                        <p>Qty: ${item.quantity}</p>
                    </div>
                    <span class="order-item-price">$${(item.price * item.quantity).toFixed(2)}</span>
                </div>
            `).join('');

            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const shipping = subtotal > 50 ? 0 : 9.99;
            const tax = subtotal * 0.08;
            const total = subtotal + shipping + tax;

            document.getElementById('orderSubtotal').textContent = `$${subtotal.toFixed(2)}`;
            document.getElementById('orderShipping').textContent = shipping === 0 ? 'FREE' : `$${shipping.toFixed(2)}`;
            document.getElementById('orderTax').textContent = `$${tax.toFixed(2)}`;
            document.getElementById('orderTotal').textContent = `$${total.toFixed(2)}`;
        }

        function selectPayment(el) {
            document.querySelectorAll('.payment-method').forEach(pm => pm.classList.remove('selected'));
            el.classList.add('selected');
            el.querySelector('input').checked = true;
        }

        function placeOrder() {
            const name = document.getElementById('checkoutName').value;
            const email = document.getElementById('checkoutEmail').value;
            const phone = document.getElementById('checkoutPhone').value;
            const address = document.getElementById('checkoutAddress').value;
            const city = document.getElementById('checkoutCity').value;
            const postal = document.getElementById('checkoutPostal').value;
            const country = document.getElementById('checkoutCountry').value;

            if (!name || !email || !phone || !address || !city || !postal || !country) {
                showToast('Please fill in all required fields', 'error');
                return;
            }

            if (cart.length === 0) {
                showToast('Your cart is empty', 'error');
                return;
            }

            // Show success
            document.getElementById('successOverlay').classList.add('active');
            document.body.style.overflow = 'hidden';

            // Clear cart
            cart = [];
            saveCart();
            updateCartCount();
        }

        function closeSuccess() {
            document.getElementById('successOverlay').classList.remove('active');
            document.body.style.overflow = '';
            showSection('home');
        }

        // --- Reviews Slider ---
        function renderReviews() {
            const track = document.getElementById('reviewsTrack');
            track.innerHTML = reviews.map(review => `
                <div class="review-card">
                    <div class="review-header">
                        <img src="${review.avatar}" alt="${review.name}" class="review-avatar">
                        <div class="review-meta">
                            <h4>${review.name}</h4>
                            <div class="stars">${'★'.repeat(review.rating)}</div>
                        </div>
                    </div>
                    <p class="review-text">"${review.text}"</p>
                </div>
            `).join('');
        }

        function slideReviews(direction) {
            const track = document.getElementById('reviewsTrack');
            const cards = track.querySelectorAll('.review-card');
            const cardWidth = cards[0].offsetWidth + 24;
            const maxSlide = cards.length - Math.floor(track.parentElement.offsetWidth / cardWidth);

            reviewSlideIndex += direction;
            if (reviewSlideIndex < 0) reviewSlideIndex = 0;
            if (reviewSlideIndex > maxSlide) reviewSlideIndex = maxSlide;

            track.style.transform = `translateX(-${reviewSlideIndex * cardWidth}px)`;
        }

        // --- Auth Modal ---
        function openAuth() {
            document.getElementById('authModal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeAuth() {
            document.getElementById('authModal').classList.remove('active');
            document.body.style.overflow = '';
        }

        function switchAuthTab(tab) {
            document.querySelectorAll('.auth-tab').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.auth-form').forEach(f => f.classList.remove('active'));

            event.target.classList.add('active');
            document.getElementById(tab === 'login' ? 'loginForm' : 'registerForm').classList.add('active');
        }

        function handleLogin(e) {
            e.preventDefault();
            showToast('Login successful! Welcome back.', 'success');
            closeAuth();
        }

        function handleRegister(e) {
            e.preventDefault();
            const password = document.getElementById('regPassword').value;
            const confirm = document.getElementById('regConfirm').value;

            if (password !== confirm) {
                showToast('Passwords do not match', 'error');
                return;
            }

            showToast('Account created successfully! Welcome to Dumith Market.', 'success');
            closeAuth();
        }

        // --- Contact Form ---
        function submitContact(e) {
            e.preventDefault();
            const name = document.getElementById('contactName');
            const email = document.getElementById('contactEmail');
            const message = document.getElementById('contactMessage');
            let valid = true;

            // Reset errors
            document.querySelectorAll('.form-group').forEach(g => g.classList.remove('error'));

            if (!name.value.trim()) {
                name.parentElement.classList.add('error');
                valid = false;
            }

            if (!email.value.trim() || !email.value.includes('@')) {
                email.parentElement.classList.add('error');
                valid = false;
            }

            if (!message.value.trim()) {
                message.parentElement.classList.add('error');
                valid = false;
            }

            if (!valid) {
                showToast('Please fill in all required fields', 'error');
                return;
            }

            showToast('Message sent successfully! We will get back to you soon.', 'success');
            document.getElementById('contactForm').reset();
        }

        // --- Mobile Menu ---
        function openMobileMenu() {
            document.getElementById('mobileMenu').classList.add('active');
            document.getElementById('menuOverlay').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeMobileMenu() {
            document.getElementById('mobileMenu').classList.remove('active');
            document.getElementById('menuOverlay').classList.remove('active');
            document.body.style.overflow = '';
        }

        // --- Toast Notifications ---
        function showToast(message, type = 'success') {
            const container = document.getElementById('toastContainer');
            const toast = document.createElement('div');
            toast.className = `toast ${type}`;

            const icons = {
                success: 'fa-check-circle',
                error: 'fa-times-circle',
                warning: 'fa-exclamation-circle'
            };

            toast.innerHTML = `
                <i class="fas ${icons[type]}"></i>
                <span>${message}</span>
            `;

            container.appendChild(toast);

            setTimeout(() => {
                toast.style.animation = 'slideOut 0.4s ease forwards';
                setTimeout(() => toast.remove(), 400);
            }, 3000);
        }

        // --- Close modals on overlay click ---
        document.getElementById('productModal').addEventListener('click', (e) => {
            if (e.target === document.getElementById('productModal')) closeProductModal();
        });

        document.getElementById('wishlistModal').addEventListener('click', (e) => {
            if (e.target === document.getElementById('wishlistModal')) closeWishlistModal();
        });

        document.getElementById('authModal').addEventListener('click', (e) => {
            if (e.target === document.getElementById('authModal')) closeAuth();
        });

        document.getElementById('successOverlay').addEventListener('click', (e) => {
            if (e.target === document.getElementById('successOverlay')) closeSuccess();
        });

        // --- Keyboard shortcuts ---
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape') {
                closeProductModal();
                closeWishlistModal();
                closeAuth();
                closeCart();
                closeSuccess();
                closeMobileMenu();
            }
        });
    </script>
</body>
</html>
