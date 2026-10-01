# Política de Segurança (Security Policy)
Este repositório é um projeto exclusivamente educacional composto por arquivos de documentação (Markdown) com uma coleção de APIs para teste. Por não conter código-fonte executável, binários ou serviços em produção, o escopo de segurança é voltado à integridade do conteúdo informativo.

## Versões suportadas
Como se trata de uma base de conhecimento em constante atualização, apenas o conteúdo mais recente na branch principal (`main`) recebe revisões e correções.

## O que é considerado um problema de segurança?
Mesmo em repositórios de documentação, levamos a segurança dos leitores a sério. Exemplos de vulnerabilidades ou riscos relevantes:
- **Comandos danosos ou inseguros:** Instruções ou exemplos de comandos Git/Bash que possam expor credenciais, chaves SSH, tokens de API ou dados sensíveis sem o devido alerta.
- **Links maliciosos ou sequestro de domínios (Broken Link Hijacking):** Links externos na documentação que apontem para sites maliciosos, páginas de phishing ou domínios expirados.
- **Injeção de scripts / XSS:** Caso o leitor utilize visualizadores específicos de Markdown com renderização de HTML habilitada.

## Como reportar uma vulnerabilidade
Se você identificou uma falha ou risco de segurança neste repositório:
1. **Não abra uma Issue pública** imediatamente se a falha puder induzir leitores a riscos graves (como execução de scripts ou links maliciosos ativos).
2. Utilize o recurso nativo de **[Security Advisory privado do GitHub](https://docs.github.com/pt/code-security/security-advisories/guidance-on-reporting-and-communicating-about-vulnerabilities)** (disponível na aba *Security > Report a vulnerability* do repositório).
3. Inclua na mensagem:
   - O arquivo e a linha onde o problema foi encontrado.
   - Uma breve explicação do risco de segurança (ex: por que aquele comando ou link pode ser perigoso).
   - Sugestão de correção (opcional, mas muito bem-vinda).

## Prazos e o que esperar
- **Confirmação de recebimento:** Buscaremos responder ao contato em até **48 horas**.
- **Avaliação:** Em até **5 dias úteis**, avaliaremos o relato e confirmaremos se a correção será aplicada.
- **Resolução:** Se confirmada a falha, uma correção será enviada diretamente à branch principal e você receberá os devidos créditos no commit ou nas notas de lançamento (caso deseje ser mencionado).
