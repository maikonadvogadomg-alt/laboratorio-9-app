# 🧬 Receita para recriar: Meu Chat

_Gerada sem IA, lendo 149 arquivo(s). Serve para remontar este app como HTML modular — com qualquer IA, um arquivo por vez._

## 1. O que é

- **Nome:** Meu Chat
- **Partes de código:** 123 (18 tela, 100 logica, 0 servidor, 0 dados, 5 estilo)
- **Tem servidor (rotas /api):** não — dá para ser só HTML
- **Peças de fora (bibliotecas):** @capacitor/cli, child_process, electron, fs, http, os, path, react-native, react-native-webview, readline, x, zlib

## 2. Estrutura modular proposta

```
index.html            ← a página; chama os módulos NA ORDEM
css/app.css           ← o visual
js/00-core.js         ← a "locomotiva": cria window.APP (registrar, guardar, avisar)
js/10-base.js         ← Meu Chat — 00-base.js: peças comuns (MC) (era ferramentas/laboratorio2/ferramentas/meu-chat/js/00-base.js)
js/15-banco.js        ← Meu Chat — 10-banco.js: onde tudo fica guardado (IndexedDB do aparelho (era ferramentas/laboratorio2/ferramentas/meu-chat/js/10-banco.js)
js/20-nuvem.js        ← Meu Chat — 12-nuvem.js · ☁️ NUVEM (Supabase) — 17/11 - O chat continua (era ferramentas/laboratorio2/ferramentas/meu-chat/js/12-nuvem.js)
js/25-provedores.js   ← Meu Chat — 20-provedores.js: conversar com as IAs (Gemini, Groq, OpenR (era ferramentas/laboratorio2/ferramentas/meu-chat/js/20-provedores.js)
js/30-memoria.js      ← Meu Chat — 30-memoria.js: 🧠 a memória que vai junto em TODA conversa. (era ferramentas/laboratorio2/ferramentas/meu-chat/js/30-memoria.js)
js/35-contextos.js    ← Meu Chat — 33-contextos.js: 📌 CONTEXTOS — "cartões" de assunto que vo (era ferramentas/laboratorio2/ferramentas/meu-chat/js/33-contextos.js)
js/40-guia.js         ← 🧭 Painel do Guia (16/11): o que é cada app do Maikon, a versão atual  (era ferramentas/laboratorio2/ferramentas/meu-chat/js/34-guia.js)
js/45-jeito.js        ← Meu Chat — 35-jeito.js: 🎭 O JEITO DE CADA IA. Para não ter "mudança d (era ferramentas/laboratorio2/ferramentas/meu-chat/js/35-jeito.js)
js/50-voz.js          ← Meu Chat — 40-voz.js: 🎤 falar (ditado) e 🔊 ouvir a resposta. 🔊 DOIS (era ferramentas/laboratorio2/ferramentas/meu-chat/js/40-voz.js)
js/55-internet.js     ← Meu Chat — 50-internet.js: 🌐 pesquisar e 🔗 ler links. - Gemini e Cla (era ferramentas/laboratorio2/ferramentas/meu-chat/js/50-internet.js)
js/60-previa.js       ← Meu Chat — 60-previa.js: 👁 ver o código funcionando, na hora. - HTML: (era ferramentas/laboratorio2/ferramentas/meu-chat/js/60-previa.js)
js/65-texto.js        ← Meu Chat — 70-texto.js: mostra a resposta da IA bonitinha (negrito, li (era ferramentas/laboratorio2/ferramentas/meu-chat/js/70-texto.js)
js/70-chat.js         ← Meu Chat — 80-chat.js: a conversa (mensagens, fotos, mandar, parar, li (era ferramentas/laboratorio2/ferramentas/meu-chat/js/80-chat.js)
js/75-config.js       ← Meu Chat — 85-config.js: ⚙️ chaves das IAs, modelo, busca, voz, instru (era ferramentas/laboratorio2/ferramentas/meu-chat/js/85-config.js)
js/80-cofre.js        ← Meu Chat — 87-cofre.js: 🔐 Cofre de chaves. Mostra cada chave guardada (era ferramentas/laboratorio2/ferramentas/meu-chat/js/87-cofre.js)
js/85-backup.js       ← Meu Chat — 90-backup.js: 💾 backup de tudo (conversas + memória + ajus (era ferramentas/laboratorio2/ferramentas/meu-chat/js/90-backup.js)
js/90-ponte-lab.js    ← 🔬 Ponte com o Laboratório: quando o Meu Chat está DENTRO do Laboratór (era ferramentas/laboratorio2/ferramentas/meu-chat/js/95-ponte-lab.js)
js/91-cofre-arquivo.js← 🔐 Arquivo de chaves do Maikon — o MESMO formato no Mini SK, no Meu Ch (era ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/cofre-arquivo.js)
js/92-guia-maikon.js  ← 🧭 Guia das ferramentas do Maikon — o MESMO texto em todos os apps (Mi (era ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/guia-maikon.js)
js/93-guia-versoes.js ← 🧭 Guia das VERSÕES — o que é cada app do Maikon, qual a versão atual, (era ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/guia-versoes.js)
js/94-nuvem-neon.js   ← 🐘 Nuvem pelo NEON (17/11) — usada pelo Meu Chat e pelo SK Jurídico HT (era ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/nuvem-neon.js)
js/95-voz-francisco.js← !/usr/bin/env python3 -*- coding: utf-8 -*- (era ferramentas/laboratorio2/ferramentas/meu-chat/voz-francisco.py)
js/96-casca.js        ← js/00-casca.js (era ferramentas/laboratorio2/js/00-casca.js)
js/97-importar.js     ← js/02-importar.js (era ferramentas/laboratorio2/js/02-importar.js)
js/98-dependencias.js ← js/03-dependencias.js (era ferramentas/laboratorio2/js/03-dependencias.js)
js/98-analisar.js     ← js/04-analisar.js (era ferramentas/laboratorio2/js/04-analisar.js)
js/98-plano.js        ← js/05-plano.js (era ferramentas/laboratorio2/js/05-plano.js)
js/98-05a-markdown.js ← js/05a-markdown.js (era ferramentas/laboratorio2/js/05a-markdown.js)
js/98-scripts.js      ← js/06-scripts.js (era ferramentas/laboratorio2/js/06-scripts.js)
js/98-06b-scripts-fim.js← js/06b-scripts-fim.js (era ferramentas/laboratorio2/js/06b-scripts-fim.js)
js/98-terminal.js     ← js/07-terminal.js (era ferramentas/laboratorio2/js/07-terminal.js)
js/98-07a-busca-npm.js← js/07a-busca-npm.js (era ferramentas/laboratorio2/js/07a-busca-npm.js)
js/98-exportar.js     ← js/08-exportar.js (era ferramentas/laboratorio2/js/08-exportar.js)
js/98-integracao.js   ← js/09-integracao.js (era ferramentas/laboratorio2/js/09-integracao.js)
js/98-celular.js      ← js/10-celular.js (era ferramentas/laboratorio2/js/10-celular.js)
js/98-lab-base.js     ← js/11-lab-base.js (era ferramentas/laboratorio2/js/11-lab-base.js)
js/98-lab-mapa.js     ← js/12-lab-mapa.js (era ferramentas/laboratorio2/js/12-lab-mapa.js)
js/98-lab-previa.js   ← js/13-lab-previa.js (era ferramentas/laboratorio2/js/13-lab-previa.js)
js/98-lab-pesquisa.js ← js/14-lab-pesquisa.js (era ferramentas/laboratorio2/js/14-lab-pesquisa.js)
js/98-lab-comparar.js ← js/15-lab-comparar.js (era ferramentas/laboratorio2/js/15-lab-comparar.js)
js/98-15a-tar.js      ← js/15a-tar.js (era ferramentas/laboratorio2/js/15a-tar.js)
js/98-lab-ferramentas.js← js/16-lab-ferramentas.js (era ferramentas/laboratorio2/js/16-lab-ferramentas.js)
js/98-lab-termux.js   ← LABORATÓRIO 2 — 17-lab-termux.js · 💻 TERMINAL DE VERDADE (16/11) Troc (era ferramentas/laboratorio2/js/17-lab-termux.js)
js/98-lab-desmontar.js← js/18-lab-desmontar.js (era ferramentas/laboratorio2/js/18-lab-desmontar.js)
js/98-embutido.js     ← logica (era ferramentas/laboratorio2/js/19-embutido.js)
js/98-base.js         ← Meu Chat — 00-base.js: peças comuns (MC) (era ferramentas/meu-chat/js/00-base.js)
js/98-banco.js        ← Meu Chat — 10-banco.js: onde tudo fica guardado (IndexedDB do aparelho (era ferramentas/meu-chat/js/10-banco.js)
js/98-nuvem.js        ← Meu Chat — 12-nuvem.js · ☁️ NUVEM (Supabase) — 17/11 - O chat continua (era ferramentas/meu-chat/js/12-nuvem.js)
js/98-provedores.js   ← Meu Chat — 20-provedores.js: conversar com as IAs (Gemini, Groq, OpenR (era ferramentas/meu-chat/js/20-provedores.js)
js/98-memoria.js      ← Meu Chat — 30-memoria.js: 🧠 a memória que vai junto em TODA conversa. (era ferramentas/meu-chat/js/30-memoria.js)
js/98-contextos.js    ← Meu Chat — 33-contextos.js: 📌 CONTEXTOS — "cartões" de assunto que vo (era ferramentas/meu-chat/js/33-contextos.js)
js/98-guia.js         ← 🧭 Painel do Guia (16/11): o que é cada app do Maikon, a versão atual  (era ferramentas/meu-chat/js/34-guia.js)
js/98-jeito.js        ← Meu Chat — 35-jeito.js: 🎭 O JEITO DE CADA IA. Para não ter "mudança d (era ferramentas/meu-chat/js/35-jeito.js)
js/98-voz.js          ← Meu Chat — 40-voz.js: 🎤 falar (ditado) e 🔊 ouvir a resposta. 🔊 DOIS (era ferramentas/meu-chat/js/40-voz.js)
js/98-internet.js     ← Meu Chat — 50-internet.js: 🌐 pesquisar e 🔗 ler links. - Gemini e Cla (era ferramentas/meu-chat/js/50-internet.js)
js/98-previa.js       ← Meu Chat — 60-previa.js: 👁 ver o código funcionando, na hora. - HTML: (era ferramentas/meu-chat/js/60-previa.js)
js/98-texto.js        ← Meu Chat — 70-texto.js: mostra a resposta da IA bonitinha (negrito, li (era ferramentas/meu-chat/js/70-texto.js)
js/98-chat.js         ← Meu Chat — 80-chat.js: a conversa (mensagens, fotos, mandar, parar, li (era ferramentas/meu-chat/js/80-chat.js)
js/98-config.js       ← Meu Chat — 85-config.js: ⚙️ chaves das IAs, modelo, busca, voz, instru (era ferramentas/meu-chat/js/85-config.js)
js/98-cofre.js        ← Meu Chat — 87-cofre.js: 🔐 Cofre de chaves. Mostra cada chave guardada (era ferramentas/meu-chat/js/87-cofre.js)
js/98-backup.js       ← Meu Chat — 90-backup.js: 💾 backup de tudo (conversas + memória + ajus (era ferramentas/meu-chat/js/90-backup.js)
js/98-ponte-lab.js    ← 🔬 Ponte com o Laboratório: quando o Meu Chat está DENTRO do Laboratór (era ferramentas/meu-chat/js/95-ponte-lab.js)
js/98-cofre-arquivo.js← 🔐 Arquivo de chaves do Maikon — o MESMO formato no Mini SK, no Meu Ch (era ferramentas/meu-chat/js/lib/cofre-arquivo.js)
js/98-guia-maikon.js  ← 🧭 Guia das ferramentas do Maikon — o MESMO texto em todos os apps (Mi (era ferramentas/meu-chat/js/lib/guia-maikon.js)
js/98-guia-versoes.js ← 🧭 Guia das VERSÕES — o que é cada app do Maikon, qual a versão atual, (era ferramentas/meu-chat/js/lib/guia-versoes.js)
js/98-nuvem-neon.js   ← 🐘 Nuvem pelo NEON (17/11) — usada pelo Meu Chat e pelo SK Jurídico HT (era ferramentas/meu-chat/js/lib/nuvem-neon.js)
js/98-base.js         ← Laboratório — 00-base.js: peças comuns (LB) (era js/00-base.js)
js/98-banco.js        ← Laboratório — 10-banco.js: os projetos guardados no aparelho (IndexedD (era js/10-banco.js)
js/98-importar.js     ← Laboratório — 20-importar.js: traz um projeto (.zip, .tar.gz, pasta, u (era js/20-importar.js)
js/98-analise.js      ← Laboratório — 30-analise.js: lê o projeto INTEIRO (vários arquivos ou  (era js/30-analise.js)
js/98-plano.js        ← Laboratório — 40-plano.js: o PLANO MACRO do projeto, em .md (para ler  (era js/40-plano.js)
js/98-comparar.js     ← Laboratório — 50-comparar.js: ⚖️ A (o que funciona) × B (o que não fun (era js/50-comparar.js)
js/98-ferramentas.js  ← Laboratório — 60-ferramentas.js: 🧰 AS SUAS FERRAMENTAS NUM LUGAR SÓ.  (era js/60-ferramentas.js)
js/98-ia.js           ← Laboratório — 70-ia.js: 🤖 IA — o MEU CHAT aqui dentro (chat livre, do (era js/70-ia.js)
js/98-memoria.js      ← Laboratório — 75-memoria.js: 📒 MEMÓRIA — o caderno de cada projeto (e (era js/75-memoria.js)
js/98-terminal.js     ← Laboratório — 80-terminal.js: 💻 TERMINAL DE VERDADE — com a MESMA lóg (era js/80-terminal.js)
js/98-lab-ponte.js    ← Laboratório — 90-lab-ponte.js: a "tomada" que deixa as ferramentas do  (era js/90-lab-ponte.js)
js/98-lab-base.js     ← 91-lab-base.js (veio do Laboratório antigo) — o que ele entende como " (era js/91-lab-base.js)
js/98-lab-mapa.js     ← js/12-lab-mapa.js (era js/92-lab-mapa.js)
js/98-lab-previa.js   ← js/13-lab-previa.js (era js/93-lab-previa.js)
js/98-lab-desmontar.js← js/18-lab-desmontar.js (era js/94-lab-desmontar.js)
js/98-fatiador.js     ← Laboratório — 95-fatiador.js: ✂️ FATIADOR INTELIGENTE Pega um arquivo  (era js/95-fatiador.js)
js/98-recuperar.js    ← Laboratório — 96-recuperar.js: ♻️ RECUPERADOR DE BACKUP Abre os backup (era js/96-recuperar.js)
js/98-brincar.js      ← Laboratório — 97-brincar.js: 🧸 BRINCAR (o laboratório de brinquedo, p (era js/97-brincar.js)
js/98-combinar.js     ← Laboratório — 98-combinar.js: 🧬 COMBINAR — pegar pedaços de códigos d (era js/98-combinar.js)
js/98-98w-desembrulhar.js← Laboratório — 98w-desembrulhar.js: 📦 DESEMBRULHAR — tira de volta os  (era js/98w-desembrulhar.js)
js/98-98x-raiox.js    ← Laboratório — 98x-raiox.js: 🔍 RAIO-X DE APK e de .EXE (e de zip de pr (era js/98x-raiox.js)
js/98-98x2-raiox-mais.js← Laboratório — 98x2-raiox-mais.js: 🔍 RAIO-X, parte 2 (17/11) — tirar i (era js/98x2-raiox-mais.js)
js/98-98y-grupos.js   ← Laboratório — 98y-grupos.js: 🧩 GRUPOS — seus códigos HTML trabalhando (era js/98y-grupos.js)
js/98-98z-navegar.js  ← Laboratório — 98z-navegar.js: barrinha NO TOPO (ao lado da versão) com (era js/98z-navegar.js)
js/98-juntar.js       ← -*- coding: utf-8 -*- (era kits/juntar.py)
js/98-kit-replit.js   ← !/usr/bin/env node (era kits/kit-replit.cjs)
js/98-organizar.js    ← -*- coding: utf-8 -*- (era kits/organizar.py)
js/98-ferramentas.js  ← Caça-Bug — 40-ferramentas.js Abre cada ferramenta (Cirurgião, Projeto  (era kits/receita-montar/js/40-ferramentas.js)
js/98-montar.js       ← -*- coding: utf-8 -*- (era kits/receita-montar/montar.py)
js/98-servir.js       ← -*- coding: utf-8 -*- (era kits/servir.py)
js/98-voz-francisco.js← !/usr/bin/env python3 -*- coding: utf-8 -*- (era kits/voz-francisco.py)
js/98-ai-code-studio.js← AI Code Studio — Título (era ferramentas/ai-code-studio.html)
js/98-arrumador.js    ← Arrumador de Backups — 🗃 Arrumador de Backups (era ferramentas/arrumador.html)
js/98-banco-neon.js   ← Banco de Dados (Neon) — 🗄 Banco de Dados (Neon) (era ferramentas/banco-neon.html)
js/98-colador.js      ← Colador de Links — 🔗 Colador de Links (era ferramentas/colador.html)
js/98-faxina.js       ← 🧹 Faxina de Repetidos — 🧹 Faxina de Repetidos (era ferramentas/faxina.html)
js/98-iara-suite.js   ← Iara Suite — Code Editor · APK Builder · Site Extractor — Olá, Mundo! (era ferramentas/iara-suite.html)
js/98-juntador.js     ← Juntador de Arquivos — 🧩 Juntador de Arquivos (era ferramentas/juntador.html)
js/98-colador.js      ← Colador de Links — 🔗 Colador de Links (era ferramentas/laboratorio2/ferramentas/colador.html)
js/98-meu-chat.js     ← Meu Chat (era ferramentas/laboratorio2/ferramentas/meu-chat/index.html)
js/98-laboratorio2.js ← 🔬 Laboratório 2 — 🔬 Laboratório 2 (era ferramentas/laboratorio2/index.html)
js/98-meu-chat.js     ← Meu Chat (era ferramentas/meu-chat/index.html)
js/98-montador.js     ← Montador Universal — 🧩 Montador Universal (era ferramentas/montador.html)
js/98-numerador.js    ← Numerador de Códigos — 🔢 Numerador de Códigos (era ferramentas/numerador.html)
js/98-picotador.js    ← Picotador de Memória e Backup — ✂️ Picotador de Memória e Backup (era ferramentas/picotador.html)
js/98-preparador.js   ← Preparador Universal — 🧰 Preparador Universal (era ferramentas/preparador.html)
js/98-projeto-lab.js  ← Projeto Lab (era ferramentas/projeto-lab.html)
js/98-replicador.js   ← Replicador de Projeto (era ferramentas/replicador.html)
js/98-inicio.js       ← Laboratório — 🔬 Laboratório (era index.html)
js/99-app.js          ← o último: monta a tela com o que embarcou
```

## 3. As partes, uma por uma

| # | Era | Vira | Tipo | O que faz | Usa |
|---|---|---|---|---|---|
| 1 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/00-base.js` | `js/10-base.js` | logica | Meu Chat — 00-base.js: peças comuns (MC) | — |
| 2 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/10-banco.js` | `js/15-banco.js` | logica | Meu Chat — 10-banco.js: onde tudo fica guardado (IndexedDB do aparelho — não some ao fecha | — |
| 3 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/12-nuvem.js` | `js/20-nuvem.js` | logica | Meu Chat — 12-nuvem.js · ☁️ NUVEM (Supabase) — 17/11 - O chat continua funcionando SEM int | — |
| 4 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/20-provedores.js` | `js/25-provedores.js` | logica | Meu Chat — 20-provedores.js: conversar com as IAs (Gemini, Groq, OpenRouter, OpenAI, DeepS | — |
| 5 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/30-memoria.js` | `js/30-memoria.js` | logica | Meu Chat — 30-memoria.js: 🧠 a memória que vai junto em TODA conversa. A IA guarda sozinha | — |
| 6 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/33-contextos.js` | `js/35-contextos.js` | logica | Meu Chat — 33-contextos.js: 📌 CONTEXTOS — "cartões" de assunto que você LIGA e DESLIGA. D | — |
| 7 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/34-guia.js` | `js/40-guia.js` | logica | 🧭 Painel do Guia (16/11): o que é cada app do Maikon, a versão atual e COMO USAR, passo a | — |
| 8 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/35-jeito.js` | `js/45-jeito.js` | logica | Meu Chat — 35-jeito.js: 🎭 O JEITO DE CADA IA. Para não ter "mudança drástica" quando troc | — |
| 9 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/40-voz.js` | `js/50-voz.js` | logica | Meu Chat — 40-voz.js: 🎤 falar (ditado) e 🔊 ouvir a resposta. 🔊 DOIS "motores" de voz (⚙ | — |
| 10 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/50-internet.js` | `js/55-internet.js` | logica | Meu Chat — 50-internet.js: 🌐 pesquisar e 🔗 ler links. - Gemini e Claude pesquisam sozinh | — |
| 11 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/60-previa.js` | `js/60-previa.js` | logica | Meu Chat — 60-previa.js: 👁 ver o código funcionando, na hora. - HTML: abre a página como  | — |
| 12 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/70-texto.js` | `js/65-texto.js` | logica | Meu Chat — 70-texto.js: mostra a resposta da IA bonitinha (negrito, listas, links, blocos  | — |
| 13 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/80-chat.js` | `js/70-chat.js` | logica | Meu Chat — 80-chat.js: a conversa (mensagens, fotos, mandar, parar, lista de conversas). C | — |
| 14 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/85-config.js` | `js/75-config.js` | logica | Meu Chat — 85-config.js: ⚙️ chaves das IAs, modelo, busca, voz, instruções, tema | — |
| 15 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/87-cofre.js` | `js/80-cofre.js` | logica | Meu Chat — 87-cofre.js: 🔐 Cofre de chaves. Mostra cada chave guardada (👁 ver, 📋 copiar) | — |
| 16 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/90-backup.js` | `js/85-backup.js` | logica | Meu Chat — 90-backup.js: 💾 backup de tudo (conversas + memória + ajustes) e restaurar SEM | — |
| 17 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/95-ponte-lab.js` | `js/90-ponte-lab.js` | logica | 🔬 Ponte com o Laboratório: quando o Meu Chat está DENTRO do Laboratório (aba 🤖 IA), o La | — |
| 18 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/99-app.js` | css/app.css | logica | Meu Chat — 99-app.js: liga tudo quando abre | — |
| 19 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/cofre-arquivo.js` | `js/91-cofre-arquivo.js` | logica | 🔐 Arquivo de chaves do Maikon — o MESMO formato no Mini SK, no Meu Chat e no que vier dep | — |
| 20 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/guia-maikon.js` | `js/92-guia-maikon.js` | logica | 🧭 Guia das ferramentas do Maikon — o MESMO texto em todos os apps (Mini SK, Meu Chat…). A | — |
| 21 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/guia-versoes.js` | `js/93-guia-versoes.js` | logica | 🧭 Guia das VERSÕES — o que é cada app do Maikon, qual a versão atual, e COMO USAR (passo  | — |
| 22 | `ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/nuvem-neon.js` | `js/94-nuvem-neon.js` | logica | 🐘 Nuvem pelo NEON (17/11) — usada pelo Meu Chat e pelo SK Jurídico HTML. Você cola o ende | — |
| 23 | `ferramentas/laboratorio2/ferramentas/meu-chat/voz-francisco.py` | `js/95-voz-francisco.js` | logica | !/usr/bin/env python3 -*- coding: utf-8 -*- | — |
| 24 | `ferramentas/laboratorio2/js/00-casca.js` | `js/96-casca.js` | logica | js/00-casca.js | — |
| 25 | `ferramentas/laboratorio2/js/02-importar.js` | `js/97-importar.js` | logica | js/02-importar.js | — |
| 26 | `ferramentas/laboratorio2/js/03-dependencias.js` | `js/98-dependencias.js` | logica | js/03-dependencias.js | ${url} |
| 27 | `ferramentas/laboratorio2/js/04-analisar.js` | `js/98-analisar.js` | logica | js/04-analisar.js | — |
| 28 | `ferramentas/laboratorio2/js/05-plano.js` | `js/98-plano.js` | logica | js/05-plano.js | — |
| 29 | `ferramentas/laboratorio2/js/05a-markdown.js` | `js/98-05a-markdown.js` | logica | js/05a-markdown.js | — |
| 30 | `ferramentas/laboratorio2/js/06-scripts.js` | `js/98-scripts.js` | logica | js/06-scripts.js | — |
| 31 | `ferramentas/laboratorio2/js/06b-scripts-fim.js` | `js/98-06b-scripts-fim.js` | logica | js/06b-scripts-fim.js | — |
| 32 | `ferramentas/laboratorio2/js/07-terminal.js` | `js/98-terminal.js` | logica | js/07-terminal.js | — |
| 33 | `ferramentas/laboratorio2/js/07a-busca-npm.js` | `js/98-07a-busca-npm.js` | logica | js/07a-busca-npm.js | — |
| 34 | `ferramentas/laboratorio2/js/08-exportar.js` | `js/98-exportar.js` | logica | js/08-exportar.js | — |
| 35 | `ferramentas/laboratorio2/js/09-integracao.js` | `js/98-integracao.js` | logica | js/09-integracao.js | — |
| 36 | `ferramentas/laboratorio2/js/10-celular.js` | `js/98-celular.js` | logica | js/10-celular.js | — |
| 37 | `ferramentas/laboratorio2/js/11-lab-base.js` | `js/98-lab-base.js` | logica | js/11-lab-base.js | — |
| 38 | `ferramentas/laboratorio2/js/12-lab-mapa.js` | `js/98-lab-mapa.js` | logica | js/12-lab-mapa.js | — |
| 39 | `ferramentas/laboratorio2/js/13-lab-previa.js` | `js/98-lab-previa.js` | logica | js/13-lab-previa.js | — |
| 40 | `ferramentas/laboratorio2/js/14-lab-pesquisa.js` | `js/98-lab-pesquisa.js` | logica | js/14-lab-pesquisa.js | — |
| 41 | `ferramentas/laboratorio2/js/15-lab-comparar.js` | `js/98-lab-comparar.js` | logica | js/15-lab-comparar.js | — |
| 42 | `ferramentas/laboratorio2/js/15a-tar.js` | `js/98-15a-tar.js` | logica | js/15a-tar.js | — |
| 43 | `ferramentas/laboratorio2/js/16-lab-ferramentas.js` | `js/98-lab-ferramentas.js` | logica | js/16-lab-ferramentas.js | — |
| 44 | `ferramentas/laboratorio2/js/17-lab-termux.js` | `js/98-lab-termux.js` | logica | LABORATÓRIO 2 — 17-lab-termux.js · 💻 TERMINAL DE VERDADE (16/11) Trocado pelo terminal AT | — |
| 45 | `ferramentas/laboratorio2/js/18-lab-desmontar.js` | `js/98-lab-desmontar.js` | logica | js/18-lab-desmontar.js | — |
| 46 | `ferramentas/laboratorio2/js/19-embutido.js` | `js/98-embutido.js` | logica | — | — |
| 47 | `ferramentas/meu-chat/js/00-base.js` | `js/98-base.js` | logica | Meu Chat — 00-base.js: peças comuns (MC) | — |
| 48 | `ferramentas/meu-chat/js/10-banco.js` | `js/98-banco.js` | logica | Meu Chat — 10-banco.js: onde tudo fica guardado (IndexedDB do aparelho — não some ao fecha | — |
| 49 | `ferramentas/meu-chat/js/12-nuvem.js` | `js/98-nuvem.js` | logica | Meu Chat — 12-nuvem.js · ☁️ NUVEM (Supabase) — 17/11 - O chat continua funcionando SEM int | — |
| 50 | `ferramentas/meu-chat/js/20-provedores.js` | `js/98-provedores.js` | logica | Meu Chat — 20-provedores.js: conversar com as IAs (Gemini, Groq, OpenRouter, OpenAI, DeepS | — |
| 51 | `ferramentas/meu-chat/js/30-memoria.js` | `js/98-memoria.js` | logica | Meu Chat — 30-memoria.js: 🧠 a memória que vai junto em TODA conversa. A IA guarda sozinha | — |
| 52 | `ferramentas/meu-chat/js/33-contextos.js` | `js/98-contextos.js` | logica | Meu Chat — 33-contextos.js: 📌 CONTEXTOS — "cartões" de assunto que você LIGA e DESLIGA. D | — |
| 53 | `ferramentas/meu-chat/js/34-guia.js` | `js/98-guia.js` | logica | 🧭 Painel do Guia (16/11): o que é cada app do Maikon, a versão atual e COMO USAR, passo a | — |
| 54 | `ferramentas/meu-chat/js/35-jeito.js` | `js/98-jeito.js` | logica | Meu Chat — 35-jeito.js: 🎭 O JEITO DE CADA IA. Para não ter "mudança drástica" quando troc | — |
| 55 | `ferramentas/meu-chat/js/40-voz.js` | `js/98-voz.js` | logica | Meu Chat — 40-voz.js: 🎤 falar (ditado) e 🔊 ouvir a resposta. 🔊 DOIS "motores" de voz (⚙ | — |
| 56 | `ferramentas/meu-chat/js/50-internet.js` | `js/98-internet.js` | logica | Meu Chat — 50-internet.js: 🌐 pesquisar e 🔗 ler links. - Gemini e Claude pesquisam sozinh | — |
| 57 | `ferramentas/meu-chat/js/60-previa.js` | `js/98-previa.js` | logica | Meu Chat — 60-previa.js: 👁 ver o código funcionando, na hora. - HTML: abre a página como  | — |
| 58 | `ferramentas/meu-chat/js/70-texto.js` | `js/98-texto.js` | logica | Meu Chat — 70-texto.js: mostra a resposta da IA bonitinha (negrito, listas, links, blocos  | — |
| 59 | `ferramentas/meu-chat/js/80-chat.js` | `js/98-chat.js` | logica | Meu Chat — 80-chat.js: a conversa (mensagens, fotos, mandar, parar, lista de conversas). C | — |
| 60 | `ferramentas/meu-chat/js/85-config.js` | `js/98-config.js` | logica | Meu Chat — 85-config.js: ⚙️ chaves das IAs, modelo, busca, voz, instruções, tema | — |
| 61 | `ferramentas/meu-chat/js/87-cofre.js` | `js/98-cofre.js` | logica | Meu Chat — 87-cofre.js: 🔐 Cofre de chaves. Mostra cada chave guardada (👁 ver, 📋 copiar) | — |
| 62 | `ferramentas/meu-chat/js/90-backup.js` | `js/98-backup.js` | logica | Meu Chat — 90-backup.js: 💾 backup de tudo (conversas + memória + ajustes) e restaurar SEM | — |
| 63 | `ferramentas/meu-chat/js/95-ponte-lab.js` | `js/98-ponte-lab.js` | logica | 🔬 Ponte com o Laboratório: quando o Meu Chat está DENTRO do Laboratório (aba 🤖 IA), o La | — |
| 64 | `ferramentas/meu-chat/js/99-app.js` | css/app.css | logica | Meu Chat — 99-app.js: liga tudo quando abre | — |
| 65 | `ferramentas/meu-chat/js/lib/cofre-arquivo.js` | `js/98-cofre-arquivo.js` | logica | 🔐 Arquivo de chaves do Maikon — o MESMO formato no Mini SK, no Meu Chat e no que vier dep | — |
| 66 | `ferramentas/meu-chat/js/lib/guia-maikon.js` | `js/98-guia-maikon.js` | logica | 🧭 Guia das ferramentas do Maikon — o MESMO texto em todos os apps (Mini SK, Meu Chat…). A | — |
| 67 | `ferramentas/meu-chat/js/lib/guia-versoes.js` | `js/98-guia-versoes.js` | logica | 🧭 Guia das VERSÕES — o que é cada app do Maikon, qual a versão atual, e COMO USAR (passo  | — |
| 68 | `ferramentas/meu-chat/js/lib/nuvem-neon.js` | `js/98-nuvem-neon.js` | logica | 🐘 Nuvem pelo NEON (17/11) — usada pelo Meu Chat e pelo SK Jurídico HTML. Você cola o ende | — |
| 69 | `js/00-base.js` | `js/98-base.js` | logica | Laboratório — 00-base.js: peças comuns (LB) | — |
| 70 | `js/10-banco.js` | `js/98-banco.js` | logica | Laboratório — 10-banco.js: os projetos guardados no aparelho (IndexedDB), cada um SEPARADO | — |
| 71 | `js/20-importar.js` | `js/98-importar.js` | logica | Laboratório — 20-importar.js: traz um projeto (.zip, .tar.gz, pasta, um HTML só, vários ar | — |
| 72 | `js/30-analise.js` | `js/98-analise.js` | logica | Laboratório — 30-analise.js: lê o projeto INTEIRO (vários arquivos ou um HTML só) e descob | — |
| 73 | `js/40-plano.js` | `js/98-plano.js` | logica | Laboratório — 40-plano.js: o PLANO MACRO do projeto, em .md (para ler aqui e para levar pa | — |
| 74 | `js/50-comparar.js` | `js/98-comparar.js` | logica | Laboratório — 50-comparar.js: ⚖️ A (o que funciona) × B (o que não funciona), lado a lado. | — |
| 75 | `js/60-ferramentas.js` | `js/98-ferramentas.js` | logica | Laboratório — 60-ferramentas.js: 🧰 AS SUAS FERRAMENTAS NUM LUGAR SÓ. Cada ferramenta é um | — |
| 76 | `js/70-ia.js` | `js/98-ia.js` | logica | Laboratório — 70-ia.js: 🤖 IA — o MEU CHAT aqui dentro (chat livre, do jeito da última ver | — |
| 77 | `js/75-memoria.js` | `js/98-memoria.js` | logica | Laboratório — 75-memoria.js: 📒 MEMÓRIA — o caderno de cada projeto (e um caderno geral).  | — |
| 78 | `js/80-terminal.js` | `js/98-terminal.js` | logica | Laboratório — 80-terminal.js: 💻 TERMINAL DE VERDADE — com a MESMA lógica do Mini SK (a qu | — |
| 79 | `js/90-lab-ponte.js` | `js/98-lab-ponte.js` | logica | Laboratório — 90-lab-ponte.js: a "tomada" que deixa as ferramentas do Laboratório ANTIGO ( | — |
| 80 | `js/91-lab-base.js` | `js/98-lab-base.js` | logica | 91-lab-base.js (veio do Laboratório antigo) — o que ele entende como "um arquivo chama o o | — |
| 81 | `js/92-lab-mapa.js` | `js/98-lab-mapa.js` | logica | js/12-lab-mapa.js | — |
| 82 | `js/93-lab-previa.js` | `js/98-lab-previa.js` | logica | js/13-lab-previa.js | — |
| 83 | `js/94-lab-desmontar.js` | `js/98-lab-desmontar.js` | logica | js/18-lab-desmontar.js | — |
| 84 | `js/95-fatiador.js` | `js/98-fatiador.js` | logica | Laboratório — 95-fatiador.js: ✂️ FATIADOR INTELIGENTE Pega um arquivo grande (HTML, JS, TS | — |
| 85 | `js/96-recuperar.js` | `js/98-recuperar.js` | logica | Laboratório — 96-recuperar.js: ♻️ RECUPERADOR DE BACKUP Abre os backups .json dos seus app | — |
| 86 | `js/97-brincar.js` | `js/98-brincar.js` | logica | Laboratório — 97-brincar.js: 🧸 BRINCAR (o laboratório de brinquedo, para APRENDER) 📥 Cai | — |
| 87 | `js/98-combinar.js` | `js/98-combinar.js` | logica | Laboratório — 98-combinar.js: 🧬 COMBINAR — pegar pedaços de códigos diferentes e montar u | estilos.css, pecas.js |
| 88 | `js/98w-desembrulhar.js` | `js/98-98w-desembrulhar.js` | logica | Laboratório — 98w-desembrulhar.js: 📦 DESEMBRULHAR — tira de volta os códigos HTML que um  | — |
| 89 | `js/98x-raiox.js` | `js/98-98x-raiox.js` | logica | Laboratório — 98x-raiox.js: 🔍 RAIO-X DE APK e de .EXE (e de zip de projeto) Abre um .apk  | — |
| 90 | `js/98x2-raiox-mais.js` | `js/98-98x2-raiox-mais.js` | logica | Laboratório — 98x2-raiox-mais.js: 🔍 RAIO-X, parte 2 (17/11) — tirar informação de BUILD e | — |
| 91 | `js/98y-grupos.js` | `js/98-98y-grupos.js` | logica | Laboratório — 98y-grupos.js: 🧩 GRUPOS — seus códigos HTML trabalhando JUNTOS (a ideia do  | — |
| 92 | `js/98z-navegar.js` | `js/98-98z-navegar.js` | logica | Laboratório — 98z-navegar.js: barrinha NO TOPO (ao lado da versão) com ⬅ voltar · ➡ avança | — |
| 93 | `js/99-app.js` | css/app.css | logica | Laboratório — 99-app.js: liga as telas. O projeto escolhido lá em cima vale para TODAS as  | — |
| 94 | `kits/juntar.py` | `js/98-juntar.js` | logica | -*- coding: utf-8 -*- | x.css, x.js |
| 95 | `kits/kit-replit.cjs` | `js/98-kit-replit.js` | logica | !/usr/bin/env node | — |
| 96 | `kits/organizar.py` | `js/98-organizar.js` | logica | -*- coding: utf-8 -*- | — |
| 97 | `kits/receita-montar/js/40-ferramentas.js` | `js/98-ferramentas.js` | logica | Caça-Bug — 40-ferramentas.js Abre cada ferramenta (Cirurgião, Projeto Lab, Triagem, Perito | — |
| 98 | `kits/receita-montar/montar.py` | `js/98-montar.js` | logica | -*- coding: utf-8 -*- | — |
| 99 | `kits/servir.py` | `js/98-servir.js` | logica | -*- coding: utf-8 -*- | — |
| 100 | `kits/voz-francisco.py` | `js/98-voz-francisco.js` | logica | !/usr/bin/env python3 -*- coding: utf-8 -*- | — |
| 101 | `ferramentas/ai-code-studio.html` | `js/98-ai-code-studio.js` | tela | AI Code Studio — Título | guia-maikon.js, jszip.min.js |
| 102 | `ferramentas/arrumador.html` | `js/98-arrumador.js` | tela | Arrumador de Backups — 🗃 Arrumador de Backups | — |
| 103 | `ferramentas/banco-neon.html` | `js/98-banco-neon.js` | tela | Banco de Dados (Neon) — 🗄 Banco de Dados (Neon) | — |
| 104 | `ferramentas/colador.html` | `js/98-colador.js` | tela | Colador de Links — 🔗 Colador de Links | manifest.json |
| 105 | `ferramentas/faxina.html` | `js/98-faxina.js` | tela | 🧹 Faxina de Repetidos — 🧹 Faxina de Repetidos | — |
| 106 | `ferramentas/iara-suite.html` | `js/98-iara-suite.js` | tela | Iara Suite — Code Editor · APK Builder · Site Extractor — Olá, Mundo! | jszip.min.js |
| 107 | `ferramentas/juntador.html` | `js/98-juntador.js` | tela | Juntador de Arquivos — 🧩 Juntador de Arquivos | — |
| 108 | `ferramentas/laboratorio2/ferramentas/colador.html` | `js/98-colador.js` | tela | Colador de Links — 🔗 Colador de Links | manifest.json |
| 109 | `ferramentas/laboratorio2/ferramentas/meu-chat/css/app.css` | css/app.css | estilo | — | — |
| 110 | `ferramentas/laboratorio2/ferramentas/meu-chat/index.html` | `js/98-meu-chat.js` | tela | Meu Chat | manifest.json, icon-192.png, app.css, 00-base.js |
| 111 | `ferramentas/laboratorio2/index.html` | `js/98-laboratorio2.js` | tela | 🔬 Laboratório 2 — 🔬 Laboratório 2 | jszip.min.js, pako.min.js, acorn.min.js, 00-casca.js |
| 112 | `ferramentas/meu-chat/css/app.css` | css/app.css | estilo | — | — |
| 113 | `ferramentas/meu-chat/index.html` | `js/98-meu-chat.js` | tela | Meu Chat | manifest.json, icon-192.png, app.css, 00-base.js |
| 114 | `ferramentas/montador.html` | `js/98-montador.js` | tela | Montador Universal — 🧩 Montador Universal | — |
| 115 | `ferramentas/numerador.html` | `js/98-numerador.js` | tela | Numerador de Códigos — 🔢 Numerador de Códigos | — |
| 116 | `ferramentas/picotador.html` | `js/98-picotador.js` | tela | Picotador de Memória e Backup — ✂️ Picotador de Memória e Backup | — |
| 117 | `ferramentas/preparador.html` | `js/98-preparador.js` | tela | Preparador Universal — 🧰 Preparador Universal | package.json |
| 118 | `ferramentas/projeto-lab.html` | `js/98-projeto-lab.js` | tela | Projeto Lab | — |
| 119 | `ferramentas/replicador.html` | `js/98-replicador.js` | tela | Replicador de Projeto | jszip.min.js |
| 120 | `css/app.css` | css/app.css | estilo | — | — |
| 121 | `css/extra.css` | css/app.css | estilo | Laboratório 31/10 — abas novas: 🤖 IA, 📒 Memória, 💻 Terminal, 🧰 Ferramentas | — |
| 122 | `css/antigo.css` | css/app.css | estilo | Visual das ferramentas que vieram do Laboratório antigo (Desmontar, Mapa, Prévia), ligado  | — |
| 123 | `index.html` | `js/98-inicio.js` | tela | Laboratório — 🔬 Laboratório | app.css, extra.css, antigo.css, jszip.min.js |

## 4. Montar passo a passo (cada bloco é um pedido pronto: 📋 Copiar → colar na IA)

### Passo 0 — combinar as regras com a IA

```text
Vamos recriar o app "Meu Chat" como HTML MODULAR, que abre pelo index.html, sem servidor e sem nada da Replit.
Regras: (1) index.html chama os arquivos js/ na ordem, antes do </body>; (2) js/00-core.js cria window.APP com APP.registrar(modulo), APP.guardar(chave, valor) em IndexedDB/localStorage e APP.avisar(texto); (3) cada arquivo js/NN-nome.js cuida de UM assunto, começa com (function (APP) { e termina com })(window.APP); (4) js/99-app.js vem por último e monta a tela com os módulos registrados; (5) textos em português do Brasil.
Vou pedir UM arquivo por vez. Responda só com o arquivo completo, sem cortar nada. Primeiro: crie index.html, css/app.css e js/00-core.js.
```

### Passo 1 — `js/10-base.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/00-base.js`, 43 linhas)

```text
Crie js/10-base.js. Ele faz: Meu Chat — 00-base.js: peças comuns (MC).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 2 — `js/15-banco.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/10-banco.js`, 26 linhas)

```text
Crie js/15-banco.js. Ele faz: Meu Chat — 10-banco.js: onde tudo fica guardado (IndexedDB do aparelho — não some ao fechar).
No app original ele tinha estas funções/partes: abrir, req, loja.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 3 — `js/20-nuvem.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/12-nuvem.js`, 278 linhas)

```text
Crie js/20-nuvem.js. Ele faz: Meu Chat — 12-nuvem.js · ☁️ NUVEM (Supabase) — 17/11 - O chat continua funcionando SEM internet: tudo fica no aparelho (IndexedDB). - Com a nuvem ligada, ele COPIA para o Supabase e traz de volta em qualquer aparelho (celular, PC, outro celular) entrando com o mesmo e-mail e senha.
No app original ele tinha estas funções/partes: cfg, sessao, ehNeon, neonConn, logado, ligada, auth, traduzir, guardarSessao, token, rest, mod, marcar, ganchos, marcarPrefs, prefsViajam, semFotos, linha.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 4 — `js/25-provedores.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/20-provedores.js`, 240 linhas)

```text
Crie js/25-provedores.js. Ele faz: Meu Chat — 20-provedores.js: conversar com as IAs (Gemini, Groq, OpenRouter, OpenAI, DeepSeek, Claude). - Várias chaves; quando uma acaba (limite/cota), passa sozinho para a próxima ("revezar"). - Busca a lista de modelos de verdade na hora de testar a chave (nada de nome velho chumbado). - As chaves ficam SÓ neste aparelho.
No app original ele tinha estas funções/partes: detectar, procurarOllama, chaves, salvarChaves, pontoGemini, listarModelos, pontoLivre, geracao, modeloDe, testarChave, erroLegivel, corsAviso, ehLimite, cabAnthropic, lerSSE, pedir, parcial, conversar.
Ele chamava estes endereços: http://127.0.0.1:11434/api/tags. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 5 — `js/30-memoria.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/30-memoria.js`, 77 linhas)

```text
Crie js/30-memoria.js. Ele faz: Meu Chat — 30-memoria.js: 🧠 a memória que vai junto em TODA conversa. A IA guarda sozinha o que for importante escrevendo [[lembrar: …]] no fim da resposta (o app tira isso do texto, guarda e mostra "🧠 guardei"). [[esquecer: …]] apaga.
No app original ele tinha estas funções/partes: texto, salvar, lembrar, esquecer, aplicarMarcas, guiaParaPergunta, tamanhoTexto, sistema, abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 6 — `js/35-contextos.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/33-contextos.js`, 178 linhas)

```text
Crie js/35-contextos.js. Ele faz: Meu Chat — 33-contextos.js: 📌 CONTEXTOS — "cartões" de assunto que você LIGA e DESLIGA. Diferente da 🧠 memória (que vale para sempre e vai em tudo): um contexto é o resumo de um assunto ou de uma conversa (por exemplo, o que você vinha fazendo com o Claude), para a IA não começar do zero. Ligado = vai junto em toda conversa. Desligado = fica guardado, sem gastar.
No app original ele tinha estas funções/partes: lista, gravar, semear, esconder, tokens, ligados, texto, pintarChip, pintar, novo, clique.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 7 — `js/40-guia.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/34-guia.js`, 39 linhas)

```text
Crie js/40-guia.js. Ele faz: 🧭 Painel do Guia (16/11): o que é cada app do Maikon, a versão atual e COMO USAR, passo a passo. 🔊 lê em voz alta (voz Francisco ou a do aparelho) · 🤖 Perguntar: o chat explica aquele app.
No app original ele tinha estas funções/partes: textoDe, pintar, iniciar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 8 — `js/45-jeito.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/35-jeito.js`, 56 linhas)

```text
Crie js/45-jeito.js. Ele faz: Meu Chat — 35-jeito.js: 🎭 O JEITO DE CADA IA. Para não ter "mudança drástica" quando troca de IA: um jeito de conversar que vale para TODAS (parceiro, calmo, honesto) e, se quiser, um jeito só de uma (ex.: o Perplexity como pesquisador jurídico que sempre traz as fontes). Tudo editável em ⚙️ → 🎭 Jeito de cada IA.
No app original ele tinha estas funções/partes: geral, deUma, texto, pintar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 9 — `js/50-voz.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/40-voz.js`, 227 linhas)

```text
Crie js/50-voz.js. Ele faz: Meu Chat — 40-voz.js: 🎤 falar (ditado) e 🔊 ouvir a resposta. 🔊 DOIS "motores" de voz (⚙️ → Voz): - 📱 "Voz do aparelho" (o padrão): funciona com QUALQUER IA (Gemini, Groq, Claude, Ollama…), grátis e sem limite. Você escolhe a voz (as ⭐ são as naturais), a velocidade e o tom.
No app original ele tinha estas funções/partes: podeOuvir, ouvir, parar, marcar, paraFala, pedacos, noPC, motor, temAndroid, temNavegador, natural, vozesAparelho, cfgVoz, falarFrase, enfileirar, verificarFim, pararAparelho, fluxo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 10 — `js/55-internet.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/50-internet.js`, 58 linhas)

```text
Crie js/55-internet.js. Ele faz: Meu Chat — 50-internet.js: 🌐 pesquisar e 🔗 ler links. - Gemini e Claude pesquisam sozinhos (a busca vem embutida neles). - As outras IAs: usa a SUA chave de busca (Serper, Tavily ou Brave), se tiver, e manda os resultados junto. - Link na mensagem: o app lê a página (pelo leitor r.jina.ai, grátis) e manda o texto para a IA.
No app original ele tinha estas funções/partes: buscar, lerLink, preparar.
Ele chamava estes endereços: https://google.serper.dev/search, https://api.tavily.com/search, https://api.search.brave.com/res/v1/web/search?count=8&country=BR&search_lang=pt-br&q=, https://r.jina.ai/. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 11 — `js/60-previa.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/60-previa.js`, 76 linhas)

```text
Crie js/60-previa.js. Ele faz: Meu Chat — 60-previa.js: 👁 ver o código funcionando, na hora. - HTML: abre a página como ela é. - TSX / JSX (React): monta com React + Babel + Tailwind (pela internet) e mostra o componente. Os erros aparecem embaixo, em vermelho.
No app original ele tinha estas funções/partes: paginaHTML, paginaReact, falha, req, App, tipoDe, abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 12 — `js/65-texto.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/70-texto.js`, 45 linhas)

```text
Crie js/65-texto.js. Ele faz: Meu Chat — 70-texto.js: mostra a resposta da IA bonitinha (negrito, listas, links, blocos de código com 📋 copiar, ⤓ baixar e 👁 ver funcionando).
No app original ele tinha estas funções/partes: inline, render, ligar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 13 — `js/70-chat.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/80-chat.js`, 252 linhas)

```text
Crie js/70-chat.js. Ele faz: Meu Chat — 80-chat.js: a conversa (mensagens, fotos, mandar, parar, lista de conversas). Cada conversa fica guardada no aparelho. Vai para a IA: a memória + as últimas mensagens.
No app original ele tinha estas funções/partes: nova, abrirConversa, guardar, reduzir, anexar, pintarAnexos, htmlMsg, dedup, hora, pintar, mandar, responder, depois, comparar, juntar, tela, escolherComparar, resumirSePrecisar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 14 — `js/75-config.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/85-config.js`, 115 linhas)

```text
Crie js/75-config.js. Ele faz: Meu Chat — 85-config.js: ⚙️ chaves das IAs, modelo, busca, voz, instruções, tema.
No app original ele tinha estas funções/partes: opcoesVoz, pintar, clique, mudou, aplicarTema, abrir.
Ele chamava estes endereços: voz-francisco.py. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 15 — `js/80-cofre.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/87-cofre.js`, 94 linhas)

```text
Crie js/80-cofre.js. Ele faz: Meu Chat — 87-cofre.js: 🔐 Cofre de chaves. Mostra cada chave guardada (👁 ver, 📋 copiar) e leva SÓ as chaves para outro app/aparelho num arquivo trancado com senha — o mesmo arquivo do Mini SK (js/lib/cofre-arquivo.js).
No app original ele tinha estas funções/partes: todas, pintar, status, conteudo, baixar, trazer, selarTexto, trazerTexto.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 16 — `js/85-backup.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/90-backup.js`, 44 linhas)

```text
Crie js/85-backup.js. Ele faz: Meu Chat — 90-backup.js: 💾 backup de tudo (conversas + memória + ajustes) e restaurar SEM APAGAR NADA.
No app original ele tinha estas funções/partes: gerar, baixar, restaurar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 17 — `js/90-ponte-lab.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/95-ponte-lab.js`, 20 linhas)

```text
Crie js/90-ponte-lab.js. Ele faz: 🔬 Ponte com o Laboratório: quando o Meu Chat está DENTRO do Laboratório (aba 🤖 IA), o Laboratório pode mandar texto para a caixa de escrever (o plano do projeto, a memória, a comparação A × B). Só aceita mensagens da própria página (mesmo endereço).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 18 — `js/91-cofre-arquivo.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/cofre-arquivo.js`, 61 linhas)

```text
Crie js/91-cofre-arquivo.js. Ele faz: 🔐 Arquivo de chaves do Maikon — o MESMO formato no Mini SK, no Meu Chat e no que vier depois. Guarda SÓ as chaves (IA, GitHub, Expo, pesquisa e "Minhas chaves"), trancadas com uma senha sua (AES-GCM 256 + PBKDF2 com 250 mil voltas — sem a senha, o arquivo não abre). Assim dá para levar as chaves de um app/aparelho para outro sem passar pelo WhatsApp.
No app original ele tinha estas funções/partes: b64, deB64, chaveDaSenha, normal, selar, abrir, contar, mascara.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 19 — `js/92-guia-maikon.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/guia-maikon.js`, 118 linhas)

```text
Crie js/92-guia-maikon.js. Ele faz: 🧭 Guia das ferramentas do Maikon — o MESMO texto em todos os apps (Mini SK, Meu Chat…). A IA de cada app lê isto sozinha: assim ela já sabe o que ele tem, para que serve cada coisa, e quando é melhor mandar para outra ferramenta ou "levar para o Claude". Para atualizar: troque este arquivo nos apps (o Claude manda a versão nova junto).
No app original ele tinha estas funções/partes: resumoParaClaude, esconder.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 20 — `js/93-guia-versoes.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/guia-versoes.js`, 163 linhas)

```text
Crie js/93-guia-versoes.js. Ele faz: 🧭 Guia das VERSÕES — o que é cada app do Maikon, qual a versão atual, e COMO USAR (passo a passo). Uma fonte só: o painel 🧭 do Meu Chat mostra isto para ele ler, e a IA recebe o mesmo texto (junto do guia-maikon.js) para saber explicar. Atualizado pelo Claude a cada versão nova.
No app original ele tinha estas funções/partes: texto.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 21 — `js/94-nuvem-neon.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/js/lib/nuvem-neon.js`, 60 linhas)

```text
Crie js/94-nuvem-neon.js. Ele faz: 🐘 Nuvem pelo NEON (17/11) — usada pelo Meu Chat e pelo SK Jurídico HTML. Você cola o endereço do banco (a "connection string" postgresql://…) e pronto: o app cria a tabela SOZINHO (não precisa rodar nada em inglês no site do Neon). ⚠ Esse endereço tem a SENHA do banco: fica só no seu aparelho (como uma chave de IA),.
No app original ele tinha estas funções/partes: traduzir, preparar, upsert, listar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 22 — `js/95-voz-francisco.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/voz-francisco.py`, 134 linhas)

```text
Crie js/95-voz-francisco.js. Ele faz: !/usr/bin/env python3 -*- coding: utf-8 -*-.
No app original ele tinha estas funções/partes: _listar, _falar, Voz, _cabecalhos, do_OPTIONS, _json, _pedido, do_GET, do_POST, _tratar, log_message.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 23 — `js/96-casca.js` (era `ferramentas/laboratorio2/js/00-casca.js`, 328 linhas)

```text
Crie js/96-casca.js. Ele faz: js/00-casca.js.
No app original ele tinha estas funções/partes: Shell, triggerAutoSave, restoreSession, navigate, openTab, activateTab, closeTab, renderTabs, toast, openModal, closeModal, updateStatusBar, updateBadges, updateSidebarInfo, startClock, tick, checkPreviousSession, setState.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 24 — `js/97-importar.js` (era `ferramentas/laboratorio2/js/02-importar.js`, 746 linhas)

```text
Crie js/97-importar.js. Ele faz: js/02-importar.js.
No app original ele tinha estas funções/partes: loadLibs, Importer, getIcon, isTextFile, formatSize, showProgress, logProgress, hideProgress, initDropZone, openFolderPicker, openFilePicker, processFolderFiles, processFiles, processZip, processTar, parseTar, readTarString, processGz.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 25 — `js/98-dependencias.js` (era `ferramentas/laboratorio2/js/03-dependencias.js`, 733 linhas)

```text
Crie js/98-dependencias.js. Ele faz: js/03-dependencias.js.
No app original ele tinha estas funções/partes: DepsAnalyzer, translateDesc, classifyDep, getCDNTag, hasCDN, analyze, addDep, renderSummary, setText, renderPkgTabs, setPkg, setFilter, filterDeps, renderDeps, renderDepCard, labelRelevance, showToolbar, showMonorepoBanner.
Ele chamava estes endereços: https://registry.npmjs.org/${dep.name}/latest, https://registry.npmjs.org/${name}/latest. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 26 — `js/98-analisar.js` (era `ferramentas/laboratorio2/js/04-analisar.js`, 816 linhas)

```text
Crie js/98-analisar.js. Ele faz: js/04-analisar.js.
No app original ele tinha estas funções/partes: CodeAnalyzer, analyze, detectFrameworks, detectBugs, detectConsoleLogs, detectRoutes, buildStructureMap, renderSummary, setText, renderFrameworks, renderBugs, labelBugType, setBugFilter, renderConsoleLogs, renderRoutes, renderRoutesPanel, routeCardHTML, setRouteFilter.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 27 — `js/98-plano.js` (era `ferramentas/laboratorio2/js/05-plano.js`, 717 linhas)

```text
Crie js/98-plano.js. Ele faz: js/05-plano.js.
No app original ele tinha estas funções/partes: Planner, setPlanType, toggleSection, setProgress, hideProgress, tick, generate, genOverview, genTech, genStructure, genDeps, row, genRoutes, genBugs, genModules, renderModulesMD, genSteps, genSetupScripts.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 28 — `js/98-05a-markdown.js` (era `ferramentas/laboratorio2/js/05a-markdown.js`, 70 linhas)

```text
Crie js/98-05a-markdown.js. Ele faz: js/05a-markdown.js.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 29 — `js/98-scripts.js` (era `ferramentas/laboratorio2/js/06-scripts.js`, 752 linhas)

```text
Crie js/98-scripts.js. Ele faz: js/06-scripts.js.
No app original ele tinha estas funções/partes: ScriptGen, toggleOpt, setTab, generate, collectDirs, collectKeyFiles, genBAT, genSH, genPS1, genMakefile, dirs_for_make, buildPackageJSON, buildGitignore, buildEnvExample, renderScript, highlightScript.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 30 — `js/98-06b-scripts-fim.js` (era `ferramentas/laboratorio2/js/06b-scripts-fim.js`, 188 linhas)

```text
Crie js/98-06b-scripts-fim.js. Ele faz: js/06b-scripts-fim.js.
No app original ele tinha estas funções/partes: patchScriptGen, highlightScript, copyScript, downloadBAT, downloadSH, downloadPS1, downloadMakefile, downloadAll, _dl.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 31 — `js/98-terminal.js` (era `ferramentas/laboratorio2/js/07-terminal.js`, 784 linhas)

```text
Crie js/98-terminal.js. Ele faz: js/07-terminal.js.
No app original ele tinha estas funções/partes: Terminal, initEnv, handleKey, runInput, runCmd, cmdHelp, cmdClear, cmdLs, cmdPwd, cmdCd, cmdCat, cmdEcho, cmdNode, cmdNpm, cmdNpx, cmdGit, cmdEnv, cmdWhoami.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 32 — `js/98-07a-busca-npm.js` (era `ferramentas/laboratorio2/js/07a-busca-npm.js`, 168 linhas)

```text
Crie js/98-07a-busca-npm.js. Ele faz: js/07a-busca-npm.js.
No app original ele tinha estas funções/partes: NpmSearch, search, renderResults, translateDesc, install, setupLiveSearch.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 33 — `js/98-exportar.js` (era `ferramentas/laboratorio2/js/08-exportar.js`, 774 linhas)

```text
Crie js/98-exportar.js. Ele faz: js/08-exportar.js.
No app original ele tinha estas funções/partes: Exporter, updateSummary, setProgress, hideProgress, tick, addHistory, renderHistory, exportPlan, copyPlan, exportBugs, copyBugs, exportDeps, exportDepsJSON, copyDeps, exportRoutes, exportRoutesJSON, copyRoutes, exportStructure.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 34 — `js/98-integracao.js` (era `ferramentas/laboratorio2/js/09-integracao.js`, 653 linhas)

```text
Crie js/98-integracao.js. Ele faz: js/09-integracao.js.
No app original ele tinha estas funções/partes: Integration, init, updateClock, updateStatusBar, setupKeyboardShortcuts, setupGlobalDrop, showDropOverlay, hideDropOverlay, setupStateWatcher, onStateChange, markFlowDone, updateWelcomeFlow, updateBugBadge, patchShellToast, showToast, closeToast, patchShellBadges, patchShellNavigate.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 35 — `js/98-celular.js` (era `ferramentas/laboratorio2/js/10-celular.js`, 20 linhas)

```text
Crie js/98-celular.js. Ele faz: js/10-celular.js.
No app original ele tinha estas funções/partes: celular, alternar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 36 — `js/98-lab-base.js` (era `ferramentas/laboratorio2/js/11-lab-base.js`, 149 linhas)

```text
Crie js/98-lab-base.js. Ele faz: js/11-lab-base.js.
No app original ele tinha estas funções/partes: ehBinario, arquivos, binarios, lista, tipo, pasta, normalizar, raizComum, resolver, raizDoArquivo, resolverApelido, achar, tem, nomePacote, referencias, add, refsJS, mapa.
O original usava as bibliotecas x: em HTML puro, use a versão de CDN (ou faça sem ela, se for simples).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 37 — `js/98-lab-mapa.js` (era `ferramentas/laboratorio2/js/12-lab-mapa.js`, 148 linhas)

```text
Crie js/98-lab-mapa.js. Ele faz: js/12-lab-mapa.js.
No app original ele tinha estas funções/partes: tela, listar, detalhe, link, arvore, extrair, mermaid, relatorio, verCodigo, desmontar, previa, pesquisar, ver.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 38 — `js/98-lab-previa.js` (era `ferramentas/laboratorio2/js/13-lab-previa.js`, 288 linhas)

```text
Crie js/98-lab-previa.js. Ele faz: js/13-lab-previa.js.
No app original ele tinha estas funções/partes: pegarConversor, temJSX, urlPacote, blobURL, urlBinario, urlDe, prepararJS, reescreverImports, ehTailwindCSS, prepararCSS, montarPagina, candidatos, tela, listarExtras, mostrarLog, mostrarConsole, rodar, rodarColado.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 39 — `js/98-lab-pesquisa.js` (era `ferramentas/laboratorio2/js/14-lab-pesquisa.js`, 160 linhas)

```text
Crie js/98-lab-pesquisa.js. Ele faz: js/14-lab-pesquisa.js.
No app original ele tinha estas funções/partes: mil, json, enc, semInternet, dados, pesquisar, info, cdn, comparar, col, linha, alternativas, substitutos, ajuda.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 40 — `js/98-lab-comparar.js` (era `ferramentas/laboratorio2/js/15-lab-comparar.js`, 208 linhas)

```text
Crie js/98-lab-comparar.js. Ele faz: js/15-lab-comparar.js.
No app original ele tinha estas funções/partes: diff, norm, trechos, htmlDiff, mdDiff, tela, opcoes, entrada, mostrar, arquivos, colados, semTopo, projetos, textoMD, baixarMD, copiarMD.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 41 — `js/98-15a-tar.js` (era `ferramentas/laboratorio2/js/15a-tar.js`, 45 linhas)

```text
Crie js/98-15a-tar.js. Ele faz: js/15a-tar.js.
No app original ele tinha estas funções/partes: ehTar, descompactar, texto, octal, abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 42 — `js/98-lab-ferramentas.js` (era `ferramentas/laboratorio2/js/16-lab-ferramentas.js`, 83 linhas)

```text
Crie js/98-lab-ferramentas.js. Ele faz: js/16-lab-ferramentas.js.
No app original ele tinha estas funções/partes: bytes, tela, cartao, achar, abrirAqui, telaPropria, kit.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 43 — `js/98-lab-termux.js` (era `ferramentas/laboratorio2/js/17-lab-termux.js`, 379 linhas)

```text
Crie js/98-lab-termux.js. Ele faz: LABORATÓRIO 2 — 17-lab-termux.js · 💻 TERMINAL DE VERDADE (16/11) Trocado pelo terminal ATUAL do Laboratório (o que não cai): ▶ Ligar tudo · 🚀 Rodar · ⏹ Parar · 🦙 Ollama · 🗣 Voz Francisco · 🧰 Verificar e instalar · 🩺 Terminal parado? - No celular: Termux (ttyd ws://127.0.0.1:7681/ws + ponte de arquivos 7683).
No app original ele tinha estas funções/partes: espera, status, pst, carregarScript, carregarCss, prepararTela, escreverTela, enviar, tamanho, ligado, conectar, desconectar, copiar, nome, dentro, responder, corpo, andar.
O original usava as bibliotecas http, fs, path, os: em HTML puro, use a versão de CDN (ou faça sem ela, se for simples).
Ele chamava estes endereços: ferramentas/meu-chat/voz-francisco.py. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 44 — `js/98-lab-desmontar.js` (era `ferramentas/laboratorio2/js/18-lab-desmontar.js`, 462 linhas)

```text
Crie js/98-lab-desmontar.js. Ele faz: js/18-lab-desmontar.js.
No app original ele tinha estas funções/partes: comPonte, explicar, lerJS, ehBiblioteca, nomesDoTopo, analisar, linhaDe, slug, picar, pad, nomeDoPedaco, dividirScript, secaoDe, pedaco, agrupar, rodarEm, ouvir, plano.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 45 — `js/98-embutido.js` (era `ferramentas/laboratorio2/js/19-embutido.js`, 2 linhas)

```text
Crie js/98-embutido.js. Ele é uma parte de logica do app.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 46 — `js/98-base.js` (era `ferramentas/meu-chat/js/00-base.js`, 43 linhas)

```text
Crie js/98-base.js. Ele faz: Meu Chat — 00-base.js: peças comuns (MC).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 47 — `js/98-banco.js` (era `ferramentas/meu-chat/js/10-banco.js`, 26 linhas)

```text
Crie js/98-banco.js. Ele faz: Meu Chat — 10-banco.js: onde tudo fica guardado (IndexedDB do aparelho — não some ao fechar).
No app original ele tinha estas funções/partes: abrir, req, loja.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 48 — `js/98-nuvem.js` (era `ferramentas/meu-chat/js/12-nuvem.js`, 280 linhas)

```text
Crie js/98-nuvem.js. Ele faz: Meu Chat — 12-nuvem.js · ☁️ NUVEM (Supabase) — 17/11 - O chat continua funcionando SEM internet: tudo fica no aparelho (IndexedDB). - Com a nuvem ligada, ele COPIA para o Supabase e traz de volta em qualquer aparelho (celular, PC, outro celular) entrando com o mesmo e-mail e senha.
No app original ele tinha estas funções/partes: cfg, sessao, ehNeon, neonConn, logado, ligada, auth, traduzir, guardarSessao, token, rest, mod, horaUnica, marcar, ganchos, marcarPrefs, prefsViajam, semFotos.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 49 — `js/98-provedores.js` (era `ferramentas/meu-chat/js/20-provedores.js`, 240 linhas)

```text
Crie js/98-provedores.js. Ele faz: Meu Chat — 20-provedores.js: conversar com as IAs (Gemini, Groq, OpenRouter, OpenAI, DeepSeek, Claude). - Várias chaves; quando uma acaba (limite/cota), passa sozinho para a próxima ("revezar"). - Busca a lista de modelos de verdade na hora de testar a chave (nada de nome velho chumbado). - As chaves ficam SÓ neste aparelho.
No app original ele tinha estas funções/partes: detectar, procurarOllama, chaves, salvarChaves, pontoGemini, listarModelos, pontoLivre, geracao, modeloDe, testarChave, erroLegivel, corsAviso, ehLimite, cabAnthropic, lerSSE, pedir, parcial, conversar.
Ele chamava estes endereços: http://127.0.0.1:11434/api/tags. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 50 — `js/98-memoria.js` (era `ferramentas/meu-chat/js/30-memoria.js`, 77 linhas)

```text
Crie js/98-memoria.js. Ele faz: Meu Chat — 30-memoria.js: 🧠 a memória que vai junto em TODA conversa. A IA guarda sozinha o que for importante escrevendo [[lembrar: …]] no fim da resposta (o app tira isso do texto, guarda e mostra "🧠 guardei"). [[esquecer: …]] apaga.
No app original ele tinha estas funções/partes: texto, salvar, lembrar, esquecer, aplicarMarcas, guiaParaPergunta, tamanhoTexto, sistema, abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 51 — `js/98-contextos.js` (era `ferramentas/meu-chat/js/33-contextos.js`, 178 linhas)

```text
Crie js/98-contextos.js. Ele faz: Meu Chat — 33-contextos.js: 📌 CONTEXTOS — "cartões" de assunto que você LIGA e DESLIGA. Diferente da 🧠 memória (que vale para sempre e vai em tudo): um contexto é o resumo de um assunto ou de uma conversa (por exemplo, o que você vinha fazendo com o Claude), para a IA não começar do zero. Ligado = vai junto em toda conversa. Desligado = fica guardado, sem gastar.
No app original ele tinha estas funções/partes: lista, gravar, semear, esconder, tokens, ligados, texto, pintarChip, pintar, novo, clique.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 52 — `js/98-guia.js` (era `ferramentas/meu-chat/js/34-guia.js`, 39 linhas)

```text
Crie js/98-guia.js. Ele faz: 🧭 Painel do Guia (16/11): o que é cada app do Maikon, a versão atual e COMO USAR, passo a passo. 🔊 lê em voz alta (voz Francisco ou a do aparelho) · 🤖 Perguntar: o chat explica aquele app.
No app original ele tinha estas funções/partes: textoDe, pintar, iniciar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 53 — `js/98-jeito.js` (era `ferramentas/meu-chat/js/35-jeito.js`, 56 linhas)

```text
Crie js/98-jeito.js. Ele faz: Meu Chat — 35-jeito.js: 🎭 O JEITO DE CADA IA. Para não ter "mudança drástica" quando troca de IA: um jeito de conversar que vale para TODAS (parceiro, calmo, honesto) e, se quiser, um jeito só de uma (ex.: o Perplexity como pesquisador jurídico que sempre traz as fontes). Tudo editável em ⚙️ → 🎭 Jeito de cada IA.
No app original ele tinha estas funções/partes: geral, deUma, texto, pintar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 54 — `js/98-voz.js` (era `ferramentas/meu-chat/js/40-voz.js`, 227 linhas)

```text
Crie js/98-voz.js. Ele faz: Meu Chat — 40-voz.js: 🎤 falar (ditado) e 🔊 ouvir a resposta. 🔊 DOIS "motores" de voz (⚙️ → Voz): - 📱 "Voz do aparelho" (o padrão): funciona com QUALQUER IA (Gemini, Groq, Claude, Ollama…), grátis e sem limite. Você escolhe a voz (as ⭐ são as naturais), a velocidade e o tom.
No app original ele tinha estas funções/partes: podeOuvir, ouvir, parar, marcar, paraFala, pedacos, noPC, motor, temAndroid, temNavegador, natural, vozesAparelho, cfgVoz, falarFrase, enfileirar, verificarFim, pararAparelho, fluxo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 55 — `js/98-internet.js` (era `ferramentas/meu-chat/js/50-internet.js`, 58 linhas)

```text
Crie js/98-internet.js. Ele faz: Meu Chat — 50-internet.js: 🌐 pesquisar e 🔗 ler links. - Gemini e Claude pesquisam sozinhos (a busca vem embutida neles). - As outras IAs: usa a SUA chave de busca (Serper, Tavily ou Brave), se tiver, e manda os resultados junto. - Link na mensagem: o app lê a página (pelo leitor r.jina.ai, grátis) e manda o texto para a IA.
No app original ele tinha estas funções/partes: buscar, lerLink, preparar.
Ele chamava estes endereços: https://google.serper.dev/search, https://api.tavily.com/search, https://api.search.brave.com/res/v1/web/search?count=8&country=BR&search_lang=pt-br&q=, https://r.jina.ai/. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 56 — `js/98-previa.js` (era `ferramentas/meu-chat/js/60-previa.js`, 76 linhas)

```text
Crie js/98-previa.js. Ele faz: Meu Chat — 60-previa.js: 👁 ver o código funcionando, na hora. - HTML: abre a página como ela é. - TSX / JSX (React): monta com React + Babel + Tailwind (pela internet) e mostra o componente. Os erros aparecem embaixo, em vermelho.
No app original ele tinha estas funções/partes: paginaHTML, paginaReact, falha, req, App, tipoDe, abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 57 — `js/98-texto.js` (era `ferramentas/meu-chat/js/70-texto.js`, 45 linhas)

```text
Crie js/98-texto.js. Ele faz: Meu Chat — 70-texto.js: mostra a resposta da IA bonitinha (negrito, listas, links, blocos de código com 📋 copiar, ⤓ baixar e 👁 ver funcionando).
No app original ele tinha estas funções/partes: inline, render, ligar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 58 — `js/98-chat.js` (era `ferramentas/meu-chat/js/80-chat.js`, 252 linhas)

```text
Crie js/98-chat.js. Ele faz: Meu Chat — 80-chat.js: a conversa (mensagens, fotos, mandar, parar, lista de conversas). Cada conversa fica guardada no aparelho. Vai para a IA: a memória + as últimas mensagens.
No app original ele tinha estas funções/partes: nova, abrirConversa, guardar, reduzir, anexar, pintarAnexos, htmlMsg, dedup, hora, pintar, mandar, responder, depois, comparar, juntar, tela, escolherComparar, resumirSePrecisar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 59 — `js/98-config.js` (era `ferramentas/meu-chat/js/85-config.js`, 115 linhas)

```text
Crie js/98-config.js. Ele faz: Meu Chat — 85-config.js: ⚙️ chaves das IAs, modelo, busca, voz, instruções, tema.
No app original ele tinha estas funções/partes: opcoesVoz, pintar, clique, mudou, aplicarTema, abrir.
Ele chamava estes endereços: voz-francisco.py. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 60 — `js/98-cofre.js` (era `ferramentas/meu-chat/js/87-cofre.js`, 94 linhas)

```text
Crie js/98-cofre.js. Ele faz: Meu Chat — 87-cofre.js: 🔐 Cofre de chaves. Mostra cada chave guardada (👁 ver, 📋 copiar) e leva SÓ as chaves para outro app/aparelho num arquivo trancado com senha — o mesmo arquivo do Mini SK (js/lib/cofre-arquivo.js).
No app original ele tinha estas funções/partes: todas, pintar, status, conteudo, baixar, trazer, selarTexto, trazerTexto.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 61 — `js/98-backup.js` (era `ferramentas/meu-chat/js/90-backup.js`, 44 linhas)

```text
Crie js/98-backup.js. Ele faz: Meu Chat — 90-backup.js: 💾 backup de tudo (conversas + memória + ajustes) e restaurar SEM APAGAR NADA.
No app original ele tinha estas funções/partes: gerar, baixar, restaurar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 62 — `js/98-ponte-lab.js` (era `ferramentas/meu-chat/js/95-ponte-lab.js`, 20 linhas)

```text
Crie js/98-ponte-lab.js. Ele faz: 🔬 Ponte com o Laboratório: quando o Meu Chat está DENTRO do Laboratório (aba 🤖 IA), o Laboratório pode mandar texto para a caixa de escrever (o plano do projeto, a memória, a comparação A × B). Só aceita mensagens da própria página (mesmo endereço).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 63 — `js/98-cofre-arquivo.js` (era `ferramentas/meu-chat/js/lib/cofre-arquivo.js`, 61 linhas)

```text
Crie js/98-cofre-arquivo.js. Ele faz: 🔐 Arquivo de chaves do Maikon — o MESMO formato no Mini SK, no Meu Chat e no que vier depois. Guarda SÓ as chaves (IA, GitHub, Expo, pesquisa e "Minhas chaves"), trancadas com uma senha sua (AES-GCM 256 + PBKDF2 com 250 mil voltas — sem a senha, o arquivo não abre). Assim dá para levar as chaves de um app/aparelho para outro sem passar pelo WhatsApp.
No app original ele tinha estas funções/partes: b64, deB64, chaveDaSenha, normal, selar, abrir, contar, mascara.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 64 — `js/98-guia-maikon.js` (era `ferramentas/meu-chat/js/lib/guia-maikon.js`, 118 linhas)

```text
Crie js/98-guia-maikon.js. Ele faz: 🧭 Guia das ferramentas do Maikon — o MESMO texto em todos os apps (Mini SK, Meu Chat…). A IA de cada app lê isto sozinha: assim ela já sabe o que ele tem, para que serve cada coisa, e quando é melhor mandar para outra ferramenta ou "levar para o Claude". Para atualizar: troque este arquivo nos apps (o Claude manda a versão nova junto).
No app original ele tinha estas funções/partes: resumoParaClaude, esconder.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 65 — `js/98-guia-versoes.js` (era `ferramentas/meu-chat/js/lib/guia-versoes.js`, 163 linhas)

```text
Crie js/98-guia-versoes.js. Ele faz: 🧭 Guia das VERSÕES — o que é cada app do Maikon, qual a versão atual, e COMO USAR (passo a passo). Uma fonte só: o painel 🧭 do Meu Chat mostra isto para ele ler, e a IA recebe o mesmo texto (junto do guia-maikon.js) para saber explicar. Atualizado pelo Claude a cada versão nova.
No app original ele tinha estas funções/partes: texto.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 66 — `js/98-nuvem-neon.js` (era `ferramentas/meu-chat/js/lib/nuvem-neon.js`, 73 linhas)

```text
Crie js/98-nuvem-neon.js. Ele faz: 🐘 Nuvem pelo NEON (17/11) — usada pelo Meu Chat e pelo SK Jurídico HTML. Você cola o endereço do banco (a "connection string" postgresql://…) e pronto: o app cria a tabela SOZINHO (não precisa rodar nada em inglês no site do Neon). ⚠ Esse endereço tem a SENHA do banco: fica só no seu aparelho (como uma chave de IA),.
No app original ele tinha estas funções/partes: traduzir, preparar, upsert, listar, conv.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 67 — `js/98-base.js` (era `js/00-base.js`, 28 linhas)

```text
Crie js/98-base.js. Ele faz: Laboratório — 00-base.js: peças comuns (LB).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 68 — `js/98-banco.js` (era `js/10-banco.js`, 25 linhas)

```text
Crie js/98-banco.js. Ele faz: Laboratório — 10-banco.js: os projetos guardados no aparelho (IndexedDB), cada um SEPARADO e com nome. Projeto = { id, nome, criado, origem, arquivos: { caminho: { t: texto } | { b: tamanho-binário } } }.
No app original ele tinha estas funções/partes: abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 69 — `js/98-importar.js` (era `js/20-importar.js`, 65 linhas)

```text
Crie js/98-importar.js. Ele faz: Laboratório — 20-importar.js: traz um projeto (.zip, .tar.gz, pasta, um HTML só, vários arquivos, código colado).
No app original ele tinha estas funções/partes: decodificar, registro, semTopo, lerTar, str, deCompactado, guardar, nomeSem.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 70 — `js/98-analise.js` (era `js/30-analise.js`, 178 linhas)

```text
Crie js/98-analise.js. Ele faz: Laboratório — 30-analise.js: lê o projeto INTEIRO (vários arquivos ou um HTML só) e descobre: os arquivos, como cada página carrega, as funções (o que fazem, quem chama quem), as ligações entre arquivos, dependências, rotas, e os problemas. O "motor" das funções é o do 🔪 Desmontar.
No app original ele tinha estas funções/partes: explicar, tipoArq, ehBiblioteca, linhaDe, lerJS, analisarCodigo, importsPorTexto, resolver, tenta, prob, tem.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 71 — `js/98-plano.js` (era `js/40-plano.js`, 93 linhas)

```text
Crie js/98-plano.js. Ele faz: Laboratório — 40-plano.js: o PLANO MACRO do projeto, em .md (para ler aqui e para levar para a IA).
No app original ele tinha estas funções/partes: arvore, andar, inl, cel.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 72 — `js/98-comparar.js` (era `js/50-comparar.js`, 119 linhas)

```text
Crie js/98-comparar.js. Ele faz: Laboratório — 50-comparar.js: ⚖️ A (o que funciona) × B (o que não funciona), lado a lado. Mostra arquivos novos/sumidos/mudados, as funções que mudaram e os problemas que só existem em B.
No app original ele tinha estas funções/partes: diff, norm, ladoAlado, lin, chave, linhaF.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 73 — `js/98-ferramentas.js` (era `js/60-ferramentas.js`, 142 linhas)

```text
Crie js/98-ferramentas.js. Ele faz: Laboratório — 60-ferramentas.js: 🧰 AS SUAS FERRAMENTAS NUM LUGAR SÓ. Cada ferramenta é um HTML que funciona sozinho (pasta ferramentas/). Abre aqui dentro e continua guardando os próprios dados. "↗ Tela própria" abre numa aba só dela.
No app original ele tinha estas funções/partes: achar, cartao, tela, abrir, podeMandar, zipDoProjeto, soltos, tipo, mandar, encaixar, kit.
Ele chamava estes endereços: kits/. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 74 — `js/98-ia.js` (era `js/70-ia.js`, 63 linhas)

```text
Crie js/98-ia.js. Ele faz: Laboratório — 70-ia.js: 🤖 IA — o MEU CHAT aqui dentro (chat livre, do jeito da última versão): as suas chaves (Gemini, Groq, OpenRouter…), o 🦙 Ollama sozinho quando estiver ligado, voz natural, memória, internet e fotos. Os botões 📎 colocam na caixa do chat o PLANO do projeto, a MEMÓRIA dele, a COMPARAÇÃO A × B.
No app original ele tinha estas funções/partes: quadro, mandar, esconderChaves, colar, tela, pintarNome, acao, pintar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 75 — `js/98-memoria.js` (era `js/75-memoria.js`, 56 linhas)

```text
Crie js/98-memoria.js. Ele faz: Laboratório — 75-memoria.js: 📒 MEMÓRIA — o caderno de cada projeto (e um caderno geral). O que é o projeto, o que já funciona, o que falta, as decisões e os erros já resolvidos. Salva sozinho enquanto você escreve (fica guardado neste aparelho, neste navegador). 📎 manda para a 🤖 IA junto com a pergunta, para ela não se perder.
No app original ele tinha estas funções/partes: chave, ler, gravar, idAtual, tela.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 76 — `js/98-terminal.js` (era `js/80-terminal.js`, 376 linhas)

```text
Crie js/98-terminal.js. Ele faz: Laboratório — 80-terminal.js: 💻 TERMINAL DE VERDADE — com a MESMA lógica do Mini SK (a que não cai): 📱 TERMUX (celular): conecta no ttyd (ws://127.0.0.1:7681/ws), religa sozinho se cair, e liga a ponte de arquivos em PEDACINHOS (antes ia numa linha gigante e o Termux derrubava a conexão); se a ponte cair, religa sozinha. Instala o Node sozinho na 1ª vez.
No app original ele tinha estas funções/partes: espera, status, pst, carregarScript, carregarCss, prepararTela, escreverTela, enviar, tamanho, ligado, conectar, desconectar, copiar, nome, dentro, responder, corpo, andar.
O original usava as bibliotecas http, fs, path, os: em HTML puro, use a versão de CDN (ou faça sem ela, se for simples).
Ele chamava estes endereços: ferramentas/meu-chat/voz-francisco.py. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 77 — `js/98-lab-ponte.js` (era `js/90-lab-ponte.js`, 49 linhas)

```text
Crie js/98-lab-ponte.js. Ele faz: Laboratório — 90-lab-ponte.js: a "tomada" que deixa as ferramentas do Laboratório ANTIGO (19/10) — 🔪 Desmontar, 🗺️ Mapa e 🧪 Prévia de vários arquivos — funcionarem aqui dentro, sem mexer nelas. Elas pediam um "Shell" (o miolo do app antigo). Aqui o Shell é de mentirinha e conversa com o LB.
No app original ele tinha estas funções/partes: arquivosDoAtual, criarProjeto.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 78 — `js/98-lab-base.js` (era `js/91-lab-base.js`, 146 linhas)

```text
Crie js/98-lab-base.js. Ele faz: 91-lab-base.js (veio do Laboratório antigo) — o que ele entende como "um arquivo chama o outro": - HTML:  <script src>, <link href>, <img src>, <iframe src>, <a href="x.html"> - JS/TS: import … from 'x', import('x'), require('x'), export … from 'x' - CSS:   @import 'x', url(x).
No app original ele tinha estas funções/partes: ehBinario, arquivos, binarios, lista, tipo, pasta, normalizar, raizComum, resolver, raizDoArquivo, resolverApelido, achar, tem, nomePacote, referencias, add, refsJS, mapa.
O original usava as bibliotecas x: em HTML puro, use a versão de CDN (ou faça sem ela, se for simples).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 79 — `js/98-lab-mapa.js` (era `js/92-lab-mapa.js`, 149 linhas)

```text
Crie js/98-lab-mapa.js. Ele faz: js/12-lab-mapa.js.
No app original ele tinha estas funções/partes: tela, listar, detalhe, link, arvore, extrair, mermaid, relatorio, verCodigo, desmontar, previa, pesquisar, ver.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 80 — `js/98-lab-previa.js` (era `js/93-lab-previa.js`, 289 linhas)

```text
Crie js/98-lab-previa.js. Ele faz: js/13-lab-previa.js.
No app original ele tinha estas funções/partes: pegarConversor, temJSX, urlPacote, blobURL, urlBinario, urlDe, prepararJS, reescreverImports, ehTailwindCSS, prepararCSS, montarPagina, candidatos, tela, listarExtras, mostrarLog, mostrarConsole, rodar, rodarColado.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 81 — `js/98-lab-desmontar.js` (era `js/94-lab-desmontar.js`, 463 linhas)

```text
Crie js/98-lab-desmontar.js. Ele faz: js/18-lab-desmontar.js.
No app original ele tinha estas funções/partes: comPonte, explicar, lerJS, ehBiblioteca, nomesDoTopo, analisar, linhaDe, slug, picar, pad, nomeDoPedaco, dividirScript, secaoDe, pedaco, agrupar, rodarEm, ouvir, plano.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 82 — `js/98-fatiador.js` (era `js/95-fatiador.js`, 598 linhas)

```text
Crie js/98-fatiador.js. Ele faz: Laboratório — 95-fatiador.js: ✂️ FATIADOR INTELIGENTE Pega um arquivo grande (HTML, JS, TS, TSX, JSX, CSS, Python, MD) e corta em FATIAS do tamanho que você escolher (50 a 500 linhas), SEM cortar no meio de uma função: ele só corta entre um bloco e outro (a leitura dos blocos é a mesma do Fatiador do Mini SK, que sabe pular textos, comentários e regex).
No app original ele tinha estas funções/partes: lineStates, nameOfJs, splitByStarts, pullComments, splitJs, tryBase, short, splitCss, splitPy, splitMd, splitPlain, splitHtml, push, langOf, slice, rejoin, cerca, porDentro.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 83 — `js/98-recuperar.js` (era `js/96-recuperar.js`, 178 linhas)

```text
Crie js/98-recuperar.js. Ele faz: Laboratório — 96-recuperar.js: ♻️ RECUPERADOR DE BACKUP Abre os backups .json dos seus apps antigos (Exportar Backup, LocalStorage, playground, Iara, SK Editor, AI Code Studio…) e o snippets.csv da Replit, ACHA os códigos, páginas e conversas guardados lá dentro e transforma em ARQUIVOS de verdade: vira projeto do Laboratório, .zip ou .md.
No app original ele tinha estas funções/partes: tirarSegredos, pareceCodigo, tipoDe, limpo, ehB64, deB64, talvezJSON, add, conversaMD, nomeDe, textoDe, linhaSecreta, andar, lerCSV, recuperar, tela, mostrar, pintar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 84 — `js/98-brincar.js` (era `js/97-brincar.js`, 249 linhas)

```text
Crie js/98-brincar.js. Ele faz: Laboratório — 97-brincar.js: 🧸 BRINCAR (o laboratório de brinquedo, para APRENDER) 📥 Caixa: joga todos os seus códigos (arquivos, .zip, backups .json/.csv, o projeto escolhido) num lugar só. 🔁 Repetidos: acha os iguais e os QUASE iguais (versão 1, versão 2…) e marca ⭐ a mais completa. "Ficar só com a ⭐" manda as outras para a pasta lixeira/ da caixa — nada é apagado.
No app original ele tinha estas funções/partes: caixa, brinquedos, nomeCurto, limpo, ICONE, normal, guardar, familias, raiz, tri, simCurto, sim, ext, comoPagina, esc, tomada, injetar, memoriaDe.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 85 — `js/98-combinar.js` (era `js/98-combinar.js`, 218 linhas)

```text
Crie js/98-combinar.js. Ele faz: Laboratório — 98-combinar.js: 🧬 COMBINAR — pegar pedaços de códigos diferentes e montar um código novo. 1) Ele lê TODOS os seus projetos do Laboratório (inclusive o que o 🔪 Desmontar e o ✂️ Fatiador separaram) e lista cada pedaço: funções, variáveis, classes — com o que cada um faz, o que ele USA e de quais elementos da tela (ids) ele precisa.
No app original ele tinha estas funções/partes: parse, nomesDoPadrao, usos, andar, explicar, idsUsados, scriptsDe, lerTudo, NAVEGADOR, resolver, fichaMD, linha, htmlDosProjetos, montar, tela, ler, pintar, pintarCesta.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 86 — `js/98-98w-desembrulhar.js` (era `js/98w-desembrulhar.js`, 127 linhas)

```text
Crie js/98-98w-desembrulhar.js. Ele faz: Laboratório — 98w-desembrulhar.js: 📦 DESEMBRULHAR — tira de volta os códigos HTML que um "montador" guardou DENTRO de um HTML só (cada um virava uma aba). Serve para recuperar ferramentas que você só tem nesse formato juntado (o original separado se perdeu). Procura em todo lugar onde um montador costuma esconder:.
No app original ele tinha estas funções/partes: ehHTML, pareceB64, deB64, tituloDe, procurarNoJS, andar, procurar, rec, desembrulhar, add, tela, rodar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 87 — `js/98-98x-raiox.js` (era `js/98x-raiox.js`, 236 linhas)

```text
Crie js/98-98x-raiox.js. Ele faz: Laboratório — 98x-raiox.js: 🔍 RAIO-X DE APK e de .EXE (e de zip de projeto) Abre um .apk (ou .zip/.aab) SEM instalar, olha por dentro e faz um RELATÓRIO em português: - que tipo de app é (Capacitor, Cordova, React Native, Flutter, site embrulhado…); - se ele só abre um SITE da internet (server.url) — aí "funciona sem servidor" porque usa o servidor de lá;.
No app original ele tinha estas funções/partes: mascara, examinar, tam, tem, inflar, textoAscii, examinarExe, busca, temTexto, tela, mostrar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 88 — `js/98-98x2-raiox-mais.js` (era `js/98x2-raiox-mais.js`, 190 linhas)

```text
Crie js/98-98x2-raiox-mais.js. Ele faz: Laboratório — 98x2-raiox-mais.js: 🔍 RAIO-X, parte 2 (17/11) — tirar informação de BUILD e de APK O build (a pasta dist, ou a tela dentro do APK) vem "embolado": tudo espremido numa linha só, às vezes num arquivo, às vezes em 50. Mesmo assim dá para tirar muita coisa: 📖 Frases em português — os textos da tela, as mensagens de erro e de aviso (ficam legíveis no build).
No app original ele tinha estas funções/partes: literais, pareceClasse, frasesDe, promptsDe, limparCaminho, originaisDe, desembolar, ind, quebrou, analisar, andar, conjunto, dif, comparar, bloco.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 89 — `js/98-98y-grupos.js` (era `js/98y-grupos.js`, 154 linhas)

```text
Crie js/98-98y-grupos.js. Ele faz: Laboratório — 98y-grupos.js: 🧩 GRUPOS — seus códigos HTML trabalhando JUNTOS (a ideia do Caça-Bug, sem montar.py). - Crie um grupo (ex.: 🧹 Limpeza, 💾 Backup, ⚖️ Comparação) e ponha nele os seus códigos .html. - Cada grupo tem uma 🧺 MESA: os arquivos que circulam entre os códigos. - 📤 ENTREGAR: pega um arquivo da mesa e coloca DENTRO do código, como se você tivesse tocado em.
No app original ele tinha estas funções/partes: grupos, grupo, ferramentas, mesa, nomeLimpo, ehTexto, salvar, cap, pega, comTomada, arquivoDaMesa, quadro, entregar, colarTexto, relatorio, tela, clique, pintar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 90 — `js/98-98z-navegar.js` (era `js/98z-navegar.js`, 31 linhas)

```text
Crie js/98-98z-navegar.js. Ele faz: Laboratório — 98z-navegar.js: barrinha NO TOPO (ao lado da versão) com ⬅ voltar · ➡ avançar (entre as abas que você abriu) e 🔍− 🔍+ (diminuir/aumentar a tela inteira). O tamanho escolhido fica guardado neste aparelho.
No app original ele tinha estas funções/partes: aplicar, pintar, montar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 91 — `js/98-juntar.js` (era `kits/juntar.py`, 67 linhas)

```text
Crie js/98-juntar.js. Ele faz: -*- coding: utf-8 -*-.
No app original ele tinha estas funções/partes: juntar, ler, css, img.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 92 — `js/98-kit-replit.js` (era `kits/kit-replit.cjs`, 168 linhas)

```text
Crie js/98-kit-replit.js. Ele faz: !/usr/bin/env node.
No app original ele tinha estas funções/partes: data, humano, rel, listar, lerJSON, examinar, TAB, crc32, criarZip, escreve, relatorio, pacoteLimpo, pacoteMontados, montarUm, pergunta.
O original usava as bibliotecas fs, path, zlib, readline, child_process: em HTML puro, use a versão de CDN (ou faça sem ela, se for simples).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 93 — `js/98-organizar.js` (era `kits/organizar.py`, 466 linhas)

```text
Crie js/98-organizar.js. Ele faz: -*- coding: utf-8 -*-.
No app original ele tinha estas funções/partes: tipo_de, humano, onde, prioridade, ler_log, gravar_log, dentro, mover, resumo_hash, examinar, separar, arrumar_download, desfazer, revisar_info, apagar_copias, Pagina, log_message, responder.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 94 — `js/98-ferramentas.js` (era `kits/receita-montar/js/40-ferramentas.js`, 136 linhas)

```text
Crie js/98-ferramentas.js. Ele faz: Caça-Bug — 40-ferramentas.js Abre cada ferramenta (Cirurgião, Projeto Lab, Triagem, Perito…) DENTRO do app, sem mexer no jeito delas funcionarem: - entrega o projeto ativo automaticamente (não precisa importar de novo);.
No app original ele tinha estas funções/partes: REG, baixar, tenta, comKit, lista, porId, esperarHub, olha, criarFrame, noFrame, alimentar, abrir, abrirComparacao, guardarRelatorio, montarLista.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 95 — `js/98-montar.js` (era `kits/receita-montar/montar.py`, 93 linhas)

```text
Crie js/98-montar.js. Ele faz: -*- coding: utf-8 -*-.
No app original ele tinha estas funções/partes: ler, no_fim_do_body, main.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 96 — `js/98-servir.js` (era `kits/servir.py`, 119 linhas)

```text
Crie js/98-servir.js. Ele faz: -*- coding: utf-8 -*-.
No app original ele tinha estas funções/partes: achar_site, porta_da_pasta, abrir_janela, main, Pagina, __init__, send_head, end_headers, log_message.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 97 — `js/98-voz-francisco.js` (era `kits/voz-francisco.py`, 134 linhas)

```text
Crie js/98-voz-francisco.js. Ele faz: !/usr/bin/env python3 -*- coding: utf-8 -*-.
No app original ele tinha estas funções/partes: _listar, _falar, Voz, _cabecalhos, do_OPTIONS, _json, _pedido, do_GET, do_POST, _tratar, log_message.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 98 — `js/98-ai-code-studio.js` (era `ferramentas/ai-code-studio.html`, 1820 linhas)

```text
Crie js/98-ai-code-studio.js. Ele faz: AI Code Studio — Título.
No app original ele tinha estas funções/partes: est, uid, isMobile, escapeHtml, copyText, AMBIENTE, activeConv, MODULE_Storage, save, saveSoon, load, normMemory, stamp, download, exportAll, importBackup, handleImport, MODULE_Provider.
Ele usa o que já foi criado em: js/98-guia-maikon.js (pelo APP).
Ele chamava estes endereços: https://api.anthropic.com/v1/messages, https://api.anthropic.com/v1/models?limit=100, https://google.serper.dev/search. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 99 — `js/98-arrumador.js` (era `ferramentas/arrumador.html`, 404 linhas)

```text
Crie js/98-arrumador.js. Ele faz: Arrumador de Backups — 🗃 Arrumador de Backups.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 100 — `js/98-banco-neon.js` (era `ferramentas/banco-neon.html`, 250 linhas)

```text
Crie js/98-banco-neon.js. Ele faz: Banco de Dados (Neon) — 🗄 Banco de Dados (Neon).
No app original ele tinha estas funções/partes: mostrarModelo, traduzir, listar, grade, cel, nomeSeguro, ver, baixar, csv, tudoDe, confirmar, rodar, limpo, campo, sqlNova, pintarNc.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 101 — `js/98-colador.js` (era `ferramentas/colador.html`, 797 linhas)

```text
Crie js/98-colador.js. Ele faz: Colador de Links — 🔗 Colador de Links.
No app original ele tinha estas funções/partes: uid, ler, gravar, nomeLista, nomeDe, pintar, fixar, tirar, mover, recarregar, pintarJanela, iniciar, montar, salvar, daLista, contar, pintarListas, caixaDe.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 102 — `js/98-faxina.js` (era `ferramentas/faxina.html`, 470 linhas)

```text
Crie js/98-faxina.js. Ele faz: 🧹 Faxina de Repetidos — 🧹 Faxina de Repetidos.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 103 — `js/98-iara-suite.js` (era `ferramentas/iara-suite.html`, 1536 linhas)

```text
Crie js/98-iara-suite.js. Ele faz: Iara Suite — Code Editor · APK Builder · Site Extractor — Olá, Mundo!.
No app original ele tinha estas funções/partes: qsa, lsSet, switchTab, detectProvider, getActiveSlot, updateAIStatus, openKeyModal, closeKeyModal, renderSlots, autoDetectSlot, toggleSlotActive, saveSlots, callAI, initEditor, renderFileList, fileIcon, openFile, onCodeChange.
O original usava as bibliotecas @capacitor/cli, electron, path, react-native, react-native-webview: em HTML puro, use a versão de CDN (ou faça sem ela, se for simples).
Ele chamava estes endereços: https://api.anthropic.com/v1/messages, https://generativelanguage.googleapis.com/v1beta/models/${model}:generateContent. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 104 — `js/98-juntador.js` (era `ferramentas/juntador.html`, 437 linhas)

```text
Crie js/98-juntador.js. Ele faz: Juntador de Arquivos — 🧩 Juntador de Arquivos.
No app original ele tinha estas funções/partes: esc, uid, toast, ext, lang, isTexto, bytesFmt, linhas, decode, pareceBinario, b64, unb64, inflate, lerZip, CRC, crc32, escreverZip, textoDocx.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 105 — `js/98-colador.js` (era `ferramentas/laboratorio2/ferramentas/colador.html`, 797 linhas)

```text
Crie js/98-colador.js. Ele faz: Colador de Links — 🔗 Colador de Links.
No app original ele tinha estas funções/partes: uid, ler, gravar, nomeLista, nomeDe, pintar, fixar, tirar, mover, recarregar, pintarJanela, iniciar, montar, salvar, daLista, contar, pintarListas, caixaDe.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 106 — `js/98-meu-chat.js` (era `ferramentas/laboratorio2/ferramentas/meu-chat/index.html`, 116 linhas)

```text
Crie js/98-meu-chat.js. Ele faz: Meu Chat.
Ele usa o que já foi criado em: js/10-base.js, js/15-banco.js, js/94-nuvem-neon.js, js/20-nuvem.js, js/25-provedores.js, js/30-memoria.js, js/35-contextos.js, js/40-guia.js, js/45-jeito.js, js/50-voz.js, js/55-internet.js, js/60-previa.js, js/65-texto.js, js/70-chat.js, js/91-cofre-arquivo.js, js/93-guia-versoes.js, js/92-guia-maikon.js, js/75-config.js, js/80-cofre.js, js/85-backup.js, js/90-ponte-lab.js (pelo APP).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 107 — `js/98-laboratorio2.js` (era `ferramentas/laboratorio2/index.html`, 4113 linhas)

```text
Crie js/98-laboratorio2.js. Ele faz: 🔬 Laboratório 2 — 🔬 Laboratório 2.
Ele usa o que já foi criado em: js/96-casca.js, js/97-importar.js, js/98-dependencias.js, js/98-analisar.js, js/98-05a-markdown.js, js/98-plano.js, js/98-scripts.js, js/98-06b-scripts-fim.js, js/98-07a-busca-npm.js, js/98-terminal.js, js/98-exportar.js, js/98-integracao.js, js/98-celular.js, js/98-lab-base.js, js/98-lab-mapa.js, js/98-lab-previa.js, js/98-lab-pesquisa.js, js/98-15a-tar.js, js/98-lab-comparar.js, js/98-lab-ferramentas.js, js/98-lab-termux.js, js/98-lab-desmontar.js, js/98-embutido.js (pelo APP).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 108 — `js/98-meu-chat.js` (era `ferramentas/meu-chat/index.html`, 116 linhas)

```text
Crie js/98-meu-chat.js. Ele faz: Meu Chat.
Ele usa o que já foi criado em: js/98-base.js, js/98-banco.js, js/98-nuvem-neon.js, js/98-nuvem.js, js/98-provedores.js, js/98-memoria.js, js/98-contextos.js, js/98-guia.js, js/98-jeito.js, js/98-voz.js, js/98-internet.js, js/98-previa.js, js/98-texto.js, js/98-chat.js, js/98-cofre-arquivo.js, js/98-guia-versoes.js, js/98-guia-maikon.js, js/98-config.js, js/98-cofre.js, js/98-backup.js, js/98-ponte-lab.js (pelo APP).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 109 — `js/98-montador.js` (era `ferramentas/montador.html`, 952 linhas)

```text
Crie js/98-montador.js. Ele faz: Montador Universal — 🧩 Montador Universal.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 110 — `js/98-numerador.js` (era `ferramentas/numerador.html`, 241 linhas)

```text
Crie js/98-numerador.js. Ele faz: Numerador de Códigos — 🔢 Numerador de Códigos.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 111 — `js/98-picotador.js` (era `ferramentas/picotador.html`, 458 linhas)

```text
Crie js/98-picotador.js. Ele faz: Picotador de Memória e Backup — ✂️ Picotador de Memória e Backup.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 112 — `js/98-preparador.js` (era `ferramentas/preparador.html`, 833 linhas)

```text
Crie js/98-preparador.js. Ele faz: Preparador Universal — 🧰 Preparador Universal.
O original usava as bibliotecas electron, path, fs, http: em HTML puro, use a versão de CDN (ou faça sem ela, se for simples).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 113 — `js/98-projeto-lab.js` (era `ferramentas/projeto-lab.html`, 2006 linhas)

```text
Crie js/98-projeto-lab.js. Ele faz: Projeto Lab.
No app original ele tinha estas funções/partes: esc, tick, fmtSize, fmtDate, normPath, dirname, basename, extOf, joinPath, hex, inflate, mask, lineFinder, parseLenientJSON, langOf, sniff, zipEntries, parsePax.
Ele chamava estes endereços: https://api.anthropic.com/v1/messages, https://api.anthropic.com/v1/models?limit=100. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 114 — `js/98-replicador.js` (era `ferramentas/replicador.html`, 805 linhas)

```text
Crie js/98-replicador.js. Ele faz: Replicador de Projeto.
No app original ele tinha estas funções/partes: goTab, toggleFilePanel, loadZip, processZip, root, renderFileList, filterFiles, openFile, copyViewer, downloadViewer, sendFileToAI, renderAnalysis, buildPkgJson, buildCommands, buildTree, print, refreshModels, saveKey.
Ele chamava estes endereços: https://registry.npmjs.org/${encodeURIComponent(pkg)}/latest, ${bases[provider]}/chat/completions. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 115 — `js/98-inicio.js` (era `index.html`, 121 linhas)

```text
Crie js/98-inicio.js. Ele faz: Laboratório — 🔬 Laboratório.
Ele usa o que já foi criado em: js/98-base.js, js/98-banco.js, js/98-importar.js, js/98-analise.js, js/98-plano.js, js/98-comparar.js, js/98-ferramentas.js, js/98-ia.js, js/98-memoria.js, js/98-terminal.js, js/98-lab-ponte.js, js/98-lab-base.js, js/98-lab-mapa.js, js/98-lab-previa.js, js/98-lab-desmontar.js, js/98-fatiador.js, js/98-recuperar.js, js/98-brincar.js, js/98-combinar.js, js/98-98w-desembrulhar.js, js/98-98x-raiox.js, js/98-98x2-raiox-mais.js, js/98-98y-grupos.js, js/98-98z-navegar.js (pelo APP).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 116 — `js/99-app.js` e conferir

```text
Crie js/99-app.js: ele olha APP.modulos e monta o menu/abas com um botão para cada módulo. Depois, me mande o index.html atualizado com todos os <script src="js/…"> na ordem certa: js/00-core.js, js/10-base.js, js/15-banco.js, js/20-nuvem.js, js/25-provedores.js, js/30-memoria.js, js/35-contextos.js, js/40-guia.js, js/45-jeito.js, js/50-voz.js, js/55-internet.js, js/60-previa.js, js/65-texto.js, js/70-chat.js, js/75-config.js, js/80-cofre.js, js/85-backup.js, js/90-ponte-lab.js, js/91-cofre-arquivo.js, js/92-guia-maikon.js, js/93-guia-versoes.js, js/94-nuvem-neon.js, js/95-voz-francisco.js, js/96-casca.js, js/97-importar.js, js/98-dependencias.js, js/98-analisar.js, js/98-plano.js, js/98-05a-markdown.js, js/98-scripts.js, js/98-06b-scripts-fim.js, js/98-terminal.js, js/98-07a-busca-npm.js, js/98-exportar.js, js/98-integracao.js, js/98-celular.js, js/98-lab-base.js, js/98-lab-mapa.js, js/98-lab-previa.js, js/98-lab-pesquisa.js, js/98-lab-comparar.js, js/98-15a-tar.js, js/98-lab-ferramentas.js, js/98-lab-termux.js, js/98-lab-desmontar.js, js/98-embutido.js, js/98-base.js, js/98-banco.js, js/98-nuvem.js, js/98-provedores.js, js/98-memoria.js, js/98-contextos.js, js/98-guia.js, js/98-jeito.js, js/98-voz.js, js/98-internet.js, js/98-previa.js, js/98-texto.js, js/98-chat.js, js/98-config.js, js/98-cofre.js, js/98-backup.js, js/98-ponte-lab.js, js/98-cofre-arquivo.js, js/98-guia-maikon.js, js/98-guia-versoes.js, js/98-nuvem-neon.js, js/98-base.js, js/98-banco.js, js/98-importar.js, js/98-analise.js, js/98-plano.js, js/98-comparar.js, js/98-ferramentas.js, js/98-ia.js, js/98-memoria.js, js/98-terminal.js, js/98-lab-ponte.js, js/98-lab-base.js, js/98-lab-mapa.js, js/98-lab-previa.js, js/98-lab-desmontar.js, js/98-fatiador.js, js/98-recuperar.js, js/98-brincar.js, js/98-combinar.js, js/98-98w-desembrulhar.js, js/98-98x-raiox.js, js/98-98x2-raiox-mais.js, js/98-98y-grupos.js, js/98-98z-navegar.js, js/98-juntar.js, js/98-kit-replit.js, js/98-organizar.js, js/98-ferramentas.js, js/98-montar.js, js/98-servir.js, js/98-voz-francisco.js, js/98-ai-code-studio.js, js/98-arrumador.js, js/98-banco-neon.js, js/98-colador.js, js/98-faxina.js, js/98-iara-suite.js, js/98-juntador.js, js/98-colador.js, js/98-meu-chat.js, js/98-laboratorio2.js, js/98-meu-chat.js, js/98-montador.js, js/98-numerador.js, js/98-picotador.js, js/98-preparador.js, js/98-projeto-lab.js, js/98-replicador.js, js/98-inicio.js, js/99-app.js.
```

## 5. Conferir no final

- [ ] Abrir o index.html na prévia: aparece a tela sem erro (▤ console vazio)?
- [ ] Cada botão abre a sua parte?
- [ ] Fechar e abrir de novo: os dados continuam?
- [ ] Nada com "replit", "REPL_", "@workspace" no código (🏗️ Preparar confere).
- [ ] 📱 PWA → deixar instalável; 📦 APK ou 🖥️ .exe.
