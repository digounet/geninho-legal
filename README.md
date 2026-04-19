# legal-site — Geninho

Site estático com os documentos legais exigidos pela App Store e pela LGPD.
Esta pasta foi preparada para ser publicada em um **repositório público** (o repo principal `Geninho` é privado e não expõe GitHub Pages no plano Free).

## Estrutura

```
legal-site/
├── _config.yml                   # Config Jekyll (tema minima)
├── index.md                      # Página inicial com links
├── politica-de-privacidade.md
├── termos-de-uso.md
├── transparencia-e-seguranca.md
└── README.md                     # este arquivo
```

## Como publicar (passo a passo)

### Opção A — GitHub Pages a partir de repo público (recomendada)

1. **Criar repo público** na sua conta GitHub (ex.: `geninho-legal`).

2. **Copiar o conteúdo** desta pasta para o novo repo:
   ```bash
   # na sua máquina, fora do repo privado:
   mkdir ~/geninho-legal && cd ~/geninho-legal
   cp -R /Users/pablo/Source/Swift/Geninho/legal-site/. .
   git init -b main
   git add .
   git commit -m "Initial: legal docs for Geninho"
   git remote add origin https://github.com/<seu-usuario>/geninho-legal.git
   git push -u origin main
   ```

3. **Ativar GitHub Pages**:
   - No GitHub, abra o repo `geninho-legal` → **Settings** → **Pages**
   - Em **Source**, selecione **Deploy from a branch**
   - Branch: `main`, pasta: `/ (root)`
   - Save

4. **Aguardar 1–2 minutos**. A URL publicada fica em:
   ```
   https://<seu-usuario>.github.io/geninho-legal/
   ```

5. **Testar no navegador** (deve abrir sem login):
   - `https://<seu-usuario>.github.io/geninho-legal/`
   - `https://<seu-usuario>.github.io/geninho-legal/politica-de-privacidade.html`
   - `https://<seu-usuario>.github.io/geninho-legal/termos-de-uso.html`

6. **Colar as URLs no App Store Connect**:
   - **App Information → Privacy Policy URL** → URL da política
   - **App Information → License Agreement** (ou nota nos metadados da versão) → URL dos termos
   - **Subscription Review Information → Terms of Service** → URL dos termos

### Opção B — Domínio próprio (se você tiver geninho.com.br)

1. Na pasta do site, criar arquivo `CNAME` com o domínio (ex.: `legal.geninho.com.br`).
2. No painel DNS do domínio, apontar um registro CNAME `legal` → `<seu-usuario>.github.io`.
3. No GitHub Pages do repo `geninho-legal`, em **Settings → Pages → Custom domain**, adicionar o domínio.
4. Aguardar verificação + HTTPS (pode levar alguns minutos).

### Opção C — Cloudflare Pages (deploy direto deste repo privado)

Útil se quiser manter tudo em **um único repo privado**.

1. Criar conta gratuita em [Cloudflare Pages](https://pages.cloudflare.com/).
2. Conectar ao GitHub e autorizar o repo privado `Geninho`.
3. Em **Build settings**, definir:
   - **Build command:** (deixar vazio)
   - **Build output directory:** `legal-site`
   - **Root directory:** (deixar vazio)
4. Deploy → URL `<projeto>.pages.dev` fica pública.

⚠️ Cloudflare Pages **não** converte Markdown automaticamente. Para essa opção, seria preciso gerar HTML (ex.: executando Jekyll localmente e publicando o HTML gerado). Para simplicidade, **prefira a Opção A**.

## Atualização futura

Quando a política ou termos mudarem:
1. Atualizar os `.md` em `documentation/legal/` (no repo privado, fonte da verdade).
2. Copiar os arquivos atualizados para `legal-site/` (manter o front-matter Jekyll no topo).
3. No repo público, commitar e push — o Pages atualiza em 1–2 minutos.

## Checklist antes de submeter à Apple

- [ ] URL da política de privacidade abre no navegador **sem login**
- [ ] Controlador identificado como "Pablo Rodrigo (desenvolvedor independente) — Recife/PE"
- [ ] Termos estão acessíveis na mesma URL raiz
- [ ] Contato `suporte@geninho.app.br` está configurado e respondendo
- [ ] URLs coladas no App Store Connect
