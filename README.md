<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Портфолио разработчика</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #f1f1f1;
            line-height: 1.6;
            padding: 20px;
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
        }
        
        .animated-banner {
            width: 100%;
            height: 200px;
            overflow: hidden;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
        }
        
        .animated-banner img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .animated-banner:hover img {
            transform: scale(1.05);
        }
        
        h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ff8a00, #e52e71, #5e5ef7);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 5s infinite alternate;
        }
        
        h2 {
            font-size: 2rem;
            margin: 30px 0 20px;
            color: #ff8a00;
            position: relative;
            display: inline-block;
        }
        
        h2::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, #ff8a00, #e52e71);
            border-radius: 3px;
        }
        
        h3 {
            font-size: 1.5rem;
            margin: 20px 0 15px;
            color: #5e5ef7;
        }
        
        p {
            margin-bottom: 15px;
            font-size: 1.1rem;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }
        
        .social-links a {
            display: inline-block;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(45deg, #5e5ef7, #e52e71);
            color: white;
            text-align: center;
            line-height: 50px;
            font-size: 1.5rem;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .social-links a:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }
        
        .section {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            transition: transform 0.3s;
        }
        
        .section:hover {
            transform: translateY(-5px);
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .skill-item {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            transition: transform 0.3s;
        }
        
        .skill-item:hover {
            transform: scale(1.05);
            background: rgba(255, 255, 255, 0.15);
        }
        
        .skill-item i {
            font-size: 2rem;
            margin-bottom: 10px;
            color: #5e5ef7;
        }
        
        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
        }
        
        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            overflow: hidden;
            transition: transform 0.3s;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
        }
        
        .project-img {
            width: 100%;
            height: 180px;
            overflow: hidden;
        }
        
        .project-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .project-card:hover .project-img img {
            transform: scale(1.1);
        }
        
        .project-info {
            padding: 20px;
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            transition: transform 0.3s;
        }
        
        .stat-card:hover {
            transform: scale(1.03);
            background: rgba(255, 255, 255, 0.1);
        }
        
        .stat-value {
            font-size: 2.5rem;
            font-weight: bold;
            background: linear-gradient(45deg, #ff8a00, #e52e71);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .contact-info {
            text-align: center;
            padding: 20px;
        }
        
        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(45deg, #5e5ef7, #e52e71);
            color: white;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            margin-top: 15px;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }
        
        footer {
            text-align: center;
            padding: 30px 0;
            margin-top: 50px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        @media (max-width: 768px) {
            .skills-grid {
                grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            }
            
            .projects {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="animated-banner">
                <img src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/79ed63bb-18f3-4a65-a14d-0b1b09118e09/darmjmf-a112912c-4d2a-41a3-8aa0-3c6b5d77f6d6.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzc5ZWQ2M2JiLTE4ZjMtNGE2NS1hMTRkLTBiMWIwOTExOGUwOVwvZGFybWptZi1hMTEyOTEyYy00ZDJhLTQxYTMtOGFhMC0zYzZiNWQ3N2Y2ZDYuZ2lmIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.zO3c9nfxBD5Ho_2cSkTJ010kGz3o88OnwA1kGkELtNg" alt="Анимированный баннер">
            </div>
            <h1>Николай Разработчик</h1>
            <p>Full-stack разработчик с фокусом на создании современных веб-приложений</p>
            
            <div class="social-links">
                <a href="https://github.com/Nick0070" target="_blank"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-telegram"></i></a>
                <a href="#"><i class="fab fa-vk"></i></a>
                <a href="#"><i class="fas fa-envelope"></i></a>
            </div>
        </header>
        
        <section class="section">
            <h2>Обо мне</h2>
            <p>Я full-stack разработчик с опытом создания современных веб-приложений. Мой стек технологий включает React, TypeScript, C# и MySQL. Стремлюсь создавать качественный код и интуитивно понятные пользовательские интерфейсы.</p>
        </section>
        
        <section class="section">
            <h2>Мои работы</h2>
            <div class="projects">
                <div class="project-card">
                    <div class="project-img">
                        <img src="https://bel-dosaaf.ru/wp-content/uploads/2022/11/logo.png" alt="Бел ДОСААФ">
                    </div>
                    <div class="project-info">
                        <h3>Бел ДОСААФ</h3>
                        <p>Сайт для региональной организации ДОСААФ. Реализован на WordPress с кастомными решениями.</p>
                        <a href="https://bel-dosaaf.ru" target="_blank" class="btn">Посмотреть</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-img">
                        <img src="https://cdn.pixabay.com/photo/2020/05/18/16/17/social-media-5187243_1280.png" alt="Проект 2">
                    </div>
                    <div class="project-info">
                        <h3>Интернет-магазин</h3>
                        <p>Полнофункциональный интернет-магазин с корзиной, фильтрами и системой оплаты.</p>
                        <a href="#" class="btn">Подробнее</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-img">
                        <img src="https://cdn.pixabay.com/photo/2020/05/16/12/11/analytics-5173540_1280.png" alt="Проект 3">
                    </div>
                    <div class="project-info">
                        <h3>Аналитическая панель</h3>
                        <p>Панель управления с графиками и аналитикой для мониторинга бизнес-показателей.</p>
                        <a href="#" class="btn">Подробнее</a>
                    </div>
                </div>
            </div>
        </section>
        
        <section class="section">
            <h2>Технологии, которые я знаю</h2>
            <h3>Frontend</h3>
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-react"></i>
                    <p>React</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-css3-alt"></i>
                    <p>CSS3</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-html5"></i>
                    <p>HTML5</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-js-square"></i>
                    <p>JavaScript</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-typescript"></i>
                    <p>TypeScript</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-wordpress"></i>
                    <p>WordPress</p>
                </div>
            </div>
            
            <h3>Backend</h3>
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-microsoft"></i>
                    <p>C#</p>
                </div>
                <div class="skill-item">
                    <i class="fas fa-database"></i>
                    <p>MySQL</p>
                </div>
            </div>
            
            <h3>DevOps & Инструменты</h3>
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-git-alt"></i>
                    <p>Git</p>
                </div>
                <div class="skill-item">
                    <i class="fas fa-code"></i>
                    <p>Postman</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-figma"></i>
                    <p>Figma</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-adobe"></i>
                    <p>Photoshop</p>
                </div>
            </div>
        </section>
        
        <section class="section">
            <h2>Моя активность</h2>
            <div class="stats">
                <div class="stat-card">
                    <p class="stat-value">15+</p>
                    <p>Завершенных проектов</p>
                </div>
                <div class="stat-card">
                    <p class="stat-value">5+</p>
                    <p>Лет опыта</p>
                </div>
                <div class="stat-card">
                    <p class="stat-value">98%</p>
                    <p>Довольных клиентов</p>
                </div>
            </div>
        </section>
        
        <section class="section">
            <h2>Связь со мной</h2>
            <div class="contact-info">
                <p>Я всегда открыт к обсуждению новых проектов и возможностей для сотрудничества.</p>
                <p>Свяжитесь со мной через одну из социальных сетей или напишите на email:</p>
                <a href="mailto:nick@example.com" class="btn">Написать мне</a>
            </div>
        </section>
        
        <footer>
            <p>© 2023 Николай Разработчик. Все права защищены.</p>
        </footer>
    </div>

    <script>
        // Простая анимация для появления элементов при прокрутке
        document.addEventListener('DOMContentLoaded', function() {
            const sections = document.querySelectorAll('.section');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            sections.forEach(section => {
                section.style.opacity = 0;
                section.style.transform = 'translateY(20px)';
                section.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
