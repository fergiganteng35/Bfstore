<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BFSTORE - Profil Pribadi</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        :root {
            --primary-color: #6b46c1;
            --secondary-color: #805ad5;
            --accent-color: #9f7aea;
            --dark-bg: #121212;
            --card-bg: #1e1e1e;
            --text-color: #f8f8f8;
        }

        body {
            background: linear-gradient(135deg, #0c0c0c 0%, #1a1a2e 50%, #16213e 100%);
            color: var(--text-color);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            text-align: center;
            padding: 40px 0;
            position: relative;
            overflow: hidden;
        }

        .profile-card {
            background: linear-gradient(145deg, var(--card-bg), #2d2d2d);
            border-radius: 20px;
            padding: 30px;
            margin: 0 auto;
            max-width: 500px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
            position: relative;
            overflow: hidden;
            animation: fadeIn 1s ease-out;
            transition: transform 0.3s ease;
        }

        .profile-card:hover {
            transform: translateY(-10px);
        }

        .profile-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(159, 122, 234, 0.1), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite;
        }

        .profile-pic {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 0 auto 20px;
            background: linear-gradient(145deg, var(--primary-color), var(--accent-color));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            color: white;
            border: 5px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            animation: pulse 2s infinite;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 700;
        }

        .tagline {
            font-size: 1.2rem;
            margin-bottom: 30px;
            color: #ccc;
        }

        .contact-info {
            margin-top: 30px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            background: rgba(255, 255, 255, 0.05);
            padding: 15px;
            border-radius: 12px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .contact-item:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateX(10px);
        }

        .contact-item i {
            font-size: 24px;
            margin-right: 15px;
            width: 30px;
            text-align: center;
            color: var(--accent-color);
        }

        .contact-item a {
            color: var(--text-color);
            text-decoration: none;
            font-size: 1.1rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            margin-top: 40px;
            gap: 20px;
        }

        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(145deg, var(--primary-color), var(--secondary-color));
            color: white;
            font-size: 20px;
            text-decoration: none;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .social-link:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }

        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            font-size: 0.9rem;
            color: #aaa;
        }

        /* Animations */
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

        @keyframes pulse {
            0% {
                box-shadow: 0 0 0 0 rgba(107, 70, 193, 0.7);
            }
            70% {
                box-shadow: 0 0 0 15px rgba(107, 70, 193, 0);
            }
            100% {
                box-shadow: 0 0 0 0 rgba(107, 70, 193, 0);
            }
        }

        @keyframes shine {
            0% {
                left: -50%;
            }
            100% {
                left: 150%;
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .profile-card {
                max-width: 90%;
                padding: 20px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .profile-pic {
                width: 120px;
                height: 120px;
                font-size: 50px;
            }
            
            .contact-item {
                padding: 12px;
            }
            
            .contact-item a {
                font-size: 1rem;
            }
        }

        @media (max-width: 480px) {
            .profile-card {
                max-width: 95%;
                padding: 15px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .profile-pic {
                width: 100px;
                height: 100px;
                font-size: 40px;
            }
            
            .contact-item {
                padding: 10px;
            }
            
            .social-links {
                gap: 15px;
            }
            
            .social-link {
                width: 45px;
                height: 45px;
                font-size: 18px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="profile-card">
                <div class="profile-pic">
                    <span>B</span>
                </div>
                <h1>BFSTORE</h1>
                <p class="tagline">Your Trusted Digital Partner</p>
                
                <div class="contact-info">
                    <div class="contact-item" onclick="copyToClipboard('083183130537')">
                        <i class="fab fa-whatsapp"></i>
                        <a href="https://wa.me/6283183130537" target="_blank">083183130537</a>
                    </div>
                    
                    <div class="contact-item" onclick="copyToClipboard('t.me/bfstore20')">
                        <i class="fab fa-telegram"></i>
                        <a href="https://t.me/bfstore20" target="_blank">t.me/bfstore20</a>
                    </div>
                    
                    <div class="contact-item" onclick="copyToClipboard('bang_frgi20')">
                        <i class="fab fa-tiktok"></i>
                        <a href="https://www.tiktok.com/@bang_frgi20" target="_blank">bang_frgi20</a>
                    </div>
                </div>
            </div>
        </header>
        
        <div class="social-links">
            <a href="https://wa.me/6283183130537" class="social-link" target="_blank">
                <i class="fab fa-whatsapp"></i>
            </a>
            <a href="https://t.me/bfstore20" class="social-link" target="_blank">
                <i class="fab fa-telegram"></i>
            </a>
            <a href="https://www.tiktok.com/@bang_frgi20" class="social-link" target="_blank">
                <i class="fab fa-tiktok"></i>
            </a>
        </div>
    </div>
    
    <footer>
        <p>&copy; 2023 BFSTORE - All Rights Reserved</p>
    </footer>

    <script>
        // Animasi saat elemen muncul di viewport
        document.addEventListener('DOMContentLoaded', function() {
            const contactItems = document.querySelectorAll('.contact-item');
            
            contactItems.forEach((item, index) => {
                item.style.animationDelay = `${index * 0.2}s`;
            });
            
            // Efek salin ke clipboard
            window.copyToClipboard = function(text) {
                navigator.clipboard.writeText(text).then(() => {
                    alert('Teks berhasil disalin: ' + text);
                }).catch(err => {
                    console.error('Gagal menyalin teks: ', err);
                });
            };
        });
    </script>
</body>
</html>
