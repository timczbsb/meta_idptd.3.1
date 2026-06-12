# Diagrama AS-IS — Jornada do Atendimento Pré-Hospitalar no DF

```mermaid
flowchart TD
  %% ===== ATORES =====
  SOL([👤 Solicitante])
  VIT([🩻 Vítima])
  OPE[📞 OPE\nOperador COPOM\nCBMDF]
  TARM[📞 TARM\nTécnico Aux.\nRegulação SAMU]
  MED[🩺 MED\nMédico Regulador\nSAMU]
  CHF[⚡ CHF\nChefe de Sala\nCBMDF]
  RAD[📡 RAD\nRádio-operador\nCBMDF]
  EQPC[🚒 EQP-C\nEquipe CBMDF\nem cena]
  EQPS[🚑 EQP-S\nEquipe SAMU\nem cena]
  LEIT[(🏥 LEIT\nCentral de Leitos\nSES-DF)]
  CAD[(💻 CAD\nSistema CBMDF)]
  CERU[(💻 CERU\nSistema SAMU)]
  HOSP[🏥 Hospital\nPlantonista]

  FP1[/⚠ Decisão fortuita\n192 ou 193?/]
  FP2[/⚠ Ping-pong\nintercentral/]
  FP3[/⚠ Conflito\npriorização/]
  FP4[/⚠ Sombra rádio\nfrota indisponível/]
  FP5[/⚠ Recusa transporte\ncena insegura/]
  FP6[/⚠ Recusa hospitalar\nretenção de maca/]

  %% ===== ETAPA 1: PRÉ-ACIONAMENTO =====
  SOL -->|"presencia emergência\ndecide qual número discar"| FP1
  VIT -->|"sofre evento"| SOL
  FP1 -->|"disca 193"| OPE
  FP1 -->|"disca 192"| TARM

  %% ===== ETAPA 2: ACOLHIMENTO =====
  SOL -->|"relata emergência\ninforma endereço"| OPE
  SOL -->|"relata emergência\ninforma endereço"| TARM
  OPE -->|"registra ocorrência"| CAD
  TARM -->|"registra chamada"| CERU
  TARM -->|"passa caso grave"| MED
  OPE -->|"transfere caso clínico"| TARM
  OPE -.->|"⚠ transferência\nsem conclusão"| FP2
  TARM -.->|"⚠ ping-pong"| FP2

  %% ===== ETAPA 3: REGULAÇÃO / DESPACHO =====
  MED -->|"orienta telefonicamente\n(baixa gravidade)"| SOL
  MED -->|"classifica gravidade\ndecide recurso"| CERU
  MED -->|"aciona despacho\nUSB/USA/motolância"| TARM
  CHF -->|"prioriza fila\naloca viatura"| CAD
  CAD -->|"despacho"| RAD
  RAD -->|"transmite missão\nvia rádio"| EQPC
  TARM -->|"notifica"| EQPS
  CHF -.->|"⚠ múltiplas ocorrências\nsimultâneas"| FP3
  RAD -.->|"⚠ sombra de rádio"| FP4

  %% ===== ETAPA 4: ATENDIMENTO EM CENA =====
  EQPC -->|"estabiliza paciente\nrealiza procedimentos"| VIT
  EQPS -->|"estabiliza paciente\nrealiza procedimentos"| VIT
  EQPC -->|"comunica-se"| SOL
  EQPS -->|"comunica-se"| SOL
  EQPS -->|"consulta destino"| MED
  MED -->|"consulta vaga"| LEIT
  LEIT -->|"confirma vaga\ndestino hospitalar"| MED
  MED -->|"define destino"| EQPS
  EQPC -.->|"⚠ recusa ou\ncena insegura"| FP5
  EQPS -.->|"⚠ recusa ou\ncena insegura"| FP5

  %% ===== ETAPA 5: HANDOFF =====
  EQPC -->|"transporta vítima\npassa caso ao plantonista"| HOSP
  EQPS -->|"transporta vítima\npassa caso ao plantonista"| HOSP
  EQPC -->|"registra RAPH\nnotifica viatura liberada"| CHF
  EQPS -->|"registra RAPH\nnotifica viatura liberada"| MED
  HOSP -.->|"⚠ recusa hospitalar\nredirecionamento"| FP6

  %% ===== ETAPA 6: ENCERRAMENTO =====
  CHF -->|"baixa viatura\nestatística"| CAD
  MED -->|"codifica CID\nfinaliza ocorrência"| CERU
  OPE -->|"codifica CID\npreenche RAPH"| CAD
  TARM -->|"preenche RAPH"| CERU
```

## Legenda de Atores

| Ator | Descrição |
|---|---|
| SOL | Solicitante (cidadão que aciona o serviço) |
| VIT | Vítima (paciente atendido) |
| OPE | Operador COPOM — CBMDF (atende o 193) |
| TARM | Técnico Auxiliar de Regulação Médica — SAMU (atende o 192) |
| MED | Médico Regulador — SAMU |
| CHF | Chefe de Sala / Despachante — CBMDF |
| RAD | Rádio-operador — CBMDF |
| EQP-C | Equipe de ponta CBMDF (bombeiros em cena) |
| EQP-S | Equipe de ponta SAMU (socorristas em cena) |
| LEIT | Central de Leitos — SES-DF |
| CAD | Sistema Computer-Aided Dispatch — CBMDF |
| CERU | Central de Regulação — SAMU |
| HOSP | Hospital / Plantonista receptor |

## Linhas Divisórias (Shostack)

| Linha | Separa |
|---|---|
| **Linha de Interação** | SOL/VIT ↔ OPE/TARM/MED/EQP-C/EQP-S |
| **Linha de Visibilidade** | Frontstage (OPE, TARM, MED orientando, EQP) ↔ Backstage (CHF, RAD, CAD, CERU, LEIT) |
| **Linha de Internal Interaction** | Backstage ↔ Sistemas de Suporte (CAD, CERU, LEIT) |
