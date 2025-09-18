<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BFSTORE - Profil Pribadi</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Variabel CSS untuk tema gelap dan gradasi */
        :root {
            --dark-bg: #121212;
            --card-bg: #1e1e1e;
            --accent-color: #7e30e1;
            --accent-color-2: #4a3cf7;
            --text-primary: #ffffff;
            --text-secondary: #b3b3b3;
            --transition: all 0.3s ease;
        }

        /* Reset dan gaya dasar */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #0c0c0c, #1a1a2e);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            min-height: 100vh;
            padding: 20px;
        }

        /* Container utama */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header dengan animasi */
        header {
            text-align: center;
            padding: 40px 20px;
            position: relative;
            overflow: hidden;
        }

        .profile-picture {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 0 auto 20px;
            background: linear-gradient(145deg, var(--accent-color), var(--accent-color-2));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            color: white;
            box-shadow: 0 10px 20px rgba(126, 48, 225, 0.3);
            animation: float 3s ease-in-out infinite;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            background: linear-gradient(to right, var(--accent-color), var(--accent-color-2));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            display: inline-block;
        }

        .tagline {
            color: var(--text-secondary);
            font-size: 1.2rem;
            margin-bottom: 30px;
        }

        /* Grid untuk kartu sosial media */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }

        /* Kartu sosial media */
        .social-card {
            background: linear-gradient(145deg, #1e1e1e, #2d2d2d);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: var(--transition);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 200px;
            position: relative;
            overflow: hidden;
        }

        .social-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to right, var(--accent-color), var(--accent-color-2));
        }

        .social-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(126, 48, 225, 0.3);
        }

        .social-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            background: linear-gradient(to right, var(--accent-color), var(--accent-color-2));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .social-name {
            font-size: 1.2rem;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .social-username {
            color: var(--text-secondary);
            margin-bottom: 15px;
            font-size: 1rem;
        }

        .social-link {
            display: inline-block;
            padding: 10px 20px;
            background: linear-gradient(to right, var(--accent-color), var(--accent-color-2));
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 500;
            transition: var(--transition);
            margin-top: 10px;
        }

        .social-link:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(126, 48, 225, 0.4);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 30px 0;
            margin-top: 50px;
            color: var(--text-secondary);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        /* Animasi */
        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Efek untuk kartu saat muncul */
        .social-card {
            animation: fadeIn 0.6s ease-out forwards;
            opacity: 0;
        }

        .social-card:nth-child(1) { animation-delay: 0.1s; }
        .social-card:nth-child(2) { animation-delay: 0.2s; }
        .social-card:nth-child(3) { animation-delay: 0.3s; }
        .social-card:nth-child(4) { animation-delay: 0.4s; }
        .social-card:nth-child(5) { animation-delay: 0.5s; }
        .social-card:nth-child(6) { animation-delay: 0.6s; }
        .social-card:nth-child(7) { animation-delay: 0.7s; }
        .social-card:nth-child(8) { animation-delay: 0.8s; }

        /* Responsivitas */
        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }
            
            .tagline {
                font-size: 1rem;
            }
            
            .social-grid {
                grid-template-columns: 1fr;
            }
            
            .profile-picture {
                width: 120px;
                height: 120px;
                font-size: 50px;
            }
        }

        @media (max-width: 480px) {
            .container {
                padding: 10px;
            }
            
            header {
                padding: 20px 10px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .social-card {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="profile-picture">
                <i class="fas fa-store"></i>
            </div>
            <h1>BFSTORE</h1>
            <p class="tagline">Your trusted partner for digital solutions</p>
        </header>

        <div class="social-grid">
            <!-- WhatsApp -->
            <div class="social-card">
                <div class="social-icon">
                    <i class="fab fa-whatsapp"></i>
                </div>
                <div class="social-name">WhatsApp</div>
                <div class="social-username">083183130537</div>
                <a href="https://wa.me/6283183130537" class="social-link" target="_blank">
                    <i class="fab fa-whatsapp"></i> Hubungi Saya
                </a>
            </div>

            <!-- Telegram -->
            <div class="social-card">
                <div class="social-icon">
                    <i class="fab fa-telegram"></i>
                </div>
                <div class="social-name">Telegram</div>
                <div class="social-username">@bfstore20</div>
                <a href="https://t.me/bfstore20" class="social-link" target="_blank">
                    <i class="fab fa-telegram"></i> Kirim Pesan
                </a>
            </div>

            <!-- Tiktok 1 -->
            <div class="social-card">
                <div class="social-icon">
                    <i class="fab fa-tiktok"></i>
                </div>
                <div class="social-name">TikTok</div>
                <div class="social-username">@egikgaje</div>
                <a href="https://www.tiktok.com/@egikgaje" class="social-link" target="_blank">
                    <i class="fab fa-tiktok"></i> Follow Saya
                </a>
            </div>

            <!-- Tiktok 2 -->
            <div class="social-card">
                <div class="social-icon">
                    <i class="fab fa-tiktok"></i>
                </div>
                <div class="social-name">TikTok</div>
                <div class="social-username">@bang_frgi20</div>
                <a href="https://www.tiktok.com/@bang_frgi20" class="social-link" target="_blank">
                    <i class="fab fa-tiktok"></i> Follow Saya
                </a>
            </div>

            <!-- Instagram -->
            <div class="social-card">
                <div class="social-icon">
                    <i class="fab fa-instagram"></i>
                </div>
                <div class="social-name">Instagram</div>
                <div class="social-username">@frgispl_</div>
                <a href="https://www.instagram.com/frgispl_/" class="social-link" target="_blank">
                    <i class="fab fa-instagram"></i> Follow Saya
                </a>
            </div>

            <!-- YouTube -->
            <div class="social-card">
                <div class="social-icon">
                    <i class="fab fa-youtube"></i>
                </div>
                <div class="social-name">YouTube</div>
                <div class="social-username">Yt bangFrgi</div>
                <a href="https://www.youtube.com/@bangFrgi" class="social-link" target="_blank">
                    <i class="fab fa-youtube"></i> Subscribe
                </a>
            </div>

            <!-- Sociabuzz -->
            <div class="social-card">
                <div class="social-icon">
                    <i class="fas fa-heart"></i>
                </div>
                <div class="social-name">Sociabuzz</div>
                <div class="social-username">fergiandi20</div>
                <a href="https://sociabuzz.com/fergiandi20/tribe" class="social-link" target="_blank">
                    <i class="fas fa-external-link-alt"></i> Kunjungi
                </a>
            </div>
        </div>

        <footer>
            <p>&copy; 2023 BFSTORE. All rights reserved.</p>
        </footer>
    </div>

    <script>
        // Script sederhana untuk menambah interaktivitas
        document.addEventListener('DOMContentLoaded', function() {
            const cards = document.querySelectorAll('.social-card');
            
            cards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-10px)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0)';
                });
            });
        });
    </script>
</body>
</html>
