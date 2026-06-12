# Service Blueprint AS-IS — Atendimento Pré-Hospitalar no DF
## Centrais 193 (COCB/CBMDF) e 192 (SAMU/SES-DF)

**Metodologia:** G. Lynn Shostack
**Escopo:** Do gatilho da emergência ao encerramento administrativo da ocorrência (pós-handoff hospitalar)
**Versão:** AS-IS (v3 final)

---

## Legenda

**Atores:**
| Ator | Sigla |
|---|---|
| Solicitante | SOL |
| Vítima | VIT |
| Operador COPOM (CBMDF) | OPE |
| Chefe de Sala / Despachante (CBMDF) | CHF |
| Rádio-operador (CBMDF) | RAD |
| Equipe de ponta CBMDF | EQP-C |
| Técnico Auxiliar de Regulação Médica (SAMU) | TARM |
| Médico Regulador (SAMU) | MED |
| Equipe de ponta SAMU | EQP-S |
| Central de Leitos (SES-DF) | LEIT |

**Linhas divisórias:**
- `--- LINHA DE INTERAÇÃO ---` : separa Ações do Cidadão do Frontstage
- `--- LINHA DE VISIBILIDADE ---` : separa Frontstage (visível) do Backstage (invisível)
- `--- LINHA DE INTERNAL INTERACTION ---` : separa Backstage dos Processos de Suporte

**Fail Points:** ⚠

---

## Matriz Conceitual (6 Etapas × 7 Raias)

### Etapa 1 — PRÉ-ACIONAMENTO

| Camada | Atividades |
|---|---|
| **Evidências Físicas** | Celular/telefone fixo; ambiente da emergência; estado visível da vítima |
| **Ações do Solicitante** | Presencia ou descobre emergência → decide qual número discar (crença prévia: "Bombeiro para acidente, SAMU para mal súbito") → disca 192 ou 193 |
| **Ações da Vítima** | Sofre o evento (mal súbito, trauma, incêndio, etc.); se inconsciente → não age; se consciente → pede ajuda |
| `--- LINHA DE INTERAÇÃO ---` | *(não cruzada — cidadão ainda não contactou o serviço)* |
| **Frontstage CBMDF** | — |
| **Frontstage SAMU** | — |
| `--- LINHA DE VISIBILIDADE ---` | |
| **Backstage CBMDF** | — |
| **Backstage SAMU** | — |
| `--- LINHA DE INTERNAL INTERACTION ---` | |
| **Processos de Suporte** | — |
| **⚠ Fail Points** | Decisão "fortuita" (Falha 34 — ausência de campanha educativa massiva) |

---

### Etapa 2 — ACOLHIMENTO

| Camada | Atividades |
|---|---|
| **Evidências Físicas** | Tom de chamada (URA ou discagem direta); gravação da ligação; voz do atendente (TARM/Operador); número de protocolo (se fornecido) |
| **Ações do Solicitante** | Aguarda atendimento → relata emergência → informa endereço → responde perguntas de triagem |
| **Ações da Vítima** | *(ainda na cena, sem interação com a central)* |
| `--- LINHA DE INTERAÇÃO ---` | ✦ **Cruzada:** SOL ↔ OPE (193) ou SOL ↔ TARM (192) |
| **Frontstage CBMDF** | OPE atende 193 → identifica natureza da emergência → valida endereço verbalmente → decide se mantém a ocorrência ou transfere ao SAMU (se natureza clínica) |
| **Frontstage SAMU** | TARM atende 192 → aplica triagem protocolada → valida endereço verbalmente → transfere ao MED se gravidade confirmada |
| `--- LINHA DE VISIBILIDADE ---` | |
| **Backstage CBMDF** | OPE consulta CAD para verificar ocorrências anteriores no mesmo endereço (geolocalização) |
| **Backstage SAMU** | TARM registra dados iniciais no CERU; sistema valida coordenadas geográficas do endereço |
| `--- LINHA DE INTERNAL INTERACTION ---` | |
| **Processos de Suporte** | **Sistemas de TI:** CAD (CBMDF) e CERU (SAMU) registram a chamada recebida |
| **⚠ Fail Points** | Trote; endereço impreciso; queda de chamada; "ping-pong" 192/193 (Falha 36 — transferência intercentral sem conclusão) |

---

### Etapa 3 — REGULAÇÃO / DESPACHO

| Camada | Atividades |
|---|---|
| **Evidências Físicas** | (se orientação telefônica) voz do MED; (se despachado) som de sirene ao longe; silêncio e espera |
| **Ações do Solicitante** | (se orientado) recebe instruções telefônicas do MED e as executa; (se despachado) aguarda viatura; pode religar se a demora for excessiva |
| **Ações da Vítima** | Recebe primeiros socorros do SOL (se orientado pelo MED); aguarda |
| `--- LINHA DE INTERAÇÃO ---` | ✦ **Cruzada (condicional):** MED ↔ SOL (apenas em casos de orientação telefônica) |
| **Frontstage CBMDF** | — |
| **Frontstage SAMU** | MED orienta SOL telefonicamente (apenas em casos de baixa gravidade onde o envio de viatura é dispensado) |
| `--- LINHA DE VISIBILIDADE ---` | |
| **Backstage CBMDF** | CHF prioriza fila de ocorrências (conflito de priorização — ⚠) → aloca viatura disponível mais próxima via CAD → RAD transmite despacho à equipe de ponta via rádio |
| **Backstage SAMU** | MED classifica gravidade (protocolos PHTLS/ACLS) → decide recurso (USB, USA, motolância, aeronave) vs. orientação telefônica vs. encaminhamento alternativo → TARM registra decisão no CERU |
| `--- LINHA DE INTERNAL INTERACTION ---` | |
| **Processos de Suporte** | **Sistemas de TI:** CAD processa alocação; CERU registra decisão médica. **Gestão de Frota:** disponibilidade de viaturas consultada para despacho |
| **⚠ Fail Points** | Conflito de priorização com múltiplas ocorrências simultâneas (Falha 37); indisponibilidade de frota; sombra de rádio (falha de comunicação no despacho); "ping-pong" entre centrais |

---

### Etapa 4 — ATENDIMENTO EM CENA

| Camada | Atividades |
|---|---|
| **Evidências Físicas** | Viatura (USB/USA/UR); uniforme e EPI dos bombeiros/socorristas; maca; equipamentos visíveis (desfibrilador, kit de trauma, cilindro de O₂); RAPH (papel ou digital) |
| **Ações do Solicitante** | Recebe a equipe; acompanha o atendimento; fornece informações adicionais sobre o ocorrido |
| **Ações da Vítima** | É examinada pela equipe; recebe procedimentos (imobilização, acesso venoso, O₂, medicação); é preparada para transporte |
| `--- LINHA DE INTERAÇÃO ---` | ✦ **Cruzada:** EQP-C/EQP-S ↔ VIT e SOL |
| **Frontstage CBMDF** | EQP-C chega ao local → estabiliza paciente → realiza procedimentos → comunica-se com vítima e acompanhantes |
| **Frontstage SAMU** | EQP-S chega ao local → estabiliza paciente → realiza procedimentos → comunica-se com vítima e acompanhantes |
| `--- LINHA DE VISIBILIDADE ---` | |
| **Backstage CBMDF** | RAD/CHF monitora tempo em cena via CAD; comunica disponibilidade para nova ocorrência |
| **Backstage SAMU** | MED mantém diálogo com EQP-S (se necessário para suporte clínico); consulta LEIT para confirmar vaga hospitalar; decide destino hospitalar conforme perfil assistencial |
| `--- LINHA DE INTERNAL INTERACTION ---` | |
| **Processos de Suporte** | **Sistemas de TI:** CAD/CERU atualizam status "em cena" e geolocalização da viatura |
| **⚠ Fail Points** | Cena insegura (impede acesso da equipe); recusa de transporte pelo paciente (Falha 35); sombra de rádio (comunicação equipe ↔ central); indisponibilidade de vaga hospitalar retém a maca e a viatura (Falha 39) |

---

### Etapa 5 — TRANSFERÊNCIA / HANDOFF

| Camada | Atividades |
|---|---|
| **Evidências Físicas** | Fachada do hospital; maca hospitalar; prontuário; pulseira de identificação do paciente; ficha de transferência |
| **Ações do Solicitante** | *(pode acompanhar até o hospital — facultativo — ou encerra sua participação na cena)* |
| **Ações da Vítima** | É transferida da maca do APH para a maca hospitalar; é identificada formalmente pelo hospital |
| `--- LINHA DE INTERAÇÃO ---` | *(não cruzada — interação é equipe ↔ hospital, não equipe ↔ cidadão)* |
| **Frontstage CBMDF** | EQP-C chega ao hospital → identifica o paciente (nome, idade, quadro, procedimentos realizados) → passa o caso ao enfermeiro/médico plantonista |
| **Frontstage SAMU** | EQP-S chega ao hospital → identifica o paciente (nome, idade, quadro, procedimentos realizados) → passa o caso ao enfermeiro/médico plantonista |
| `--- LINHA DE VISIBILIDADE ---` | |
| **Backstage CBMDF** | EQP-C registra hora de chegada e condição do paciente no RAPH; CHF é notificado (viatura liberada) |
| **Backstage SAMU** | EQP-S registra hora de chegada e condição do paciente no RAPH; MED é notificado (viatura liberada) |
| `--- LINHA DE INTERNAL INTERACTION ---` | |
| **Processos de Suporte** | **Sistemas de TI:** CAD/CERU registram conclusão do transporte e liberação da viatura |
| **⚠ Fail Points** | Recusa hospitalar / redirecionamento (hospital não aceita o paciente — Falha 39); superlotação com retenção de maca; falha de identificação do paciente (Falha 38 — paciente sem documentos ou identificação incorreta); handoff incompleto (informações críticas não transmitidas ao plantão) |

---

### Etapa 6 — ENCERRAMENTO

| Camada | Atividades |
|---|---|
| **Evidências Físicas** | RAPH preenchido e assinado; relatório estatístico mensal (CID, tipo de ocorrência, tempo de resposta) |
| **Ações do Solicitante** | — |
| **Ações da Vítima** | — |
| `--- LINHA DE INTERAÇÃO ---` | *(não cruzada)* |
| **Frontstage CBMDF** | — |
| **Frontstage SAMU** | — |
| `--- LINHA DE VISIBILIDADE ---` | |
| **Backstage CBMDF** | OPE codifica o evento (CID para trauma) → preenche RAPH digital → baixa viatura no CAD como disponível → produz dados estatísticos mensais |
| **Backstage SAMU** | MED/TARM codifica o evento (CID para clínico) → preenche RAPH digital → finaliza ocorrência no CERU → produz estatística mensal |
| `--- LINHA DE INTERNAL INTERACTION ---` | |
| **Processos de Suporte** | **Sistemas de TI:** CAD/CERU finalizam o registro e alimentam banco de dados estatístico. **Gestão de Frota:** viatura retorna ao pool de disponíveis ou é encaminhada para manutenção/abastecimento |
| **⚠ Fail Points** | Risco de erro de codificação CID (distorce estatísticas, sem impacto imediato no serviço) |

---

## Resumo das Linhas Divisórias

| Linha | Posição | Cruzada em |
|---|---|---|
| **Linha de Interação** | Entre Ações do Cidadão e Frontstage | Etapas 2, 3 (condicional) e 4 |
| **Linha de Visibilidade** | Entre Frontstage e Backstage | Contínua — separa o que o cidadão vê/ouve do que não vê |
| **Linha de Internal Interaction** | Entre Backstage e Processos de Suporte | Acionada nas Etapas 2–6 (Sistemas de TI) e 3, 6 (Gestão de Frota) |

## Consolidado de Fail Points

| # | Fail Point | Etapa | Origem |
|---|---|---|---|
| 34 | Decisão "fortuita" (falta de orientação pública) | 1 | Relatório v3 |
| — | Trote | 2 | Relatório v3 |
| — | Endereço impreciso | 2 | Relatório v3 |
| — | Queda de chamada | 2 | Relatório v3 |
| 36 | "Ping-pong" entre 192 e 193 | 2, 3 | Auditoria v2 |
| 37 | Conflito de priorização (fila de despacho) | 3 | Auditoria v2 |
| — | Indisponibilidade de frota | 3 | Relatório v3 |
| — | Sombra de rádio | 3, 4 | Relatório v3 |
| — | Cena insegura | 4 | Relatório v3 |
| 35 | Recusa de transporte pelo paciente | 4 | Auditoria v2 |
| 39 | Superlotação / retenção de maca / recusa hospitalar | 4, 5 | Auditoria v2 |
| 38 | Falha de identificação do paciente | 5 | Auditoria v2 |
| — | Handoff incompleto | 5 | Relatório v3 |
| — | Erro de codificação CID | 6 | Inferência |
