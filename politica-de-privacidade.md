---
layout: page
title: Política de Privacidade
permalink: /politica-de-privacidade.html
---

# Política de Privacidade — Geninho

**Última atualização:** 19 de abril de 2026

## 1. Quem somos e finalidade desta Política
O **Geninho** é um aplicativo iOS de apoio educacional para famílias brasileiras, focado em organização escolar, plano de estudos com IA e validação de conclusão por quiz.

Esta Política descreve, em linguagem clara, **quais dados tratamos, por que tratamos, com quem compartilhamos e quais direitos você tem** como titular, em conformidade com a **Lei Geral de Proteção de Dados Pessoais (Lei nº 13.709/2018 — LGPD)** e com as exigências da App Store.

**Controlador dos dados:**
- Responsável: **Pablo Rodrigo (desenvolvedor independente)**
- Jurisdição: Recife/PE — Brasil
- Canal de contato para privacidade, LGPD e segurança: **suporte@geninho.app.br**

Dados de identificação adicionais (documento e endereço completo) podem ser fornecidos mediante solicitação formal e fundamentada, nos termos da LGPD, através do canal de contato acima.

## 2. Princípios que adotamos
- **Minimização:** coletamos somente o necessário para o funcionamento do serviço.
- **Finalidade específica:** cada dado é usado para um propósito informado.
- **Transparência:** esta Política lista os fornecedores e os tipos de dado.
- **Segurança por padrão:** dados em trânsito e em repouso utilizam as proteções dos provedores listados na seção 6.
- **Controle parental:** perfis de crianças são criados e gerenciados apenas por um responsável com conta vinculada à mesma família.

## 3. Dados que tratamos

### 3.1 Dados de autenticação (responsável)
- e-mail;
- nome de exibição (quando fornecido pelo provedor);
- identificadores técnicos das contas (Firebase Auth UID, Apple Sign-In identifier, Google account ID quando aplicável);
- e-mail anônimo de relay da Apple, quando o usuário opta por "Ocultar meu e-mail".

**Biometria (Face ID / Touch ID)** é processada exclusivamente no dispositivo pelo iOS. O Geninho **não recebe nem transmite dados biométricos** — apenas o resultado booleano "autenticou / não autenticou".

### 3.2 Dados de família e crianças
- nome da família;
- papel dos usuários (`ownerParent`, `parent`, `child`);
- vínculos entre responsáveis e crianças;
- para cada criança: nome, ano/série escolar, configurações de estudo (janela de horário, duração, percentual mínimo de acerto no quiz, permissão de YouTube), moedas, streak e conquistas.

Crianças **não criam conta sozinhas**. O perfil é criado pelo responsável, que é titular do vínculo e responde pelos dados do menor (ver seção 9).

### 3.3 Dados escolares e pedagógicos
- escola(s) cadastrada(s) e períodos;
- grade de aulas por criança (matéria, dia, horário);
- plano do ano escolar (matérias, assuntos);
- provas/atividades (matéria, data, tópicos, nota quando informada);
- sessões de estudo geradas, concluídas ou não;
- resultados de quiz (percentual de acerto, tentativas, feedback sobre questões);
- perfil adaptativo por criança (melhores janelas de estudo, mastery por matéria/tópico).

### 3.4 Dados gerados por IA
- texto extraído por OCR de imagens/PDFs que você importa (grade, calendário de provas);
- perguntas enviadas pela criança ao **chat livre do Geninho** (Premium);
- respostas geradas por IA;
- **classificação automatizada** da pergunta (normal, pedido direto de gabarito, conteúdo inapropriado, suspeita) e razão, quando aplicável;
- perguntas classificadas como `direct_homework`, `inappropriate` ou `suspicious` ficam acessíveis ao responsável da família para revisão (coleção `flaggedQuestions`).

### 3.5 Dados de uso e assinatura
- contadores mensais de uso (planos de IA gerados, perguntas ao chat) para aplicar limites de plano;
- contadores totais (importações por OCR);
- identificador da transação de StoreKit e produto da assinatura (`com.geninho.app.premium.monthly` / `.yearly`) — **não recebemos dados de cartão**; a cobrança é 100% da Apple.

### 3.6 Dados técnicos e de publicidade (apenas plano gratuito)
- Na versão gratuita, exibimos anúncios do **Google AdMob**. Antes de solicitar anúncios personalizados, pedimos seu consentimento através do prompt nativo da Apple (**App Tracking Transparency — ATT**).
- Se você **autorizar** o rastreamento, o AdMob pode usar o IDFA (identificador de publicidade da Apple) para exibir anúncios mais relevantes.
- Se você **não autorizar**, o AdMob exibe apenas anúncios não personalizados, e o IDFA não é compartilhado.
- O Geninho **não** coleta IDFA para nenhum propósito além da exibição de anúncios no AdMob.

### 3.7 Notificações
O app usa **apenas notificações locais** (lembretes de estudo, provas próximas, conquistas). Não utilizamos serviço de push nem enviamos tokens de dispositivo a servidores externos.

## 4. Finalidades e bases legais (LGPD art. 7)

| Finalidade | Dados utilizados | Base legal |
|---|---|---|
| Criar e autenticar conta | e-mail, identificadores de provedor | Execução de contrato |
| Organizar rotina escolar | dados de 3.2, 3.3 | Execução de contrato |
| Gerar plano de estudos e quizzes com IA | 3.3 e 3.4 | Execução de contrato |
| Validar sessão de estudo por quiz | 3.3, 3.4 | Execução de contrato |
| Aplicar limites do plano Free e cobrar Premium | 3.5 | Execução de contrato |
| Moderação de chat e segurança de menor | 3.4 | Legítimo interesse + proteção do melhor interesse da criança |
| Exibir anúncios no plano gratuito | 3.6 | Consentimento (ATT) |
| Prevenir fraude e garantir segurança | logs operacionais | Legítimo interesse |
| Cumprir obrigações legais | quando exigido | Cumprimento de obrigação legal |

## 5. Processamento de imagens e IA

### 5.1 OCR
A extração de texto das imagens/PDFs importados é feita **no próprio dispositivo**, usando o framework Vision da Apple. As imagens **não** são enviadas para nossos servidores nem para provedores de IA.

### 5.2 Envio de texto à IA
Após o OCR, **apenas o texto extraído** (não a imagem) pode ser enviado a provedores de IA (ver seção 6) para estruturação em aulas, provas e assuntos. Recomendamos revisar os resultados antes de confirmar — IA pode cometer erros.

### 5.3 Chat com o Geninho
Perguntas feitas ao chat livre (Premium) e as respostas geradas trafegam pelo provedor de IA contratado. Não usamos essas conversas para treinar modelos de IA; os provedores listados na seção 6 têm cláusulas contratuais de não-treinamento para dados de API.

## 6. Operadores e fornecedores (com quem compartilhamos dados)

Compartilhamos dados **apenas com os fornecedores estritamente necessários** à operação do serviço:

| Fornecedor | Papel | Dados tratados | Local de processamento |
|---|---|---|---|
| **Google / Firebase** (Authentication, Firestore, Storage) | Autenticação e banco de dados | Todos os dados das seções 3.1 a 3.5 | EUA / multi-região |
| **Apple** (Sign in with Apple, StoreKit) | Login e cobrança de assinatura | Identificador Apple, transação de assinatura | EUA |
| **Google** (Google Sign-In) | Login opcional com conta Google | e-mail, identificador Google | EUA |
| **OpenAI** | Geração de quizzes, plano de estudos, OCR estruturado, chat | Texto (sem imagens) de 3.3 e 3.4 | EUA |
| **Google Gemini** | Fallback de IA | Idem | EUA |
| **Azure OpenAI** (quando configurado) | Provedor alternativo de IA | Idem | EUA / UE |
| **Google AdMob** | Anúncios no plano gratuito | 3.6 | EUA |

Os fornecedores acima atuam como **operadores** (art. 5º, VII da LGPD) sob instrução do Geninho. Não vendemos dados pessoais e não os compartilhamos para finalidades de marketing de terceiros.

### Transferência internacional
Os dados podem ser tratados em servidores localizados fora do Brasil (principalmente EUA). Os fornecedores listados adotam cláusulas contratuais e salvaguardas compatíveis com o art. 33 da LGPD.

## 7. Retenção e exclusão
- Dados da família, das crianças e de estudos são mantidos **enquanto a conta estiver ativa**.
- Registros de uso e limites de plano são mantidos pelo ciclo necessário para operar os planos Free e Premium.
- **Exclusão da conta:** disponível pelo próprio app ("Mais" → excluir conta) ou por e-mail a `suporte@geninho.app.br`. Após a solicitação, dados pessoais identificáveis são removidos dos sistemas ativos em até **30 dias**, observadas as obrigações legais e limitações técnicas de backups.
- Registros de transações de assinatura podem ser mantidos pelo prazo legal aplicável (fiscal/consumerista) mesmo após a exclusão da conta.

## 8. Segurança
- Conexões via HTTPS/TLS para todos os fornecedores.
- Credenciais de API **nunca** embarcadas em repositório público (armazenadas em `Config.xcconfig` local).
- Separação de permissões por papel (responsável x criança).
- Autenticação via provedores reconhecidos (Apple, Google, Firebase Auth).
- Biometria opcional para desbloquear o app no dispositivo.
- Revisão periódica de dependências e boas práticas.

Apesar dos controles, nenhum sistema é 100% imune. Ao identificar um incidente relevante que possa gerar risco a titulares, seguiremos os procedimentos previstos na LGPD (art. 48) e comunicaremos a ANPD e os titulares afetados quando aplicável.

## 9. Dados de crianças e adolescentes (LGPD art. 14)
- O Geninho é destinado a **famílias**, com perfis de crianças criados e operados **pelo responsável**.
- A base legal para tratar dados de menores é o **melhor interesse da criança**, mediante consentimento específico e em destaque do responsável no momento do cadastro do perfil.
- O responsável tem acesso a: dados cadastrais da criança, progresso escolar, perguntas feitas ao chat e itens classificados para revisão.
- Não exigimos mais dados da criança do que o necessário para a rotina escolar e o apoio pedagógico.
- O chat livre possui **classificação automatizada** que bloqueia conteúdo inapropriado e sinaliza pedidos de gabarito direto.
- O responsável pode, a qualquer momento, remover o perfil da criança no app.

## 10. Seus direitos (LGPD art. 18)
Você pode exercer, a qualquer momento, os seguintes direitos:

1. confirmação da existência de tratamento;
2. acesso aos dados;
3. correção de dados incompletos, inexatos ou desatualizados;
4. anonimização, bloqueio ou eliminação de dados desnecessários ou excessivos;
5. portabilidade dos dados;
6. eliminação dos dados tratados com base em consentimento;
7. informação sobre com quem compartilhamos dados;
8. informação sobre a possibilidade de não fornecer consentimento e suas consequências;
9. revogação do consentimento.

**Canal para exercer direitos:** `suporte@geninho.app.br`. Responderemos em até **15 dias** corridos, conforme art. 19 da LGPD.

Caso não obtenha resposta satisfatória, você pode recorrer à **Autoridade Nacional de Proteção de Dados (ANPD)** em [https://www.gov.br/anpd](https://www.gov.br/anpd).

## 11. Conteúdo gerado por IA — limitações
- Planos de estudo, quizzes e respostas do chat são apoios pedagógicos e **podem conter erros ou imprecisões**.
- O conteúdo não substitui professor, escola ou material didático oficial.
- Use a IA como ponto de partida; sempre revise com senso crítico.

## 12. Publicidade e rastreamento
- O plano Free exibe anúncios via Google AdMob.
- Pedimos seu consentimento para rastreamento via prompt nativo do iOS (App Tracking Transparency).
- Sua resposta à ATT pode ser alterada a qualquer momento em **Ajustes → Privacidade e Segurança → Rastreamento**.
- O plano Premium é **totalmente livre de anúncios**.

## 13. Atualizações desta Política
Podemos revisar esta Política para refletir mudanças legais, técnicas ou de produto. A versão vigente fica disponível dentro do app (tela **Documentos Legais**) e neste repositório. Alterações materiais serão comunicadas por canal apropriado (aviso no app ou e-mail).

## 14. Contato
- E-mail de privacidade / LGPD: **suporte@geninho.app.br**
- Encarregado pelo tratamento de dados: o canal de contato acima atende às solicitações previstas na LGPD. Por se tratar de operação de pequeno porte conduzida por desenvolvedor independente, aplica-se o tratamento flexibilizado previsto na Resolução CD/ANPD nº 2/2022 para agentes de tratamento de pequeno porte.

---

**Resumo visual rápido (não substitui o texto completo):**
- Não vendemos dados.
- Usamos Firebase, OpenAI/Gemini/Azure, AdMob e Apple/Google para funcionar.
- OCR roda no seu iPhone; só o texto extraído vai para a IA.
- Criança não cria conta sozinha — sempre um responsável.
- Você pode excluir sua conta e pedir cópia dos dados a qualquer momento.
