# imnacode
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FLSH - Plateforme Universitaire</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #3F51B5;
            --secondary: #FF5722;
            --accent: #4CAF50;
            --dark: #2C3E50;
            --light: #F5F7FA;
            --warning: #FFC107;
        }
        
        body {
            font-family: 'Roboto', sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }
        
        /* Header animé */
        header {
            background: linear-gradient(135deg, var(--primary), #5C6BC0);
            color: white;
            padding: 0.5rem 0;
            box-shadow: 0 4px 20px rgba(0,0,0,0.15);
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 70%);
            animation: pulse 15s infinite linear;
        }
        
        @keyframes pulse {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .logo-icon {
            margin-right: 10px;
            color: var(--warning);
            font-size: 2rem;
        }
        
        .nav-links {
            display: flex;
            gap: 1.5rem;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            transition: all 0.3s ease;
            position: relative;
        }
        
        .nav-links a:hover {
            background: rgba(255,255,255,0.15);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            width: 0;
            height: 2px;
            background: var(--warning);
            transition: all 0.3s ease;
        }
        
        .nav-links a:hover::after {
            width: 70%;
            left: 15%;
        }
        
        /* Hero section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://images.unsplash.com/photo-1523050854058-8df90110c9f1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80') center/cover;
            height: 70vh;
            display: flex;
            align-items: center;
            color: white;
            text-align: center;
        }
        
        .hero-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            animation: fadeIn 1s ease-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }
        
        .hero p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto 2rem;
        }
        
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background-color: var(--secondary);
            color: white;
            padding: 0.8rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-size: 1rem;
            box-shadow: 0 4px 15px rgba(255,87,34,0.3);
        }
        
        .btn i {
            margin-right: 8px;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255,87,34,0.4);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid white;
            margin-left: 1rem;
        }
        
        .btn-outline:hover {
            background: rgba(255,255,255,0.1);
        }
        
        /* Dashboard Grid */
        .dashboard {
            max-width: 1400px;
            margin: -50px auto 50px;
            padding: 0 2rem;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            position: relative;
            z-index: 2;
        }
        
        .dashboard-card {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
            text-align: center;
            border-top: 4px solid var(--primary);
        }
        
        .dashboard-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.12);
        }
        
        .card-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }
        
        /* Main App Section */
        .app-section {
            background-color: white;
            padding: 5rem 2rem;
        }
        
        .app-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 3rem;
        }
        
        .app-description {
            flex: 1;
            min-width: 300px;
        }
        
        .app-frame-container {
            flex: 1;
            min-width: 300px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 20px 50px rgba(0,0,0,0.15);
            border: 1px solid #eee;
        }
        
        .app-frame {
            width: 100%;
            height: 500px;
            border: none;
        }
        
        /* Features */
        .features {
            padding: 5rem 2rem;
            background: linear-gradient(to bottom right, #F5F7FA, #E8EAF6);
        }
        
        .features-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .feature-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }
        
        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .feature-card h3 {
            color: var(--primary);
            display: flex;
            align-items: center;
        }
        
        .feature-card h3 i {
            margin-right: 10px;
            color: var(--secondary);
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 4rem 2rem 2rem;
        }
        
        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
        }
        
        .footer-column h3 {
            color: var(--warning);
            margin-bottom: 1.5rem;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background: var(--secondary);
        }
        
        .footer-links {
            list-style: none;
            padding: 0;
        }
        
        .footer-links li {
            margin-bottom: 0.8rem;
        }
        
        .footer-links a {
            color: #ddd;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--warning);
            padding-left: 5px;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            color: white;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background: var(--secondary);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                padding: 1rem;
            }
            
            .nav-links {
                margin-top: 1rem;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .btn {
                display: block;
                width: 100%;
                margin-bottom: 1rem;
            }
            
            .btn-outline {
                margin-left: 0;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="navbar">
            <div class="logo">
                <i class="fas fa-bolt logo-icon"></i>
                <span>FLSH</span>
            </div>
            <div class="nav-links">
                <a href="#features">Fonctionnalités</a>
                 <a href="#features">Contact</a>
               <a href="#app" class="btn"><i class="fas fa-rocket"></i> Accéder à la plateforme</a>
            </div>
        </div>
    </header>
    
    <section class="hero">
        <div class="hero-content">
            <h1>Plateforme FLSH de Gestion Universitaire</h1>
            <p>Solution tout-en-un pour la délibération des examens, la gestion des notes et toutes les activités en ligne de votre faculté</p>
         
        </div>
    </section>
    
    <div class="dashboard">
        <div class="dashboard-card">
            <div class="card-icon">
                <i class="fas fa-graduation-cap"></i>
            </div>
            <h3>Délibérations</h3>
            <p>Processus automatisé et sécurisé pour les conseils de délibération</p>
        </div>
        <div class="dashboard-card">
            <div class="card-icon">
                <i class="fas fa-chart-line"></i>
            </div>
            <h3>Doyen</h3>
            <p>Mot de Bienvenue</p>
        </div>
        <div class="dashboard-card">
            <div class="card-icon">
                <i class="fas fa-file-alt"></i>
            </div>
            <h3>Procès-verbaux</h3>
            <p>Génération automatique des PV de délibération et de jury</p>
        </div>
    </div>
    
    <section class="app-section" id="app">
        <div class="app-container">
            <div class="app-description">
                <h2>Plateforme FLSH</h2>
                <p>Accédez à l'ensemble des fonctionnalités de gestion académique :</p>
                <ul>
                    <li>Publication des notes et résultats</li>
                    <li>Gestion des délibérations en temps réel</li>
                    <li>Suivi des étudiants</li>
                    <li>Tableaux de bord personnalisés</li>
                    <li>Outils de reporting avancés</li>
                </ul>
                <a href="#" class="btn"><i class="fas fa-play"></i> Démarrer maintenant</a>
            </div>
            <div class="app-frame-container">
                <iframe src="https://votre-lien-flash.com" class="app-frame" title="Plateforme FLSH"></iframe>
            </div>
        </div>
    </section>
    
    <section class="features" id="features">
        <div class="features-grid">
            <div class="feature-card">
                <h3><i class="fas fa-shield-alt"></i> Sécurité renforcée</h3>
                <p>Système de chiffrement des données et authentification multi-facteurs pour protéger les informations sensibles.</p>
            </div>
            <div class="feature-card">
                <h3><i class="fas fa-sync-alt"></i> Synchronisation en temps réel</h3>
                <p>Toutes les modifications sont immédiatement visibles par les utilisateurs autorisés, sans délai.</p>
            </div>
            <div class="feature-card">
                <h3><i class="fas fa-mobile-alt"></i> Accessibilité mobile</h3>
                <p>Interface responsive adaptée à tous les appareils, disponible 24h/24.</p>
            </div>
            <div class="feature-card">
                <h3><i class="fas fa-users-cog"></i> Condition d'utilisation</h3>
                <p>condition d'utilisatuion de cette plateforme pour chaque type d'utilisateur (Etudiants,enseignants, administrateurs).</p>
            </div>
            <div class="feature-card">
                <h3><i class="fas fa-history"></i> Historique de la faculté</h3>
                <p>Traçabilité de toutes les actions avec système de versioning et restauration.</p>
            </div>
            <div class="feature-card">
                <h3><i class="fas fa-cloud-upload-alt"></i> Sauvegarde automatique</h3>
                <p>Vos données sont sauvegardées quotidiennement sur des serveurs sécurisés.</p>
            </div>
        </div>
    </section>
    
    <footer id="contact">
        <div class="footer-content">
            <div class="footer-column">
                <h3>FLSH</h3>
                <p>Plateforme officielle de gestion académique de la faculté. Solution complète pour la délibération des examens et la gestion des activités en ligne.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
            <div class="footer-column">
                <h3>Liens utiles</h3>
                <ul class="footer-links">
                    <li><a href="#">Portail étudiant</a></li>
                    <li><a href="#">Espace enseignant</a></li>
                    <li><a href="#">Calendrier académique</a></li>
                    <li><a href="#">Règlements</a></li>
                    <li><a href="#">FAQ</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Contact</h3>
                <ul class="footer-links">
                    <li><i class="fas fa-envelope"></i> flsh.alwaysdata.net</li>
                    <li><i class="fas fa-phone"></i> +2694400225</li>
                    <li><i class="fas fa-map-marker-alt"></i> M'VOUNI, Campus Universitaire</li>
                    <li><i class="fas fa-clock"></i> Support: Lun-Samedi8h-18h</li>
                </ul>
            </div>
        </div>
        <div class="copyright">
            <p>© 2023 Plateforme FLSH - Tous droits réservés à l'UDC| Développé par le Service Informatique de la Faculté</p>
        </div>
    </footer>
</body>
</html>
