# Choisir ses technologies d'agents

> Version Markdown du contenu **affiché à l'écran** dans `presentation.html` (17 slides).
> Source de vérité = `presentation.html`. Les slides sont désignées par leur nom, jamais par un numéro.
> Le contenu des slides « maquette d'archi » et « archi AWS » est généré en JS (boîtes) — il est restitué ici sous forme de listes/tableaux.

---

## 1 · Titre (couverture)

**EBG · 25 juin 2026**

# Choisir ses technologies d'agents

Une grille de décision, pas un catalogue d'outils.

**Jonathan Gross** · Ingénieur Senior Data & AI — **Maxime Lamborelle** · Consultant Senior Data & AI

25 juin 2026 · Klee Group

---

## 2 · Klee Group — Conseil & Déploiement

## Klee Group : Conseil & Déploiement

> **[bandeau]** La puissance de l'AI, l'expertise de Klee Group : dopez vos services numériques métier, sans compromis sur la qualité et la sécurité.

**Conseil & Solutions**

- **Conseil en Transformation** — Stratégie & cadrage de la transformation · Conduite du changement & UX/UI · Innovation & design de service
- **Développement applicatif** — Solutions sur mesure, évolutives & sécurisées · Modèles spécifiques, hybride ou low code · Plateforme modulaire & interopérable
- **FP&A, Conso & ESG** — Pilotage de la performance financière · Clôture, consolidation & reporting · Plateformes (OneStream) & ESG
- **Solutions Atlassian, EasyVista** — Partenaire Platinum Atlassian · Collaboration, agilité & efficacité · Environnements de travail hybrides
- **AI & Data** — Gouvernance & compliance et valorisation des données · IA générative, prédictive & agentique · AI & Data platforms
- **Agence digitale** — Expériences utilisateurs fluides & sans couture · Parcours omnicanaux hyper personnalisés · Engagement & fidélisation

**Centre d'excellence**

- **Cybersécurité** — Sensibilisation, audit technique & Security by Design
- **DevSecOps** — Automatisation, supervision & sécurité intégrées
- **Cloud** — Adoption, migration & exploitation, FinOps & GreenOps

> **[bandeau]** **Une approche globale, un ancrage métier fort** · de l'idée à la solution opérationnelle, durable & industrielle

---

## 3 · Klee Group — Focus offre AI & Data

## Klee Group : Focus sur offre AI & DATA : 4 piliers, 2 dimensions transverses.

> **[bandeau — Conseil – Stratégie AI & Data]** Cadrage stratégique, business case, roadmap de transformation - approche pragmatique & agnostique

- **Gouvernance Data & AI** — Data & AI Compliance (RGPD, KYC, IA Act, Agec, PPD, …) · Data & AI Governance, Observability · Data Catalog & Lineage · CDO Dashboard & Data Governance opérationnelle · Politiques & éthique, Sécurité et conformité
- **Architecture AI & Data** — Stacks data modernes, Data Platform · Data Management & Data Quality · Plateformes Agentique, AI RAG et ML · Master Data Architecture · Infrastructure Cloud · Standards et bonnes pratiques
- **Build & Run** — Développer, tester, déployer et opérer des plateformes data modernes & Plateformes AI industrialisées · Master Data Repository (Customer, Supplier Product, Asset, Location, Employés, …) · Product Information Management project
- **IA ML, Générative et Agentique** — Roadmap Data & AI · Transformation AI & Adoption · DataScience and ML accelerator (Scoring and valeur Client, Fraude, Risque, …) · Gouvernance & structuration des corpus documentaire AI RAG

> **[bandeau — Conduite du changement]** Acculturation, montée en compétences, évolution culturelle · alignement & adoption durable

---

## 4 · La question posée

**La question posée**

## « Choisir ses technologies d'agents »

| Famille | Options | Verdict (gag) |
|---|---|---|
| **Frameworks open-source** | LangGraph · CrewAI · AutoGen — frameworks de développement d'agents (comportement, prompts, tools…) | C'est pareil |
| **Code vs Low-code/No-code** | | Pas important |
| **Frameworks des clouds** | Bedrock Agents · Vertex Agent Builder · Foundry Agent Service | C'est pareil |
| **Frameworks SaaS métier** | Agentforce (Salesforce) — agents collés aux données de l'éditeur | Parfait si répond au besoin, sur vos données |
| **Type de modèle & localisation** | API propriétaire → API sur AWS/Azure/GCP → Modèle sur vos VM (sur AWS/Azure/GCP) → Modèle open-source en local | Demandez à votre RSSI |

> **Notre angle —** Ces choix technologiques ne sont pas si compliqués.

---

## 5 · Le vrai chantier

**Le vrai chantier**

## Implémenter son premier agent

1. **Définir et cadrer le use case** — Audience · intégrations · gouvernance · tests · …
2. **Choisir la techno & l'archi** *(non bloquant)*
3. **Construire**
4. **Évaluer** — Jeux de tests · métriques · non-régression · red-teaming
5. **Exploiter** — Observabilité · maîtrise des coûts · itération en production

> **Notre angle —** Les choix techno, c'est **1 étape sur 5** — ne restez pas bloqués dessus. Ce qui va faire réussir (ou échouer) un agent, c'est tout le reste.

---

## 6 · La méthode

**La méthode**

## Bien choisir sa techno d'agent — en 3 réflexes

**① Situez le use case sur l'échelle d'autonomie.**
Le niveau d'autonomie visé commande tout le reste.

**② Bâtissez un socle agentique réutilisable.**
Un même socle — runtime, mémoire, identité, gateway, garde-fous, observabilité — accueille **tous** vos use cases, **à tous les échelons**.

**③ Repérez où se loge vraiment le lock-in.**
Le modèle et le framework se changent ; le runtime, lui, vous engage. Choisissez-le en conscience.

> Le **socle reste le même** ; c'est le **niveau d'autonomie** du use case qui **dimensionne ce qu'on pose dessus**.

---

## 7 · L'échelle d'autonomie

**La colonne vertébrale**

## L'échelle d'autonomie — illustrée par Léa, au Service Client

| N | Niveau | Définition | Le cas de Léa | Famille |
|---|---|---|---|---|
| 1 | **Chatbot sécurisé** | résume, reformule, rédige (texte fourni) | « Résume ce mail de réclamation, corrige mon brouillon de réponse » — sur le texte fourni, le conseiller envoie | GenAI · humain |
| 2 | **Copilot d'entreprise** | ancré sur les données internes | Résume l'historique du client *+ la politique* et rédige la réponse personnalisée | GenAI · humain |
| 3 | **Agent borné** | accomplit *une* tâche dans des limites fixées | Traite le remboursement < seuil, escalade au-dessus, refuse la fraude | Agentique · supervisé |
| 4 | **Agent end-to-end** | mène une tâche de bout en bout, sous supervision | Gère la réclamation de bout en bout : remboursement + relivraison + notif | Agentique · supervisé |
| 5 | **Système multi-agents** | plusieurs agents s'orchestrent à travers les domaines | Un superviseur orchestre service + logistique + anti-fraude + compta | Agentique · gouverné |

> Le **même besoin** de Léa gravit l'échelle — plus d'autonomie = plus de **valeur** ET plus de **risque** à gouverner.

---

## 8 · L'architecture qui se déforme (maquette d'archi)

**L'architecture qui se déforme**

## Une seule archi — les boîtes s'allument selon l'échelon

Légende : **allumée** / **gouvernance renforcée** / **éteinte** — le **socle partagé** sert tous les use cases.

**Les 11 boîtes en 2 zones :**

*Zone use case*
- **Logique d'agent & prompt** — framework mince
- **Outils & connecteurs métier** — actions métier
- **Connaissance & policy (RAG)** — RAG · règles
- **Orchestration multi-agents** — A2A · échelon 5

*Socle partagé*
- **Identité & accès** — moindre privilège
- **Runtime d'agent** — héberge · isole
- **Modèles (LLM)** — passerelle · switch · FinOps
- **Gateway & outils (MCP)** — connecteurs
- **Mémoire & état** — court / long
- **Guardrails** — filtres contenu · PII
- **Observabilité & eval** — traces · évals

**Allumage par échelon** (✅ allumée · 🔶 gouvernance renforcée · ⬜ éteinte) :

| Boîte | N1 | N2 | N3 | N4 | N5 |
|---|:--:|:--:|:--:|:--:|:--:|
| Modèles (LLM) | ✅ | ✅ | ✅ | ✅ | ✅ |
| Identité & accès | ✅ | ✅ | ✅ | ✅ | 🔶 |
| Guardrails | ✅ | ✅ | ✅ | 🔶 | 🔶 |
| Observabilité & eval | ✅ | ✅ | ✅ | 🔶 | 🔶 |
| Connaissance & policy (RAG) | ⬜ | ✅ | ✅ | ✅ | ✅ |
| Mémoire & état | ⬜ | ✅ | ✅ | ✅ | ✅ |
| Runtime d'agent | ⬜ | ⬜ | ✅ | ✅ | ✅ |
| Gateway & outils (MCP) | ⬜ | ⬜ | ✅ | ✅ | ✅ |
| Logique d'agent & prompt | ⬜ | ⬜ | ✅ | ✅ | ✅ |
| Outils & connecteurs métier | ⬜ | ⬜ | ✅ | ✅ | ✅ |
| Orchestration multi-agents | ⬜ | ⬜ | ⬜ | ⬜ | ✅ |

**Légende d'échelon (caption) :**
- **N1 — Chatbot sécurisé** *(sur votre socle)* : Déjà sur **votre socle** : modèles via une passerelle (switch + **FinOps**), identité, garde-fous, observabilité. Rien d'acheté en îlot.
- **N2 — Copilot d'entreprise** *(+ RAG · même socle)* : On ancre sur vos données : **RAG** + mémoire s'ajoutent. Toujours le **même socle**.
- **N3 — Agent borné** *(l'agent agit)* : **LA marche :** on entre dans l'**agentique** — runtime d'agent + outils s'allument, le système se met à **agir**.
- **N4 — Agent end-to-end** *(build + HITL)* : Aucune brique en plus — la **gouvernance s'intensifie** (garde-fous, évals) : c'est le prix de l'autonomie.
- **N5 — Système multi-agents** *(gouvernance max)* : Une seule boîte en plus (**orchestration A2A**). Le reste : de la gouvernance qui brille plus fort.

> L'autonomie ne se paie pas en briques techniques — **elle se paie en gouvernance.**

---

## 9 · La stack démystifiée (3 couches)

**La stack démystifiée**

## 3 couches — un lock-in *différent* par couche

| Couche | Contenu | Posture |
|---|---|---|
| **Modèle** *(le cerveau)* | Claude · GPT · Gemini / Llama · Mistral · Qwen — interchangeable via une **abstraction API** (LLM gateway · `LiteLLM`) | **SWAPPABLE** |
| **Framework** *(où l'on code la logique)* | `LangGraph`/… — il y en a beaucoup : neutres (CrewAI · Pydantic AI) ou alignés cloud (AWS Strands · Google ADK · MS Agent Framework). **Le choix importe peu**, il dépend surtout du cloud. | **LE PLUS MINCE** |
| **Runtime** *(héberge · sécurise · observe)* | `AWS Bedrock AgentCore` — mémoire, identité, gateway/MCP, observabilité. **Le vrai lock-in est ici** : ces couches *stateful* managées ne se déménagent pas d'un clic. | **ALIGNER S/ CLOUD** |

> **Ne stressez pas sur le choix du cloud.** Bedrock AgentCore ≈ Microsoft Foundry Agent Service ≈ Google Agent Runtime (Gemini Enterprise, ex-Vertex) : **même socle**, agnostiques au modèle et au framework. On illustre avec AWS — la méthode ne change pas.

---

## 10 · Code vs Low-code/No-code

_Code_ ▶ _No-code (Zapier · Power Automate · n8n)_ ▶ **Code (pour les LLMs)** *(les deux premiers en grisé, le dernier en noir)*

*(overlay centré quasi plein écran : une capture de workflow **n8n** s'affiche brièvement par-dessus, puis disparaît ; le message ci-dessous n'arrive qu'au clic suivant)*

Le no-code a donné **un peu** de pouvoir au business.
Les LLM donnent le pouvoir du **code** à **tout le monde**.

_Word / PowerPoint_ ▶ **Markdown** (+ HTML) *(Word/PowerPoint en grisé, Markdown en noir)*

*(overlay centré quasi plein écran : une capture d'un document **Markdown** s'affiche brièvement par-dessus, puis disparaît)*

---

## 11 · Le cas concret (Maxime ouvre)

**Exemple avec un use case**

## L'agent de remboursement de Léa

- **Le besoin** — Un client réclame sur une commande (plat froid, article manquant, retard) : l'agent **identifie** la clause de la politique, **calcule** le geste, **l'applique** ou **escalade**.
- **La contrainte** — Ça traverse **plusieurs systèmes** (commandes, paiement, mail). **Argent réel**, clients authentifiés, tentatives de manipulation. La **politique** fait foi, pas le LLM.
- **Ce qu'on attend** — **Autonomie bornée :** l'agent rembourse sous le seuil (≤ 25 €, ≤ 2 remb./30 j), **escalade** au-dessus, **refuse** la fraude. *(Échelle : niveau 3–4)*

---

## 12 · Archi AWS (maquette figée sur le cas de Léa)

**Le résultat concret · illustré sur AWS**

## La même maquette d'archi — figée sur le cas de Léa, sur AWS

L'archi de l'agent de remboursement — **gouvernance renforcée** : identité · garde-fous · observabilité.

**Zone use case**
- **Logique d'agent & prompt** — framework mince — *Strands Agents SDK* ✅
- **Outils & connecteurs métier** — actions métier — *Lambda · connecteurs* ✅
- **Connaissance & policy (RAG)** — RAG · règles — *Knowledge Bases for Bedrock* ✅
- **Orchestration multi-agents** — A2A · échelon 5 — ⬜ éteinte

**Socle partagé**
- **Identité & accès** — moindre privilège — *AgentCore Identity* — 🔶 gouvernance renforcée
- **Runtime d'agent** — héberge · isole — *Bedrock AgentCore Runtime · région UE* ✅
- **Modèles (LLM)** — passerelle · switch · FinOps — *Amazon Bedrock · Claude* ✅
- **Gateway & outils (MCP)** — connecteurs — *AgentCore Gateway* ✅
- **Mémoire & état** — court / long — *AgentCore Memory* ✅
- **Guardrails** — filtres contenu · PII — *Bedrock Guardrails* — 🔶 gouvernance renforcée
- **Observabilité & eval** — traces · évals — *AgentCore Observability* — 🔶 gouvernance renforcée


---

## 13 · Archi AWS réelle (diagramme RestoAgent)

**Sous le capot · l'archi réelle du cas de démo**

## L'architecture AWS de RestoAgent — l'implémentation derrière la démo

*(image : `assets/restoagent-arch.drawio.png` — diagramme drawio de l'archi réelle)*

Briques du diagramme : **User (Browser)** → HTTPS → **Webapp** (React + FastAPI/ECS · ALB · CloudFront · RDS · Cognito) → `InvokeAgentRuntime` → **AgentCore Runtime** (Strands + Claude Haiku 4.5). Le runtime est relié à **AgentCore Memory** (Conv. History), **Amazon ECR** (Agent Image), **Bedrock Claude Haiku 4.5** (LLM inference), **Bedrock Prompt Management** (system prompt) et **Amazon Cognito** (OIDC/JWT). Via `MCP tool calls` → **AgentCore Gateway** (MCP + JWT Auth) qui route vers : un **Lambda Identity Injector** → **MCP Server** (/mcp · 5 tools · identity-bound), et un **Lambda KB Retrieve** → **Bedrock Knowledge Base** (Refund Policy) → **S3**. Observabilité : **Amazon CloudWatch** (Logs + Metrics).

> Les **mêmes briques que la maquette**, en services AWS réels : **AgentCore Runtime** (Strands + Claude Haiku 4.5) · **Gateway MCP + JWT** · **Cognito** (identité) · **AgentCore Memory** · **Bedrock Knowledge Base** (policy de remboursement) + S3 · **CloudWatch** (observabilité). Outils exposés via un **MCP Server** (5 tools, identity-bound).

---

## 14 · La démo (la preuve)

## Et voici cette archi en action *(niveau 3–4)*

▶ Démo — RestoAgent, l'agent de remboursement service client

---

## 15 · Souveraineté & confidentialité

**Souveraineté & confidentialité — « si la donnée ne doit pas sortir d'Europe »**

## Où tournent les agents *et* les données ?

- **Vérité 1** — « Région EU » ≠ souverain. Le **CLOUD Act** contraint un fournisseur US quelle que soit la localisation des données.
- **Vérité 2** — Pas qu'une affaire de modèle. L'agent touche la donnée par ses **outils, sa mémoire et son observabilité** (piège : traces vers un SaaS US).

| # | Option | Détail |
|---|---|---|
| 1 | **Hyperscaler région EU** | résidence RGPD — mais juridiction US demeure |
| 2 | **Cloud souverain** | AWS Eur. Sovereign Cloud · S3NS — juridiction + résidence |
| 3 | **Fournisseur EU (Mistral, OVH,…)** | stack 100 % EU — modèles frontière un cran derrière |
| 4 | **VPC privé + modèles open-weight** | la donnée ne sort jamais — vous opérez l'inférence |
| 5 | **On-prem / air-gapped** | contrôle max — GPT/Claude/Gemini impossibles |

> Réponse pragmatique : **l'hybride par classe de données.** Non sensible → meilleure API frontière ; confidentiel → open-weight local ; un **AI gateway** route selon la sensibilité.

---

## 16 · À emporter

**À emporter**

## 3 réflexes pour choisir sa techno d'agents

- **PLACER** le use case sur l'échelle (1→5). L'échelon décide tout le reste.
- **MUTUALISER** un seul socle agentique pour tous vos use cases.
  *runtime · mémoire · identité · gateway · garde-fous · observabilité — bâti une fois, réutilisé à tous les échelons*
- **COMMENCER** bas, gouverner d'abord, monter délibérément.

---

## 17 · Clôture (couverture)

# Merci.

**Jonathan Gross** — jonathan.gross@kleegroup.com
**Maxime Lamborelle** — maxime.lamborelle@kleegroup.com

Présentation & outil à télécharger : **github.com/woodyjon/klee-agentic** *(+ QR code à l'écran — « Scannez pour la présentation & l'outil »)*

Klee Group · EBG, 25 juin 2026
