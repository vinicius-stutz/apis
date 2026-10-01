# Segurança em APIs
Guia prático e conceitual dos principais mecanismos e boas práticas de segurança para arquitetura de APIs modernas.

## HTTPS
**O que é**: É a versão segura do HTTP. Explicação: Imagina que envias uma carta transparente pelo correio; qualquer pessoa pode ler o conteúdo. O HTTPS é como colocar essa carta num cofre blindado antes de enviar. Ele encripta os dados entre o cliente (quem usa a API) e o servidor. Na prática: Nunca publiques uma API apenas com HTTP. Use certificados SSL/TLS para garantir que o endereço comece com `https://`.

## OAuth2
**O que é**: Um padrão para autorização segura. Explicação: Em vez de dares a tua senha do Google a um site terceiro, usas o *OAuth2* para dar uma "permissão temporária". É como dar a chave de manobrista do carro: ele pode conduzir, mas não consegue abrir o porta-luvas. Na prática: Permite que utilizadores façam login na tua API usando contas existentes (como Google ou Facebook) sem partilhar a senha real.

## WebAuthn
**O que é**: Autenticação Web (padrão moderno). Explicação: É uma forma de autenticar sem senhas, usando biometria (impressão digital, reconhecimento facial) ou chaves de segurança físicas (*YubiKey*). É muito mais difícil de ser hackeado do que uma senha escrita num papel. Na prática: Implementa login via impressão digital ou FaceID na tua aplicação web.

## Leveled API Keys (Chaves de API com Níveis)
**O que é**: Chaves de acesso com permissões limitadas. Explicação: Nem todos precisam da "chave mestra" da casa. O jardineiro só precisa da chave do portão, não da chave do cofre. Na prática: Cria chaves diferentes: uma "*Read-Only*" (só leitura) para utilizadores comuns e uma "Admin" (leitura e escrita) para administradores. Se a chave de leitura vazar, o hacker não consegue apagar dados.

## Authorization (Autorização)
**O que é**: Verificar o que o utilizador pode fazer. Explicação: Autenticação é saber quem tu és (mostrar o BI). Autorização é saber o que podes fazer (entrar na área VIP). Na prática: Não basta o utilizador estar logado. O código deve verificar: "Este utilizador tem permissão para apagar este ficheiro específico?".

## Rate Limiting (Limite de Taxa)
**O que é**: Limitar o número de pedidos (*requests*). Explicação: Impede que alguém sobrecarregue o teu servidor fazendo milhões de perguntas por segundo (ataque DDoS ou força bruta). É como colocar um torniquete na entrada do metro. Na prática: Configura a API para aceitar, por exemplo, apenas 100 pedidos por minuto vindos do mesmo endereço IP.

## API Versioning (Versionamento de API)
**O que é**: Criar versões diferentes da API (v1, v2). Explicação: Se mudares como a API funciona, podes quebrar o código de quem a usa. O versionamento permite lançar melhorias na "v2" sem desligar a "v1" antiga. Na prática: Usa URLs como `api.meusite.com/v1/usuarios` e `api.meusite.com/v2/usuarios`.

## Whitelisting (Lista Branca)
**O que é**: Permitir apenas o que é conhecido. Explicação: É como uma lista de convidados numa festa privada. Se o nome não está na lista, não entra. O oposto (Blacklisting) é tentar adivinhar quem barrar, o que é menos seguro. Na prática: Configura o servidor para aceitar conexões apenas de IPs confiáveis ou permitir apenas certos caracteres nos campos de texto.

## Check OWASP API Security Risks
**O que é**: Seguir a lista de riscos da OWASP (Open Web Application Security Project). Explicação: A OWASP mantém uma lista atualizada das 10 falhas de segurança mais comuns em APIs. Verificar esta lista é como fazer um check-up médico preventivo. Na prática: Lê o "OWASP API Security Top 10" e testa a tua API contra aquelas vulnerabilidades específicas.

## Use API Gateway
**O que é**: Um porteiro central para todas as tuas APIs. Explicação: Em vez de cada micro-serviço tratar da segurança sozinho, colocas um "guardião" na frente que trata da autenticação, do Rate Limiting e do monitoramento. Na prática: Ferramentas como Kong, AWS API Gateway ou Azure API Management recebem o pedido primeiro, verificam se é seguro e só depois passam para o teu código.

## Error Handling (Tratamento de Erros)
**O que é**: Responder a erros sem revelar segredos. Explicação: Se o teu código falhar, ele não deve dizer "Erro na linha 50 ao conectar no Banco de Dados com a senha 123". Isso dá dicas ao atacante. Na prática: Retorna mensagens genéricas como "Ocorreu um erro interno", mas guarda o erro detalhado nos teus logs internos (onde ninguém vê).

## Input Validation (Validação de Entrada)
**O que é**: Verificar tudo o que o utilizador envia. Explicação: Nunca confies no que vem de fora. É como lavar a fruta antes de comer. Se esperas um número de telefone, garante que não estão a enviar um código malicioso (SQL Injection). Na prática: Se o campo é "idade", o código deve rejeitar letras ou símbolos e aceitar apenas números dentro de um intervalo lógico.
