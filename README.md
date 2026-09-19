# 🧑‍💻 Matheus | Automation Engineer

🇧🇷 [Português](#-sobre-mim) | 🇺🇸 [English](#-about-me)

---

## 🇧🇷 Sobre mim

Trabalho com **Revenue Management**, cuidando de precificação, ocupação e operação diária de um portfólio de acomodações. É desse contato direto com o operacional — reservas quebradas, tarifas desatualizadas, planilhas manuais, relatórios repetitivos — que nasce a maior parte do que eu construo: automações que resolvem um problema que eu mesmo enfrentei antes de virar código.

Gosto de entender o problema de negócio a fundo antes de escrever a primeira linha, e não considero uma automação "pronta" enquanto ela não tiver testes, tratamento de erro e um jeito de me avisar quando algo sai do esperado — de preferência antes que vire dor de cabeça pra operação.

- 🔭 Atualmente automatizando processos de Revenue Management e operações de hospedagem
- 🌱 Aprendendo a levar cada automação um pouco além do script — arquitetura, testes, observabilidade
- 💬 Posso falar sobre precificação dinâmica, integrações com PMS/channel manager e automação de rotinas operacionais
- ⚡ Curiosidade: o projeto que mais me orgulho (Tetris) nasceu de um bug de overbooking que eu via se repetir toda semana

---

## 🚀 Projetos em Destaque

| Projeto | Descrição | Status |
|---|---|---|
| **Tetris** — Motor de remanejamento automático | Detecta reservas "quebradas" (divididas entre unidades diferentes por overbooking) em um PMS e resolve sozinho, testando em cascata: consolidação direta → movimento único → buffer externo → cadeia de realocações → cadeia com buffer. Nunca deixa uma reserva "estacionada" sem destino final garantido — se não encontra solução seguro, para e escala para análise manual em vez de arriscar. Reexecuta a verificação de disponibilidade em tempo real imediatamente antes de cada escrita (evita agir sobre um plano que ficou desatualizado por uma reserva nova) e mantém um log de erros críticos para auditoria. | 🟢 Em produção |
| **Sync Stays ↔ Omnibees** — Preço e disponibilidade em tempo real | Loop contínuo (a cada 1 minuto) que consulta o PMS e replica ocupação e tarifa para o channel manager, evitando overbooking e tarifas divergentes entre canais. O detalhe mais interessante: quando o token de autenticação expira, o script não pede login manual — ele se conecta via protocolo de depuração remota a uma janela de navegador já autenticada e extrai um token novo direto do armazenamento da sessão, retomando o loop sozinho. | 🟢 Em produção |
| **Sincronização de tarifas em massa** — Puxar/subir preços via planilha | Par de scripts que exporta as tarifas de todas as unidades do PMS para uma planilha (para revisão/ajuste manual ou por regra de precificação) e depois reenvia em massa. O envio usa até 50 requisições em paralelo com retomada automática: detecta limitação de requisições (HTTP 429) da API, aplica um atraso adaptativo que cresce e diminui sozinho conforme a resposta da API, e pausa o lote inteiro se a limitação persistir — transforma uma atualização manual de tarifa (unidade por unidade, dia por dia) numa operação de minutos. | 🟢 Em produção |
| **Relatório de faturamento multi-conta** | Ferramenta de linha de comando para extrair relatórios de reservas do PMS (para acompanhamento de faturamento e ocupação), configurável por arquivo de texto simples para uso recorrente sem precisar mexer em código. Suporta múltiplas contas/propriedades processadas em paralelo, com opção de saída consolidada em uma única planilha, paginação e novas tentativas automáticas em falha de rede. | 🟢 Em produção |
| **Upscaller de fotos** | Script de processamento em lote que aumenta a resolução de fotos de anúncios usando um modelo de super-resolução local (Real-ESRGAN), sem depender de serviço externo pago. Detalhe interessante: trata arquivos sem extensão (comuns em fotos baixadas de certas plataformas) renomeando-os temporariamente para que a ferramenta de upscaling consiga reconhecer o formato, sem alterar o arquivo original. | 🟢 Em produção |
| SOC Log Analysis | Projeto de estudo em análise de logs de segurança e detecção de anomalias. | 🟡 Pausado |
| SIEM OpenSource (Wazuh) | Laboratório de SIEM open-source para estudo de monitoramento e resposta a incidentes. | 🟡 Pausado |

---

## 🛠️ Tecnologias

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/-Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Playwright](https://img.shields.io/badge/-Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white)
![REST API](https://img.shields.io/badge/-REST%20API%20%2F%20JSON-black?style=flat-square&logo=json&logoColor=white)
![Linux](https://img.shields.io/badge/-Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Windows](https://img.shields.io/badge/-Windows-0078D6?style=flat-square&logo=windows&logoColor=white)
![PowerShell](https://img.shields.io/badge/-PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white)
![Git](https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white)
![Pytest](https://img.shields.io/badge/-Pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![VS Code](https://img.shields.io/badge/-VS%20Code-007ACC?style=flat-square&logo=visual-studio-code&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/-HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/-CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)

---

## 📫 Contato

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/matheussdarocha)
[![Gmail](https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:m4theusrcdrc@gmail.com)

---
---

## 🇺🇸 About me

I work in **Revenue Management**, handling pricing, occupancy and the day-to-day operation of a portfolio of accommodations. Most of what I build comes directly from that hands-on contact with operations — split/overbooked reservations, stale rates, manual spreadsheets, repetitive reports — automations that fix a problem I dealt with myself before it became code.

I like to understand the business problem in depth before writing the first line, and I don't consider an automation "done" until it has tests, error handling, and a way to flag me when something goes off-script — ideally before it becomes an operational headache.

- 🔭 Currently automating Revenue Management processes and hospitality operations
- 🌱 Learning to take each automation a bit further than the script itself — architecture, testing, observability
- 💬 Happy to talk about dynamic pricing, PMS/channel-manager integrations, and operational-workflow automation
- ⚡ Fun fact: my favorite project (Tetris) started from an overbooking bug I kept watching repeat every week

---

## 🚀 Featured Projects

| Project | Description | Status |
|---|---|---|
| **Tetris** — Automated reservation-remapping engine | Detects "split" reservations (spread across different units due to overbooking) in a PMS and resolves them automatically, cascading through strategies: direct consolidation → single move → external buffer → relocation chain → chain with buffer. Never leaves a reservation parked without a guaranteed final destination — if no safe solution exists, it stops and escalates for manual review instead of risking a bad move. Re-verifies live availability right before every write (so it never acts on a plan made stale by a new incoming reservation) and keeps a critical-error audit log. | 🟢 In production |
| **Stays ↔ Omnibees sync** — Real-time pricing & availability | A continuous loop (every minute) that reads the PMS and mirrors occupancy and rates into the channel manager, preventing overbooking and rate mismatches across channels. The interesting part: when the auth token expires, the script doesn't ask for a manual login — it connects, via remote debugging, to an already-authenticated browser window and pulls a fresh token straight out of session storage, then resumes the loop on its own. | 🟢 In production |
| **Bulk rate sync** — Pull/push pricing via spreadsheet | A pair of scripts that exports every unit's rates from the PMS into a spreadsheet (for manual review or rule-based repricing) and pushes the updates back in bulk. The upload runs up to 50 requests in parallel with automatic recovery: it detects rate-limiting (HTTP 429), applies a self-adjusting delay that grows and shrinks with the API's responses, and pauses the whole batch if throttling persists — turning a manual, unit-by-unit, day-by-day rate update into a job that takes minutes. | 🟢 In production |
| **Multi-account billing report** | A command-line tool that pulls reservation reports from the PMS for billing and occupancy tracking, configurable through a plain text file so it can be reused without touching code. Supports multiple accounts/properties processed in parallel, with an option to consolidate everything into a single spreadsheet, plus pagination and automatic retries on network failures. | 🟢 In production |
| **Photo upscaler** | A batch-processing script that upscales listing photos using a local super-resolution model (Real-ESRGAN), avoiding paid external services. Nice detail: it handles extension-less files (common from certain platforms' downloads) by temporarily renaming them so the upscaling tool can recognize the format, without touching the original file. | 🟢 In production |
| SOC Log Analysis | Study project on security log analysis and anomaly detection. | 🟡 Paused |
| SIEM OpenSource (Wazuh) | Open-source SIEM lab for monitoring and incident-response study. | 🟡 Paused |

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/-Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Playwright](https://img.shields.io/badge/-Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white)
![REST API](https://img.shields.io/badge/-REST%20API%20%2F%20JSON-black?style=flat-square&logo=json&logoColor=white)
![Linux](https://img.shields.io/badge/-Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Windows](https://img.shields.io/badge/-Windows-0078D6?style=flat-square&logo=windows&logoColor=white)
![PowerShell](https://img.shields.io/badge/-PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white)
![Git](https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white)
![Pytest](https://img.shields.io/badge/-Pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![VS Code](https://img.shields.io/badge/-VS%20Code-007ACC?style=flat-square&logo=visual-studio-code&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/-HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/-CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)

---

## 📫 Contact

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/SEU-LINKEDIN)
[![Gmail](https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:m4theusrcdrc@gmail.com)
