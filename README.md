# Primeira Contribuição IFAL Arapiraca

Repositório destinado a devs do IFAL campus Arapiraca que querem experimentar a primeira contribuição com projetos de software de código aberto.

Cada contribuição deve conter apenas um arquivo, respeitando o formato JSON. O nome do arquivo deve obedecer ao seguinte formato: `{usuário email}.json`. O nome da branch (ramo), deve ser {usuário email}. Por exemplo, a discente `jj1234@aluno.ifal.edu.br` vai realizar uma contribuição usando o ramo `jj1234` e criando o arquivo `jj1234.json`. O conteúdo deve seguir o seguinte padrão:

```json
{
  "nome": "SEU NOME",
  "turma": "SUA TURMA",
  "curso": "CURSO",
  "ano_inicio": "ANO DE INICIO",
  "email": "EMAIL COMPLETO"
}
```

## Próximos passos

https://abre.ai/hacktoberfest-ifal-ara

## Coleta de informações usando `jq`

### Número de contribuições por turma

```sh
jq -s '.[].turma' *.json | tr '[:upper:]' '[:lower:]' | tr -d '°º' | sort | uniq -ic
```

### Número de contribuições por ano início

```sh
jq -s '.[].ano_inicio' *.json | tr '[:upper:]' '[:lower:]' | tr -d '°' | sort | uniq -ic
```
### Lista de e-mails por turma

Por exemplo, a turma 923
```sh
jq -s '.[] | select(.turma == "923") | .email' *.json | tr '[:upper:]' '[:lower:]' | sort
```
