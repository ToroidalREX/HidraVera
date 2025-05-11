<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hidravera - Hidromiel 100% Artesanal</title>
    <style>
        :root {
            --dark-bg: #111111;
            --gold: #d4a017;
            --light-gold: #f9d05c;
            --orange: #ff8c00;
            --white: #ffffff;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--dark-bg);
            color: var(--white);
            overflow-x: hidden;
        }
        
        header {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('/api/placeholder/1400/800') center/cover;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            position: relative;
        }
        
        .video-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0.3;
            z-index: -1;
        }
        
        nav {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            background-color: rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(5px);
        }
        
        .logo {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            overflow: hidden;
            background-color: var(--dark-bg);
            display: flex;
            justify-content: center;
            align-items: center;
            border: 2px solid var(--gold);
        }
        
        .logo img {
            width: 80px;
            height: 80px;
            object-fit: contain;
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
            align-items: center;
        }
        
        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s;
            padding: 8px 15px;
            border-radius: 30px;
        }
        
        .nav-links a:hover {
            color: var(--dark-bg);
            background-color: var(--gold);
        }
        
        .hero-content {
            max-width: 1000px;
            position: relative;
            z-index: 2;
        }
        
        .hero-title {
            font-size: 5rem;
            font-weight: 800;
            margin-bottom: 20px;
            line-height: 1;
            text-shadow: 0 2px 10px rgba(0,0,0,0.8);
        }
        
        .hero-title span {
            color: var(--gold);
        }
        
        .hero-title .better {
            color: var(--white);
            font-weight: 900;
        }
        
        .hero-subtitle {
            font-size: 1.8rem;
            margin-bottom: 30px;
            font-weight: 300;
            text-shadow: 0 2px 10px rgba(0,0,0,0.8);
        }
        
        .hero-text {
            font-size: 1.2rem;
            margin-bottom: 40px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            text-shadow: 0 2px 10px rgba(0,0,0,0.8);
        }
        
        .cta-button {
            background-color: var(--gold);
            color: var(--dark-bg);
            border: none;
            padding: 15px 30px;
            font-size: 1.2rem;
            font-weight: bold;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
            margin-top: 20px;
            letter-spacing: 1px;
            border-radius: 50px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        
        .cta-button:hover {
            background-color: var(--light-gold);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.4);
        }
        
        section {
            padding: 100px 20px;
            position: relative;
            overflow: hidden;
        }
        
        .section-title {
            font-size: 3.5rem;
            text-align: center;
            margin-bottom: 60px;
            color: var(--gold);
            position: relative;
            padding-bottom: 20px;
            text-transform: uppercase;
            font-weight: 800;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 150px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--gold), transparent);
        }
        
        /* Estilos para la imagen de la abeja */
        .bee-illustration {
            position: absolute;
            width: 200px;
            height: auto;
            z-index: 1;
            opacity: 0.8;
        }
        
        .bee-top-right {
            top: 120px;
            right: 50px;
            transform: rotate(15deg);
        }
        
        .bee-bottom-left {
            bottom: 80px;
            left: 50px;
            transform: rotate(-10deg) scale(0.8);
        }
        
        .bee-center {
            position: relative;
            width: 300px;
            height: 200px;
            margin: 0 auto 40px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .bee-center img {
            width: 250px;
            height: auto;
        }
        
        .bee-watermark {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 100px;
            height: auto;
            opacity: 0.1;
            z-index: 0;
            pointer-events: none;
        }
        
        .about-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 70px;
            margin-top: 60px;
            align-items: center;
        }
        
        .about-text {
            flex: 1;
            min-width: 300px;
            max-width: 600px;
        }
        
        .about-text p {
            font-size: 1.2rem;
            line-height: 1.8;
            margin-bottom: 25px;
        }
        
        .about-text .highlight {
            color: var(--gold);
            font-weight: bold;
        }
        
        .about-image {
            flex: 1;
            min-width: 300px;
            max-width: 500px;
            position: relative;
        }
        
        .about-image img {
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
            transition: transform 0.5s;
        }
        
        .about-image:hover img {
            transform: scale(1.03);
        }
        
        .about-image::before {
            content: '';
            position: absolute;
            top: -15px;
            right: -15px;
            width: 100%;
            height: 100%;
            border: 3px solid var(--gold);
            border-radius: 20px;
            z-index: -1;
            transition: all 0.5s;
        }
        
        .about-image:hover::before {
            top: -20px;
            right: -20px;
        }
        
        .honey-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('/api/placeholder/1400/800') center/cover;
            opacity: 0.1;
            z-index: -1;
        }
        
        .products {
            background-color: rgba(0,0,0,0.7);
            position: relative;
        }
        
        .products::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('/api/placeholder/1400/800') center/cover;
            opacity: 0.1;
            z-index: -1;
        }
        
        .products-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 60px;
            margin-top: 60px;
        }
        
        .product-card {
            background: rgba(0,0,0,0.7);
            border-radius: 20px;
            overflow: hidden;
            width: 320px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
            transition: all 0.4s;
            position: relative;
            border: 1px solid rgba(212,160,23,0.2);
        }
        
        .product-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 30px 50px rgba(0,0,0,0.6);
            border-color: var(--gold);
        }
        
        .product-ribbon {
            position: absolute;
            top: 20px;
            right: -30px;
            background-color: var(--gold);
            color: var(--dark-bg);
            padding: 5px 30px;
            font-weight: bold;
            transform: rotate(45deg);
            z-index: 10;
            box-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }
        
        .product-image {
            height: 350px;
            overflow: hidden;
            position: relative;
        }
        
        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.7s;
        }
        
        .product-card:hover .product-image img {
            transform: scale(1.08);
        }
        
        .product-deity {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            padding: 15px;
            background: linear-gradient(to top, rgba(0,0,0,0.8), transparent);
            color: var(--gold);
            text-align: center;
            font-weight: bold;
            letter-spacing: 1px;
        }
        
        .product-content {
            padding: 30px;
            text-align: center;
        }
        
        .product-title {
            font-size: 2rem;
            margin-bottom: 15px;
            color: var(--gold);
            font-weight: 800;
        }
        
        .product-description {
            margin-bottom: 20px;
            font-size: 1.1rem;
            color: var(--white);
            line-height: 1.6;
        }
        
        .product-price {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 25px;
            color: var(--light-gold);
        }
        
        .product-button {
            background-color: var(--gold);
            color: var(--dark-bg);
            border: none;
            padding: 12px 25px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            border-radius: 50px;
            display: inline-block;
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .product-button:hover {
            background-color: var(--light-gold);
            box-shadow: 0 8px 20px rgba(0,0,0,0.3);
        }
        
        .splash-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 40%;
            background: url('/api/placeholder/500/300') center/cover;
            opacity: 0.3;
            z-index: -1;
        }
        
        .features {
            background-color: var(--dark-bg);
            position: relative;
            overflow: hidden;
        }
        
        .features-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('/api/placeholder/1400/800') center/cover;
            opacity: 0.1;
            z-index: -1;
        }
        
        .features-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 50px;
            margin-top: 60px;
        }
        
        .feature-item {
            background-color: rgba(0,0,0,0.5);
            padding: 40px;
            border-radius: 15px;
            width: 320px;
            text-align: center;
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
            transition: all 0.4s;
            border: 1px solid rgba(212,160,23,0.2);
            backdrop-filter: blur(5px);
        }
        
        .feature-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
            border-color: var(--gold);
        }
        
        .feature-icon {
            font-size: 4rem;
            color: var(--gold);
            margin-bottom: 25px;
            transition: transform 0.5s;
        }
        
        .feature-item:hover .feature-icon {
            transform: scale(1.2);
        }
        
        .feature-title {
            font-size: 1.6rem;
            margin-bottom: 20px;
            color: var(--gold);
            font-weight: bold;
        }
        
        .feature-text {
            font-size: 1.1rem;
            line-height: 1.7;
            color: rgba(255,255,255,0.9);
        }
        
        .gallery {
            background-color: var(--dark-bg);
            position: relative;
        }
        
        .gallery-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 60px;
        }
        
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            aspect-ratio: 1/1;
            cursor: pointer;
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.7s;
        }
        
        .gallery-item:hover img {
            transform: scale(1.05);
        }
        
        .gallery-item::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to top, rgba(0,0,0,0.7), transparent);
            opacity: 0;
            transition: opacity 0.5s;
        }
        
        .gallery-item:hover::after {
            opacity: 1;
        }
        
        .testimonials {
            position: relative;
            background-color: rgba(0,0,0,0.8);
        }
        
        .testimonial-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('/api/placeholder/1400/800') center/cover;
            opacity: 0.1;
            z-index: -1;
        }
        
        .testimonials-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 50px;
            margin-top: 60px;
        }
        
        .testimonial-card {
            background-color: rgba(0,0,0,0.6);
            padding: 40px;
            border-radius: 15px;
            width: 350px;
            position: relative;
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
            transition: all 0.4s;
            border: 1px solid rgba(212,160,23,0.2);
            backdrop-filter: blur(5px);
        }
        
        .testimonial-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.4);
            border-color: var(--gold);
        }
        
        .testimonial-text {
            font-size: 1.1rem;
            line-height: 1.7;
            margin-bottom: 25px;
            font-style: italic;
            color: rgba(255,255,255,0.9);
        }
        
        .testimonial-author {
            font-weight: bold;
            color: var(--gold);
            font-size: 1.1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .quote-icon {
            position: absolute;
            top: -25px;
            left: 30px;
            font-size: 5rem;
            color: rgba(212,160,23,0.2);
        }
        
        .contact {
            background-color: var(--dark-bg);
            position: relative;
        }
        
        .contact::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('/api/placeholder/1400/800') center/cover;
            opacity: 0.05;
            z-index: -1;
        }
        
        .contact-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 70px;
            margin-top: 60px;
        }
        
        .contact-info {
            flex: 1;
            min-width: 300px;
            max-width: 500px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 30px;
            background-color: rgba(0,0,0,0.3);
            padding: 20px;
            border-radius: 10px;
            transition: all 0.3s;
            border: 1px solid rgba(212,160,23,0.1);
        }
        
        .contact-item:hover {
            background-color: rgba(0,0,0,0.5);
            transform: translateX(5px);
            border-color: var(--gold);
        }
        
        .contact-icon {
            font-size: 1.5rem;
            color: var(--gold);
            margin-right: 20px;
            width: 60px;
            height: 60px;
            background-color: rgba(212,160,23,0.1);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .contact-item:hover .contact-icon {
            background-color: var(--gold);
            color: var(--dark-bg);
        }
        
        .contact-text {
            font-size: 1.1rem;
        }
        
        .contact-text span {
            display: block;
            color: var(--gold);
            font-weight: bold;
            margin-bottom: 5px;
            font-size: 1.2rem;
        }
        
        .form-container {
            flex: 1;
            min-width: 300px;
            max-width: 550px;
            background-color: rgba(0,0,0,0.3);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            border: 1px solid rgba(212,160,23,0.1);
            backdrop-filter: blur(5px);
        }
        
        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }
        
        .form-group {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }
        
        .form-group label {
            font-size: 1rem;
            color: var(--gold);
            font-weight: bold;
            letter-spacing: 1px;
        }
        
        .form-group input,
        .form-group textarea {
            padding: 15px;
            background-color: rgba(255,255,255,0.05);
            border: 1px solid rgba(212,160,23,0.2);
            color: var(--white);
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s;
        }
        
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--gold);
            background-color: rgba(255,255,255,0.1);
        }
        
        .form-group textarea {
            resize: vertical;
            min-height: 150px;
        }
        
        .submit-button {
            background-color: var(--gold);
            color: var(--dark-bg);
            border: none;
            padding: 15px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            border-radius: 8px;
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .submit-button:hover {
            background-color: var(--light-gold);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.3);
        }
        
        footer {
            background-color: rgba(0,0,0,0.9);
            padding: 80px 20px 40px;
            position: relative;
        }
        
        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 50px;
        }
        
        .footer-logo {
            flex: 1;
            min-width: 250px;
            max-width: 300px;
        }
        
        .footer-logo img {
            width: 120px;
            margin-bottom: 25px;
        }
        
        .footer-logo p {
            font-size: 1rem;
            color: rgba(255,255,255,0.7);
            line-height: 1.7;
        }
        
        .footer-links {
            flex: 1;
            min-width: 200px;
            max-width: 300px;
        }
        
        .footer-title {
            color: var(--gold);
            margin-bottom: 25px;
            font-size: 1.3rem;
            font-weight: bold;
            position: relative;
            padding-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .footer-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 3px;
            background-color: var(--gold);
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 15px;
        }
        
        .footer-links a {
            color: rgba(255,255,255,0.7);
            text-decoration: none;
            transition: all 0.3s;
            font-size: 1rem;
            display: block;
            padding: 5px 0;
        }
        
        .footer-links a:hover {
            color: var(--gold);
            transform: translateX(5px);
        }
        
        .social-media {
            display: flex;
            gap: 15px;
            margin-top: 25px;
        }
        
        .social-icon {
            width: 45px;
            height: 45px;
            background-color: rgba(212,160,23,0.1);
            color: var(--gold);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            text-decoration: none;
            transition: all 0.3s;
            font-size: 1.2rem;
            border: 1px solid rgba(212,160,23,0.3);
        }
        
        .social-icon:hover {
            background-color: var(--gold);
            color: var(--dark-bg);
            transform: translateY(-5px);
        }
        
        .copyright {
            margin-top: 60px;
            border-top: 1px solid rgba(255,255,255,0.1);
            padding-top: 30px;
            color: rgba(255,255,255,0.5);
            font-size: 0.9rem;
            text-align: center;
        }
        
        .bee-decoration {
            position: absolute;
            animation: floatAnimation 6s ease-in-out infinite;
            z-index: 1;
            opacity: 0.5;
        }
        
        .bee-1 {
            top: 20%;
            left: 5%;
            font-size: 2rem;
        }
        
        .bee-2 {
            top: 70%;
            right: 10%;
            font-size: 2.5rem;
            animation-delay: 1s;
        }
        
        .bee-3 {
            bottom: 15%;
            left: 15%;
            font-size: 1.8rem;
            animation-delay: 2s;
        }
        
        .honey-drops {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            overflow: hidden;
            z-index: 0;
            pointer-events: none;
        }
        
        .honey-drop {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: var(--gold);
            border-radius: 50%;
            opacity: 0.1;
            animation: dropFall linear infinite;
        }
        
        @keyframes floatAnimation {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }
        
        @keyframes dropFall {
            0% {
                transform: translateY(-100px) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.1;
            }
            100% {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }
        
        @media (max-width: 768px) {
            .hero-title {
                font-size: 3.5rem;
            }
            
            .nav-links {
                display: none;
            }
            
            .section-title {
                font-size: 2.5rem;
            }
            
            .footer-content {
                flex-direction: column;
                align-items: center;
                text-align: center;
            }
            
            .footer-title::after {
                left: 50%;
                transform: translateX(-50%);
            }
            
            .contact-item {
                flex-direction: column;
                text-align: center;
                padding: 25px 15px;
            }
            
            .contact-icon {
                margin-right: 0;
                margin-bottom: 15px;
            }
            
            .about-image::before {
                display: none;
            }
        }
        
        @media (max-width: 480px) {
            .hero-title {
                font-size: 2.8rem;
            }
            
            .hero-subtitle {
                font-size: 1.5rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .product-card,
            .feature-item,
            .testimonial-card {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <!-- Decoración de abejas y gotas de miel -->
    <div class="bee-decoration bee-1">🐝</div>
    <div class="bee-decoration bee-2">🐝</div>
    <div class="bee-decoration bee-3">🐝</div>
    
    <div class="honey-drops">
        <!-- Las gotas se generarán con JavaScript -->
    </div>
    
    <header id="inicio">
        <video class="video-bg" autoplay muted loop>
            <source src="/api/placeholder/1400/800" type="video/mp4">
        </video>
        
        <nav>
            <div class="logo">
                <img src="/api/placeholder/300/200" alt="Hidravera Logo">
            </div>
            <div class="nav-links">
                <a href="#inicio">Inicio</a>
                <a href="#nosotros">Nosotros</a>
                <a href="#productos">Productos</a>
                <a href="#galeria">Galería</a>
                <a href="#contacto">Contacto</a>
                <a href="#">🛒</a>
            </div>
        </nav>
        
        <div class="hero-content">
            <h1 class="hero-title"><span>BEE</span> BETTER<br><span class="better">FEEL BETTER.</span></h1>
            <h2 class="hero-subtitle">Hidromiel 100% Artesanal</h2>
            <p class="hero-text">La bebida ancestral maya elaborada con miel natural, tradición y pasión. Un sabor único elaborado en Veracruz.</p>
            <a href="#productos" class="cta-button">Descubre nuestros productos</a>
        </div>
    </header>
    
    <!-- Imagen de abeja como marca de agua -->
    <img src="/api/placeholder/300/200" alt="Abeja Hidravera" class="bee-watermark">
    
    <section id="nosotros" class="about">
        <div class="honey-bg"></div>
        <!-- Imagen de abeja en esquina superior derecha -->
        <img src="/api/placeholder/300/200" alt="Abeja Hidravera" class="bee-illustration bee-top-right">
        
        <h2 class="section-title">Nuestra Historia</h2>
        
        <!-- Abeja central como elemento decorativo -->
        <div class="bee-center">
            <img src="/api/placeholder/300/200" alt="Abeja Hidravera">
        </div>
        <div class="about-container">
            <div class="about-text">
                <p>Hidravera es un proyecto que busca posicionar en el mercado una <span class="highlight">bebida alcohólica ancestral fermentada</span> a partir de miel de abeja y agua. Es una alternativa artesanal y natural frente a bebidas alcohólicas tradicionales, como la cerveza.</p>
                <p>La elaboración de Hidravera es de <span class="highlight">alta calidad</span>, con un proceso que respeta los métodos tradicionales, teniendo como resultado una bebida que se destaca por su presentación elegante, su sabor, y su enfoque en ingredientes naturales, a su vez, responde al creciente interés por bebidas artesanales.</p>
                <p>Nuestra misión es rescatar y preservar esta antigua tradición maya mientras ofrecemos una experiencia única de sabor y conexión con nuestras raíces culturales.</p>
                <a href="#productos" class="cta-button">Ver productos</a>
            </div>
            <div class="about-image">
                <img src="/api/placeholder/500/400" alt="Proceso de elaboración de hidromiel">
            </div>
        </div>
    </section>
    
    <section id="productos" class="products">
        <div class="splash-overlay"></div>
        
        <h2 class="section-title">Nuestros Productos</h2>
        <div class="products-container">
            <div class="product-card">
                <div class="product-ribbon">Popular</div>
                <div class="product-image">
                    <img src="/api/placeholder/300/320" alt="Muzenkab Hidromiel">
                    <div class="product-deity">AH MUZENKAB</div>
                </div>
                <div class="product-content">
                    <h3 class="product-title">MUZENKAB</h3>
                    <p class="product-description">Hidromiel tradicional elaborada con la receta ancestral maya. Dios de la miel, protector y patrón de las abejas.</p>
                    <p class="product-price">$80.00 MXN</p>
                    <button class="product-button">Comprar ahora</button>
                </div>
            </div>
            
            <div class="product-card">
                <div class="product-image">
                    <img src="/api/placeholder/300/320" alt="Kinich Hidromiel">
                    <div class="product-deity">KINICH AHAU</div>
                </div>
                <div class="product-content">
                    <h3 class="product-title">KINICH</h3>
                    <p class="product-description">Hidromiel con aroma a naranja. Dios del sol. El color naranja representa la salida del amanecer.</p>
                    <p class="product-price">$95.00 MXN</p>
                    <button class="product-button">Comprar ahora</button>
                </div>
            </div>
            
            <div class="product-card">
                <div class="product-ribbon">Especial</div>
                <div class="product-image">
                    <img src="/api/placeholder/300/320" alt="Edición Especial Hidromiel">
                    <div class="product-deity">EDICIÓN ESPECIAL</div>
                </div>
                <div class="product-content">
                    <h3 class="product-title">EDICIÓN COLECCIÓN</h3>
                    <p class="product-description">Hidromiel edición especial con sabores únicos y presentación premium. Ideal para regalos y ocasiones especiales.</p>
                    <p class="product-price">$120.00 MXN</p>
                    <button class="product-button">Comprar ahora</button>
                </div>
            </div>
        </div>
    </section>
    
    <section class="features">
        <div class="features-bg"></div>
        <!-- Imagen de abeja en esquina inferior izquierda -->
        <img src="/api/placeholder/300/200" alt="Abeja Hidravera" class="bee-illustration bee-bottom-left">
        <h2 class="section-title">¿Por qué elegir Hidravera?</h2>
        <div class="features-container">
            <div class="feature-item">
                <div class="feature-icon">🌿</div>
                <h3 class="feature-title">100% Natural</h3>
                <p class="feature-text">Elaborada exclusivamente con miel pura de abeja y agua, sin conservadores ni aditivos artificiales.</p>
            </div>
            
            <div class="feature-item">
                <div class="feature-icon">🏺</div>
                <h3 class="feature-title">Tradición Maya</h3>
                <p class="feature-text">Respetamos el proceso de elaboración ancestral maya, conservando sus técnicas y tradiciones.</p>
            </div>
            
            <div class="feature-item">
                <div class="feature-icon">🌎</div>
                <h3 class="feature-title">Producto Local</h3>
                <p class="feature-text">Elaborado con orgullo en Veracruz, apoyando a productores locales y a la economía de la región.</p>
            </div>
            
            <div class="feature-item">
                <div class="feature-icon">✨</div>
                <h3 class="feature-title">Calidad Premium</h3>
                <p class="feature-text">Cada botella pasa por rigurosos controles de calidad para garantizar una experiencia excepcional.</p>
            </div>
        </div>
    </section>
    
    <section id="galeria" class="gallery">
        <h2 class="section-title">Galería</h2>
        <div class="gallery-container">
            <div class="gallery-item">
                <img src="/api/placeholder/400/400" alt="Proceso de elaboración de Hidravera">
            </div>
            <div class="gallery-item">
                <img src="/api/placeholder/400/400" alt="Botellas de Hidromiel">
            </div>
            <div class="gallery-item">
                <img src="/api/placeholder/400/400" alt="Ingredientes naturales">
            </div>
            <div class="gallery-item">
                <img src="/api/placeholder/400/400" alt="Degustación de Hidromiel">
            </div>
            <div class="gallery-item">
                <img src="/api/placeholder/400/400" alt="Colmenas de abejas">
            </div>
            <div class="gallery-item">
                <img src="/api/placeholder/400/400" alt="Festivales y eventos">
            </div>
        </div>
    </section>
    
    <section class="testimonials">
        <div class="testimonial-bg"></div>
        <h2 class="section-title">Lo que dicen nuestros clientes</h2>
        <div class="testimonials-container">
            <div class="testimonial-card">
                <div class="quote-icon">❝</div>
                <p class="testimonial-text">Nunca había probado hidromiel hasta que descubrí Hidravera. El sabor es increíblemente suave y aromático, nada comparable con otras bebidas alcohólicas. Ahora es mi elección para ocasiones especiales.</p>
                <p class="testimonial-author">- Carlos Mendoza</p>
            </div>
            
            <div class="testimonial-card">
                <div class="quote-icon">❝</div>
                <p class="testimonial-text">La presentación es preciosa y el sabor es excepcional. Me encanta la conexión con la cultura maya y que sea un producto 100% artesanal. La variedad Kinich con aroma a naranja es mi favorita.</p>
                <p class="testimonial-author">- Ana González</p>
            </div>
            
            <div class="testimonial-card">
                <div class="quote-icon">❝</div>
                <p class="testimonial-text">Como entusiasta de las bebidas artesanales, puedo decir que Hidravera está a otro nivel. El proceso de fermentación y el uso de miel pura se nota en cada sorbo. Es una experiencia única que todos deberían probar.</p>
                <p class="testimonial-author">- Roberto Jiménez</p>
            </div>
        </div>
    </section>
    
    <section id="contacto" class="contact">
        <h2 class="section-title">Contáctanos</h2>
        <div class="contact-container">
            <div class="contact-info">
                <div class="contact-item">
                    <div class="contact-icon">📍</div>
                    <div class="contact-text">
                        <span>Dirección</span>
                        Av. Principal #123, Veracruz, México
                    </div>
                </div>
                
                <div class="contact-item">
                    <div class="contact-icon">📱</div>
                    <div class="contact-text">
                        <span>Teléfono</span>
                        +52 229 123 4567
                    </div>
                </div>
                
                <div class="contact-item">
                    <div class="contact-icon">✉️</div>
                    <div class="contact-text">
                        <span>Email</span>
                        info@hidravera.com
                    </div>
                </div>
                
                <div class="contact-item">
                    <div class="contact-icon">🕒</div>
                    <div class="contact-text">
                        <span>Horario</span>
                        Lunes a Viernes: 9:00 AM - 6:00 PM<br>
                        Sábados: 10:00 AM - 2:00 PM
                    </div>
                </div>
                
                <div class="social-media">
                    <a href="#" class="social-icon">f</a>
                    <a href="#" class="social-icon">i</a>
                    <a href="#" class="social-icon">t</a>
                </div>
            </div>
            
            <div class="form-container">
                <form class="contact-form">
                    <div class="form-group">
                        <label for="name">Nombre</label>
                        <input type="text" id="name" placeholder="Tu nombre">
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" placeholder="Tu email">
                    </div>
                    
                    <div class="form-group">
                        <label for="subject">Asunto</label>
                        <input type="text" id="subject" placeholder="Asunto">
                    </div>
                    
                    <div class="form-group">
                        <label for="message">Mensaje</label>
                        <textarea id="message" placeholder="Tu mensaje"></textarea>
                    </div>
                    
                    <button type="submit" class="submit-button">Enviar Mensaje</button>
                </form>
            </div>
        </div>
    </section>
    
    <footer>
        <div class="footer-content">
            <div class="footer-logo">
                <img src="/api/placeholder/300/200" alt="Hidravera Logo">
                <p>Hidravera: Hidromiel 100% artesanal elaborado en Veracruz. Una experiencia ancestral maya en cada sorbo.</p>
                
                <div class="social-media">
                    <a href="#" class="social-icon">f</a>
                    <a href="#" class="social-icon">i</a>
                    <a href="#" class="social-icon">t</a>
                </div>
            </div>
            
            <div class="footer-links">
                <h4 class="footer-title">Enlaces Rápidos</h4>
                <ul>
                    <li><a href="#inicio">Inicio</a></li>
                    <li><a href="#nosotros">Nosotros</a></li>
                    <li><a href="#productos">Productos</a></li>
                    <li><a href="#galeria">Galería</a></li>
                    <li><a href="#contacto">Contacto</a></li>
                </ul>
            </div>
            
            <div class="footer-links">
                <h4 class="footer-title">Productos</h4>
                <ul>
                    <li><a href="#productos">Muzenkab</a></li>
                    <li><a href="#productos">Kinich</a></li>
                    <li><a href="#productos">Edición Especial</a></li>
                    <li><a href="#productos">Paquetes</a></li>
                </ul>
            </div>
        </div>
        
        <div class="copyright">
            © 2025 Hidravera. Todos los derechos reservados. Producto 100% artesanal elaborado en Veracruz, México.
        </div>
    </footer>

    <script>
        // Crear gotas de miel animadas
        const honeyDrops = document.querySelector('.honey-drops');
        
        function createHoneyDrops() {
            for (let i = 0; i < 20; i++) {
                const drop = document.createElement('div');
                drop.classList.add('honey-drop');
                
                // Posición aleatoria
                const posX = Math.floor(Math.random() * 100);
                drop.style.left = posX + '%';
                
                // Tamaño aleatorio
                const size = Math.floor(Math.random() * 15) + 5;
                drop.style.width = size + 'px';
                drop.style.height = size + 'px';
                
                // Velocidad aleatoria
                const duration = Math.floor(Math.random() * 20) + 10;
                drop.style.animationDuration = duration + 's';
                
                // Retraso aleatorio
                const delay = Math.floor(Math.random() * 20);
                drop.style.animationDelay = delay + 's';
                
                honeyDrops.appendChild(drop);
            }
        }
        
        // Iniciar animación de gotas
        createHoneyDrops();
        
        // Función para reemplazar los placeholders con la imagen de la abeja
        function replacePlaceholders() {
            // URL de la imagen de abeja que proporcionaste
            const beeImageUrl = '/api/placeholder/300/200'; // Reemplazado con placeholder para este ejemplo
            
            // Seleccionar todas las imágenes de abeja
            const beeImages = document.querySelectorAll('.bee-illustration, .bee-center img, .bee-watermark');
            
            // Reemplazar con la imagen real
            beeImages.forEach(img => {
                img.src = beeImageUrl;
            });
        }
        
        // Ejecutar cuando el documento esté cargado
        document.addEventListener('DOMContentLoaded', replacePlaceholders);
    </script>
</body>
</html>
