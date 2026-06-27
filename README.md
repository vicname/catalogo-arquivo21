# Catálogo Arquivo 21

Catálogo de produtos da **Arquivo 21** — cadastro de produtos com SKU, preço,
fornecedor, descrição, copy e ângulos de venda. App de página única (HTML/JS),
sem build e sem servidor: os dados ficam salvos no próprio navegador
(`localStorage`).

> **Onde ficam os dados?** No aparelho onde você usa o app. Não há sincronização
> em nuvem — cada celular/computador tem o seu próprio catálogo.

## Instalar como app (PWA)

O catálogo é um **PWA**: dá para instalar na tela inicial do celular ou na área
de trabalho e abrir como um aplicativo (com ícone, em tela cheia e funcionando
offline). Para isso, ele precisa estar **publicado num link `https://`** — não
funciona abrindo o arquivo direto (`file://`).

### 1. Publicar (uma vez) — GitHub Pages

1. No GitHub, abra o repositório `catalogo-arquivo21`.
2. **Settings → Pages**.
3. Em *Build and deployment → Source*, escolha **Deploy from a branch**.
4. Selecione a branch `main` (ou a branch publicada) e a pasta `/ (root)`.
5. Salve. Em ~1 min o site fica no ar em:
   `https://vicname.github.io/catalogo-arquivo21/`

### 2. Instalar no aparelho

- **Android (Chrome):** abra o link → toque no botão **"↓ Instalar app"** no
  topo (ou menu ⋮ → *Instalar aplicativo*).
- **Computador (Chrome/Edge):** abra o link → botão **"↓ Instalar app"** no topo
  (ou o ícone de instalar na barra de endereço).
- **iPhone (Safari):** abra o link → botão **Compartilhar** →
  **"Adicionar à Tela de Início"**.

Depois de instalado, o app abre offline e atualiza sozinho quando há internet.

## Rodar/testar localmente

Como o service worker exige `http(s)`, use um servidor local simples:

```bash
python3 -m http.server 8000
# abra http://127.0.0.1:8000/index.html
```

## Estrutura

```
index.html              app (UI + lógica + estilos)
manifest.webmanifest    metadados do PWA (nome, cores, ícones)
sw.js                   service worker (cache offline do app shell)
icons/                  ícones do app (192/512, maskable, apple-touch, favicon)
```
