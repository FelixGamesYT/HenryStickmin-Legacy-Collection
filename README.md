# Henry Stickmin Legacy Collection — Mobile Web Edition

Launcher web mobile-first projetado para navegadores Android modernos (como o Google Chrome no Android) e otimizado para hospedagem estática gratuita pelo **GitHub Pages**, com estética nostálgica da era Flash (2007–2015) e integração local preparada para o emulador **Ruffle Web**.

---

## Estrutura de Pastas do Repositório

```text
HenryStickminLegacyCollection/
├── .nojekyll
├── index.html
├── README.md
├── css/
│   └── style.css
├── js/
│   └── app.js
├── assets/
│   ├── images/
│   └── games/
└── ruffle/
```

---

## Como Adicionar os Arquivos no Repositório

### 1. Motor Ruffle Web (`./ruffle/`)
Para execução 100% independente de CDN diretamente no GitHub Pages:
1. Baixe o pacote oficial **Ruffle Self-Hosted (Web)** em [ruffle.rs](https://ruffle.rs/).
2. Extraia todos os arquivos do pacote para dentro da pasta `ruffle/`, garantindo que existam:
   - `ruffle/ruffle.js`
   - Todos os arquivos `.wasm` e chunks `.js` complementares na mesma pasta `ruffle/`.

### 2. Jogos Flash (`./assets/games/`)
Envie os seis arquivos `.swf` originais para a pasta `assets/games/` com os nomes exatos abaixo:

| Episódio | Jogo | Caminho Relativo |
| :--- | :--- | :--- |
| Prologue | Crossing the Pit | `./assets/games/flash_crossingthepit.swf` |
| Episode 1 | Breaking the Bank | `./assets/games/breakingthebank.swf` |
| Episode 2 | Escaping the Prison | `./assets/games/escapingtheprisongame.swf` |
| Episode 3 | Stealing the Diamond | `./assets/games/stealingthediamondgame.swf` |
| Episode 4 | Infiltrating the Airship | `./assets/games/infiltratingtheairshipgame.swf` |
| Episode 5 | Fleeing the Complex | `./assets/games/fleeing_the_complex.swf` |

### 3. Imagens dos Cards (`./assets/images/`)
Envie as seis imagens de capa para a pasta `assets/images/` usando os nomes abaixo (o launcher detecta automaticamente `.jpg`, `.png` ou `.webp`):

- **Crossing the Pit** (Stickman atravessando uma área com linhas de movimento):
  `./assets/images/crossing_the_pit.jpg` (ou `.png` / `.webp`)
- **Breaking the Bank** (Henry com TNT):
  `./assets/images/breaking_the_bank.jpg`
- **Escaping the Prison** (Henry com bolo em uma cela):
  `./assets/images/escaping_the_prison.jpg`
- **Stealing the Diamond** (Diamante azul em exposição):
  `./assets/images/stealing_the_diamond.jpg`
- **Infiltrating the Airship** (Dirigível vermelho):
  `./assets/images/infiltrating_the_airship.jpg`
- **Fleeing the Complex** (Henry com bigode em ambiente nevado):
  `./assets/images/fleeing_the_complex.jpg`

---

## Como Publicar no GitHub Pages

1. Crie um repositório no GitHub (por exemplo, `henry-stickmin-legacy-collection`).
2. Envie todos os arquivos e pastas da raiz de `HenryStickminLegacyCollection/` (incluindo o arquivo oculto `.nojekyll`) para a branch `main`.
3. No repositório do GitHub, acesse **Settings → Pages**.
4. Em **Build and deployment**, selecione:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` e pasta `/ (root)`
5. Clique em **Save** e aguarde a publicação.
6. Abra o link público gerado (ex.: `https://seu-usuario.github.io/henry-stickmin-legacy-collection/`) diretamente no **Chrome do Android**.

### Detalhes Técnicos de Compatibilidade com GitHub Pages
- **Arquivo `.nojekyll`:** Impede que o Jekyll do GitHub Pages ignore arquivos ou altere caminhos de assets.
- **Caminhos Relativos (`./`):** Todos os vínculos de CSS, JS, imagens, SWFs e chunks WebAssembly do Ruffle usam resolução relativa à URL atual, funcionando tanto em domínios raiz (`usuario.github.io/`) quanto em repositórios de projeto (`usuario.github.io/repositorio/`).
- **MIME Types Nativos:** O GitHub Pages serve automaticamente `.wasm` como `application/wasm`, `.js` como `application/javascript` e `.swf` como `application/x-shockwave-flash` sobre HTTPS, garantindo execução nativa do Ruffle no Android sem qualquer backend.
