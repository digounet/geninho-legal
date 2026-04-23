# legal-site — Geninho

Site público do Geninho: **landing page + documentos legais** exigidos pela App Store e pela LGPD.
Publicado em **https://geninho.app.br** via GitHub Pages + domínio próprio.

Disponível em **três idiomas**: pt-BR (padrão), en, es. Cada idioma tem sua
landing e seu conjunto completo de documentos legais sob um subpath diferente.

## Estrutura

```
legal-site/
├── _config.yml                        # Jekyll (tema minima + defaults por pasta)
├── CNAME                              # Domínio custom (geninho.app.br)
│
├── index.html                         # Landing pt-BR           → /
├── politica-de-privacidade.md         # pt-BR                   → /privacidade/
├── termos-de-uso.md                   # pt-BR                   → /termos/
├── transparencia-e-seguranca.md       # pt-BR                   → /transparencia/
│
├── en/
│   ├── index.html                     # Landing EN              → /en/
│   ├── privacy-policy.md              # EN                      → /en/privacy/
│   ├── terms-of-use.md                # EN                      → /en/terms/
│   └── transparency-and-security.md   # EN                      → /en/transparency/
│
├── es/
│   ├── index.html                     # Landing ES              → /es/
│   ├── politica-de-privacidad.md      # ES                      → /es/privacidad/
│   ├── terminos-de-uso.md             # ES                      → /es/terminos/
│   └── transparencia-y-seguridad.md   # ES                      → /es/transparencia/
│
├── assets/                            # Compartilhadas pelas 3 landings
│   ├── geninho.png / geninho.mp4 / …
└── README.md                          # este arquivo
```

As três `index.html` são **auto-contidas** (CSS inline, sem tema). Usam a mesma
paleta e estrutura; apenas o texto, o `<html lang>`, o estado ativo do seletor
de idioma e os links de docs legais no rodapé mudam.

Os `.md` legais usam o tema `minima` com `layout: page` e trazem um seletor de
idioma no topo do corpo (PT · EN · ES) para permitir troca entre versões.

## URLs públicas

| Documento | pt-BR (autoritativo) | EN | ES |
|---|---|---|---|
| Landing | `https://geninho.app.br/` | `https://geninho.app.br/en/` | `https://geninho.app.br/es/` |
| Privacidade | `/privacidade/` | `/en/privacy/` | `/es/privacidad/` |
| Termos | `/termos/` | `/en/terms/` | `/es/terminos/` |
| Transparência | `/transparencia/` | `/en/transparency/` | `/es/transparencia/` |

> As versões en/es são **traduções de cortesia**. Em caso de divergência, a
> versão em português prevalece — cada doc traz esse aviso no topo.

## Como publicar (passo a passo)

### 1. Criar repositório público no GitHub

Sugestão de nome: `geninho-legal` ou `geninho-site`.

```bash
mkdir ~/geninho-legal && cd ~/geninho-legal
cp -R /Users/pablo/Source/Swift/Geninho/legal-site/. .
git init -b main
git add .
git commit -m "Initial: legal docs for Geninho"
git remote add origin https://github.com/<seu-usuario>/geninho-legal.git
git push -u origin main
```

### 2. Ativar GitHub Pages

No GitHub: repo `geninho-legal` → **Settings → Pages**

- **Source:** Deploy from a branch
- **Branch:** `main`
- **Folder:** `/ (root)`
- **Save**

Aguarde 1–2 min. Em **Custom domain**, o GitHub deve ler o arquivo `CNAME` e já
exibir `geninho.app.br`. Se não aparecer, digite manualmente e salve.

Depois marque **Enforce HTTPS** (pode levar até 24h para o certificado
Let's Encrypt ser emitido).

### 3. Configurar DNS no seu registrador (Registro.br ou onde estiver)

Para o domínio **apex** (`geninho.app.br`), crie registros **A** apontando para
os 4 IPs do GitHub Pages:

| Tipo | Nome | Valor | TTL |
|---|---|---|---|
| A | `@` (ou vazio) | `185.199.108.153` | 3600 |
| A | `@` | `185.199.109.153` | 3600 |
| A | `@` | `185.199.110.153` | 3600 |
| A | `@` | `185.199.111.153` | 3600 |

Opcionalmente, registros **AAAA** (IPv6):

| Tipo | Nome | Valor |
|---|---|---|
| AAAA | `@` | `2606:50c0:8000::153` |
| AAAA | `@` | `2606:50c0:8001::153` |
| AAAA | `@` | `2606:50c0:8002::153` |
| AAAA | `@` | `2606:50c0:8003::153` |

Para redirecionar `www.geninho.app.br` → `geninho.app.br`:

| Tipo | Nome | Valor |
|---|---|---|
| CNAME | `www` | `<seu-usuario>.github.io` |

⚠️ **Remova qualquer registro A/AAAA/CNAME antigo** apontando para outro lugar
no apex antes de criar os novos. O Registro.br costuma levar 5–60 min para propagar.

### 4. Validar

Depois que o DNS propagar, abra no navegador (navegação anônima recomendada):

```
https://geninho.app.br/                          ← landing pt-BR
https://geninho.app.br/privacidade/
https://geninho.app.br/termos/
https://geninho.app.br/transparencia/

https://geninho.app.br/en/                       ← landing EN
https://geninho.app.br/en/privacy/
https://geninho.app.br/en/terms/
https://geninho.app.br/en/transparency/

https://geninho.app.br/es/                       ← landing ES
https://geninho.app.br/es/privacidad/
https://geninho.app.br/es/terminos/
https://geninho.app.br/es/transparencia/
```

Se HTTPS ainda não estiver ativo, o GitHub ativa o certificado automaticamente
até 24h após o DNS propagar. Até lá, `http://` funciona.

### 5. Preencher o App Store Connect (override por localização)

O ASC permite **um `Privacy Policy URL` por localização do app**. Para cada
idioma habilitado no app, entre em **App Store Connect → My Apps → Geninho →
App Information** e, no seletor de idioma no topo da página, alterne entre os
idiomas para setar URLs diferentes:

| Localização no ASC | Privacy Policy URL | Marketing URL | Support URL |
|---|---|---|---|
| Brazilian Portuguese (pt-BR) | `https://geninho.app.br/privacidade/` | `https://geninho.app.br` | `https://geninho.app.br` |
| English (U.S.) / English (U.K.) | `https://geninho.app.br/en/privacy/` | `https://geninho.app.br/en/` | `https://geninho.app.br/en/` |
| Spanish (Mexico) / Spanish (Spain) | `https://geninho.app.br/es/privacidad/` | `https://geninho.app.br/es/` | `https://geninho.app.br/es/` |

Para **Terms of Service** (aparece em Subscription Review Information):

| Localização | Terms URL |
|---|---|
| pt-BR | `https://geninho.app.br/termos/` |
| en | `https://geninho.app.br/en/terms/` |
| es | `https://geninho.app.br/es/terminos/` |

> A Apple **exige** que a Privacy Policy URL esteja preenchida para cada
> localização habilitada. Se você deixar em branco, o ASC copia a da
> localização padrão (pt-BR) — aceitável como fallback, mas a experiência
> correta é apontar para a versão no idioma do usuário.

## Atualização futura

Quando a política ou termos mudarem:

1. Atualizar **primeiro** os `.md` em `documentation/legal/pt-BR/` (fonte da verdade).
2. Atualizar as versões en/es em `documentation/legal/en/` e `documentation/legal/es/`.
3. Refletir nos `.md` Jekyll em `legal-site/{,en/,es/}*.md` (o front-matter
   deve permanecer; só o corpo muda).
4. `cp -R legal-site/. ~/geninho-legal/` e `git commit && git push` no repo público.
5. O Pages republica em 1–2 min.

## Checklist antes de submeter à Apple

- [ ] DNS apontando para os IPs do GitHub Pages e propagado (testar `dig geninho.app.br`)
- [ ] `https://geninho.app.br/` abre a landing pt-BR sem login
- [ ] `https://geninho.app.br/en/` abre a landing EN sem login
- [ ] `https://geninho.app.br/es/` abre a landing ES sem login
- [ ] Os 3 docs legais de cada idioma abrem e têm o aviso de "cortesia" no topo (en/es)
- [ ] Seletor de idioma PT · EN · ES aparece em todas as páginas
- [ ] Enforce HTTPS ativo no GitHub Pages
- [ ] Controlador identificado como "Pablo Rodrigo (desenvolvedor independente) — Recife/PE"
- [ ] Contato `suporte@geninho.app.br` configurado e respondendo
- [ ] Botão "App Store" / "Download on the App Store" / "Descargar en la App Store" nas 3 landings apontando para a URL real do app após aprovação
- [ ] URLs coladas no App Store Connect **para cada localização habilitada do app** (pt-BR + en + es)
