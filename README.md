<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Gabriel Fernandes | GitHub</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #0d1117;
            color: #ffffff;
            line-height: 1.6;
        }

        /* MENU */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 8%;
            background: rgba(13, 17, 23, 0.85);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid #30363d;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            color: #58a6ff;
            font-size: 22px;
            font-weight: bold;
        }

        nav ul {
            display: flex;
            gap: 25px;
            list-style: none;
        }

        nav a {
            color: #c9d1d9;
            text-decoration: none;
            transition: 0.3s;
        }

        nav a:hover {
            color: #58a6ff;
        }

        /* HERO */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 100px 20px 50px;
            background:
                radial-gradient(circle at top, #161b22 0%, #0d1117 55%);
        }

        .hero p {
            color: #8b949e;
            font-size: 20px;
            margin-bottom: 15px;
        }

        .hero h1 {
            font-size: clamp(45px, 8vw, 90px);
            background: linear-gradient(
                90deg,
                #58a6ff,
                #bc8cff,
                #58a6ff
            );
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;

            animation:
                entrada 1.5s ease-out,
                brilho 4s linear infinite;
        }

        @keyframes entrada {
            from {
                opacity: 0;
                transform: translateY(40px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes brilho {
            0% {
                background-position: 0% center;
            }

            100% {
                background-position: 200% center;
            }
        }

        .subtitle {
            margin-top: 15px;
            max-width: 650px;
            color: #8b949e;
            font-size: 18px;
        }

        .buttons {
            display: flex;
            gap: 15px;
            margin-top: 30px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn {
            padding: 12px 25px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: bold;
            transition: 0.3s;
        }

        .btn-primary {
            background: #238636;
            color: white;
        }

        .btn-primary:hover {
            background: #2ea043;
            transform: translateY(-3px);
        }

        .btn-secondary {
            border: 1px solid #30363d;
            color: #c9d1d9;
        }

        .btn-secondary:hover {
            border-color: #58a6ff;
            color: #58a6ff;
            transform: translateY(-3px);
        }

        /* SEÇÕES */
        section {
            padding: 100px 8%;
            max-width: 1200px;
            margin: auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 35px;
            color: #58a6ff;
        }

        .section-title p {
            color: #8b949e;
        }

        /* SOBRE */
        .about {
            text-align: center;
            max-width: 800px;
            margin: auto;
            color: #c9d1d9;
            font-size: 18px;
        }

        /* TECNOLOGIAS */
        .skills {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
        }

        .skill {
            padding: 25px;
            text-align: center;
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 10px;
            transition: 0.3s;
        }

        .skill:hover {
            transform: translateY(-8px);
            border-color: #58a6ff;
            box-shadow: 0 10px 30px rgba(88, 166, 255, 0.1);
        }

        .skill h3 {
            color: #ffffff;
            margin-bottom: 5px;
        }

        .skill span {
            color: #8b949e;
        }

        /* PROJETOS */
        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .project {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 25px;
            transition: 0.3s;
        }

        .project:hover {
            transform: translateY(-8px);
            border-color: #58a6ff;
        }

        .project h3 {
            color: #58a6ff;
            margin-bottom: 10px;
        }

        .project p {
            color: #8b949e;
            margin-bottom: 20px;
        }

        .project a {
            color: #58a6ff;
            text-decoration: none;
            font-weight: bold;
        }

        /* CONTATO */
        .contact {
            text-align: center;
        }

        .contact p {
            color: #8b949e;
            margin-bottom: 25px;
        }

        .social {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .social a {
            padding: 12px 20px;
            border: 1px solid #30363d;
            border-radius: 8px;
            color: #c9d1d9;
            text-decoration: none;
            transition: 0.3s;
        }

        .social a:hover {
            color: #58a6ff;
            border-color: #58a6ff;
        }

        /* RODAPÉ */
        footer {
            text-align: center;
            padding: 30px;
            border-top: 1px solid #30363d;
            color: #8b949e;
        }

        /* CELULAR */
        @media (max-width: 600px) {
            header {
                padding: 15px 5%;
            }

            nav ul {
                gap: 12px;
                font-size: 14px;
            }

            .hero h1 {
                font-size: 45px;
            }

            section {
                padding: 80px 5%;
            }
        }
    </style>
</head>

<body>

    <header>
        <nav>
            <div class="logo">&lt;Gabriel /&gt;</div>

            <ul>
                <li><a href="#inicio">Início</a></li>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#tecnologias">Skills</a></li>
                <li><a href="#projetos">Projetos</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </nav>
    </header>

    <main>

        <section class="hero" id="inicio">
            <p>Olá, eu sou</p>

            <h1>Gabriel Fernandes</h1>

            <p class="subtitle">
                Desenvolvedor apaixonado por tecnologia,
                programação e criação de projetos incríveis.
            </p>

            <div class="buttons">
                <a href="#projetos" class="btn btn-primary">
                    Ver meus projetos
                </a>

                <a href="#contato" class="btn btn-secondary">
                    Entre em contato
                </a>
            </div>
        </section>

        <section id="sobre">
            <div class="section-title">
                <h2>Sobre mim</h2>
                <p>Um pouco sobre quem eu sou</p>
            </div>

            <div class="about">
                <p>
                    Olá! Meu nome é Gabriel Fernandes.
                    Sou uma pessoa apaixonada por tecnologia e programação.
                    Gosto de aprender coisas novas, desenvolver projetos
                    e transformar ideias em soluções através do código.
                </p>
            </div>
        </section>

        <section id="tecnologias">
            <div class="section-title">
                <h2>Tecnologias</h2>
                <p>Ferramentas que estou aprendendo e utilizando</p>
            </div>

            <div class="skills">
                <div class="skill">
                    <h3>HTML</h3>
                    <span>Estrutura Web</span>
                </div>

                <div class="skill">
                    <h3>CSS</h3>
                    <span>Design & Animações</span>
                </div>

                <div class="skill">
                    <h3>Git</h3>
                    <span>Versionamento</span>
                </div>

                <div class="skill">
                    <h3>GitHub</h3>
                    <span>Projetos & Código</span>
                </div>
            </div>
        </section>

        <section id="projetos">
            <div class="section-title">
                <h2>Projetos</h2>
                <p>Alguns dos meus trabalhos</p>
            </div>

            <div class="projects">

                <div class="project">
                    <h3>Projeto 01</h3>

                    <p>
                        Descrição do seu primeiro projeto.
                        Você pode colocar aqui informações
                        sobre o que desenvolveu.
                    </p>

                    <a href="#">
                        Ver projeto →
                    </a>
                </div>

                <div class="project">
                    <h3>Projeto 02</h3>

                    <p>
                        Descrição do seu segundo projeto.
                        Adicione tecnologias e funcionalidades
                        utilizadas.
                    </p>

                    <a href="#">
                        Ver projeto →
                    </a>
                </div>

                <div class="project">
                    <h3>Projeto 03</h3>

                    <p>
                        Descrição do seu terceiro projeto.
                        Coloque aqui o que você desenvolveu.
                    </p>

                    <a href="#">
                        Ver projeto →
                    </a>
                </div>

            </div>
        </section>

        <section id="contato" class="contact">
            <div class="section-title">
                <h2>Contato</h2>
                <p>Vamos conversar?</p>
            </div>

            <p>
                Você pode me encontrar através das minhas redes.
            </p>

            <div class="social">
                <a href="https://github.com/" target="_blank">
                    GitHub
                </a>

                <a href="#" target="_blank">
                    Instagram
                </a>

                <a href="#" target="_blank">
                    LinkedIn
                </a>
            </div>
        </section>

    </main>

    <footer>
        <p>
            © 2026 Gabriel Fernandes. Todos os direitos reservados.
        </p>
    </footer>

</body>
</html>
