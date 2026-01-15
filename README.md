<!DOCTYPE html>
<html lang="lv">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rīgas Kristus Piedzimšanas Katedrāle - Pareizticīgo Draudze</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Roboto:wght@300;400;500&display=swap">
    
    <style>
        /* --- VISPĀRĪGIE IESTATĪJUMI --- */
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Roboto', sans-serif; }
        
        /* Definējam krāsas vienuviet, lai tās viegli mainītu visā lapā */
        :root {
            --primary: #2a5d84;   /* Tumši zils - galvenā krāsa */
            --secondary: #d4a84f; /* Zelta krāsa - akcentiem */
            --accent: #8b4513;    /* Brūns */
            --light: #f9f7f2;     /* Gaišs fons */
            --dark: #1a2a3a;      /* Tumšs teksts/fons */
            --gold-light: #e8c988;
            --blue-light: #a3c6e0;
        }

        body { background-color: var(--light); color: var(--dark); line-height: 1.7; overflow-x: hidden; }
        
        /* --- GALVENE (HEADER) --- */
        header {
            /* Fona attēls ar tumšu pārklājumu, lai teksts būtu lasāms */
            background: linear-gradient(rgba(26, 42, 58, 0.8), rgba(26, 42, 58, 0.8)), url('https://img1.advisor.travel/1314x680px-Nativity_Cathedral_Riga_29.jpg');
            background-size: cover; background-position: center;
            color: white; padding: 1rem 0; position: relative; height: 100vh;
            display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center;
        }
        
        /* Dekoratīvā līnija apakšā */
        .ornament {
            position: absolute; bottom: 0; left: 0; width: 100%; height: 60px;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 10" preserveAspectRatio="none"><path d="M0,0 L50,10 L100,0 Z" fill="%23d4a84f"/></svg>');
            background-repeat: repeat-x; z-index: 1;
        }

        /* Augšējā izvēlnes josla */
        .top-bar {
            position: absolute; top: 0; left: 0; right: 0;
            display: flex; justify-content: space-between; align-items: center;
            padding: 1rem 5%; background-color: rgba(0, 0, 0, 0.4); z-index: 100;
        }
        
        /* Logo stili */
        .logo { display: flex; align-items: center; }
        .logo img { height: 60px; margin-right: 15px; }
        .logo h1 { font-size: 1.5rem; font-weight: normal; text-transform: uppercase; letter-spacing: 1px; font-family: 'Playfair Display', serif; }
        
        /* Navigācija */
        nav ul { display: flex; list-style: none; }
        nav li { margin: 0 15px; }
        nav a { color: white; text-decoration: none; font-size: 1.1rem; transition: all 0.3s ease; padding: 8px 15px; border-radius: 4px; position: relative; }
        /* Animētā līnija zem saitēm */
        nav a:after { content: ''; position: absolute; width: 0; height: 2px; background: var(--secondary); bottom: 0; left: 50%; transform: translateX(-50%); transition: width 0.3s ease; }
        nav a:hover:after { width: 100%; }
        nav a:hover { color: var(--secondary); }

        /* Galvenais teksts centrā */
        .header-content { max-width: 900px; padding: 0 20px; margin-top: 60px; z-index: 2; }
        .header-content h2 { font-size: 3.5rem; margin-bottom: 1.5rem; font-weight: normal; text-shadow: 2px 2px 6px rgba(0,0,0,0.6); font-family: 'Playfair Display', serif; line-height: 1.2; }
        .header-content p { font-size: 1.4rem; margin-bottom: 2.5rem; max-width: 700px; text-shadow: 1px 1px 3px rgba(0,0,0,0.7); margin-left: auto; margin-right: auto; }

        /* --- POGU STILI (BUTTONS) --- */
        .btn {
            display: inline-block; background-color: var(--secondary); color: var(--dark);
            padding: 14px 35px; border-radius: 25px; text-decoration: none; font-weight: bold;
            margin: 10px 8px; transition: all 0.3s ease; border: 2px solid var(--secondary);
            font-size: 1.1rem; box-shadow: 0 4px 15px rgba(0,0,0,0.15); cursor: pointer;
        }
        .btn:hover { background-color: transparent; color: var(--secondary); transform: translateY(-3px); box-shadow: 0 8px 25px rgba(0,0,0,0.2); filter: brightness(1.05); }
        .btn-outline { background-color: transparent; color: var(--secondary); border: 2px solid var(--secondary); }
        .btn-outline:hover { background-color: var(--secondary); color: var(--dark); }

        /* --- SADAĻU STILI --- */
        section { padding: 6rem 10%; position: relative; }
        .section-title { text-align: center; margin-bottom: 4rem; }
        .section-title h2 { font-size: 2.8rem; color: var(--primary); margin-bottom: 1.5rem; position: relative; display: inline-block; font-family: 'Playfair Display', serif; }
        .section-title h2:after { content: ''; position: absolute; bottom: -15px; left: 50%; transform: translateX(-50%); width: 100px; height: 4px; background-color: var(--secondary); }
        .section-title p { max-width: 750px; margin: 25px auto 0; color: #666; font-size: 1.2rem; }

        /* --- 'FEATURES' (3 kārtis augšā) --- */
        .features { display: flex; justify-content: center; padding: 5rem 2rem; background-color: white; position: relative; }
        /* Zig-zag līnija virs sadaļas */
        .features:before { content: ''; position: absolute; top: -60px; left: 0; width: 100%; height: 60px; background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 10" preserveAspectRatio="none"><path d="M0,10 L50,0 L100,10 Z" fill="%23ffffff"/></svg>'); background-repeat: repeat-x; }
        .feature-card {
            width: 320px; margin: 0 20px; text-align: center; padding: 35px 25px;
            border-radius: 15px; box-shadow: 0 10px 30px rgba(42,93,132,0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease; background: white;
            position: relative; overflow: hidden; z-index: 1;
        }
        .feature-card:before { content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 4px; background: linear-gradient(90deg, var(--primary), var(--secondary)); }
        .feature-card:hover { transform: translateY(-10px); box-shadow: 0 15px 40px rgba(42,93,132,0.15); }
        .feature-icon { font-size: 3.5rem; color: var(--primary); margin-bottom: 25px; }
        .feature-card h3 { font-size: 1.6rem; margin-bottom: 18px; color: var(--primary); font-family: 'Playfair Display', serif; }

        /* --- PAR MUMS SADAĻA --- */
        .about-content { display: flex; align-items: center; gap: 60px; }
        .about-text { flex: 1; }
        .about-text h3 { font-size: 2rem; margin-bottom: 25px; color: var(--primary); font-family: 'Playfair Display', serif; }
        .about-image { flex: 1; border-radius: 15px; overflow: hidden; box-shadow: 0 15px 40px rgba(0,0,0,0.2); position: relative; }
        .about-image img { width: 100%; height: auto; display: block; transition: transform 0.5s ease; }
        .about-image:hover img { transform: scale(1.08); }

        /* --- NOTIKUMU SADAĻA --- */
        .events { background-color: #f0f5ff; position: relative; }
        .events:before { content: ''; position: absolute; top: -60px; left: 0; width: 100%; height: 60px; background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 10" preserveAspectRatio="none"><path d="M0,10 L50,0 L100,10 Z" fill="%23f0f5ff"/></svg>'); background-repeat: repeat-x; }
        .events-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); gap: 35px; }
        .event-card { background-color: white; border-radius: 15px; overflow: hidden; box-shadow: 0 8px 25px rgba(0,0,0,0.08); transition: transform 0.3s ease, box-shadow 0.3s ease; position: relative; }
        .event-card:hover { transform: translateY(-8px); box-shadow: 0 12px 30px rgba(0,0,0,0.12); }
        .event-image { height: 230px; overflow: hidden; position: relative; }
        .event-image img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.5s ease; }
        .event-card:hover .event-image img { transform: scale(1.15); }
        .event-content { padding: 25px; }
        .event-date { background-color: var(--secondary); color: var(--dark); display: inline-block; padding: 8px 20px; border-radius: 30px; font-weight: bold; margin-bottom: 18px; font-size: 1.1rem; }
        .event-content h3 { font-size: 1.5rem; margin-bottom: 15px; color: var(--primary); font-family: 'Playfair Display', serif; }

        /* --- KALENDĀRA DIZAINS --- */
        .calendar { background-color: #fff; border-radius: 15px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); overflow: hidden; margin-top: 40px; border: 1px solid #eee; }
        
        /* Kalendāra galvene ar pogām */
        .calendar-header { display: flex; justify-content: space-between; align-items: center; background: var(--primary); color: white; padding: 15px 20px; }
        .calendar-nav-btn { background: none; border: none; color: white; font-size: 1.2rem; cursor: pointer; padding: 5px 10px; transition: transform 0.2s ease, opacity 0.2s; }
        .calendar-nav-btn:hover { transform: scale(1.2); opacity: 0.8; }
        #calendar-month-year { font-family: 'Playfair Display', serif; font-size: 1.5rem; text-transform: capitalize; }
        
        /* Kalendāra režģis (7 dienas) */
        .calendar-grid { display: grid; grid-template-columns: repeat(7, 1fr); background-color: #fff; }
        .calendar-day, .calendar-day-header { aspect-ratio: 1 / 1; padding: 8px; border: 1px solid #f0f0f0; display: flex; flex-direction: column; justify-content: space-between; }
        .calendar-day-header { font-weight: bold; text-align: center; background: var(--gold-light); justify-content: center; align-items: center; }
        .day-number { align-self: flex-start; }
        
        /* Notikums kalendārā (zilais klucītis) */
        .calendar-event { background: var(--blue-light); border-radius: 4px; padding: 5px; font-size: 0.9rem; cursor: pointer; transition: background-color 0.3s ease; width: 100%; text-align: center; color: var(--dark); margin-top: 4px; overflow: hidden; white-space: nowrap; text-overflow: ellipsis; }
        .event-time { font-weight: bold; display: block; margin-top: 2px; }
        .calendar-event:hover { background: var(--secondary); color: var(--dark); }
        .calendar-day.today { background-color: rgba(212, 168, 79, 0.1); }
        .calendar-day.today .day-number { background: var(--secondary); color: var(--dark); border-radius: 50%; width: 28px; height: 28px; display: inline-flex; align-items: center; justify-content: center; }

        /* --- GALERIJA --- */
        .gallery { position: relative; background: linear-gradient(to bottom, var(--light), var(--blue-light)); }
        .gallery-container { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 20px; }
        .gallery-item { border-radius: 12px; overflow: hidden; height: 280px; box-shadow: 0 8px 20px rgba(0,0,0,0.15); cursor: pointer; position: relative; }
        .gallery-item img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.5s ease; }
        .gallery-item:hover img { transform: scale(1.15); }
        .gallery-item:after { content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: linear-gradient(to top, rgba(42, 93, 132, 0.7), transparent); opacity: 0; transition: opacity 0.3s ease; }
        .gallery-item:hover:after { opacity: 1; }

        /* --- KONTAKTI --- */
        .contact { background: linear-gradient(rgba(42, 93, 132, 0.92), rgba(42, 93, 132, 0.92)), url('https://img1.advisor.travel/1314x680px-Nativity_Cathedral_Riga_29.jpg'); background-size: cover; background-position: center; background-attachment: fixed; color: white; text-align: center; position: relative; }
        .contact .section-title h2 { color: var(--secondary); }
        .contact .section-title p { color: rgba(255,255,255,0.85); }
        .contact:before { content: ''; position: absolute; top: -60px; left: 0; width: 100%; height: 60px; background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 10" preserveAspectRatio="none"><path d="M0,10 L50,0 L100,10 Z" fill="%232a5d84"/></svg>'); background-repeat: repeat-x; opacity: 0.92; }
        
        .contact-container { display: flex; justify-content: space-between; max-width: 1300px; margin: 0 auto; gap: 50px; }
        .contact-info, .contact-form { flex: 1; background-color: rgba(26, 42, 58, 0.7); padding: 40px; border-radius: 15px; backdrop-filter: blur(5px); border: 1px solid rgba(255, 255, 255, 0.1); }
        .contact-info h3, .contact-form h3 { font-size: 2rem; margin-bottom: 30px; color: var(--secondary); font-family: 'Playfair Display', serif; }
        .contact-item { display: flex; align-items: flex-start; margin-bottom: 25px; text-align: left; }
        .contact-icon { font-size: 1.7rem; color: var(--secondary); margin-right: 20px; min-width: 35px; }
        .contact-text h4 { margin-bottom: 8px; font-size: 1.3rem; }
        .contact-form input, .contact-form textarea, .contact-form select { width: 100%; padding: 15px; margin-bottom: 22px; border: 1px solid #ddd; border-radius: 8px; background-color: rgba(255, 255, 255, 0.95); font-size: 1.1rem; transition: all 0.3s ease; }
        .contact-form input:focus, .contact-form textarea:focus, .contact-form select:focus { outline: none; border-color: var(--primary); box-shadow: 0 0 0 3px rgba(42, 93, 132, 0.2); }
        .contact-form textarea { height: 180px; resize: vertical; }

        /* --- KĀJENE (FOOTER) --- */
        footer { background-color: var(--dark); color: white; padding: 4rem 10% 1.5rem; position: relative; }
        footer:before { content: ''; position: absolute; top: -60px; left: 0; width: 100%; height: 60px; background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 10" preserveAspectRatio="none"><path d="M0,0 L50,10 L100,0 Z" fill="%231a2a3a"/></svg>'); background-repeat: repeat-x; }
        .footer-container { display: flex; justify-content: space-between; flex-wrap: wrap; gap: 50px; margin-bottom: 3rem; }
        .footer-col { flex: 1; min-width: 280px; }
        .footer-col h4 { font-size: 1.4rem; margin-bottom: 25px; color: var(--secondary); position: relative; padding-bottom: 12px; font-family: 'Playfair Display', serif; }
        .footer-col h4::after { content: ''; position: absolute; bottom: 0; left: 0; width: 60px; height: 3px; background-color: var(--secondary); }
        .footer-col ul { list-style: none; }
        .footer-col ul li { margin-bottom: 14px; display: flex; align-items: flex-start; }
        .footer-col ul li i { color: var(--secondary); margin-right: 12px; margin-top: 5px; }
        .footer-col ul li a { color: #ddd; text-decoration: none; transition: color 0.3s ease; flex: 1; }
        .footer-col ul li a:hover { color: var(--secondary); }
        .social-links { display: flex; gap: 18px; margin-top: 25px; }
        .social-links a { display: flex; align-items: center; justify-content: center; width: 50px; height: 50px; background-color: rgba(255, 255, 255, 0.12); border-radius: 50%; color: white; transition: all 0.4s ease; font-size: 1.4rem; }
        .social-links a:hover { background-color: var(--secondary); color: var(--dark); transform: translateY(-5px); }
        .copyright { text-align: center; padding-top: 25px; border-top: 1px solid rgba(255, 255, 255, 0.15); font-size: 1rem; color: #aaa; }

        /* --- MUZNIRSTOŠIE LOGI --- */
        .modal, .lightbox { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 1000; overflow: auto; }
        .modal { background-color: rgba(0, 0, 0, 0.8); justify-content: center; align-items: center; padding: 20px; }
        .lightbox { background-color: rgba(0,0,0,0.9); z-index: 1001; padding-top: 60px; }
        .modal-content { background-color: var(--light); max-width: 700px; width: 100%; border-radius: 15px; overflow: hidden; box-shadow: 0 15px 45px rgba(0, 0, 0, 0.3); position: relative; animation: modalOpen 0.5s ease; }
        @keyframes modalOpen { from { opacity: 0; transform: translateY(-50px); } to { opacity: 1; transform: translateY(0); } }
        .modal-header { background-color: var(--primary); color: white; padding: 25px; display: flex; justify-content: space-between; align-items: center; }
        .modal-header h3 { font-size: 1.8rem; font-family: 'Playfair Display', serif; }
        .close-modal, .lightbox-close { cursor: pointer; transition: 0.3s; color: white; border: none; background: none; }
        .close-modal { font-size: 2rem; }
        .lightbox-close { position: absolute; top: 15px; right: 35px; font-size: 40px; font-weight: bold; }
        .close-modal:hover { transform: rotate(90deg); }
        .modal-body { padding: 30px; max-height: 70vh; overflow-y: auto; }
        .modal-form .form-group { margin-bottom: 20px; }
        .modal-form label { display: block; margin-bottom: 8px; font-weight: 500; color: var(--dark); }
        .modal-form input, .modal-form select, .modal-form textarea { width: 100%; padding: 14px; border: 1px solid #ddd; border-radius: 8px; font-size: 1.1rem; transition: border-color 0.3s, box-shadow 0.3s; }
        .modal-form input:focus, .modal-form select:focus, .modal-form textarea:focus { border-color: var(--primary); outline: none; box-shadow: 0 0 0 3px rgba(42, 93, 132, 0.2); }
        .modal-footer { padding: 20px 30px; background-color: #f5f5f5; text-align: right; border-top: 1px solid #eee; }
        .lightbox-content { margin: auto; display: block; width: 80%; max-width: 800px; animation-name: zoom; animation-duration: 0.6s; }
        @keyframes zoom { from {transform:scale(0)} to {transform:scale(1)} }

        /* --- MOBILĀS IERĪCES --- */
        .mobile-menu-btn { display: none; background: none; border: none; color: white; font-size: 1.8rem; cursor: pointer; }
        .mobile-menu { position: fixed; top: 0; right: -300px; width: 300px; height: 100vh; background-color: var(--dark); z-index: 1000; padding: 30px; transition: right 0.4s ease; box-shadow: -5px 0 15px rgba(0, 0, 0, 0.2); }
        .mobile-menu.active { right: 0; }
        .mobile-menu ul { list-style: none; margin-top: 60px; }
        .mobile-menu ul li { margin-bottom: 25px; }
        .mobile-menu ul li a { color: white; text-decoration: none; font-size: 1.3rem; display: block; padding: 12px; border-bottom: 1px solid rgba(255, 255, 255, 0.1); transition: color 0.3s; }
        .mobile-menu ul li a:hover { color: var(--secondary); }
        .close-menu { position: absolute; top: 25px; right: 25px; background: none; border: none; color: white; font-size: 1.8rem; cursor: pointer; }

        /* Adaptīvā dizaina punkti */
        @media (max-width: 1200px) { .about-content { flex-direction: column; } .contact-container { flex-direction: column; } .feature-card { margin-bottom: 40px; } }
        @media (max-width: 992px) { nav ul { display: none; } .header-content h2 { font-size: 2.8rem; } .features { flex-wrap: wrap; } .section-title h2 { font-size: 2.3rem; } .mobile-menu-btn { display: block; } }
        @media (max-width: 768px) { .header-content h2 { font-size: 2.2rem; } .header-content p { font-size: 1.2rem; } }
        @media (max-width: 576px) { .logo h1 { font-size: 1.1rem; } }
    </style>
</head>
<body>
    <header>
        <div class="top-bar">
            <div class="logo">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyMDAgMjAwIj48Y2lyY2xlIGN4PSIxMDAiIGN5PSIxMDAiIHI9Ijk1IiBmaWxsPSJub25lIiBzdHJva2U9IiNkNGE4NGYiIHN0cm9rZS13aWR0aD0iOCIvPjxwYXRoIGQ9Ik0xMDAgMzBDNjAgMzAgMzAgNjAgMzAgMTAwYzAgNDAgMzAgNzAgNzAgNzAgNDAgMCA3MC0zMCA3MC03MGMwLTQwLTMwLTcwLTcwLTcweiIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMmE1ZDg0IiBzdHJva2Utd2lkdGg9IjgiLz48Y2lyY2xlIGN4PSIxMDAiIGN5PSIxMDAiIHI9IjYwIiBmaWxsPSJub25lIiBzdHJva2U9IiNkNGE4NGYiIHN0cm9rZS13aWR0aD0iOCIvPjxjaXJjbGUgY3g9IjEwMCIgY3k9IjEwMCIgcj0iNDAiIGZpbGw9IiMyYTVkODQiIG9wYWNpdHk9IjAuMyIvPjxwYXRoIGQ9Ik04MCAxMDBoNDBNMTAwIDgwdjQwIiBzdHJva2U9IiNmZmYiIHN0cm9rZS13aWR0aD0iOCIvPjwvc3ZnPg==" alt="Katedrāles logo">
                <h1>Rīgas Kristus Piedzimšanas Katedrāle</h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#sakums">Sākums</a></li>
                    <li><a href="#par-mums">Par mums</a></li>
                    <li><a href="#notikumi">Notikumi</a></li>
                    <li><a href="#galerija">Galerija</a></li>
                    <li><a href="#kontakti">Kontakti</a></li>
                </ul>
            </nav>
            <button class="mobile-menu-btn" aria-label="Izvēlne">
                <i class="fas fa-bars"></i>
            </button>
        </div>
        <div class="header-content">
            <h2>Sveicināti Rīgas Kristus Piedzimšanas Katedrālē</h2>
            <p>Latvijas Pareizticīgās Baznīcas sirds un dvēseles miera vieta kopš 1877. gada</p>
            <div>
                <a href="#notikumi" class="btn">Tuvākie notikumi</a>
                <a href="#kontakti" class="btn btn-outline">Apmeklēt draudzi</a>
            </div>
        </div>
        <div class="ornament"></div>
    </header>

    <section class="features">
        <div class="feature-card">
            <div class="feature-icon"><i class="fas fa-church"></i></div>
            <h3>Dievkalpojumi</h3>
            <p>Svētdienās un svētku dienās pulcēsimies kopā Dieva godam un garīgā stiprināšanās</p>
        </div>
        <div class="feature-card">
            <div class="feature-icon"><i class="fas fa-hands-praying"></i></div>
            <h3>Garīgā palīdzība</h3>
            <p>Mūsu garīdznieki vienmēr ir gatavi jums palīdzēt un atbalstīt garīgajā ceļojumā</p>
        </div>
        <div class="feature-card">
            <div class="feature-icon"><i class="fas fa-people-group"></i></div>
            <h3>Draudzes kopiena</h3>
            <p>Piedalieties mūsu dažādajās draudzes aktivitātēs un kopienas dzīvē</p>
        </div>
    </section>

    <section id="par-mums" class="about">
        <div class="section-title">
            <h2>Par Mūsu Draudzi</h2>
            <p>Rīgas Kristus Piedzimšanas pareizticīgo katedrāle ir viena no nozīmīgākajām pareizticīgo baznīcām Latvijā</p>
        </div>
        <div class="about-content">
            <div class="about-text">
                <h3>Mūsu vēsture un misija</h3>
                <p>Katedrāle tika uzcelta 1877. gadā un ir kalpojusi kā garīgais centrs pareizticīgajiem Rīgā jau vairāk nekā 140 gadus. Mūsu misija ir izplatīt Kristus mīlestību, sniegt garīgo vadību un veicināt kopienas attīstību.</p>
                <p>Katedrāles arhitektūra ir ievērojams piemērs neobizantiešu stila baznīcām Baltijā. Tās iekštelpas rotā grezni freskas un ikonostas, kas rada patiesi svētku atmosfēru.</p>
                <p>Mēs atveram savas durvis ikvienam, kas meklē garīgo mieru, atbalstu un kopienu. Piedalieties mūsu dievkalpojumos, garīgajās nodarbībās un kopienas pasākumos.</p>
                <a href="#" class="btn" id="learn-more-btn">Uzzināt vairāk</a>
            </div>
            <div class="about-image">
                <img src="https://upload.wikimedia.org/wikipedia/commons/9/99/Catedral_de_la_Natividad_de_Cristo%2C_Riga%2C_Letonia%2C_2012-08-07%2C_DD_03.JPG" alt="Katedrāles iekštelpas">
            </div>
        </div>
    </section>

    <section id="notikumi" class="events">
        <div class="section-title">
            <h2>Tuvākie Notikumi</h2>
            <p>Piedalieties mūsu garīgajos pasākumos un kopienas aktivitātēs</p>
        </div>
        <div class="events-container">
            <div class="event-card">
                <div class="event-image"><img src="https://zinas.nra.lv/_mm/photos/2023-01/1440px/591530_7cebb8e607.jpg" loading="lazy" alt="Dievkalpojums"></div>
                <div class="event-content">
                    <div class="event-date">Janvāris 22, 10:00</div>
                    <h3>Svētdienas dievkalpojums</h3>
                    <p>Iknedēļas svētdienas dievkalpojums ar garīgajām dziesmām, lūgšanām un svēto Liturģiju.</p>
                    <a href="#" class="btn register-btn" data-event="Svētdienas dievkalpojums">Pieteikties</a>
                </div>
            </div>
            <div class="event-card">
                <div class="event-image"><img src="https://static1.squarespace.com/static/59ccbd1c2278e76a7fedfe78/t/5ebd90325aff806ad80fa9af/1589481526501/Child_and_Icon_of_Christ_in_Church.jpg?format=1500w" loading="lazy" alt="Bērnu nodarbības"></div>
                <div class="event-content">
                    <div class="event-date">Janvāris 24, 16:00</div>
                    <h3>Bērnu garīgās audzināšanas nodarbības</h3>
                    <p>Nodarbības bērniem par baznīcas tradīcijām, svētajiem rakstiem un garīgajām vērtībām.</p>
                    <a href="#" class="btn register-btn" data-event="Bērnu garīgās audzināšanas nodarbības">Pieteikties</a>
                </div>
            </div>
            <div class="event-card">
                <div class="event-image"><img src="https://resources.cdn.uzdevumi.lv/578bfc2f-f254-48a5-82b3-9ef57096cded/shutterstock146893088w300png.png" loading="lazy" alt="Koncerts"></div>
                <div class="event-content">
                    <div class="event-date">Janvāris 29, 18:00</div>
                    <h3>Sakrālās mūzikas koncerts</h3>
                    <p>Garīgo dziesmu vakars ar vietējo baznīcas koru un viesmāksliniekiem.</p>
                    <a href="#" class="btn register-btn" data-event="Sakrālās mūzikas koncerts">Pieteikties</a>
                </div>
            </div>
        </div>

        <div class="section-title" style="margin-top: 80px;">
            <h2>Notikumu Kalendārs</h2>
            <p>Plānojiet savu laiku un piedalieties mūsu pasākumos</p>
        </div>
        
        <div class="calendar">
            <div class="calendar-header">
                <button id="prev-month" class="calendar-nav-btn"><i class="fas fa-chevron-left"></i></button>
                <span id="calendar-month-year" class="calendar-title">Janvāris 2026</span>
                <button id="next-month" class="calendar-nav-btn"><i class="fas fa-chevron-right"></i></button>
            </div>
            <div class="calendar-grid">
                </div>
        </div>
    </section>

    <section id="galerija" class="gallery">
        <div class="section-title">
            <h2>Baznīcas Galerija</h2>
            <p>Apskatiet mūsu katedrāles skaistumu un garīgo atmosfēru</p>
        </div>
        <div class="gallery-container">
            <div class="gallery-item"><img src="https://www.russkije.lv/media/original/i/ikonostas_hristorozd_sobora.jpg" loading="lazy" alt="Katedrāles iekštelpas"></div>
            <div class="gallery-item"><img src="https://www.russkije.lv/media/original/k/krist-piedz-katedr-pareizticiba.lvX.jpg" loading="lazy" alt="Ikonostas"></div>
            <div class="gallery-item"><img src="https://img1.advisor.travel/1314x680px-Nativity_Cathedral_Riga_29.jpg" loading="lazy" alt="Dievkalpojums"></div>
            <div class="gallery-item"><img src="https://cdntest.db.lv/lvold/735/2019/article/0024/234002/206322_ORIGINAL_1295020783.jpg" loading="lazy" alt="Bērnu nodarbības"></div>
            <div class="gallery-item"><img src="https://the-passenger.de/wp-content/uploads/2019/07/7033556083849628689_img_1350-2000x1200.jpg" loading="lazy" alt="Koncerts"></div>
            <div class="gallery-item"><img src="https://media-cdn.tripadvisor.com/media/photo-s/0c/a1/51/7e/rigas-kristus-piedzimsanas.jpg" loading="lazy" alt="Katedrāles eksterjers"></div>
        </div>
    </section>

    <section id="kontakti" class="contact">
        <div class="section-title">
            <h2>Sazināties ar Mums</h2>
            <p>Mēs ar prieku atbildēsim uz visiem jūsu jautājumiem</p>
        </div>
        <div class="contact-container">
            <div class="contact-info">
                <h3>Mūsu kontakti</h3>
                <div class="contact-item"><div class="contact-icon"><i class="fas fa-map-marker-alt"></i></div><div class="contact-text"><h4>Adrese</h4><p>Brīvības bulvāris 23, Rīga, LV-1050</p></div></div>
                <div class="contact-item"><div class="contact-icon"><i class="fas fa-phone"></i></div><div class="contact-text"><h4>Telefons</h4><p>+371 67 123 456</p></div></div>
                <div class="contact-item"><div class="contact-icon"><i class="fas fa-envelope"></i></div><div class="contact-text"><h4>E-pasts</h4><p>info@rigaskatedrale.lv</p></div></div>
                <div class="contact-item"><div class="contact-icon"><i class="fas fa-clock"></i></div><div class="contact-text"><h4>Darba laiks</h4><p>Pirmdiena - Piektdiena: 9:00 - 17:00<br>Svētdiena: 7:00 - 19:00</p></div></div>
                <div class="map" style="height: 250px; background-color: #eee; margin-top: 30px; border-radius: 10px; overflow: hidden;">
                    <iframe src="https://maps.google.com/maps?q=Br%C4%ABv%C4%ABbas%20bulv%C4%81ris%2023,%20R%C4%ABga&t=&z=15&ie=UTF8&iwloc=&output=embed" width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
                </div>
            </div>
            <div class="contact-form">
                <h3>Sūtīt ziņu</h3>
                <form>
                    <input type="text" placeholder="Vārds" required>
                    <input type="email" placeholder="E-pasts" required>
                    <input type="tel" placeholder="Telefons">
                    <select><option value="" disabled selected>Izvēlieties tematu</option><option>Garīgie jautājumi</option><option>Kāzu organizēšana</option><option>Bērnu kristības</option><option>Ziedojumi</option><option>Cits jautājums</option></select>
                    <textarea placeholder="Jūsu ziņa..." required></textarea>
                    <button type="submit" class="btn">Sūtīt ziņu</button>
                </form>
            </div>
        </div>
    </section>

    <footer>
        <div class="footer-container">
            <div class="footer-col">
                <h4>Rīgas Kristus Piedzimšanas Katedrāle</h4>
                <p>Latvijas Pareizticīgās Baznīcas sirds un dvēseles miera vieta kopš 1877. gada.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a><a href="#"><i class="fab fa-instagram"></i></a><a href="#"><i class="fab fa-youtube"></i></a><a href="#"><i class="fab fa-twitter"></i></a>
                </div>
            </div>
            <div class="footer-col">
                <h4>Ātras saites</h4>
                <ul>
                    <li><i class="fas fa-chevron-right"></i><a href="#sakums">Sākums</a></li>
                    <li><i class="fas fa-chevron-right"></i><a href="#par-mums">Par mums</a></li>
                    <li><i class="fas fa-chevron-right"></i><a href="#notikumi">Notikumi</a></li>
                    <li><i class="fas fa-chevron-right"></i><a href="#galerija">Galerija</a></li>
                    <li><i class="fas fa-chevron-right"></i><a href="#kontakti">Kontakti</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h4>Dievkalpojumu laiki</h4>
                <ul>
                    <li><i class="far fa-calendar-alt"></i> Svētdienas: 8:00 - 11:00</li>
                    <li><i class="far fa-calendar-alt"></i> Sestdienas: 17:00 - 19:00</li>
                    <li><i class="far fa-calendar-alt"></i> Svētku dienas: 9:00 - 12:00</li>
                    <li><i class="far fa-calendar-alt"></i> Veselības svētīšana: Ceturdienās 15:00</li>
                </ul>
            </div>
            <div class="footer-col">
                <h4>Ziedojumi</h4>
                <p>Jūsu ziedojumi palīdz uzturēt un attīstīt mūsu katedrāli.</p>
                <a href="#" class="btn" id="donate-btn">Ziedot</a>
            </div>
        </div>
        <div class="copyright">
            <p>© 2025 Rīgas Kristus Piedzimšanas Pareizticīgo Katedrāle. Visas tiesības aizsargātas.</p>
        </div>
    </footer>

    <div id="lightbox-modal" class="lightbox"><span class="lightbox-close">×</span><img class="lightbox-content" id="lightbox-image"></div>
    
    <div class="mobile-menu">
        <button class="close-menu"><i class="fas fa-times"></i></button>
        <ul><li><a href="#sakums">Sākums</a></li><li><a href="#par-mums">Par mums</a></li><li><a href="#notikumi">Notikumi</a></li><li><a href="#galerija">Galerija</a></li><li><a href="#kontakti">Kontakti</a></li></ul>
    </div>
    
    <div class="modal" id="registration-modal">
        <div class="modal-content">
            <div class="modal-header"><h3 id="modal-event-title">Pieteikšanās notikumam</h3><button class="close-modal">×</button></div>
            <div class="modal-body">
                <form class="modal-form" id="registration-form">
                    <div class="form-group"><label for="event-name">Notikums:</label><input type="text" id="event-name" readonly></div>
                    <div class="form-group"><label for="full-name">Vārds, Uzvārds*</label><input type="text" id="full-name" required></div>
                    <div class="form-group"><label for="email">E-pasts*</label><input type="email" id="email" required></div>
                    <div class="form-group"><label for="phone">Telefons</label><input type="tel" id="phone"></div>
                    <div class="form-group"><label for="participants">Dalībnieku skaits*</label><input type="number" id="participants" min="1" value="1" required></div>
                    <div class="form-group"><label for="message">Papildus informācija</label><textarea id="message" rows="3"></textarea></div>
                </form>
            </div>
            <div class="modal-footer"><button type="submit" form="registration-form" class="btn">Nosūtīt pieteikumu</button></div>
        </div>
    </div>
    
    <div class="modal" id="learn-more-modal">
        <div class="modal-content">
            <div class="modal-header"><h3>Par Mūsu Draudzi</h3><button class="close-modal">×</button></div>
            <div class="modal-body">
                <h4>Vēsturiskā apskats</h4><p>Rīgas Kristus Piedzimšanas pareizticīgo katedrāle tika uzcelta 1877. gadā...</p>
                <h4>Arhitektūras īpatnības</h4><p>Katedrāle ir iespaidīgs arhitektūras piemineklis...</p>
                <h4>Garīgā dzīve</h4><p>Mūsu draudze ir aktīva un daudzveidīga...</p>
            </div>
            <div class="modal-footer"><button class="btn close-modal-btn">Aizvērt</button></div>
        </div>
    </div>
    
    <div class="modal" id="event-details-modal">
        <div class="modal-content">
            <div class="modal-header"><h3 id="event-details-title">Notikuma informācija</h3><button class="close-modal">×</button></div>
            <div class="modal-body" id="event-details-body"></div>
            <div class="modal-footer"><button class="btn" id="register-from-calendar-btn">Pieteikties</button><button class="btn btn-outline close-modal-btn">Aizvērt</button></div>
        </div>
    </div>
    
    <div class="modal" id="donation-modal">
        <div class="modal-content">
            <div class="modal-header"><h3>Atbalstiet Mūsu Draudzi</h3><button class="close-modal">×</button></div>
            <div class="modal-body">
                <form class="modal-form" id="donation-form">
                    <div class="form-group"><label for="donor-name">Vārds, Uzvārds</label><input type="text" id="donor-name"></div>
                    <div class="form-group"><label for="donor-email">E-pasts</label><input type="email" id="donor-email"></div>
                    <div class="form-group"><label for="donation-amount">Ziedojuma summa (EUR)*</label><input type="number" id="donation-amount" min="1" required></div>
                    <div class="form-group"><label for="donation-purpose">Mērķis</label><select id="donation-purpose"><option value="general">Vispārējs ziedojums</option><option value="renovation">Katedrāles renovācija</option><option value="other">Cits</option></select></div>
                </form>
            </div>
            <div class="modal-footer"><button type="submit" form="donation-form" class="btn">Ziedot</button></div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // --- PALĪGFUNKCIJAS ---
            // Īsāks pieraksts: get('id') aizvieto document.getElementById('id')
            const get = id => document.getElementById(id);
            const getAll = sel => document.querySelectorAll(sel);
            const show = el => el.style.display = 'flex';
            const hide = el => el.style.display = 'none';

            // --- MOBILĀ IZVĒLNE ---
            const mobileMenu = document.querySelector('.mobile-menu');
            document.querySelector('.mobile-menu-btn').addEventListener('click', () => mobileMenu.classList.add('active'));
            document.querySelector('.close-menu').addEventListener('click', () => mobileMenu.classList.remove('active'));

            // --- PLŪDENĀ RITINĀŠANA (SMOOTH SCROLL) ---
            getAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        mobileMenu.classList.remove('active');
                        window.scrollTo({ top: targetElement.offsetTop - 80, behavior: 'smooth' });
                    }
                });
            });

            // --- UZNIRSTOŠO LOGU SISTĒMA (MODALS) ---
            const modals = getAll('.modal');
            const eventNameInput = get('event-name');
            const lightbox = get('lightbox-modal');
            
            // Aizvēršanas pogu loģika
            getAll('.close-modal, .close-modal-btn, .lightbox-close').forEach(btn => {
                btn.addEventListener('click', function() {
                    const modal = this.closest('.modal') || this.closest('.lightbox');
                    if(modal) hide(modal);
                });
            });

            // Aizvērt, ja noklikšķina ārpus loga
            window.addEventListener('click', (e) => {
                modals.forEach(m => { if(e.target === m) hide(m); });
                if(e.target === lightbox) hide(lightbox);
            });

            // Pogu darbības (atvērt logus)
            get('learn-more-btn')?.addEventListener('click', (e) => { e.preventDefault(); show(get('learn-more-modal')); });
            get('donate-btn')?.addEventListener('click', (e) => { e.preventDefault(); show(get('donation-modal')); });

            getAll('.register-btn').forEach(btn => {
                btn.addEventListener('click', function(e) {
                    e.preventDefault();
                    eventNameInput.value = this.getAttribute('data-event');
                    show(get('registration-modal'));
                });
            });

            // Formu nosūtīšana (simulācija ar alert)
            get('registration-form')?.addEventListener('submit', function(e) {
                e.preventDefault(); alert('Paldies par pieteikšanos!'); this.reset(); hide(get('registration-modal'));
            });
            get('donation-form')?.addEventListener('submit', function(e) {
                e.preventDefault(); alert('Paldies par ziedojumu!'); this.reset(); hide(get('donation-modal'));
            });
            document.querySelector('.contact-form form')?.addEventListener('submit', function(e) {
                e.preventDefault(); alert('Paldies par ziņu!'); this.reset();
            });

            // --- KALENDĀRA LOĢIKA ---
            const eventsData = {
                '2026-0-22': { title: 'Svētdienas dievkalpojums', time: '10:00', description: 'Iknedēļas dievkalpojums.', canRegister: true },
                '2026-0-24': { title: 'Bērnu nodarbības', time: '16:00', description: 'Nodarbības bērniem.', canRegister: true },
                '2026-0-29': { title: 'Koncerts', time: '18:00', description: 'Garīgo dziesmu vakars.', canRegister: true }
            };

            let calDate = new Date();
            // Iestatām sākuma datumu uz 2026. gada janvāri demo nolūkiem
            calDate.setFullYear(2026); calDate.setMonth(0);

            const monthNames = ["Janvāris", "Februāris", "Marts", "Aprīlis", "Maijs", "Jūnijs", "Jūlijs", "Augusts", "Septembris", "Oktobris", "Novembris", "Decembris"];
            const calGrid = document.querySelector('.calendar-grid');
            const calTitle = get('calendar-month-year');
            const evtModal = get('event-details-modal');

            // Galvenā funkcija, kas ģenerē kalendāra rūtiņas
            function renderCalendar() {
                const y = calDate.getFullYear(), m = calDate.getMonth();
                calTitle.textContent = `${monthNames[m]} ${y}`;
                
                let html = '<div class="calendar-day-header">P</div><div class="calendar-day-header">O</div><div class="calendar-day-header">T</div><div class="calendar-day-header">C</div><div class="calendar-day-header">P</div><div class="calendar-day-header">S</div><div class="calendar-day-header">Sv</div>';
                
                // Aprēķina, kurā nedēļas dienā sākas mēnesis
                const firstDay = new Date(y, m, 1).getDay();
                const daysInMonth = new Date(y, m + 1, 0).getDate();
                const offset = (firstDay === 0) ? 6 : firstDay - 1;

                // Tukšās dienas pirms mēneša sākuma
                for(let i=0; i<offset; i++) html += '<div class="calendar-day empty"></div>';
                
                const today = new Date();
                
                // Ģenerē dienas
                for(let d=1; d<=daysInMonth; d++) {
                    const key = `${y}-${m}-${d}`;
                    const isToday = d===today.getDate() && m===today.getMonth() && y===today.getFullYear() ? ' today' : '';
                    let evtHtml = '';
                    // Ja šajā datumā ir notikums, pievieno to
                    if(eventsData[key]) {
                        evtHtml = `<div class="calendar-event" data-key="${key}"><span>${eventsData[key].title}</span><span class="event-time">${eventsData[key].time}</span></div>`;
                    }
                    html += `<div class="calendar-day${isToday}"><span class="day-number">${d}</span>${evtHtml}</div>`;
                }
                calGrid.innerHTML = html;
            }

            // Kalendāra navigācijas pogas (< un >)
            get('prev-month').addEventListener('click', () => { calDate.setMonth(calDate.getMonth()-1); renderCalendar(); });
            get('next-month').addEventListener('click', () => { calDate.setMonth(calDate.getMonth()+1); renderCalendar(); });

            // Kalendāra notikumu klikšķu apstrāde
            calGrid.addEventListener('click', (e) => {
                const evtEl = e.target.closest('.calendar-event');
                if(evtEl) {
                    e.stopPropagation();
                    const data = eventsData[evtEl.dataset.key];
                    get('event-details-title').textContent = data.title;
                    get('event-details-body').innerHTML = `<p><strong>Laiks:</strong> ${data.time}</p><p>${data.description}</p>`;
                    
                    const regBtn = get('register-from-calendar-btn');
                    if(data.canRegister) {
                        regBtn.style.display = 'inline-block';
                        regBtn.onclick = () => { eventNameInput.value = data.title; hide(evtModal); show(get('registration-modal')); };
                    } else regBtn.style.display = 'none';
                    
                    show(evtModal);
                }
            });

            renderCalendar(); // Palaiž kalendāru pirmo reizi

            // --- ATTĒLU APSKATS (LIGHTBOX) ---
            getAll('.gallery-item').forEach(item => {
                item.addEventListener('click', () => {
                    show(lightbox);
                    get('lightbox-image').src = item.querySelector('img').src;
                });
            });

            // --- ANIMĀCIJAS UZ RITINĀŠANU ---
            const obs = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });

            getAll('.feature-card, .event-card, .about-image, .gallery-item').forEach(el => {
                el.style.opacity = 0;
                el.style.transform = 'translateY(30px)';
                el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                obs.observe(el);
            });
        });
    </script>
</body>
</html>
