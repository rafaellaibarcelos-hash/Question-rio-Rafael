<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feedback Pessoal - Coordenador Comercial & Família</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #1a73e8;
            --secondary: #0d47a1;
            --accent: #ff6d00;
            --family: #e91e63;
            --light: #f5f7fa;
            --dark: #2d3748;
            --success: #4caf50;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a73e8 0%, #0d47a1 100%);
            color: #333;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 40px 20px;
        }
        
        .container {
            background-color: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            width: 100%;
            max-width: 800px;
            overflow: hidden;
            margin-bottom: 30px;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 30px;
            text-align: center;
            position: relative;
        }
        
        .profile-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.2);
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            backdrop-filter: blur(10px);
        }
        
        h1 {
            font-size: 2.2rem;
            margin-bottom: 10px;
        }
        
        .subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
            margin-bottom: 10px;
        }
        
        .intro {
            padding: 25px;
            line-height: 1.6;
            font-size: 1.05rem;
            background-color: var(--light);
        }
        
        .intro p {
            margin-bottom: 15px;
        }
        
        .highlight {
            background-color: rgba(255, 109, 0, 0.1);
            border-left: 4px solid var(--accent);
            padding: 15px;
            margin: 15px 0;
            border-radius: 0 8px 8px 0;
        }
        
        .family-section {
            background-color: rgba(233, 30, 99, 0.1);
            border-left: 4px solid var(--family);
        }
        
        form {
            padding: 0 25px 25px;
        }
        
        .form-group {
            margin-bottom: 25px;
            padding: 20px;
            border-radius: 10px;
            background-color: #f8f9fa;
            border-left: 4px solid var(--primary);
        }
        
        .family-question {
            border-left: 4px solid var(--family);
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--primary);
        }
        
        .family-label {
            color: var(--family);
        }
        
        input[type="text"],
        textarea,
        select {
            width: 100%;
            padding: 14px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s;
            margin-top: 5px;
        }
        
        input[type="text"]:focus,
        textarea:focus,
        select:focus {
            border-color: var(--primary);
            outline: none;
        }
        
        textarea {
            min-height: 120px;
            resize: vertical;
        }
        
        .relationship-selector {
            display: flex;
            gap: 15px;
            margin: 20px 0;
            flex-wrap: wrap;
        }
        
        .relationship-option {
            flex: 1;
            min-width: 120px;
            text-align: center;
            padding: 15px;
            border: 2px solid #ddd;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .relationship-option:hover {
            border-color: var(--primary);
            background-color: #e8f0fe;
        }
        
        .relationship-option.selected {
            border-color: var(--primary);
            background-color: #e8f0fe;
            font-weight: bold;
        }
        
        .relationship-option.family {
            border-color: var(--family);
        }
        
        .relationship-option.family.selected {
            border-color: var(--family);
            background-color: #fce4ec;
        }
        
        .relationship-option i {
            font-size: 24px;
            margin-bottom: 10px;
            display: block;
        }
        
        .rating {
            display: flex;
            gap: 15px;
            margin: 10px 0;
            flex-wrap: wrap;
        }
        
        .rating-option {
            flex: 1;
            min-width: 100px;
            text-align: center;
            padding: 10px;
            border: 2px solid #ddd;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .rating-option:hover {
            border-color: var(--primary);
            background-color: #e8f0fe;
        }
        
        .rating-option.selected {
            border-color: var(--primary);
            background-color: #e8f0fe;
            font-weight: bold;
        }
        
        button {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            border: none;
            padding: 16px 30px;
            font-size: 1.1rem;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            display: block;
            margin: 20px auto;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .thank-you {
            display: none;
            text-align: center;
            padding: 40px;
            background-color: var(--light);
            border-radius: 10px;
            margin-top: 20px;
        }
        
        .thank-you h2 {
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        footer {
            text-align: center;
            color: white;
            margin-top: 20px;
            font-size: 0.9rem;
            padding: 20px;
        }
        
        .optional {
            font-weight: normal;
            color: #666;
            font-size: 0.9em;
        }
        
        @media (max-width: 600px) {
            h1 {
                font-size: 1.8rem;
            }
            
            .intro, form {
                padding: 20px;
            }
            
            .rating, .relationship-selector {
                flex-direction: column;
            }
            
            .relationship-option {
                min-width: auto;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="profile-badge">Coordenador Comercial</div>
            <h1>Espelho Social & Familiar</h1>
            <p class="subtitle">Feedback para Desenvolvimento Pessoal, Profissional e Familiar</p>
        </header>
        
        <div class="intro">
            <p>Olá,</p>
            <p>Gostaria de convidá-lo(a) para participar de uma atividade chamada Espelho Social, que tem como objetivo ampliar a visão sobre si mesmo por meio de percepções externas.</p>
            <p>Escolhi você por fazer parte do meu círculo de confiança e por conviver comigo em um contexto importante.</p>
            
            <div class="highlight">
                <p><strong>Como funciona:</strong></p>
                <p>Escolha um momento para refletir e responder às perguntas abaixo com sinceridade.</p>
                <p>A atividade não é para julgamento, mas sim para ampliar a autoconsciência e identificar percepções sobre meus comportamentos, atitudes e impacto interpessoal.</p>
                <p>Suas respostas serão totalmente confidenciais e usadas apenas para meu desenvolvimento pessoal.</p>
            </div>
        </div>
        
        <form id="perceptionForm">
            <div class="form-group">
                <label for="name">Seu nome (opcional):</label>
                <input type="text" id="name" name="name" placeholder="Como gostaria de ser identificado">
            </div>
            
            <div class="form-group">
                <label>Como nos conhecemos? <span class="optional">(Selecione uma opção)</span></label>
                <div class="relationship-selector">
                    <div class="relationship-option" data-value="trabalho">
                        <i class="fas fa-briefcase"></i>
                        <div>Trabalho/Profissional</div>
                    </div>
                    <div class="relationship-option family" data-value="familia">
                        <i class="fas fa-home"></i>
                        <div>Família</div>
                    </div>
                    <div class="relationship-option" data-value="amizade">
                        <i class="fas fa-users"></i>
                        <div>Amizade</div>
                    </div>
                    <div class="relationship-option" data-value="academico">
                        <i class="fas fa-graduation-cap"></i>
                        <div>Ambiente Acadêmico</div>
                    </div>
                </div>
            </div>
            
            <div class="form-group">
                <label>1. Quais são os 3 principais pontos fortes que você enxerga em mim?</label>
                <textarea id="strengths" name="strengths" placeholder="Ex: Liderança, comunicação, resiliência, paciência, senso de humor..." required></textarea>
            </div>
            
            <div class="form-group" id="professional-section">
                <label>2. Como você avalia minhas habilidades de liderança e gestão comercial?</label>
                <div class="rating">
                    <div class="rating-option" data-value="excelente">Excelente</div>
                    <div class="rating-option" data-value="bom">Bom</div>
                    <div class="rating-option" data-value="regular">Regular</div>
                    <div class="rating-option" data-value="precisa-melhorar">Precisa melhorar</div>
                </div>
                <textarea name="leadership-details" placeholder="Comentários adicionais sobre gestão..."></textarea>
            </div>
            
            <div class="form-group family-question" id="family-section-1" style="display: none;">
                <label class="family-label">2. Como você descreveria meu papel na nossa família?</label>
                <textarea name="family-role" placeholder="Ex: Protetor, conselheiro, unificador, exemplo..."></textarea>
            </div>
            
            <div class="form-group">
                <label>3. O que eu faço que gera impacto positivo nas pessoas ao meu redor?</label>
                <textarea id="impact" name="impact" placeholder="Ex: Motiva a equipe, resolve conflitos, traz ideias inovadoras, apoia emocionalmente..." required></textarea>
            </div>
            
            <div class="form-group">
                <label>4. Como você avalia minha capacidade de comunicação e relacionamento?</label>
                <div class="rating">
                    <div class="rating-option" data-value="excelente">Excelente</div>
                    <div class="rating-option" data-value="bom">Bom</div>
                    <div class="rating-option" data-value="regular">Regular</div>
                    <div class="rating-option" data-value="precisa-melhorar">Precisa melhorar</div>
                </div>
                <textarea name="communication-details" placeholder="Comentários adicionais sobre comunicação..."></textarea>
            </div>
            
            <div class="form-group">
                <label>5. O que você acredita que eu poderia melhorar ou desenvolver?</label>
                <textarea id="improvement" name="improvement" placeholder="Ex: Paciência, delegação, tomada de decisão, expressão de sentimentos..." required></textarea>
            </div>
            
            <div class="form-group family-question" id="family-section-2" style="display: none;">
                <label class="family-label">6. Como posso ser um membro ainda melhor da nossa família?</label>
                <textarea name="family-improvement" placeholder="Ex: Passar mais tempo junto, ouvir mais, compartilhar mais experiências..."></textarea>
            </div>
            
            <div class="form-group">
                <label>7. Se tivesse que me descrever em 3 palavras, quais seriam?</label>
                <input type="text" id="words" name="words" placeholder="Ex: Determinado, estratégico, carismático, cuidadoso, divertido" required>
            </div>
            
            <div class="form-group">
                <label>8. Como você se sente quando está comigo?</label>
                <textarea id="feeling" name="feeling" placeholder="Ex: Motivado, ouvido, inspirado, relaxado, feliz..." required></textarea>
            </div>
            
            <div class="form-group">
                <label>9. Como você avalia meu equilíbrio entre vida profissional e pessoal?</label>
                <div class="rating">
                    <div class="rating-option" data-value="excelente">Excelente</div>
                    <div class="rating-option" data-value="bom">Bom</div>
                    <div class="rating-option" data-value="regular">Regular</div>
                    <div class="rating-option" data-value="precisa-melhorar">Precisa melhorar</div>
                </div>
                <textarea name="balance-details" placeholder="Comentários adicionais..."></textarea>
            </div>
            
            <div class="form-group family-question" id="family-section-3" style="display: none;">
                <label class="family-label">10. O que mais valoriza em nosso relacionamento familiar?</label>
                <textarea name="family-value" placeholder="Ex: Nossas conversas, momentos juntos, apoio mútuo, tradições..."></textarea>
            </div>
            
            <button type="submit">Enviar Respostas</button>
        </form>
        
        <div class="thank-you" id="thankYou">
            <h2>Muito Obrigado!</h2>
            <p>Agradeço muito pelo seu tempo e sinceridade!</p>
            <p>Suas respostas foram registradas e serão de grande valor para o meu desenvolvimento pessoal e profissional.</p>
        </div>
    </div>
    
    <footer>
        <p>Espelho Social - Desenvolvimento Pessoal, Profissional e Familiar</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Mostrar/ocultar perguntas baseadas no tipo de relacionamento
            const relationshipOptions = document.querySelectorAll('.relationship-option');
            const professionalSection = document.getElementById('professional-section');
            const familySections = document.querySelectorAll('.family-question');
            
            relationshipOptions.forEach(option => {
                option.addEventListener('click', function() {
                    // Remover seleção anterior
                    relationshipOptions.forEach(opt => opt.classList.remove('selected'));
                    
                    // Selecionar este
                    this.classList.add('selected');
                    
                    // Mostrar/ocultar seções baseadas na seleção
                    const value = this.getAttribute('data-value');
                    
                    if (value === 'familia') {
                        professionalSection.style.display = 'none';
                        familySections.forEach(section => section.style.display = 'block');
                    } else {
                        professionalSection.style.display = 'block';
                        familySections.forEach(section => section.style.display = 'none');
                    }
                });
            });
            
            // Adicionar interatividade às opções de classificação
            const ratingOptions = document.querySelectorAll('.rating-option');
            ratingOptions.forEach(option => {
                option.addEventListener('click', function() {
                    // Remover seleção anterior no mesmo grupo
                    const parent = this.parentElement;
                    const siblings = parent.querySelectorAll('.rating-option');
                    siblings.forEach(sib => sib.classList.remove('selected'));
                    
                    // Selecionar este
                    this.classList.add('selected');
                });
            });
            
            // Manipular envio do formulário
            document.getElementById('perceptionForm').addEventListener('submit', function(e) {
                e.preventDefault();
                
                // Aqui você normalmente enviaria os dados para um servidor
                // Como é apenas uma demonstração, vamos apenas mostrar a mensagem de agradecimento
                
                document.getElementById('perceptionForm').style.display = 'none';
                document.getElementById('thankYou').style.display = 'block';
                
                // Rolando para a mensagem de agradecimento
                document.getElementById('thankYou').scrollIntoView({ behavior: 'smooth' });
            });
        });
    </script>
</body>
</html>
