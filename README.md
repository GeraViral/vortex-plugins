# Plugins do Grupo Vórtex para o Claude Code

Um marketplace com os plugins que a gente usa. Hoje tem um.

## site-pronto

Monta um site animado com o Claude Code: projeto Next.js, a biblioteca de animação, e um guia de design que tira a cara de IA do resultado.

### Instalar

Um comando. Ele adiciona este marketplace e instala o plugin de uma vez:

```bash
claude plugin install site-pronto --marketplace GeraViral/vortex-plugins
```

Isso vale a partir do Claude Code **2.1.292**. Rode `claude --version` para conferir.

Dentro de uma sessão do Claude Code, a partir da **2.1.275**, o mesmo comando é:

```text
/plugin install site-pronto --marketplace GeraViral/vortex-plugins
```

Se a sua versão for mais antiga, dá em dois comandos:

```bash
claude plugin marketplace add GeraViral/vortex-plugins
claude plugin install site-pronto@vortex
```

### Usar

Abra o Claude Code na pasta onde quer o site e digite:

```text
/site-pronto:novo
```

Ele pergunta o nome da pasta e do que é o site, e monta a partir daí.

### O que entra

| | |
|---|---|
| `/site-pronto:novo` | cria o projeto Next.js, instala a animação e conduz o resto |
| `/site-pronto:design` | as regras de design, com os números prontos, para escrever ou revisar qualquer tela |

Nenhum dos dois roda nada sozinho: cada comando é lido pelo Claude, que executa os passos com você olhando e pedindo confirmação.

### Pré-requisitos

- **Claude Code** num plano pago, acesso à API, ou um provedor terceiro. O plano gratuito do claude.ai não inclui Claude Code.
- **Node 20 ou mais novo**. A skill confere e avisa antes de criar qualquer coisa.
- **Git**, para publicar depois. Não é necessário para rodar o site na sua máquina.

### O 21st.dev é opcional

O catálogo de componentes do 21st.dev entra como MCP, e **precisa de uma chave própria**, que sai em [21st.dev/magic/console](https://21st.dev/magic/console):

```bash
claude mcp add magic -- npx -y @21st-dev/magic@latest
```

Sem chave, o servidor sobe e as ferramentas falham na primeira chamada. Se você não tem, pule: o site fica pronto do mesmo jeito.

### Desinstalar

```bash
claude plugin uninstall site-pronto@vortex
```

## Licença

MIT.
