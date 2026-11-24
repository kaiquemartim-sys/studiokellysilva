# Link da bio – Studio Kelly Silva

Mini site estático (só HTML e CSS, sem JavaScript) em que a página inteira é o flyer,
com áreas clicáveis invisíveis por cima da imagem.

```
kelly-silva/
  index.html
  css/style.css
  assets/img/flyer.jpg   (flyer, 941 x 1672 px, formato story 9:16)
  assets/img/logo.png    (favicon feito do logo KS)
  README.md
```

## 1. Links já configurados

- WhatsApp: `https://wa.me/5581999161480` (com a mensagem pronta "Olá! Vim pelo seu Instagram e gostaria de agendar um horário.")
- Instagram: `https://www.instagram.com/studiokellysilva/`
- Localização: abre uma busca no Google Maps por "Studio Kelly Silva Surubim PE".
  Se tiver o link do seu endereço no Maps, troque a URL da âncora `hit--loc`.

Para mudar o número ou o @, use Ctrl+F no `index.html` e "substituir tudo".

## 2. Ver no computador

- Mais simples: dê dois cliques no `index.html`.
- Ou, com Python instalado, na pasta do projeto: `python3 -m http.server 8000` e abra http://localhost:8000
- Para ver como no celular: F12 no navegador e ative o modo dispositivo (ícone de celular).

## 3. Publicar no GitHub Pages

1. Crie um repositório no GitHub (ex.: `kelly-silva`) e envie os arquivos desta pasta
   (o `index.html` precisa ficar na raiz do repositório).
2. No repositório: **Settings → Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)` e salve.
4. Em 1 a 2 minutos o site fica em `https://SEU-USUARIO.github.io/kelly-silva/`.
5. Cole esse endereço no link da bio do Instagram.

## 4. Publicar na Vercel

1. Crie conta em https://vercel.com e envie esta pasta para um repositório no GitHub.
2. Clique em **Add New → Project** e importe o repositório.
3. Em **Framework Preset** deixe **Other**. Não precisa de build command nem output directory.
4. Clique em **Deploy**. O endereço sai como `https://kelly-silva.vercel.app`.
   (Sem GitHub: instale a CLI com `npm i -g vercel` e rode `vercel` dentro da pasta.)

## 5. Editar links

Cada área clicável é uma linha `<a class="hit hit--NOME" href="...">` no `index.html`.
Mude só o `href`. O texto da mensagem do WhatsApp fica depois de `?text=` e está codificado
em URL. Para trocar, escreva a frase em https://www.urlencoder.org e cole o resultado.

| Classe | Onde fica no flyer | Link |
|---|---|---|
| `hit--logo` | logo e nome do studio | Instagram |
| `hit--c1` a `hit--c6` | os 6 cartões de serviços | WhatsApp |
| `hit--wa` | botão "Fale Comigo no WhatsApp" | WhatsApp |
| `hit--loc` | "João Alfredo e Surubim – PE" | Google Maps |
| `hit--igi` | ícone do Instagram | Instagram |
| `hit--wai` | ícone do WhatsApp | WhatsApp |

## 6. Editar posição e tamanho das áreas

As posições ficam no fim do bloco de áreas em `css/style.css` (`.hit--c1{ left; top; width; height }`),
em **% da imagem**. Para calcular a partir de pixels (imagem de 941 x 1672):

- `left = x / 941 * 100`
- `top = y / 1672 * 100`
- `width = largura / 941 * 100`
- `height = altura / 1672 * 100`

Para **ver** as áreas durante o ajuste, adicione temporariamente no CSS:

```css
.hit { outline: 2px solid lime; background: rgba(0,255,0,.25); }
```

Se trocar o flyer: substitua `assets/img/flyer.jpg`, atualize `width` e `height` da tag `<img>`
e refaça as porcentagens. Mantenha a proporção 9:16 para o layout continuar certo.
