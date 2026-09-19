# Plantas Daninhas — Identificação e Classificação

App de estudos gamificado para Agronomia, construído a partir da **Aula 2 – Classificação e Identificação das Plantas Daninhas**.
HTML + CSS + JavaScript puro (sem dependências, sem build obrigatório).

## Como rodar
- Abra `index.html` no navegador (funciona por duplo clique), ou
- `python3 -m http.server 8000` na pasta do projeto e acesse http://localhost:8000
- Para um único arquivo com tudo embutido: `python3 tools/build_arquivo_unico.py` → `dist/plantas-daninhas.html`
- Teste da lógica: `node tools/testar.js`  ·  Diagnóstico dos dados: `PD.diagnostico()` no console do navegador

## Estrutura
```
index.html
css/app.css                  visual (tokens claro/escuro)
assets/plantas/              fotos (id-1.jpg, id-2.jpg…)
js/config.js                 configurações (questões por fase, % de aprovação…)
js/data/plantas.js           BANCO DE PLANTAS
js/data/imagens.js           IMAGENS: liga cada planta às suas fotos
js/data/conceitos.js         questões curadas de Classificação + Resumo da aula
js/data/caracteristicas.js   questões do modo Características
js/data/fases.js             as 6 fases     · js/data/modos.js  os 4 modos de jogo
js/data/familias.js          grupos botânicos e classificação prática
js/questoes/                 BANCO DE QUESTÕES (tipos gerados + curados + sorteio)
js/quiz/                     lógica do quiz e PONTUAÇÃO
js/progressao/               PROGRESSÃO (fases, estatísticas, erros) — localStorage
js/estudo/                   busca do MODO ESTUDO
js/ui/                       telas e componentes
```

## Como expandir
**Nova planta:** copie um bloco em `js/data/plantas.js` (regras no cabeçalho do arquivo). Ela entra sozinha nas questões de nome, científico, família e classificação.
**Foto:** salve em `assets/plantas/` e registre em `js/data/imagens.js` (`principal` = usada nos quizzes; `extras` = só no Estudar). Sem foto, a planta mostra um *placeholder* identificado e não entra no modo visual.
**Nova questão de conceito:** adicione uma linha `c(...)` em `js/data/conceitos.js`. **Nova questão de características:** um item em `js/data/caracteristicas.js`.
**Nova fase:** um objeto em `js/data/fases.js`. **Novo tipo de questão:** `PD.questoes.registrar(...)` em `js/questoes/`.

## Fidelidade ao material
Nomes científicos e populares seguem a grafia dos slides (inclusive `Momocardia`, `Eichornia`, `Portulaca oleraceae`, `Spermacophyta`, `Caussopa`). Notas editoriais aparecem na ficha de cada espécie.
Fotos atuais: extraídas dos próprios slides da aula.
