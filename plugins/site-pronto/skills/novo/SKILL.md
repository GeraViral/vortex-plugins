---
name: novo
description: Monta um site animado do zero com Next.js, a biblioteca de animação e o guia de design. Use quando a pessoa pedir "cria um site", "monta uma landing page", "quero um site animado", "/site-pronto:novo", ou quando ela acabou de instalar este plugin e quer começar.
---

# Site pronto

Monta um site que não tem cara de feito por IA. Três coisas, nesta ordem: o projeto, a animação, o design.

## Antes de começar, confira duas coisas

Rode as duas e **mostre o resultado para a pessoa** antes de seguir:

```bash
node --version
```

Precisa de **Node 20 ou mais novo**. Se der `command not found` ou vier abaixo de 20, pare aqui e mande a pessoa instalar em [nodejs.org](https://nodejs.org). Nada abaixo funciona.

```bash
git --version
```

Não é obrigatório para rodar o site, mas sem ele a pessoa não consegue publicar depois. Se faltar, avise e siga.

## Passo 1, o projeto

Pergunte **o nome da pasta** e **do que é o site** antes de criar qualquer coisa. Sem as duas respostas você vai escrever um site genérico, que é exatamente o que este plugin existe para evitar.

```bash
npx create-next-app@latest NOME --typescript --tailwind --app --no-src-dir --import-alias "@/*" --yes
```

Troque `NOME` pela resposta. O `--yes` aceita os padrões e evita que o instalador fique perguntando.

Se a pasta já existir e tiver conteúdo, **não sobrescreva**: pergunte se é para usar outro nome ou para montar dentro do projeto que já está lá.

## Passo 2, a animação

```bash
npm install motion
```

**O pacote chama `motion`.** O nome antigo era `framer-motion`, e ainda existe no npm, mas o nome que a documentação usa hoje é `motion`. Tutorial que manda instalar `framer-motion` está desatualizado; os dois publicam a mesma versão, então instalar o antigo não quebra, mas o import e os exemplos que a pessoa vai achar usam o novo.

No código, o import é:

```tsx
import { motion } from "motion/react";
```

Três coisas resolvem 90% do que as pessoas querem, e você deve usar só essas três no primeiro site:

- **entrada**: `initial={{ opacity: 0, y: 20 }}` com `animate={{ opacity: 1, y: 0 }}`
- **ao aparecer na rolagem**: troque `animate` por `whileInView` e some `viewport={{ once: true }}`, senão repete toda vez que a pessoa rola
- **ao passar o mouse**: `whileHover={{ scale: 1.03 }}`

Mais que isso numa landing page cansa. Animação boa é a que ninguém comenta.

## Passo 3, o design

**Carregue a skill `design` deste plugin antes de escrever qualquer componente.** Ela tem as regras que separam um site que parece feito por um designer de um que parece feito por IA, e é a parte que mais muda o resultado.

## Passo 4, componentes prontos (opcional)

O 21st.dev é um catálogo de componentes que o Claude pode consultar enquanto monta. Ele entra como MCP:

```bash
claude mcp add magic -- npx -y @21st-dev/magic@latest
```

**Precisa de uma chave**, que sai em [21st.dev/magic/console](https://21st.dev/magic/console). Sem chave o servidor sobe e as ferramentas falham na primeira chamada, o que confunde. Se a pessoa não tiver chave, **diga para pular este passo**: o site fica pronto do mesmo jeito, só sem o catálogo.

## No fim

Rode e deixe no ar para a pessoa ver:

```bash
npm run dev
```

Diga o endereço (`http://localhost:3000`) e **pergunte o que ela quer mudar**. Não liste o que você fez: mostre o site.

## O que não fazer

- Não instale biblioteca de componente visual (shadcn, Material, Chakra) sem a pessoa pedir. O Tailwind do Next já basta para a primeira versão, e cada biblioteca a mais é uma decisão que ela vai ter que manter.
- Não escreva texto de exemplo em latim. Se não souber o que escrever, pergunte.
- Não prometa publicação. Montar o site e publicar são coisas diferentes, e publicar depende de conta em algum lugar.
