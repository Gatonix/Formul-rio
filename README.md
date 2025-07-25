# Formul-rio
Formulário Designer
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulário - Equipe de Designers</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 700px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #5865F2, #3B82F6);
            color: white;
            padding: 30px;
            text-align: center;
        }

        .header h1 {
            font-size: 28px;
            margin-bottom: 10px;
        }

        .header p {
            opacity: 0.9;
            font-size: 16px;
        }

        .form-container {
            padding: 40px;
        }

        .form-group {
            margin-bottom: 25px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #333;
            font-size: 14px;
        }

        .required {
            color: #e74c3c;
        }

        input[type="text"],
        input[type="email"],
        input[type="number"],
        input[type="url"],
        select,
        textarea {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e1e8ed;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s ease;
            font-family: inherit;
        }

        input:focus,
        select:focus,
        textarea:focus {
            outline: none;
            border-color: #5865F2;
            box-shadow: 0 0 0 3px rgba(88, 101, 242, 0.1);
        }

        textarea {
            resize: vertical;
            min-height: 100px;
        }

        .checkbox-group {
            display: flex;
            align-items: flex-start;
            gap: 10px;
            margin-top: 10px;
        }

        .checkbox-group input[type="checkbox"] {
            width: auto;
            margin-top: 2px;
        }

        .checkbox-group label {
            margin-bottom: 0;
            font-weight: normal;
            cursor: pointer;
        }

        .radio-group {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-top: 10px;
        }

        .radio-option {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .radio-option input[type="radio"] {
            width: auto;
        }

        .radio-option label {
            margin-bottom: 0;
            font-weight: normal;
            cursor: pointer;
        }

        .submit-btn {
            background: linear-gradient(135deg, #5865F2, #3B82F6);
            color: white;
            padding: 15px 40px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
            width: 100%;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(88, 101, 242, 0.3);
        }

        .submit-btn:active {
            transform: translateY(0);
        }

        .error-message {
            color: #e74c3c;
            font-size: 12px;
            margin-top: 5px;
            display: none;
        }

        .success-message {
            background: #d4edda;
            color: #155724;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            border: 1px solid #c3e6cb;
            display: none;
        }

        @media (max-width: 600px) {
            .form-container {
                padding: 20px;
            }
            
            .header {
                padding: 20px;
            }
            
            .header h1 {
                font-size: 24px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🎨 Equipe de Designers</h1>
            <p>Junte-se à nossa equipe criativa no Discord!</p>
        </div>

        <div class="form-container">
            <div class="success-message" id="successMessage">
                ✅ Formulário enviado com sucesso! Entraremos em contato em breve.
            </div>

            <form id="designerForm">
                <div class="form-group">
                    <label for="nome">Nome Completo <span class="required">*</span></label>
                    <input type="text" id="nome" name="nome" required>
                    <div class="error-message" id="nomeError">Por favor, digite seu nome completo.</div>
                </div>

                <div class="form-group">
                    <label for="idade">Idade <span class="required">*</span></label>
                    <input type="number" id="idade" name="idade" min="16" max="100" required>
                    <div class="error-message" id="idadeError">Você deve ter pelo menos 16 anos para se candidatar.</div>
                </div>

                <div class="form-group">
                    <label for="discord">Discord (usuário#0000) <span class="required">*</span></label>
                    <input type="text" id="discord" name="discord" placeholder="exemplo#1234" required>
                    <div class="error-message" id="discordError">Por favor, digite seu Discord no formato usuário#0000.</div>
                </div>

                <div class="form-group">
                    <label for="portfolio">Link do Portfólio <span class="required">*</span></label>
                    <input type="url" id="portfolio" name="portfolio" placeholder="https://..." required>
                    <small style="color: #666; font-size: 12px;">
                        Compartilhe seu Behance, Dribbble, site pessoal ou Google Drive organizado
                    </small>
                    <div class="error-message" id="portfolioError">Por favor, forneça um link válido para seu portfólio.</div>
                </div>

                <div class="form-group">
                    <label>Experiência <span class="required">*</span></label>
                    <div class="radio-group">
                        <div class="radio-option">
                            <input type="radio" id="exp-comercial" name="experiencia" value="comercial" required>
                            <label for="exp-comercial">Experiência Comercial (trabalhos pagos, freelances, empresas)</label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" id="exp-fivem" name="experiencia" value="fivem" required>
                            <label for="exp-fivem">Experiência com FiveM (servidores de RP, mods, interfaces)</label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" id="exp-ambas" name="experiencia" value="ambas" required>
                            <label for="exp-ambas">Ambas as experiências</label>
                        </div>
                    </div>
                    <div class="error-message" id="experienciaError">Por favor, selecione sua experiência.</div>
                </div>

                <div class="form-group">
                    <label for="experiencia-desc">Descreva sua experiência</label>
                    <textarea id="experiencia-desc" name="experiencia-desc" placeholder="Conte um pouco sobre seus trabalhos anteriores, projetos realizados, tempo de experiência, etc."></textarea>
                </div>

                <div class="form-group">
                    <label>Disponibilidade <span class="required">*</span></label>
                    <div class="checkbox-group">
                        <input type="checkbox" id="dia" name="disponibilidade" value="dia">
                        <label for="dia">Dia (08h às 22h)</label>
                    </div>
                    <div class="checkbox-group">
                        <input type="checkbox" id="tarde" name="disponibilidade" value="tarde">
                        <label for="tarde">Tarde (13h às 22h/23h)</label>
                    </div>
                    <div class="checkbox-group">
                        <input type="checkbox" id="noite" name="disponibilidade" value="noite">
                        <label for="noite">Noite (18h às 23h)</label>
                    </div>
                    <div class="error-message" id="disponibilidadeError">Por favor, selecione pelo menos um horário de disponibilidade.</div>
                </div>

                <div class="form-group">
                    <div class="checkbox-group">
                        <input type="checkbox" id="microfone" name="microfone" required>
                        <label for="microfone">Confirmo que possuo microfone funcional <span class="required">*</span></label>
                    </div>
                    <div class="error-message" id="microfoneError">É obrigatório ter microfone para participar da equipe.</div>
                </div>

                <div class="form-group">
                    <label for="observacoes">Observações adicionais</label>
                    <textarea id="observacoes" name="observacoes" placeholder="Algo mais que gostaria de compartilhar? Especialidades, softwares que domina, etc."></textarea>
                </div>

                <button type="submit" class="submit-btn">Enviar Candidatura</button>
            </form>
        </div>
    </div>

    <script>
        document.getElementById('designerForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Reset previous errors
            const errorMessages = document.querySelectorAll('.error-message');
            errorMessages.forEach(msg => msg.style.display = 'none');
            
            let isValid = true;
            
            // Validate nome
            const nome = document.getElementById('nome').value.trim();
            if (!nome) {
                document.getElementById('nomeError').style.display = 'block';
                isValid = false;
            }
            
            // Validate idade
            const idade = parseInt(document.getElementById('idade').value);
            if (!idade || idade < 16) {
                document.getElementById('idadeError').style.display = 'block';
                isValid = false;
            }
            
            // Validate discord
            const discord = document.getElementById('discord').value.trim();
            if (!discord || !discord.includes('#')) {
                document.getElementById('discordError').style.display = 'block';
                isValid = false;
            }
            
            // Validate portfolio
            const portfolio = document.getElementById('portfolio').value.trim();
            if (!portfolio || !portfolio.startsWith('http')) {
                document.getElementById('portfolioError').style.display = 'block';
                isValid = false;
            }
            
            // Validate experiencia
            const experiencia = document.querySelector('input[name="experiencia"]:checked');
            if (!experiencia) {
                document.getElementById('experienciaError').style.display = 'block';
                isValid = false;
            }
            
            // Validate disponibilidade
            const disponibilidade = document.querySelectorAll('input[name="disponibilidade"]:checked');
            if (disponibilidade.length === 0) {
                document.getElementById('disponibilidadeError').style.display = 'block';
                isValid = false;
            }
            
            // Validate microfone
            const microfone = document.getElementById('microfone').checked;
            if (!microfone) {
                document.getElementById('microfoneError').style.display = 'block';
                isValid = false;
            }
            
            if (isValid) {
                // Collect form data
                const formData = {
                    nome: nome,
                    idade: idade,
                    discord: discord,
                    portfolio: portfolio,
                    experiencia: experiencia.value,
                    experienciaDesc: document.getElementById('experiencia-desc').value.trim(),
                    disponibilidade: Array.from(disponibilidade).map(cb => cb.value),
                    microfone: microfone,
                    observacoes: document.getElementById('observacoes').value.trim()
                };
                
                // Prepare email content
                const emailBody = `
NOVA CANDIDATURA - EQUIPE DE DESIGNERS

Nome: ${formData.nome}
Idade: ${formData.idade} anos
Discord: ${formData.discord}
Portfólio: ${formData.portfolio}

Experiência: ${formData.experiencia}
${formData.experienciaDesc ? `Descrição da experiência: ${formData.experienciaDesc}` : ''}

Disponibilidade: ${formData.disponibilidade.join(', ')}
Microfone: Sim

${formData.observacoes ? `Observações: ${formData.observacoes}` : ''}

---
Candidatura recebida em: ${new Date().toLocaleString('pt-BR')}
                `.trim();

                // Create mailto link
                const subject = encodeURIComponent(`[CANDIDATURA] ${formData.nome} - Designer Discord`);
                const body = encodeURIComponent(emailBody);
                const mailtoLink = `mailto:vicestudios03@gmail.com?subject=${subject}&body=${body}`;
                
                // Open email client
                window.location.href = mailtoLink;
            }
        });
    </script>
</body>
</html>
