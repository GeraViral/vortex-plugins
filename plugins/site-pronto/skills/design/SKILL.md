---
name: design
description: As regras de design que tiram a cara de IA de um site, com os números prontos. Use ao escrever qualquer componente visual, ao revisar um layout, quando a pessoa disser que o site "ficou com cara de template" ou "parece feito por IA", ou quando a skill novo mandar carregar.
---

# Design que não parece IA

Site feito por IA tem uma aparência própria, e ela vem de um punhado de decisões que o modelo toma sozinho quando ninguém manda. Estas regras tiram cada uma delas.

## As seis marcas e o que fazer em cada

**1. Degradê roxo-para-azul no fundo.** É a assinatura. Fundo é uma cor só, e a cor vem do assunto do site. Degradê, quando entrar, é entre dois tons da **mesma** cor, e num bloco, nunca na página inteira.

**2. Tudo centralizado.** Centralizado é o que sai quando ninguém decidiu nada. Alinhe o texto à esquerda e deixe a centralização para o que é curto: título de seção, chamada do topo, rodapé.

**3. Três cards iguais lado a lado.** Se a página tem uma fileira de três cards com ícone, título e duas linhas, ela tem cara de template. Quebre a simetria: um bloco grande e dois pequenos, ou uma lista, ou um card por linha com a imagem alternando de lado.

**4. Emoji como ícone.** Nunca. Ou um conjunto de ícones de verdade (lucide, heroicons), ou nenhum.

**5. Sombra em tudo.** Sombra serve para dizer o que está na frente. Se tudo tem, nada está. Escolha **um** elemento que flutua.

**6. Texto genérico.** "Transforme seu negócio", "Soluções inovadoras", "Eleve sua presença digital". Se você não sabe o que a empresa faz, **pergunte** em vez de preencher.

## Os números, para não chutar

**Espaço vertical entre seções:** 96px no celular, 160px no desktop. O erro mais comum é apertar: espaço é o que faz parecer caro.

**Largura do texto:** no máximo **70 caracteres** por linha. Em Tailwind, `max-w-[65ch]`. Linha mais larga que isso cansa e é a diferença mais visível entre um site de agência e um site de template.

**Escala de tamanho**, uma razão só, sem inventar tamanhos no meio:

| papel | celular | desktop |
|---|---|---|
| título da página | 40px | 72px |
| título de seção | 30px | 44px |
| corpo | 17px | 18px |
| apoio | 14px | 15px |

**Entrelinha:** 1,1 em título, 1,6 em corpo. Título com entrelinha de corpo é a segunda marca mais visível de site automático.

**Cor:** uma cor de marca, um cinza-escuro para texto (nunca `#000`), um cinza claro para linha e fundo de bloco. **Três, não mais.** Acento só no que é clicável.

**Contraste:** texto de corpo precisa de 4,5:1 contra o fundo. Cinza claro sobre branco reprova quase sempre, e é a reclamação número um de quem abre o site no celular na rua.

## Tipografia

Uma família só resolve um site inteiro. Duas é o teto, e só quando a segunda é para os títulos.

Combinações que funcionam e estão no Google Fonts:

| para | fonte |
|---|---|
| direto, qualquer assunto | Inter |
| mais calor, sem perder seriedade | Figtree |
| título com autoridade editorial | Playfair Display nos títulos, Inter no corpo |
| técnico, produto de software | Geist, ou Inter com tracking negativo nos títulos |

Em título grande, aperte o tracking: `-0.02em` a partir de 40px. Sem isso, título grande parece esparramado.

## A ordem da página

Uma landing page que converte tem pouca coisa, nesta ordem:

1. **Topo**: uma frase que diz o que é, para quem, e o que a pessoa ganha. Não é slogan, é descrição.
2. **Prova**: número, logotipo de cliente, depoimento com nome e rosto. Sem prova, o resto não é lido.
3. **Como funciona**: três passos, no máximo, cada um com uma frase.
4. **Objeção**: a dúvida que faz a pessoa não comprar, respondida antes de ela perguntar.
5. **Ação**: um botão, repetindo o que o topo prometeu.

Seção que não cabe em um desses cinco papéis sai da página.

## Antes de entregar, confira

- [ ] A largura do texto passa de 70 caracteres em alguma linha?
- [ ] Tem fileira de três cards iguais?
- [ ] Tem emoji fazendo papel de ícone?
- [ ] Tem mais de três cores?
- [ ] O cinza do corpo passa em 4,5:1 contra o fundo?
- [ ] Tem texto que serviria para qualquer empresa?
- [ ] No celular, em 375px de largura, alguma coisa estoura para o lado?

Qualquer "sim" nas seis primeiras, ou na última, volta para a prancheta.
