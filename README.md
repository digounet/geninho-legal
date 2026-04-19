# legal-site — Geninho

Site estático com os documentos legais exigidos pela App Store e pela LGPD.
Publicado em **https://geninho.app.br** via GitHub Pages + domínio próprio.

## Estrutura

```
legal-site/
├── _config.yml                   # Config Jekyll (tema minima + URL do domínio)
├── CNAME                         # Domínio custom (geninho.app.br)
├── index.md                      # Página inicial com links
├── politica-de-privacidade.md
├── termos-de-uso.md
├── transparencia-e-seguranca.md
└── README.md                     # este arquivo
```

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

Aguarde 1–2 min. Em **Custom domain**, o GitHub deve ler o arquivo `CNAME` e já exibir `geninho.app.br`. Se não aparecer, digite manualmente e salve.

Depois marque **Enforce HTTPS** (pode levar até 24h para o certificado Let's Encrypt ser emitido).

### 3. Configurar DNS no seu registrador (Registro.br ou onde estiver)

Para o domínio **apex** (`geninho.app.br`), crie registros **A** apontando para os 4 IPs do GitHub Pages:

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

⚠️ **Remova qualquer registro A/AAAA/CNAME antigo** apontando para outro lugar no apex antes de criar os novos. O Registro.br costuma levar 5–60 min para propagar.

### 4. Validar

Depois que o DNS propagar, abra no navegador (navegação anônima recomendada):

- `https://geninho.app.br/` → página inicial
- `https://geninho.app.br/politica-de-privacidade.html`
- `https://geninho.app.br/termos-de-uso.html`
- `https://geninho.app.br/transparencia-e-seguranca.html`

Se HTTPS ainda não estiver ativo, o GitHub ativa o certificado automaticamente até 24h após o DNS propagar. Até lá, `http://` funciona.

### 5. Colar no App Store Connect

- **App Information → Privacy Policy URL:** `https://geninho.app.br/politica-de-privacidade.html`
- **App Information → Marketing URL (opcional):** `https://geninho.app.br`
- **App Information → Support URL:** `https://geninho.app.br` (ou, melhor, criar uma página `/suporte` depois)
- **Subscription Review Information → Terms of Service:** `https://geninho.app.br/termos-de-uso.html`

## Atualização futura

Quando a política ou termos mudarem:

1. Atualizar os `.md` em `documentation/legal/` (repo privado, fonte da verdade).
2. Copiar para `legal-site/` e manter o front-matter Jekyll no topo.
3. `cp -R legal-site/. ~/geninho-legal/` e `git commit && git push` no repo público.
4. O Pages republica em 1–2 min.

## Checklist antes de submeter à Apple

- [ ] DNS apontando para os IPs do GitHub Pages e propagado (testar `dig geninho.app.br`)
- [ ] `https://geninho.app.br/politica-de-privacidade.html` abre sem login
- [ ] `https://geninho.app.br/termos-de-uso.html` abre sem login
- [ ] Enforce HTTPS ativo no GitHub Pages
- [ ] Controlador identificado como "Pablo Rodrigo (desenvolvedor independente) — Recife/PE"
- [ ] Contato `suporte@geninho.app.br` configurado e respondendo
- [ ] URLs coladas no App Store Connect
