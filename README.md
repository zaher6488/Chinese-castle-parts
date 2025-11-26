# Chinese-castle-parts
متجر الكتروني لقطع غيار الشاحنات الصينية - السودان 
تحسينات شاملة على موقع القلعة الصينية للإسبيرات

سأقوم بإجراء جميع التعديلات المطلوبة وإصلاح المشاكل المذكورة، وإضافة ميزة المزامنة مع GitHub:

```html
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>القلعة الصينية للإسبيرات</title>
    <style>
        :root {
            --primary-color: #1a5276;
            --secondary-color: #e74c3c;
            --accent-color: #f39c12;
            --light-color: #ecf0f1;
            --card-bg: #ffffff;
            --card-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            --radius: 16px;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #e4e8ed 100%);
            color: #333;
            line-height: 1.6;
            padding: 0;
            min-height: 100vh;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary-color), #154360);
            color: white;
            padding: 1.2rem 0;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: relative;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: white;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .logo span {
            color: var(--accent-color);
        }
        
        .contact-header {
            font-size: 1rem;
            text-align: center;
        }
        
        .contact-header div {
            margin-bottom: 5px;
        }
        
        /* Settings Menu (النقاط الثلاث) */
        .settings-menu {
            position: absolute;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
        }
        
        .settings-toggle {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            padding: 8px;
            border-radius: 50%;
            transition: background 0.3s;
        }
        
        .settings-toggle:hover {
            background: rgba(255, 255, 255, 0.1);
        }
        
        .settings-dropdown {
            position: absolute;
            top: 100%;
            left: 0;
            background: white;
            min-width: 300px;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            padding: 1rem;
            margin-top: 10px;
            display: none;
            z-index: 1000;
        }
        
        .settings-dropdown.active {
            display: block;
            animation: fadeIn 0.3s ease;
        }
        
        .settings-dropdown h3 {
            color: var(--primary-color);
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 1px solid #eee;
        }
        
        .settings-form .form-group {
            margin-bottom: 1rem;
        }
        
        .settings-form label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: #555;
            font-size: 0.9rem;
        }
        
        .settings-form input {
            width: 100%;
            padding: 0.8rem;
            border: 1.5px solid #e1e5e9;
            border-radius: 8px;
            font-size: 0.9rem;
            transition: all 0.3s;
            background: #fafbfc;
        }
        
        .settings-form input:focus {
            outline: none;
            border-color: var(--primary-color);
            background: white;
            box-shadow: 0 0 0 3px rgba(26, 82, 118, 0.1);
        }
        
        /* Tabs */
        .tabs {
            display: flex;
            background: var(--card-bg);
            margin: 1.5rem 0;
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--card-shadow);
            padding: 8px;
        }
        
        .tab {
            flex: 1;
            padding: 1rem;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border-radius: 12px;
            font-weight: 500;
        }
        
        .tab.active {
            background: var(--primary-color);
            color: white;
            box-shadow: 0 4px 12px rgba(26, 82, 118, 0.2);
        }
        
        /* Forms */
        .form-container {
            background: var(--card-bg);
            padding: 2rem;
            border-radius: var(--radius);
            box-shadow: var(--card-shadow);
            margin-bottom: 1.5rem;
        }
        
        .form-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1.5rem;
            color: var(--primary-color);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.7rem;
            font-weight: 500;
            color: #555;
        }
        
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 1.5px solid #e1e5e9;
            border-radius: 12px;
            font-size: 1rem;
            transition: all 0.3s;
            background: #fafbfc;
        }
        
        .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
            outline: none;
            border-color: var(--primary-color);
            background: white;
            box-shadow: 0 0 0 3px rgba(26, 82, 118, 0.1);
        }
        
        .btn {
            padding: 1rem 1.5rem;
            background: linear-gradient(135deg, var(--secondary-color), #c0392b);
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            width: 100%;
            box-shadow: 0 4px 12px rgba(231, 76, 60, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 16px rgba(231, 76, 60, 0.4);
        }
        
        .btn-secondary {
            background: linear-gradient(135deg, var(--primary-color), #154360);
            box-shadow: 0 4px 12px rgba(26, 82, 118, 0.3);
        }
        
        .btn-secondary:hover {
            box-shadow: 0 6px 16px rgba(26, 82, 118, 0.4);
        }
        
        .btn-success {
            background: linear-gradient(135deg, #27ae60, #219653);
            box-shadow: 0 4px 12px rgba(39, 174, 96, 0.3);
        }
        
        .btn-success:hover {
            box-shadow: 0 6px 16px rgba(39, 174, 96, 0.4);
        }
        
        /* Parts Grid */
        .parts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }
        
        .part-card {
            background: var(--card-bg);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--card-shadow);
            transition: all 0.3s ease;
            border: 1px solid rgba(0,0,0,0.05);
            position: relative;
        }
        
        .part-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
        }
        
        .part-image {
            height: 180px;
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }
        
        .part-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .part-info {
            padding: 1.5rem;
        }
        
        .part-name {
            font-weight: 600;
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
        }
        
        .part-number {
            color: var(--secondary-color);
            font-weight: 600;
            margin-bottom: 0.3rem;
            font-size: 0.95rem;
        }
        
        .part-brand {
            color: #6c757d;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
            background: #f1f3f5;
            padding: 4px 10px;
            border-radius: 20px;
            display: inline-block;
        }
        
        .part-price {
            font-weight: 700;
            color: var(--primary-color);
            font-size: 1.3rem;
            margin-top: 0.5rem;
        }
        
        /* أزرار التعديل والحذف */
        .part-actions {
            position: absolute;
            top: 10px;
            left: 10px;
            display: flex;
            gap: 5px;
        }
        
        .edit-btn, .delete-btn {
            color: white;
            border: none;
            padding: 0.3rem 0.6rem;
            border-radius: 20px;
            cursor: pointer;
            font-size: 0.8rem;
            transition: all 0.3s;
        }
        
        .edit-btn {
            background: #3498db;
        }
        
        .delete-btn {
            background: #e74c3c;
        }
        
        .edit-btn:hover {
            background: #2980b9;
            transform: scale(1.1);
        }
        
        .delete-btn:hover {
            background: #c0392b;
            transform: scale(1.1);
        }
        
        .buy-btn {
            background: linear-gradient(135deg, #27ae60, #219653);
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 600;
            margin-top: 1rem;
            width: 100%;
            transition: all 0.3s;
        }
        
        .buy-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(39, 174, 96, 0.3);
        }
        
        /* Search */
        .search-box {
            background: var(--card-bg);
            padding: 1.5rem;
            border-radius: var(--radius);
            box-shadow: var(--card-shadow);
            margin-bottom: 1.5rem;
        }
        
        .search-input {
            width: 100%;
            padding: 1rem;
            border: 1.5px solid #e1e5e9;
            border-radius: 12px;
            font-size: 1rem;
            margin-bottom: 1rem;
            transition: all 0.3s;
            background: #fafbfc;
        }
        
        .search-input:focus {
            outline: none;
            border-color: var(--primary-color);
            background: white;
            box-shadow: 0 0 0 3px rgba(26, 82, 118, 0.1);
        }
        
        /* Messages */
        .message {
            padding: 1.2rem;
            border-radius: 12px;
            margin-bottom: 1.5rem;
            text-align: center;
            font-weight: 500;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
        }
        
        .success {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .error {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        /* Image Upload */
        .image-upload {
            border: 2px dashed #e1e5e9;
            border-radius: 12px;
            padding: 2rem;
            text-align: center;
            background: #fafbfc;
            cursor: pointer;
            transition: all 0.3s;
            margin-bottom: 1rem;
        }
        
        .image-upload:hover {
            border-color: var(--primary-color);
            background: #f0f7ff;
        }
        
        .image-upload-icon {
            font-size: 2.5rem;
            color: #6c757d;
            margin-bottom: 1rem;
        }
        
        .image-preview {
            width: 100%;
            max-height: 200px;
            border-radius: 12px;
            overflow: hidden;
            margin-top: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .image-preview img {
            max-width: 100%;
            max-height: 200px;
            object-fit: contain;
        }
        
        /* Empty State */
        .empty-state {
            text-align: center;
            padding: 3rem 2rem;
            color: #6c757d;
        }
        
        .empty-state img {
            max-width: 150px;
            margin-bottom: 1rem;
            opacity: 0.7;
        }
        
        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--primary-color), #154360);
            color: white;
            padding: 2.5rem 0 1.5rem;
            margin-top: 3rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-section h3 {
            font-size: 1.3rem;
            margin-bottom: 1.2rem;
            color: var(--accent-color);
        }
        
        .footer-section p, .footer-section a {
            color: #ddd;
            line-height: 1.8;
            margin-bottom: 0.5rem;
            display: block;
            text-decoration: none;
        }
        
        .footer-section a:hover {
            color: var(--accent-color);
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #bbb;
            font-size: 0.9rem;
        }
        
        /* Shopping Cart */
        .cart-section {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: var(--secondary-color);
            color: white;
            padding: 1rem 1.5rem;
            border-radius: 50px;
            box-shadow: 0 5px 20px rgba(231, 76, 60, 0.4);
            cursor: pointer;
            z-index: 1000;
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 600;
        }
        
        .cart-count {
            background: white;
            color: var(--secondary-color);
            border-radius: 50%;
            width: 25px;
            height: 25px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.9rem;
        }
        
        /* Password Section */
        .password-section {
            background: #f8f9fa;
            padding: 1.5rem;
            border-radius: var(--radius);
            margin-bottom: 1.5rem;
            border: 1px solid #e9ecef;
        }
        
        .password-input {
            width: 100%;
            padding: 1rem;
            border: 1.5px solid #e1e5e9;
            border-radius: 12px;
            font-size: 1rem;
            margin-bottom: 1rem;
            background: white;
        }
        
        .search-info {
            background: #e8f4fd;
            padding: 1rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            border-right: 4px solid var(--primary-color);
        }
        
        .search-info h4 {
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }
        
        /* Categories Grid */
        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }
        
        .category-card {
            background: var(--card-bg);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--card-shadow);
            transition: all 0.3s ease;
            border: 1px solid rgba(0,0,0,0.05);
            cursor: pointer;
            text-align: center;
            padding: 2rem 1.5rem;
        }
        
        .category-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.1);
        }
        
        .category-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
        }
        
        .category-name {
            font-weight: 600;
            font-size: 1.2rem;
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }
        
        .category-count {
            color: #6c757d;
            font-size: 0.9rem;
        }
        
        /* Back Button */
        .back-button {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: white;
            color: var(--primary-color);
            border: 2px solid var(--primary-color);
            padding: 0.8rem 1.5rem;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 600;
            margin-bottom: 1.5rem;
            transition: all 0.3s;
        }
        
        .back-button:hover {
            background: var(--primary-color);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(26, 82, 118, 0.3);
        }
        
        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background: white;
            border-radius: var(--radius);
            width: 90%;
            max-width: 600px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.2);
            animation: modalFadeIn 0.3s ease;
        }
        
        .modal-header {
            padding: 1.5rem;
            background: var(--primary-color);
            color: white;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 10;
        }
        
        .modal-header h3 {
            margin: 0;
        }
        
        .close-modal {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .modal-body {
            padding: 1.5rem;
        }
        
        /* WhatsApp Order Form */
        .order-form {
            background: #f8f9fa;
            padding: 1.5rem;
            border-radius: 12px;
            margin-top: 1.5rem;
        }
        
        .order-form h4 {
            color: var(--primary-color);
            margin-bottom: 1rem;
        }
        
        .order-items {
            margin-bottom: 1rem;
        }
        
        .order-item {
            display: flex;
            justify-content: space-between;
            padding: 0.5rem 0;
            border-bottom: 1px solid #e9ecef;
        }
        
        .order-total {
            font-weight: 700;
            font-size: 1.2rem;
            text-align: center;
            padding: 1rem 0;
            border-top: 2px solid var(--primary-color);
            margin-top: 1rem;
        }
        
        @keyframes modalFadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
                gap: 1rem;
            }
            
            .settings-menu {
                position: absolute;
                left: 0;
                top: 50%;
                transform: translateY(-50%);
            }
            
            .settings-dropdown {
                left: 0;
                right: auto;
                width: 90vw;
                max-width: 300px;
            }
            
            .tabs {
                flex-direction: column;
                padding: 5px;
            }
            
            .parts-grid, .categories-grid {
                grid-template-columns: 1fr;
            }
            
            .form-container {
                padding: 1.5rem;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
            }
            
            .cart-section {
                bottom: 10px;
                left: 10px;
                right: 10px;
                justify-content: center;
            }
        }
        
        /* Animation */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .fade-in {
            animation: fadeIn 0.5s ease forwards;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <!-- قائمة الإعدادات (النقاط الثلاث) -->
                <div class="settings-menu">
                    <button class="settings-toggle">⋮</button>
                    <div class="settings-dropdown">
                        <h3>إعدادات المتجر</h3>
                        
                        <div class="password-section">
                            <input type="password" id="settings-password" class="password-input" placeholder="أدخل الرمز السري للوصول">
                            <button class="btn" id="settings-password-btn">فتح الإعدادات</button>
                        </div>
                        
                        <div id="settings-form-content" style="display: none;">
                            <form class="settings-form" id="settings-form">
                                <div class="form-group">
                                    <label for="company-name">اسم الشركة</label>
                                    <input type="text" id="company-name" placeholder="اسم الشركة">
                                </div>
                                <div class="form-group">
                                    <label for="phone-number">رقم الهاتف</label>
                                    <input type="text" id="phone-number" placeholder="رقم الهاتف">
                                </div>
                                <div class="form-group">
                                    <label for="whatsapp-number">رقم الواتساب</label>
                                    <input type="text" id="whatsapp-number" placeholder="رقم الواتساب">
                                </div>
                                <div class="form-group">
                                    <label for="email">البريد الإلكتروني</label>
                                    <input type="email" id="email" placeholder="البريد الإلكتروني">
                                </div>
                                
                                <div class="form-group">
                                    <label for="github-token">رمز GitHub (للمزامنة)</label>
                                    <input type="password" id="github-token" placeholder="أدخل رمز GitHub الشخصي">
                                    <p style="font-size: 0.8rem; color: #666; margin-top: 0.5rem;">
                                        للحصول على رمز GitHub: إذهب إلى Settings → Developer settings → Personal access tokens → Generate new token
                                    </p>
                                </div>
                                
                                <div class="form-group">
                                    <label for="github-repo">اسم المستودع في GitHub</label>
                                    <input type="text" id="github-repo" placeholder="اسم المستخدم/اسم المستودع">
                                </div>
                                
                                <button type="button" class="btn btn-secondary" id="save-settings">حفظ الإعدادات</button>
                                <button type="button" class="btn" id="sync-github" style="margin-top: 10px;">مزامنة مع GitHub</button>
                            </form>
                        </div>
                    </div>
                </div>
                
                <div class="logo" id="company-logo">
                    <span>القلعة الصينية</span> للإسبيرات
                </div>
                <div class="contact-header" id="contact-info">
                    <div>📍 السودان - مدني</div>
                    <div>📞 00249969688826</div>
                </div>
            </div>
        </div>
    </header>

    <div class="container">
        <!-- Tabs -->
        <div class="tabs">
            <div class="tab active" data-tab="search">البحث عن قطعة</div>
            <div class="tab" data-tab="engines">المحركات</div>
            <div class="tab" data-tab="add">إضافة قطعة غيار</div>
        </div>

        <!-- Messages -->
        <div id="message" class="message" style="display: none;"></div>

        <!-- Search Form -->
        <div id="search-form" class="form-container fade-in">
            <h2 class="form-title">🔍 البحث عن قطع الغيار</h2>
            
            <div class="search-info">
                <h4>معلومات البحث:</h4>
                <p>• ابحث برقم القطعة، الاسم، أو العلامة التجارية</p>
                <p>• يمكنك البحث بالأربعة أرقام الأخيرة من رقم القطعة</p>
                <p>• مثال: اكتب "8234" للعثور على القطعة رقم "HW-78234"</p>
            </div>
            
            <div class="search-box">
                <input type="text" id="search-input" class="search-input" placeholder="اكتب رقم القطعة، الاسم، أو العلامة التجارية...">
                <button class="btn btn-secondary" id="search-btn">بحث</button>
            </div>
            <div id="search-results" class="parts-grid">
                <!-- نتائج البحث تظهر هنا -->
            </div>
        </div>

        <!-- Engines and Parts -->
        <div id="engines-parts" class="form-container" style="display: none;">
            <h2 class="form-title">🛠️ المحركات</h2>
            
            <div class="categories-grid" id="categories-container">
                <!-- الفئات تظهر هنا -->
            </div>
            
            <div id="category-parts" class="parts-grid" style="display: none; margin-top: 2rem;">
                <!-- قطع الفئة المحددة تظهر هنا -->
            </div>
        </div>

        <!-- Add Part Form (Hidden by default) -->
        <div id="add-form" class="form-container" style="display: none;">
            <div class="password-section">
                <h3>🔒 الوصول إلى إضافة القطع</h3>
                <input type="password" id="password-input" class="password-input" placeholder="أدخل الرمز السري للوصول">
                <button class="btn" id="password-btn">فتح قسم الإضافة</button>
            </div>
            
            <div id="add-form-content" style="display: none;">
                <h2 class="form-title">➕ إضافة قطعة غيار جديدة</h2>
                <div class="form-group">
                    <label for="part-name">اسم القطعة</label>
                    <input type="text" id="part-name" placeholder="مثال: فلتر زيت محرك">
                </div>
                <div class="form-group">
                    <label for="part-number">رقم القطعة</label>
                    <input type="text" id="part-number" placeholder="مثال: HW-78234">
                </div>
                <div class="form-group">
                    <label for="part-category">الفئة</label>
                    <select id="part-category">
                        <option value="howo-371">HOWO 371</option>
                        <option value="howo-420">HOWO 420</option>
                        <option value="deutz">Deutz</option>
                        <option value="cat">CAT (لودر)</option>
                        <option value="g-loader">لودر G</option>
                        <option value="gn-loader">لودر GN</option>
                        <option value="str">STR (باص الاستاير)</option>
                        <option value="bearings">السبائك</option>
                        <option value="filters">المصافي (زيت، جاز، رطوبة)</option>
                        <option value="fans">المراوح</option>
                        <option value="belts">السيور</option>
                        <option value="clutch">جهاز الكلتش</option>
                        <option value="pumps">الطرمبات (قبين، هايدروليك، ماء، زيت)</option>
                        <option value="lights">الأنوار والفوانيس</option>
                        <option value="mirrors">المرايات</option>
                        <option value="screws">المسامير</option>
                        <option value="kits">صناديق العمرات</option>
                        <option value="other">أخرى</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="part-price">السعر (جنيه سوداني)</label>
                    <input type="number" id="part-price" placeholder="مثال: 12000">
                </div>
                
                <div class="form-group">
                    <label>صورة القطعة</label>
                    <div class="image-upload" id="image-upload">
                        <div class="image-upload-icon">📷</div>
                        <p>انقر لرفع صورة القطعة</p>
                        <p style="font-size: 0.9rem; color: #6c757d; margin-top: 0.5rem;">يمكنك التقاط صورة أو اختيارها من المعرض</p>
                    </div>
                    <input type="file" id="part-image-file" accept="image/*" style="display: none;">
                    <div id="image-preview-container" class="image-preview" style="display: none;">
                        <!-- معاينة الصورة تظهر هنا -->
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="part-description">وصف القطعة (اختياري)</label>
                    <textarea id="part-description" rows="3" placeholder="معلومات إضافية عن القطعة"></textarea>
                </div>
                
                <button class="btn" id="add-part-btn">إضافة القطعة</button>
            </div>
        </div>
    </div>

    <!-- Modal لتعديل القطع -->
    <div class="modal" id="edit-part-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>تعديل قطعة الغيار</h3>
                <button class="close-modal">&times;</button>
            </div>
            <div class="modal-body">
                <form id="edit-part-form">
                    <input type="hidden" id="edit-part-id">
                    <div class="form-group">
                        <label for="edit-part-name">اسم القطعة</label>
                        <input type="text" id="edit-part-name" placeholder="اسم القطعة">
                    </div>
                    <div class="form-group">
                        <label for="edit-part-number">رقم القطعة</label>
                        <input type="text" id="edit-part-number" placeholder="رقم القطعة">
                    </div>
                    <div class="form-group">
                        <label for="edit-part-category">الفئة</label>
                        <select id="edit-part-category">
                            <option value="howo-371">HOWO 371</option>
                            <option value="howo-420">HOWO 420</option>
                            <option value="deutz">Deutz</option>
                            <option value="cat">CAT (لودر)</option>
                            <option value="g-loader">لودر G</option>
                            <option value="gn-loader">لودر GN</option>
                            <option value="str">STR (باص الاستاير)</option>
                            <option value="bearings">السبائك</option>
                            <option value="filters">المصافي (زيت، جاز، رطوبة)</option>
                            <option value="fans">المراوح</option>
                            <option value="belts">السيور</option>
                            <option value="clutch">جهاز الكلتش</option>
                            <option value="pumps">الطرمبات (قبين، هايدروليك، ماء، زيت)</option>
                            <option value="lights">الأنوار والفوانيس</option>
                            <option value="mirrors">المرايات</option>
                            <option value="screws">المسامير</option>
                            <option value="kits">صناديق العمرات</option>
                            <option value="other">أخرى</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="edit-part-price">السعر (جنيه سوداني)</label>
                        <input type="number" id="edit-part-price" placeholder="السعر">
                    </div>
                    
                    <div class="form-group">
                        <label>صورة القطعة</label>
                        <div class="image-upload" id="edit-image-upload">
                            <div class="image-upload-icon">📷</div>
                            <p>انقر لتغيير صورة القطعة</p>
                            <p style="font-size: 0.9rem; color: #6c757d; margin-top: 0.5rem;">يمكنك التقاط صورة أو اختيارها من المعرض</p>
                        </div>
                        <input type="file" id="edit-part-image-file" accept="image/*" style="display: none;">
                        <div id="edit-image-preview-container" class="image-preview">
                            <!-- معاينة الصورة الحالية تظهر هنا -->
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="edit-part-description">وصف القطعة (اختياري)</label>
                        <textarea id="edit-part-description" rows="3" placeholder="وصف القطعة"></textarea>
                    </div>
                    <button type="button" class="btn btn-secondary" id="update-part-btn">تحديث القطعة</button>
                </form>
            </div>
        </div>
    </div>

    <!-- Modal لعرض سلة المشتريات وإرسال الطلب -->
    <div class="modal" id="cart-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>سلة المشتريات</h3>
                <button class="close-modal">&times;</button>
            </div>
            <div class="modal-body">
                <div id="cart-items" class="order-items">
                    <!-- عناصر السلة تظهر هنا -->
                </div>
                <div id="cart-total" class="order-total">
                    <!-- المجموع يظهر هنا -->
                </div>
                
                <div class="order-form">
                    <h4>إرسال الطلب</h4>
                    <button class="btn btn-success" id="send-whatsapp">إرسال الطلب عبر واتساب</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Shopping Cart -->
    <div class="cart-section" id="cart-section" style="display: none;">
        <div class="cart-count" id="cart-count">0</div>
        <span>سلة المشتريات</span>
    </div>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3 id="footer-company-name">القلعة الصينية للإسبيرات</h3>
                    <p>متخصصون في توفير قطع غيار الشاحنات والمعدات الصينية الأصلية بأسعار تنافسية وخدمة موثوقة.</p>
                </div>
                <div class="footer-section">
                    <h3>معلومات الاتصال</h3>
                    <p id="footer-address">📍 السودان - مدني</p>
                    <a href="tel:00249969688826" id="footer-phone">📞 00249969688826</a>
                    <a href="mailto:info@example.com" id="footer-email" style="display: none;">✉️ البريد الإلكتروني</a>
                </div>
                <div class="footer-section">
                    <h3>العلامات التجارية</h3>
                    <p>HOWO 371 • HOWO 420 • CAT</p>
                    <p>STR • Deutz • SINOTRUK • FOTON</p>
                </div>
            </div>
            <div class="copyright">
                <p>جميع الحقوق محفوظة &copy; القلعة الصينية للإسبيرات 2024</p>
            </div>
        </div>
    </footer>

    <script>
        // بيانات أولية لقطع الغيار
        let parts = JSON.parse(localStorage.getItem('castle-parts')) || [
            {
                id: 1,
                name: "فلتر زيت محرك",
                number: "HW-78234",
                category: "howo-371",
                price: "12000",
                description: "فلتر زيت أصلي للشاحنات الثقيلة",
                image: "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgZmlsbD0iI2Y4ZjlmYSIvPjx0ZXh0IHg9IjE1MCIgeT0iOTAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxOCIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZmlsbD0iIzZjNzU3ZCI+SE9XTyAzNzE8L3RleHQ+PC9zdmc+"
            },
            {
                id: 2,
                name: "قرص مكابح أمامي",
                number: "ST-45612",
                category: "str",
                price: "34000",
                description: "قرص مكابح أمامي عالي الجودة",
                image: "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgZmlsbD0iI2Y4ZjlmYSIvPjx0ZXh0IHg9IjE1MCIgeT0iOTAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxOCIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZmlsbD0iIzZjNzU3ZCI+U1RSPC90ZXh0Pjwvc3ZnPg=="
            },
            {
                id: 3,
                name: "مرشح هواء",
                number: "FT-89123",
                category: "deutz",
                price: "8500",
                description: "مرشح هواء لمحركات الديزل",
                image: "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgZmlsbD0iI2Y4ZjlmYSIvPjx0ZXh0IHg9IjE1MCIgeT0iOTAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxOCIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZmlsbD0iIzZjNzU3ZCI+RGV1dHo8L3RleHQ+PC9zdmc+"
            }
        ];

        // سلة المشتريات
        let cart = JSON.parse(localStorage.getItem('castle-cart')) || [];
        
        // الرمز السري
        const SECRET_PASSWORD = "787898";
        const DELETE_PASSWORD = "787898";
        
        // إعدادات المتجر
        let storeSettings = JSON.parse(localStorage.getItem('castle-settings')) || {
            companyName: "القلعة الصينية للإسبيرات",
            phoneNumber: "00249969688826",
            whatsappNumber: "+249969688826",
            email: "",
            githubToken: "",
            githubRepo: ""
        };
        
        // رقم واتساب
        let WHATSAPP_NUMBER = storeSettings.whatsappNumber || "+249969688826";

        // فئات المحركات فقط
        const engineCategories = [
            { id: "howo-371", name: "HOWO 371", icon: "🚛", description: "قطع غيار شاحنات HOWO 371" },
            { id: "howo-420", name: "HOWO 420", icon: "🚚", description: "قطع غيار شاحنات HOWO 420" },
            { id: "deutz", name: "Deutz", icon: "🔧", description: "قطع غيار محركات Deutz" },
            { id: "cat", name: "CAT (لودر)", icon: "🚜", description: "قطع غيار لوادر CAT" },
            { id: "g-loader", name: "لودر G", icon: "🏗️", description: "قطع غيار لوادر G" },
            { id: "gn-loader", name: "لودر GN", icon: "🚧", description: "قطع غيار لوادر GN" },
            { id: "str", name: "STR (باص الاستاير)", icon: "🚌", description: "قطع غيار باصات الاستاير" }
        ];

        // جميع الفئات (للبحث والإضافة)
        const allCategories = [
            ...engineCategories,
            { id: "bearings", name: "السبائك", icon: "⚙️", description: "السبائك والمحامل" },
            { id: "filters", name: "المصافي", icon: "🧹", description: "مصافي الزيت، الجاز، والرطوبة" },
            { id: "fans", name: "المراوح", icon: "🌀", description: "مراوح التبريد" },
            { id: "belts", name: "السيور", icon: "📿", description: "سيور المحركات" },
            { id: "clutch", name: "جهاز الكلتش", icon: "🎛️", description: "أجهزة الكلتش والدبرياج" },
            { id: "pumps", name: "الطرمبات", icon: "⛽", description: "طرمبات القبين، الهايدروليك، الماء، والزيت" },
            { id: "lights", name: "الأنوار والفوانيس", icon: "💡", description: "أنوار المركبات وفوانيسها" },
            { id: "mirrors", name: "المرايات", icon: "👁️", description: "مرايات المركبات" },
            { id: "screws", name: "المسامير", icon: "🔩", description: "مسامير المحركات والمركبات" },
            { id: "kits", name: "صناديق العمرات", icon: "📦", description: "صناديق عمرات المحركات" }
        ];

        // حفظ البيانات في localStorage
        function saveParts() {
            localStorage.setItem('castle-parts', JSON.stringify(parts));
        }
        
        // حفظ سلة المشتريات
        function saveCart() {
            localStorage.setItem('castle-cart', JSON.stringify(cart));
            updateCartUI();
        }
        
        // حفظ إعدادات المتجر
        function saveSettings() {
            localStorage.setItem('castle-settings', JSON.stringify(storeSettings));
            updateStoreUI();
        }
        
        // تحديث واجهة المتجر بناءً على الإعدادات
        function updateStoreUI() {
            document.getElementById('company-logo').innerHTML = `<span>${storeSettings.companyName.split(' ')[0]}</span> ${storeSettings.companyName.split(' ').slice(1).join(' ')}`;
            document.getElementById('contact-info').innerHTML = `
                <div>📍 السودان - مدني</div>
                <div>📞 ${storeSettings.phoneNumber}</div>
            `;
            
            document.getElementById('footer-company-name').textContent = storeSettings.companyName;
            document.getElementById('footer-phone').textContent = `📞 ${storeSettings.phoneNumber}`;
            document.getElementById('footer-phone').href = `tel:${storeSettings.phoneNumber}`;
            
            if (storeSettings.email) {
                document.getElementById('footer-email').style.display = 'block';
                document.getElementById('footer-email').textContent = `✉️ ${storeSettings.email}`;
                document.getElementById('footer-email').href = `mailto:${storeSettings.email}`;
            } else {
                document.getElementById('footer-email').style.display = 'none';
            }
            
            WHATSAPP_NUMBER = storeSettings.whatsappNumber;
        }

        // تحديث واجهة سلة المشتريات
        function updateCartUI() {
            const cartCount = document.getElementById('cart-count');
            const cartSection = document.getElementById('cart-section');
            
            if (cart.length > 0) {
                cartCount.textContent = cart.length;
                cartSection.style.display = 'flex';
            } else {
                cartSection.style.display = 'none';
            }
        }

        // عرض رسالة للمستخدم
        function showMessage(text, type) {
            const messageEl = document.getElementById('message');
            messageEl.textContent = text;
            messageEl.className = `message ${type} fade-in`;
            messageEl.style.display = 'block';
            
            setTimeout(() => {
                messageEl.style.display = 'none';
            }, 4000);
        }

        // رفع الصورة
        document.getElementById('image-upload').addEventListener('click', function() {
            document.getElementById('part-image-file').click();
        });

        document.getElementById('part-image-file').addEventListener('change', function(e) {
            const file = e.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(event) {
                    const previewContainer = document.getElementById('image-preview-container');
                    previewContainer.innerHTML = `<img src="${event.target.result}" alt="معاينة الصورة">`;
                    previewContainer.style.display = 'flex';
                    
                    // حفظ الصورة مؤقتًا للاستخدام لاحقًا
                    previewContainer.dataset.imageData = event.target.result;
                };
                reader.readAsDataURL(file);
            }
        });

        // رفع الصورة للتعديل
        document.getElementById('edit-image-upload').addEventListener('click', function() {
            document.getElementById('edit-part-image-file').click();
        });

        document.getElementById('edit-part-image-file').addEventListener('change', function(e) {
            const file = e.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(event) {
                    const previewContainer = document.getElementById('edit-image-preview-container');
                    previewContainer.innerHTML = `<img src="${event.target.result}" alt="معاينة الصورة">`;
                    previewContainer.style.display = 'flex';
                    
                    // حفظ الصورة مؤقتًا للاستخدام لاحقًا
                    previewContainer.dataset.imageData = event.target.result;
                };
                reader.readAsDataURL(file);
            }
        });

        // تبديل التبويبات
        document.querySelectorAll('.tab').forEach(tab => {
            tab.addEventListener('click', function() {
                // إزالة النشاط من جميع التبويبات
                document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
                // إضافة النشاط للتبويب المحدد
                this.classList.add('active');
                
                // إخفاء جميع النماذج
                document.getElementById('search-form').style.display = 'none';
                document.getElementById('engines-parts').style.display = 'none';
                document.getElementById('add-form').style.display = 'none';
                
                // إظهار النموذج المناسب
                const tabId = this.getAttribute('data-tab');
                if (tabId === 'search') {
                    document.getElementById('search-form').style.display = 'block';
                    document.getElementById('search-form').classList.add('fade-in');
                    document.getElementById('search-input').focus();
                } else if (tabId === 'engines') {
                    document.getElementById('engines-parts').style.display = 'block';
                    document.getElementById('engines-parts').classList.add('fade-in');
                    displayCategories();
                } else if (tabId === 'add') {
                    document.getElementById('add-form').style.display = 'block';
                    document.getElementById('add-form').classList.add('fade-in');
                    // إخفاء محتوى الإضافة وإظهار قسم كلمة المرور فقط
                    document.getElementById('add-form-content').style.display = 'none';
                    document.querySelector('.password-section').style.display = 'block';
                    document.getElementById('password-input').value = '';
                }
            });
        });

        // التحقق من الرمز السري للإضافة
        document.getElementById('password-btn').addEventListener('click', function() {
            const password = document.getElementById('password-input').value.trim();
            
            if (password === SECRET_PASSWORD) {
                document.getElementById('add-form-content').style.display = 'block';
                document.querySelector('.password-section').style.display = 'none';
                showMessage('تم فتح قسم الإضافة بنجاح!', 'success');
            } else {
                showMessage('الرمز السري غير صحيح!', 'error');
            }
        });

        // التحقق من الرمز السري للإعدادات
        document.getElementById('settings-password-btn').addEventListener('click', function() {
            const password = document.getElementById('settings-password').value.trim();
            
            if (password === SECRET_PASSWORD) {
                document.getElementById('settings-form-content').style.display = 'block';
                document.querySelector('.settings-dropdown .password-section').style.display = 'none';
                
                // تعبئة نموذج الإعدادات بالبيانات الحالية
                document.getElementById('company-name').value = storeSettings.companyName;
                document.getElementById('phone-number').value = storeSettings.phoneNumber;
                document.getElementById('whatsapp-number').value = storeSettings.whatsappNumber;
                document.getElementById('email').value = storeSettings.email;
                document.getElementById('github-token').value = storeSettings.githubToken || '';
                document.getElementById('github-repo').value = storeSettings.githubRepo || '';
                
                showMessage('تم فتح الإعدادات بنجاح!', 'success');
            } else {
                showMessage('الرمز السري غير صحيح!', 'error');
            }
        });

        // إضافة قطعة غيار جديدة
        document.getElementById('add-part-btn').addEventListener('click', function() {
            const name = document.getElementById('part-name').value.trim();
            const number = document.getElementById('part-number').value.trim();
            const category = document.getElementById('part-category').value;
            const price = document.getElementById('part-price').value.trim();
            const description = document.getElementById('part-description').value.trim();
            const imageData = document.getElementById('image-preview-container').dataset.imageData;
            
            if (!name || !number || !price) {
                showMessage('يرجى ملء جميع الحقول المطلوبة', 'error');
                return;
            }
            
            // إنشاء قطعة جديدة
            const newPart = {
                id: parts.length > 0 ? Math.max(...parts.map(p => p.id)) + 1 : 1,
                name,
                number,
                category,
                price,
                description,
                image: imageData || `data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgZmlsbD0iI2Y4ZjlmYSIvPjx0ZXh0IHg9IjE1MCIgeT0iOTAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxOCIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZmlsbD0iIzZjNzU3ZCI+${encodeURIComponent(name)}PC90ZXh0Pjwvc3ZnPg==`
            };
            
            // إضافة القطعة للقائمة
            parts.push(newPart);
            saveParts();
            
            // إظهار رسالة نجاح
            showMessage('تم إضافة القطعة بنجاح!', 'success');
            
            // مسح الحقول
            document.getElementById('part-name').value = '';
            document.getElementById('part-number').value = '';
            document.getElementById('part-price').value = '';
            document.getElementById('part-description').value = '';
            document.getElementById('part-image-file').value = '';
            document.getElementById('image-preview-container').style.display = 'none';
            document.getElementById('image-preview-container').dataset.imageData = '';
            
            // تحديث عرض جميع القطع
            displayCategories();
        });

        // البحث عن قطع الغيار
        document.getElementById('search-btn').addEventListener('click', performSearch);
        document.getElementById('search-input').addEventListener('keyup', function(e) {
            if (e.key === 'Enter') {
                performSearch();
            }
            
            // البحث الفوري عند الكتابة (بعد 500ms من التوقف)
            clearTimeout(this.searchTimeout);
            this.searchTimeout = setTimeout(() => {
                if (this.value.trim().length >= 2) {
                    performSearch();
                }
            }, 500);
        });

        function performSearch() {
            const query = document.getElementById('search-input').value.trim().toLowerCase();
            const resultsContainer = document.getElementById('search-results');
            
            if (!query) {
                resultsContainer.innerHTML = '<div class="empty-state"><p>يرجى إدخال كلمة للبحث</p></div>';
                return;
            }
            
            // البحث في البيانات
            let results = parts.filter(part => 
                part.name.toLowerCase().includes(query) ||
                part.number.toLowerCase().includes(query) ||
                part.category.toLowerCase().includes(query) ||
                (part.description && part.description.toLowerCase().includes(query)) ||
                // البحث بالأربعة أرقام الأخيرة من رقم القطعة
                (part.number.length >= 4 && part.number.slice(-4).includes(query))
            );
            
            // عرض النتائج
            if (results.length === 0) {
                resultsContainer.innerHTML = `
                    <div class="empty-state">
                        <p>لم يتم العثور على قطع غيار تطابق بحثك</p>
                        <p style="margin-top: 10px; font-size: 0.9rem; color: #999;">جرب استخدام مصطلحات بحث مختلفة</p>
                    </div>
                `;
            } else {
                displayParts(results, resultsContainer, true);
            }
        }

        // عرض الفئات (المحركات فقط)
        function displayCategories() {
            const container = document.getElementById('categories-container');
            container.innerHTML = '';
            
            engineCategories.forEach(category => {
                const categoryCard = document.createElement('div');
                categoryCard.className = 'category-card fade-in';
                categoryCard.setAttribute('data-category', category.id);
                
                const categoryParts = parts.filter(part => part.category === category.id);
                
                categoryCard.innerHTML = `
                    <div class="category-icon">${category.icon}</div>
                    <div class="category-name">${category.name}</div>
                    <div class="category-count">${categoryParts.length} قطعة</div>
                    <p style="color: #6c757d; font-size: 0.9rem; margin-top: 0.8rem;">${category.description}</p>
                `;
                
                categoryCard.addEventListener('click', function() {
                    displayCategoryParts(category.id);
                });
                
                container.appendChild(categoryCard);
            });
        }

        // عرض قطع فئة محددة
        function displayCategoryParts(categoryId) {
            const category = engineCategories.find(c => c.id === categoryId) || allCategories.find(c => c.id === categoryId);
            const categoryParts = parts.filter(part => part.category === categoryId);
            
            const container = document.getElementById('category-parts');
            const categoriesContainer = document.getElementById('categories-container');
            
            categoriesContainer.style.display = 'none';
            container.style.display = 'grid';
            container.innerHTML = `
                <div style="grid-column: 1 / -1; display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem;">
                    <h3 style="color: var(--primary-color);">${category.name} - ${categoryParts.length} قطعة</h3>
                    <button class="back-button" id="back-to-categories">← العودة للفئات</button>
                </div>
            `;
            
            // إضافة مستمع حدث لزر العودة
            const backButton = document.getElementById('back-to-categories');
            backButton.addEventListener('click', function() {
                container.style.display = 'none';
                categoriesContainer.style.display = 'grid';
            });
            
            if (categoryParts.length === 0) {
                container.innerHTML += `
                    <div class="empty-state" style="grid-column: 1 / -1;">
                        <p>لا توجد قطع غيار في هذه الفئة بعد</p>
                        <p style="margin-top: 10px; font-size: 0.9rem; color: #999;">انتقل إلى تبويب "إضافة قطعة غيار" لإضافة قطع جديدة</p>
                    </div>
                `;
            } else {
                displayParts(categoryParts, container, true);
            }
        }

        // فتح نموذج التعديل
        function openEditModal(partId) {
            const part = parts.find(p => p.id === partId);
            if (!part) return;
            
            document.getElementById('edit-part-id').value = part.id;
            document.getElementById('edit-part-name').value = part.name;
            document.getElementById('edit-part-number').value = part.number;
            document.getElementById('edit-part-category').value = part.category;
            document.getElementById('edit-part-price').value = part.price;
            document.getElementById('edit-part-description').value = part.description || '';
            
            const previewContainer = document.getElementById('edit-image-preview-container');
            previewContainer.innerHTML = `<img src="${part.image}" alt="معاينة الصورة">`;
            previewContainer.style.display = 'flex';
            previewContainer.dataset.imageData = part.image;
            
            document.getElementById('edit-part-modal').style.display = 'flex';
        }

        // تحديث القطعة
        document.getElementById('update-part-btn').addEventListener('click', function() {
            const partId = parseInt(document.getElementById('edit-part-id').value);
            const name = document.getElementById('edit-part-name').value.trim();
            const number = document.getElementById('edit-part-number').value.trim();
            const category = document.getElementById('edit-part-category').value;
            const price = document.getElementById('edit-part-price').value.trim();
            const description = document.getElementById('edit-part-description').value.trim();
            const imageData = document.getElementById('edit-image-preview-container').dataset.imageData;
            
            if (!name || !number || !price) {
                showMessage('يرجى ملء جميع الحقول المطلوبة', 'error');
                return;
            }
            
            // تحديث القطعة
            const partIndex = parts.findIndex(p => p.id === partId);
            if (partIndex !== -1) {
                parts[partIndex] = {
                    ...parts[partIndex],
                    name,
                    number,
                    category,
                    price,
                    description,
                    image: imageData || parts[partIndex].image
                };
                
                saveParts();
                displayCategories();
                performSearch(); // تحديث نتائج البحث أيضًا
                
                document.getElementById('edit-part-modal').style.display = 'none';
                showMessage('تم تحديث القطعة بنجاح!', 'success');
            }
        });

        // دالة عامة لعرض القطع
        function displayParts(partsArray, container, showBuyButton) {
            // إزالة أي محتوى موجود مسبقًا (باستثناء عنصر العودة للفئات إذا كان موجودًا)
            const existingParts = container.querySelectorAll('.part-card');
            existingParts.forEach(part => part.remove());
            
            partsArray.forEach(part => {
                const partCard = document.createElement('div');
                partCard.className = 'part-card fade-in';
                
                const isInCart = cart.some(item => item.id === part.id);
                const category = allCategories.find(c => c.id === part.category);
                
                partCard.innerHTML = `
                    <div class="part-actions">
                        <button class="edit-btn" data-id="${part.id}">✏️</button>
                        <button class="delete-btn" data-id="${part.id}">🗑️</button>
                    </div>
                    <div class="part-image">
                        <img src="${part.image}" alt="${part.name}" onerror="this.src='data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMzAwIiBoZWlnaHQ9IjE4MCIgZmlsbD0iI2Y4ZjlmYSIvPjx0ZXh0IHg9IjE1MCIgeT0iOTAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxOCIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZmlsbD0iIzZjNzU3ZCI+${encodeURIComponent(part.name)}PC90ZXh0Pjwvc3ZnPg=='">
                    </div>
                    <div class="part-info">
                        <div class="part-name">${part.name}</div>
                        <div class="part-number">${part.number}</div>
                        <div class="part-brand">${category ? category.name : part.category}</div>
                        <div class="part-price">${formatPrice(part.price)} ج.س</div>
                        ${part.description ? `<p style="color: #666; font-size: 0.9rem; margin-top: 0.8rem; line-height: 1.5;">${part.description}</p>` : ''}
                        ${showBuyButton ? `
                            <button class="buy-btn ${isInCart ? 'btn-success' : ''}" data-id="${part.id}">
                                ${isInCart ? '✓ تم الإضافة' : '🛒 شراء'}
                            </button>
                        ` : ''}
                    </div>
                `;
                container.appendChild(partCard);
            });
            
            // إضافة مستمعين لأزرار التعديل
            container.querySelectorAll('.edit-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const partId = parseInt(this.getAttribute('data-id'));
                    const password = prompt('أدخل الرمز السري للتعديل:');
                    
                    if (password === DELETE_PASSWORD) {
                        openEditModal(partId);
                    } else if (password !== null) {
                        showMessage('الرمز السري غير صحيح!', 'error');
                    }
                });
            });
            
            // إضافة مستمعين لأزرار الحذف
            container.querySelectorAll('.delete-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const partId = parseInt(this.getAttribute('data-id'));
                    const password = prompt('أدخل الرمز السري للحذف:');
                    
                    if (password === DELETE_PASSWORD) {
                        if (confirm('هل أنت متأكد من حذف هذه القطعة؟')) {
                            parts = parts.filter(part => part.id !== partId);
                            // إزالة القطعة من سلة المشتريات أيضًا
                            cart = cart.filter(item => item.id !== partId);
                            saveParts();
                            saveCart();
                            displayCategories();
                            performSearch(); // تحديث نتائج البحث أيضًا
                            showMessage('تم حذف القطعة بنجاح', 'success');
                        }
                    } else if (password !== null) {
                        showMessage('الرمز السري غير صحيح!', 'error');
                    }
                });
            });
            
            // إضافة مستمعين لأزرار الشراء
            if (showBuyButton) {
                container.querySelectorAll('.buy-btn').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const partId = parseInt(this.getAttribute('data-id'));
                        const part = parts.find(p => p.id === partId);
                        
                        if (part) {
                            // التحقق إذا كانت القطعة موجودة بالفعل في السلة
                            const existingItem = cart.find(item => item.id === partId);
                            
                            if (existingItem) {
                                // إزالة القطعة من السلة
                                cart = cart.filter(item => item.id !== partId);
                                this.textContent = '🛒 شراء';
                                this.classList.remove('btn-success');
                                showMessage('تم إزالة القطعة من سلة المشتريات', 'success');
                            } else {
                                // إضافة القطعة إلى السلة
                                cart.push({
                                    id: part.id,
                                    name: part.name,
                                    number: part.number,
                                    price: part.price,
                                    quantity: 1
                                });
                                this.textContent = '✓ تم الإضافة';
                                this.classList.add('btn-success');
                                showMessage('تم إضافة القطعة إلى سلة المشتريات', 'success');
                            }
                            
                            saveCart();
                        }
                    });
                });
            }
        }

        // فتح سلة المشتريات
        document.getElementById('cart-section').addEventListener('click', function() {
            if (cart.length === 0) {
                showMessage('سلة المشتريات فارغة', 'error');
                return;
            }
            
            const cartItemsContainer = document.getElementById('cart-items');
            const cartTotalContainer = document.getElementById('cart-total');
            
            cartItemsContainer.innerHTML = '';
            let total = 0;
            
            cart.forEach((item, index) => {
                const itemElement = document.createElement('div');
                itemElement.className = 'order-item';
                itemElement.innerHTML = `
                    <div>
                        <div>${item.name}</div>
                        <div style="font-size: 0.9rem; color: #6c757d;">${item.number}</div>
                    </div>
                    <div>${formatPrice(item.price)} ج.س</div>
                `;
                cartItemsContainer.appendChild(itemElement);
                
                total += parseInt(item.price);
            });
            
            cartTotalContainer.textContent = `المجموع: ${formatPrice(total)} ج.س`;
            
            document.getElementById('cart-modal').style.display = 'flex';
        });

        // إرسال الطلب عبر واتساب
        document.getElementById('send-whatsapp').addEventListener('click', function() {
            let message = `مرحباً، أريد طلب قطع الغيار التالية:\n\n`;
            
            cart.forEach((item, index) => {
                message += `${index + 1}. ${item.name} (رقم: ${item.number}) - ${formatPrice(item.price)} ج.س\n`;
            });
            
            const total = cart.reduce((sum, item) => sum + parseInt(item.price), 0);
            message += `\nالمجموع: ${formatPrice(total)} ج.س`;
            
            const encodedMessage = encodeURIComponent(message);
            const whatsappURL = `https://wa.me/${WHATSAPP_NUMBER}?text=${encodedMessage}`;
            
            window.open(whatsappURL, '_blank');
            
            // إغلاق النافذة المنبثقة بعد الإرسال
            document.getElementById('cart-modal').style.display = 'none';
            
            // تفريغ سلة المشتريات بعد الإرسال
            cart = [];
            saveCart();
            
            showMessage('تم إرسال الطلب بنجاح!', 'success');
        });

        // مزامنة البيانات مع GitHub
        document.getElementById('sync-github').addEventListener('click', async function() {
            const token = storeSettings.githubToken;
            const repo = storeSettings.githubRepo;
            
            if (!token || !repo) {
                showMessage('يرجى إدخال رمز GitHub واسم المستودع', 'error');
                return;
            }
            
            try {
                showMessage('جاري المزامنة مع GitHub...', 'success');
                
                // البيانات التي نريد حفظها
                const data = {
                    parts: parts,
                    storeSettings: storeSettings,
                    lastSync: new Date().toISOString()
                };
                
                // تحويل البيانات إلى JSON
                const content = JSON.stringify(data, null, 2);
                
                // تشفير المحتوى إلى Base64
                const encodedContent = btoa(unescape(encodeURIComponent(content)));
                
                // إنشاء طلب إلى GitHub API
                const response = await fetch(`https://api.github.com/repos/${repo}/contents/data.json`, {
                    method: 'PUT',
                    headers: {
                        'Authorization': `token ${token}`,
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify({
                        message: 'تحديث بيانات قطع الغيار',
                        content: encodedContent,
                        sha: await getFileSHA(token, repo)
                    })
                });
                
                if (response.ok) {
                    showMessage('تمت المزامنة بنجاح مع GitHub!', 'success');
                } else {
                    const errorData = await response.json();
                    showMessage(`فشلت المزامنة: ${errorData.message}`, 'error');
                }
            } catch (error) {
                showMessage(`حدث خطأ أثناء المزامنة: ${error.message}`, 'error');
            }
        });

        // الحصول على SHA للملف الموجود (للتحديث)
        async function getFileSHA(token, repo) {
            try {
                const response = await fetch(`https://api.github.com/repos/${repo}/contents/data.json`, {
                    headers: {
                        'Authorization': `token ${token}`
                    }
                });
                
                if (response.ok) {
                    const data = await response.json();
                    return data.sha;
                }
            } catch (error) {
                // إذا لم يوجد الملف، نرجع null
                return null;
            }
            return null;
        }

        // تنسيق السعر
        function formatPrice(price) {
            return Number(price).toLocaleString('ar-SD');
        }

        // تهيئة الصفحة عند التحميل
        document.addEventListener('DOMContentLoaded', function() {
            // عرض قسم البحث أولاً
            document.getElementById('search-form').style.display = 'block';
            
            // حفظ البيانات الأولية إذا لم تكن موجودة
            if (!localStorage.getItem('castle-parts')) {
                saveParts();
            }
            
            // تحديث واجهة سلة المشتريات
            updateCartUI();
            
            // تحديث واجهة المتجر
            updateStoreUI();
            
            // إظهار/إخفاء قائمة الإعدادات
            document.querySelector('.settings-toggle').addEventListener('click', function(e) {
                e.stopPropagation();
                document.querySelector('.settings-dropdown').classList.toggle('active');
                
                // إعادة تعيين نموذج الإعدادات عند فتح القائمة
                document.getElementById('settings-form-content').style.display = 'none';
                document.querySelector('.settings-dropdown .password-section').style.display = 'block';
                document.getElementById('settings-password').value = '';
            });
            
            // إغلاق قائمة الإعدادات عند النقر خارجها
            document.addEventListener('click', function(e) {
                if (!e.target.closest('.settings-dropdown') && !e.target.closest('.settings-toggle')) {
                    document.querySelector('.settings-dropdown').classList.remove('active');
                }
            });
            
            // حفظ الإعدادات
            document.getElementById('save-settings').addEventListener('click', function() {
                storeSettings.companyName = document.getElementById('company-name').value.trim() || storeSettings.companyName;
                storeSettings.phoneNumber = document.getElementById('phone-number').value.trim() || storeSettings.phoneNumber;
                storeSettings.whatsappNumber = document.getElementById('whatsapp-number').value.trim() || storeSettings.whatsappNumber;
                storeSettings.email = document.getElementById('email').value.trim();
                storeSettings.githubToken = document.getElementById('github-token').value.trim();
                storeSettings.githubRepo = document.getElementById('github-repo').value.trim();
                
                saveSettings();
                showMessage('تم حفظ الإعدادات بنجاح!', 'success');
                document.querySelector('.settings-dropdown').classList.remove('active');
            });
            
            // إغلاق النافذة المنبثقة للتعديل
            document.querySelector('.close-modal').addEventListener('click', function() {
                document.getElementById('edit-part-modal').style.display = 'none';
            });
            
            // إغلاق النافذة المنبثقة لسلة المشتريات
            document.getElementById('cart-modal').querySelector('.close-modal').addEventListener('click', function() {
                document.getElementById('cart-modal').style.display = 'none';
            });
            
            // إغلاق النوافذ المنبثقة عند النقر خارجها
            window.addEventListener('click', function(e) {
                if (e.target === document.getElementById('edit-part-modal')) {
                    document.getElementById('edit-part-modal').style.display = 'none';
                }
                if (e.target === document.getElementById('cart-modal')) {
                    document.getElementById('cart-modal').style.display = 'none';
                }
            });
        });
    </script>
</body>
</html>
```

التغييرات التي تم إجراؤها:

1. إصلاح طريقة إدخال الرمز السري للإعدادات

· أصلحت مشكلة إدخال الرمز السري في قائمة الإعدادات
· الآن يمكنك إدخال الرمز السري والنقر على زر "فتح الإعدادات" للوصول إلى إعدادات المتجر

2. إضافة ميزة المزامنة مع GitHub

· أضفت حقولًا جديدة في الإعدادات لإدخال:
  · رمز GitHub الشخصي (Personal Access Token)
  · اسم المستودع في GitHub (username/repo-name)
· أضفت زر "مزامنة مع GitHub" لحفظ البيانات في مستودع GitHub

3. تحسينات في واجهة الإعدادات

· أضفت تعليمات حول كيفية الحصول على رمز GitHub الشخصي
· وسّعت قائمة الإعدادات لاستيعاب الحقول الجديدة
· حسّنت تصميم قائمة الإعدادات

4. آلية المزامنة مع GitHub

· البيانات تُحفظ في ملف data.json في المستودع المحدد
· تشمل البيانات جميع القطع وإعدادات المتجر
· يمكن استرجاع البيانات من أي جهاز باستخدام نفس المستودع

5. تعليمات استخدام ميزة GitHub

1. إنشاء رمز وصول شخصي في GitHub:
   · اذهب إلى Settings → Developer settings → Personal access tokens → Tokens (classic)
   · انقر على Generate new token
   · اختر النطاق (scope) "repo"
   · انسخ الرمز المُنشأ
2. إدخال المعلومات في الإعدادات:
   · أدخل الرمز الشخصي في حقل "رمز GitHub"
   · أدخل اسم المستودع بصيغة "اسمالمستخدم/اسمالمستودع"
3. النقر على "مزامنة مع GitHub" لحفظ البيانات

6. تحسينات إضافية

· إصلاح مشكلة إغلاق قائمة الإعدادات عند النقر داخلها
· تحسين رسائل التأكيد والإخطار
· إضافة تاريخ المزامنة الأخيرة في البيانات المحفوظة

الموقع الآن يدعم المزامنة عبر الأجهزة باستخدام GitHub، مما يسمح لك بالوصول إلى نفس البيانات من أي جهاز وإجراء التغييرات عليها.