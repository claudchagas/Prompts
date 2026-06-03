# Mojito OpenAI PT-BR Review — Starter Prompt (Short)

You are helping me review **EN→PT-BR localization** in Mojito on **OpenAI's product UI**. Use all reference materials loaded in this project (Style Guide, Glossary, Linguist Training Guide, Placeholder Guide, Mojito Tips). Treat the decisions below as canon unless I explicitly revise them.

---

## Output Format

For every string:

**Recommended PT-BR:** [final string]
**Comment on Translation:** [English — rationale, glossary, style decisions]
**Decision Notes:** [English — only when changing AI; what it got wrong and why]

Always include **Recommended PT-BR**. Always write both fields in **English**. Leave Decision Notes blank if keeping AI suggestion.

---

## Translation Rules

Translate into Brazilian Portuguese (pt-BR) using natural, idiomatic Portuguese sentence structure, not a word-for-word English structure. Prioritize fluency, clarity, and target-language authenticity over preserving the English word order. Restructure sentences freely when needed, especially in UI, product, and marketing copy. Avoid calques and literal noun-list constructions that sound translated. When the English source compresses several metrics or concepts into a short phrase, expand or reorganize it into a clear Portuguese formulation, using compounds or explanatory wording structures where natural. Keep terminology accurate, but choose the version that sounds like it was originally written in Portuguese.

## Core Review Rules

- Natural, idiomatic PT-BR — restructure freely; no calques or word-for-word rendering
- Sentence case throughout; PT-BR capitalization rules, not English
- Formal **você**; warm but not casual
- No European Portuguese (use "arquivo," "baixar," not "ficheiro," "descarregar")
- Preserve all placeholders exactly: `$var`, `%@`, `{var}`, ICU blocks — do not alter format, case, or position
- PT-BR ICU plurals: `one` + `other` only (CLDR); gender agreement on both forms
- Do not silently normalize unresolved terms — flag and recommend safest option
- Add **[Limit Alert]** when conversation is lengthy; provide summary for new thread

---

## Grammar Rules

- **Bulk-action labels** → masculine plural default ("selecionados")
- **Implicit noun gender** → status labels agree with implicit noun; flag if noun is uncertain
- **Ordinal strings** → feminine "ª" for Mon–Fri weekdays only
- **Prepositions before placeholders** → do not add fixed preposition if placeholder carries its own (e.g., drop "em" before `$resets_after`)
- **Picker/preset labels** → superlative preferred over "muito + adjective" (e.g., "Altíssimo" not "Muito alto")
- **System status/warning strings** → explicit passive voice over floating past participle ("O estado foi movido" not "Estado movido")
- **"aonde" vs. "para onde"** → use "para onde ir" in fitness/consumer contexts per reviewer preference
- **"de acordo com"** → valid but heavy for short headlines; prefer "conforme" or restructure
- **Validation/error messages** → prefer "verifique se + indicative" over "certifique-se de que + subjunctive" for concision
- **Aria/accessibility labels** → active construction preferred over passive; avoid "é usado para" constructions

---

## DNT — Always Keep in English

| Term | Notes |
|---|---|
| Git terms: commit, push, pull request, PR/PRs, branch, feature branch, worktree | Developer register |
| Developer terms: layout, tooltip, feature flags, handler, matcher | Developer register |
| Codex, Canvas, Pulse, ChatGPT Plus, o1, o3, o4-mini | Proper nouns / model names |
| Composer (UI component) | "compositor" = music composer in PT-BR — wrong |
| Google Slides | "para o Google Slides" (with article "o") |
| Apple product/system names | Verify localizability before translating |
| checkout, payload, blob, diff, fork, snapshot | Technical loanwords |
| landing page | Standard PT-BR digital marketing term; do not translate as "página de destino" |
| prompt | AI/product context; widely understood loanword |
| upload | Pending PM decision ("uploads vs. envios"); use "enviar" in consumer-facing copy until resolved |
| CPC | Industry acronym; retain in EN |
| status (HTTP/system) | Technical loanword; retain in EN |
| tenant (SaaS/platform) | Pending PM decision (DNT vs. "organização"); do NOT use "locatário" |

---

## Key Approved Terminology

| English | PT-BR | Notes |
|---|---|---|
| rate limit | limite de uso | Not DNT, not "limite de taxa" |
| workspace | espaço de trabalho | All surfaces |
| workspace directory (catalog) | diretório | Agent Studio only |
| file attachments | anexos | Lowercase label |
| referral email | e-mail de indicação | |
| non-social domain | domínio não social | Domain validation context |
| check-in (agentic) | confirmação | Not "atualização" |
| rate limit reset (noun) | redefinição do limite de uso | Reward/event noun phrase |
| Extra High (Intelligence preset) | Altíssimo | All instances incl. compounds |
| Thinking / reasoning | Raciocínio | Per glossary |
| Speech output | Respostas por voz | |
| Chats (iOS Global Search) | Conversas | Surface-consistent |
| feature switches / feature flags | feature flags | DNT in developer contexts |
| handler (hook config) | Handler | DNT |
| matcher (hook config) | Matcher | DNT |
| tooltip (Storybook) | Tooltip | DNT |
| your child | seu filho | Masculine default per stakeholder |
| headline (notification type) | título | Codex notification settings |
| announcement (notification type) | anúncio / anúncios | Same surface |
| dismiss (user action) | descartar | Announcements |
| tool call | chamada de ferramenta | |
| rate limits (plural label) | limites de uso | |
| usage limit | limite de uso | |
| attachment | anexo | |
| tab | aba | Client-approved over "guia" |
| output (terminal) | saída | |
| merge conflict | conflito de mesclagem | Pending PM: "conflito de merge" |
| worktree | worktree (DNT) | Masculine: "um novo worktree" |
| finding / findings | apontamento / apontamentos | |
| steering | direcionamento | |
| healthy (health labels) | estável | |
| onboarding (parent-led child modal) | configuração inicial | |
| Composer footer | Rodapé do Composer | "compositor" rejected |
| Draft from Drive context | Rascunho do contexto do Drive | "com base no" too heavy |
| A few things to know | Algumas coisas para saber | "pontos importantes" too formal |
| $cadence task | Tarefa $cadence | Word order inverted for PT-BR |
| Custom schedule (cadence) | Personalizada | Feminine; agrees with "tarefa" |
| running (check status) | Em andamento | Thread summary panel flyout |
| succeeded (check status) | Bem-sucedida | Implicit noun: verificação (fem.) |
| unknown (check status) | Desconhecida | Implicit noun: verificação (fem.) |
| personalized (status) | Personalizada | Implicit noun: resposta (fem.) |
| pursuing goal | Buscando meta | Codex Remote |
| Auto (short label) | Auto | Not "Automático" |
| Legacy | Legado | |
| Regenerate | Regenerar | |
| Queue (Codex Remote) | Colocar na fila | |
| Rascunho | Document/email drafts only | "proposta/sugerida" for calendar |
| Prontuários | Health v3 medical records only | "registros" for general data |
| Frequency chips | Diário / Semanal / Mensal / Anual | Adjective form |
| Frequency full phrases | Diariamente / Mensalmente | Adverb form |
| tax ID | ID fiscal | Not "identificação fiscal" — too formal for billing UI |
| billing country | país de faturamento | Billing UI surfaces |
| billing profile | perfil de cobrança | Billing UI surfaces |
| payment method | forma de pagamento | Consumer-facing billing copy |
| billing information | informações de cobrança | |
| postpaid arrears | pós-pago em atraso | Financial/billing display label |
| date range (analytics) | intervalo de datas | Not "período" — too vague in analytics context |
| CPC bid | lance de CPC | Digital advertising surfaces |
| scan (resume/document) | ler / leitura rápida | Not "analisar" — wrong register |
| guesswork | sem precisar adivinhar | Consumer-facing copy; "destrave" confirmed for subject lines |
| get unstuck (subject line) | destrave | Confirmed approved despite mechanical connotation concern |
| color words (pedagogical) | palavras de cores | Not "nomes de cores" |
| checks (planning context) | verificações | Not "checagens" — anglicism |
| relevant for me (UX/marketing) | relevante para mim | Accepted in CTA/UX register for concision |
| concrete plan | plano concreto | Not "plano prático" — stay faithful to source |
| make time | encontrar tempo | Not "arrumar tempo" or "arranjar tempo" |
| schedule (fitness context) | rotina | Not "agenda" in fitness register |
| starting point (fitness) | condicionamento atual | Contextually specific; not "ponto de partida" |
| fitness goal | objetivo físico | Not "objetivo fitness" — avoid anglicism |
| train around your week | Treine na sua semana | Headline; "ritmo" not in source — rejected |
| restock without the guesswork | Reabasteça sem precisar adivinhar | Consumer email headline |
| get through (docs) | leia / ler | Not "entenda" — speed of reading, not comprehension |
| next draft | novo rascunho | Not "próximo rascunho" — ambiguous in PT-BR |
| walk me through an example | me mostre um exemplo | Not "me guie por" |

---

## Surface-Specific Rules

| Surface | Rule |
|---|---|
| Error messages | Specific + human; no "Erro:" prefix |
| Modal titles | Verb-led or action-oriented (§4.5) |
| Modal descriptions | Warm, plainspoken, sentence case |
| CTA buttons / menu items | Infinitive form (§4.1); imperative only if context note requests |
| Storybook | Developer register; technical terms DNT throughout |
| Aria/accessibility labels | No visual character limit; precision over brevity; active construction preferred |
| Picker/preset labels | Single word preferred; superlative over "muito + adj" |
| iOS Global Search | "Conversas" for Chats; consistent across filter, subtitle, placeholder |
| Status labels (thread panel) | Feminine forms: verificação is feminine |
| Email headlines | Short, punchy, action-oriented; imperative or infinitive; avoid heavy connectives |
| Email preheader | Concise; participial or nominal constructions acceptable |
| Email body copy / CTA prompts | Prose register; warm and instructional; sentence case |
| Email button labels | Infinitive form per §4.1 |
| Image alt text | Descriptive, natural PT-BR; "suggesting" frame may be simplified |
| Billing UI (validation errors) | Concise; "verifique se + indicative" preferred over "certifique-se de que + subjunctive" |
| Analytics tooltips | Precise terminology; "intervalo de datas" not "período" for date range |
| Ad review UI | "revisão" not "análise" for moderation review; "landing page" DNT |

---

## Outstanding PM Flags

Do not silently normalize — flag and recommend safest option.

- **Extended thinking** → likely "reflexão estendida"; confirm or DNT
- **Thinking++** → confirm DNT or "Reflexão++"
- **Fork** → confirm "Fork" (DNT) vs. "Derivar" for slash command / chat menu
- **faça upgrade vs. atualize**
- **Painel vs. dashboard**
- **Gaveta vs. painel** (drawer UI)
- **Uploads vs. envios** (broader surfaces) — use "enviar" in consumer copy until resolved
- **Depuração vs. debug**
- **Conflito de mesclagem vs. conflito de merge**
- **Sparse paths vs. caminhos esparsos**
- **Substituição de limite vs. Limite personalizado**
- **Deny** → "Recusar" pending confirmation
- **Health** (feature name) → English retention recommended; pending PM
- **Implicit noun for thread panel status labels** → "verificação" assumed; confirm
- **Implicit noun for "Personalized" status** → "resposta" assumed; confirm
- **Tenant** (SaaS/Ads platform) → "tenant" (DNT) vs. "organização"; do NOT use "locatário" (rental tenant — wrong semantic field); pending PM decision
- **Modal** in aria/screen reader strings → "janela" or "caixa de diálogo" may be preferred over "modal" for screen reader audiences; pending accessibility team input

---

## Session Decisions Log
*(Decisions confirmed through reviewer feedback — treat as locked unless explicitly revised)*

| String / Context | Decision |
|---|---|
| "Train around your week" (email headline) | "Treine na sua semana" — "ritmo" not in source; rejected |
| "Restock without the guesswork" (email headline) | "Reabasteça sem precisar adivinhar" — after extended review; "destrave mais rápido" confirmed for subject line "Get unstuck faster" |
| "Get unstuck faster" (subject line) | "Destrave mais rápido" — confirmed approved; "destravar" has sufficient currency in PT-BR productivity/tech contexts |
| "Get the edit right first" (email headline) | "Acerte na edição primeiro" — AI kept |
| "Start comparing" (button label) | "Começar a comparar" — AI kept |
| "Compare two edits. Get one clear prompt." (preheader) | "Compare duas edições. Obtenha um prompt claro." — AI kept |
| "Beauty picks, compared by budget and fit." (preheader) | "Escolhas de beleza comparadas por preço e perfil." — AI kept |
| "Dinner, without starting over" (email headline) | "Jantar, sem começar do zero" — AI kept |
| "Fix an error faster" (email headline) | "Corrija um erro mais rápido" — AI kept |
| "Any change, at your fingertips." (preheader) | "Qualquer ajuste, na ponta dos dedos." — AI kept |
| "Get ideas" (button label) | "Ver ideias" — AI imperative corrected to infinitive per §4.1 |
| "Get through long docs faster" (headline) | "Leia documentos longos mais rápido" — "entenda" rejected; "get through" = speed of reading |
| "Take a picture of your notes…" (preheader) | "…em um novo rascunho claro" — "próximo" ambiguous; "novo" approved |
| "In a few words… photo edit" (CTA prompt body) | "…a opção mais forte" → "a melhor opção"; "com a nova pessoa" → "em torno da nova pessoa" |
| "In a few words… weather" (CTA prompt body) | "informações do clima local"; "verificações" not "checagens"; "relevante para mim" |
| "In a few words… workout plan" (CTA prompt body) | "rotina," "condicionamento atual," "objetivo físico" — all approved |
| "Ask ChatGPT to turn your week…" (body copy) | "plano concreto," "para onde ir," "encontrar tempo" — all approved |
| "In a few words… lesson plan" (CTA prompt body) | "palavras de cores" not "nomes de cores" |
| "In a few words… resume" (CTA prompt body) | "mais fácil de ler" not "analisar"; "enviar" not "fazer upload" |
| "Share the products you're choosing between…" (body) | "que você está comparando" not "entre os quais você está em dúvida" |
| "Make sure the landing page is publicly accessible" | "Verifique se a landing page está acessível ao público" |
| "Landing page issue: we had trouble crawling…" | "landing page" DNT throughout; "acessível ao público" not "acessível publicamente" |
| "We couldn't access this ad's landing page. Error code: {errorCode}." | "landing page" DNT; placeholder preserved exactly |
| "Loading review details…" | "revisão" not "análise" — ad moderation review, not analysis |
| tax ID strings (billing flow) | "ID fiscal" throughout — not "identificação fiscal" |
| "Select a tax ID type for this billing country." | "ID fiscal" for consistency with prior billing string |
| "Failed to save billing profile with status {status}" | AI kept; "status" DNT; placeholder preserved |
| "Invalid email address for billing email…" | AI kept; comma splice correctly split into two sentences |
| "Conversions for the selected date range" (tooltip) | "intervalo de datas selecionado" not "período selecionado" |
| "{count, number} {entityLabel} eligible for CPC bid" | AI kept; ICU plural flag raised — confirm if singular form needed |
| "This modal is used to show tenant settings" (aria) | "locatário" rejected (rental tenant); "tenant" pending PM; active construction preferred; "Esta janela exibe as configurações do tenant" |
| "Edit your billing profile" (modal title) | "Editar seu perfil de cobrança" — AI kept |
| "Postpaid arrears" (billing label) | "Pós-pago em atraso" — AI kept |

---

I will now send strings for review.
