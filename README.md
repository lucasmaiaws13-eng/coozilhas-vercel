# Site Coozilhas — Proposta de parceria Tramontina

Site institucional estático (HTML/CSS/JS puro, sem build). Pronto para publicar no Vercel.

## Estrutura

```
.
├── index.html        → a página (todo o conteúdo)
├── vercel.json       → configuração de cache do Vercel
├── favicon.png       → ícone da aba do navegador
├── robots.txt        → liberação para buscadores
└── img/              → todas as imagens do site
```

## Antes de publicar: inserir os 2 links

Abra o `index.html` num editor de texto e, lá no final (dentro da tag `<script>`),
preencha as duas variáveis:

```js
var URL_PLANILHA = "https://…";   // link da planilha de materiais
var URL_PLANTA   = "https://…";   // link da planta 3D
```

Enquanto ficarem vazias (`""`), os botões correspondentes aparecem
desabilitados (apagados) — o site não quebra.

## Como publicar no Vercel

### Opção A — Arrastar e soltar (mais rápido, sem conta técnica)
1. Acesse https://vercel.com e faça login (pode usar Google/GitHub).
2. No painel, clique em **Add New… → Project**.
3. Procure a área **"Deploy a template or import"** e use a opção de
   **upload**: arraste esta pasta inteira (ou o .zip dela) para a janela.
4. Confirme. Em segundos o site estará no ar num endereço `*.vercel.app`.

### Opção B — Pelo GitHub (recomendado para atualizações futuras)
1. Suba esta pasta para um repositório no GitHub.
2. No Vercel: **Add New… → Project → Import** o repositório.
3. Em *Framework Preset*, deixe **Other** (é site estático, não precisa build).
4. Clique em **Deploy**.
5. Sempre que você atualizar o repositório, o Vercel republica sozinho.

### Opção C — Pelo terminal (CLI)
```bash
npm i -g vercel     # instala a CLI uma vez
cd esta-pasta
vercel              # segue as perguntas; use as respostas padrão
vercel --prod       # publica em produção
```

## Domínio próprio (opcional)
No projeto do Vercel: **Settings → Domains → Add**, e aponte o domínio
(ex.: coozilhas.org.br) seguindo as instruções de DNS que aparecerem.

## Observações
- Não há etapa de build: é HTML puro, então o deploy é praticamente instantâneo.
- As imagens em `img/` têm cache de longo prazo configurado no `vercel.json`.
- Para trocar qualquer imagem, basta substituir o arquivo dentro de `img/`
  mantendo o mesmo nome.
