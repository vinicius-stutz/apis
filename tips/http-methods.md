# Métodos HTTP
Definições e casos práticos de uso dos métodos HTTP PATCH, HEAD, OPTIONS e TRACE em APIs REST.

## PATCH
Você só envia o que mudou, não o objeto inteiro. Imagine atualizar seu perfil no Instagram, você muda só o nome, não reenvia a foto, bio e tudo mais.
```
PATCH /users/123
{
	"nome": "Novo Nome"
}
```

## HEAD
É como o GET, mas o servidor não envia os dados. Só confirma que existem. Útil quando você só quer saber se "determinado recurso existe", sem baixar tudo.
```
HEAD /users/123
// Retona sim, existe (200) ou não (404)
```

## OPTIONS
Pergunta ao servidor quais operações podem ser realizadas. O servidor responde, por exemplo, "você pode fazer GET, POST, PATCH e DELETE neste endpoint".
```
OPTIONS /users
// Resposta: GET, POST, PATCH, DELETE
```

## TRACE
Mostra o caminho que sua requisição percorreu até o servidor. Útil para debug quando há algo errado no meio do caminho.
```
TRACE /users/123
// Retorna: caminho completo
```
