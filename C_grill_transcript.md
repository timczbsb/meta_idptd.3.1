# Transcript — Sessão `/grill-me` para Service Blueprint AS-IS

**Data:** 2026-06-12
**Serviço:** Atendimento Pré-Hospitalar no DF — Centrais 193 (COCB/CBMDF) e 192 (SAMU/SES-DF)
**Artefato de contexto:** `B_relatorio_assistente_v3.md`
**Metodologia:** Service Blueprint de G. Lynn Shostack (camadas + linhas divisórias + fail points)

---

## Perguntas e Decisões

### Pergunta 1 — Escopo da Jornada
**Questão:** O blueprint começa no gatilho da emergência e termina no handoff hospitalar + encerramento administrativo? Ou inclui alta hospitalar?

**Decisão:** ✅ Começa no gatilho da emergência (cidadão presencia/sofre evento) e termina no handoff hospitalar + encerramento administrativo. **Não inclui alta hospitalar.**

---

### Pergunta 2 — Quem é o "Cliente" (Customer Actions)?
**Questão:** Usar ator composto (Solicitante + Vítima juntos) ou separar em raias distintas?

**Decisão:** ❌ Ator único rejeitado. ✅ **Separar Solicitante e Vítima em raias distintas.** A jornada do Solicitante termina antes (no handoff da ligação / chegada da viatura) enquanto a da Vítima segue até o handoff hospitalar.

---

### Pergunta 3 — Macroetapas da Jornada
**Questão:** Manter as 6 macroetapas propostas (Pré-Acionamento, Acolhimento, Regulação/Despacho, Atendimento em Cena, Handoff, Encerramento)?

**Decisão:** ✅ Manter as 6 macroetapas.

---

### Pergunta 4 — Estrutura das Raias de Frontstage e Backstage
**Questão:** Usar raia única por camada (fundindo CBMDF e SAMU) ou sub-raias separadas para cada órgão?

**Decisão:** ❌ Raia única rejeitada. ✅ **Duas sub-raias por camada** (Frontstage CBMDF | Frontstage SAMU; Backstage CBMDF | Backstage SAMU), para preservar a distinção de papéis e os fail points de transferência intercentral.

---

### Pergunta 5 — Atores Humanos por Camada
**Questão:** Validar a matriz de papéis (TARM, Médico Regulador, Operador COPOM, Chefe de Sala, Rádio-operador, Equipe de ponta, etc.) para rotular cada atividade no blueprint.

**Decisão:** ✅ Matriz validada integralmente.

---

### Pergunta 6 — Linha de Visibilidade
**Questão:** O que fica no Frontstage (visível ao cidadão) vs. Backstage (invisível) em cada etapa? E na etapa 3, a orientação telefônica do Médico Regulador é Frontstage ou Backstage?

**Decisão:** ✅ **Frontstage:** contato telefônico (voz do atendente/Médico Regulador) e atendimento presencial em cena. **Backstage:** decisões de regulação, despacho, consulta a sistemas, codificação. Na etapa 3: a orientação telefônica do Médico Regulador é **Frontstage** quando ele fala diretamente com o cidadão; é **Backstage** quando a decisão é tomada internamente e comunicada via TARM/Operador.

---

### Pergunta 7 — Processos de Suporte
**Questão:** Quais processos de suporte incluir (Gestão de Frota, Sistemas de TI, Central de Leitos, RH, Jurídico, Formação)?

**Decisão:** ✅ Apenas **Gestão de Frota** e **Sistemas de TI** como suportes principais. Central de Leitos tratada como atividade de Backstage (dentro da raia SAMU/SES-DF).

---

### Pergunta 8 — Evidências Físicas
**Questão:** Validar a lista de evidências físicas por macroetapa (celular, gravação, viatura, uniforme, RAPH, etc.).

**Decisão:** ✅ Lista validada integralmente.

---

### Pergunta 9 — Etapa 2 (Acolhimento): Atividades de Frontstage
**Questão:** Validar fluxo de Acolhimento (Operador COPOM + TARM como primeiro contato, redirecionamento intercentral como fail point).

**Decisão:** ✅ Fluxo validado. Operador (CBMDF) ou TARM (SAMU) como primeiro contato. Redirecionamento intercentral ("ping-pong") como fail point explícito.

---

### Pergunta 10 — Etapa 3 (Regulação/Despacho): Frontstage e Backstage
**Questão:** Validar distribuição — regulação médica no Backstage (comunicação ao cidadão só por exceção) e CBMDF com lógica de despacho operacional (não médica).

**Decisão:** ✅ Distribuição validada. Frontstage SAMU apenas em caso de orientação telefônica pelo Médico Regulador. CBMDF opera com Chefe de Sala/Despachante + Rádio-operador no Backstage.

---

### Pergunta 11 — Etapa 4 (Atendimento em Cena): Frontstage e Backstage
**Questão:** Validar que o Backstage é enxuto e o principal suporte de bastidor é a confirmação de destino via Central de Leitos.

**Decisão:** ✅ Validação confirmada. Equipe em cena opera com relativa autonomia; Backstage concentrado na definição de destino hospitalar.

---

### Pergunta 12 — Etapa 5 (Handoff): Frontstage e Backstage
**Questão:** Validar que o Frontstage é só da equipe de ponta e os fail points críticos são de rede hospitalar.

**Decisão:** ✅ Validação confirmada. Frontstage restrito à passagem de caso no hospital. Fail points: recusa hospitalar, retenção de maca, falha de identificação, handoff incompleto.

---

### Pergunta 13 — Etapa 1 (Pré-Acionamento)
**Questão:** Validar que só o Solicitante age nesta etapa (Vítima é inativa/reativa) e que a Linha de Interação ainda não foi cruzada.

**Decisão:** ✅ Validação confirmada. Vítima tratada como inativa ou reativa. Primeiro cruzamento da Linha de Interação ocorre na Etapa 2 (discagem → atendimento).

---

### Pergunta 14 — Etapa 6 (Encerramento)
**Questão:** Validar que é uma etapa puramente administrativa (Backstage + Suporte), sem interação com o cidadão.

**Decisão:** ✅ Validação confirmada. Etapa enxuta: codificação CID, RAPH, baixa de viatura, estatística. Gestão de Frota é acionada para retorno da viatura ao pool.

---

### Pergunta 15 — Linha de Interação (3 pontos de cruzamento)
**Questão:** Validar que a Linha de Interação é cruzada em 3 momentos: (1) discagem → acolhimento, (2) orientação telefônica do Médico Regulador (condicional), (3) atendimento presencial em cena.

**Decisão:** ✅ Três pontos de interação validados.

---

### Pergunta 16 — Consolidado de Fail Points
**Questão:** Validar o mapa de fail points consolidado por macroetapa.

**Decisão:** ✅ Mapa de fail points validado integralmente.

---

### Pergunta 17 — Linha de Internal Interaction
**Questão:** Validar em quais etapas cada suporte é acionado (Sistemas de TI: Etapas 2-6; Gestão de Frota: Etapas 3 e 6).

**Decisão:** ✅ Mapeamento de acionamento dos suportes validado.

---

### Pergunta 18 — Formato de Entrega
**Questão:** Produzir apenas tabela conceitual (matriz 6 × 7), apenas diagrama Mermaid, ou ambos?

**Decisão:** ✅ **Opção A — Apenas tabela conceitual (matriz conceitual)**, fiel à metodologia Shostack, em `C_blueprint_asis.md`. Diagrama Mermaid será entregue separadamente em `D_diagrama_asis.md`.

---

## Resumo das Decisões

| # | Decisão | Resumo |
|---|---|---|
| 1 | Escopo | Gatilho → Handoff + Encerramento (sem alta hospitalar) |
| 2 | Cliente | Solicitante e Vítima em raias separadas |
| 3 | Macroetapas | 6 etapas |
| 4 | Sub-raias | CBMDF e SAMU separados no Frontstage e Backstage |
| 5 | Atores | TARM, MED, OPE, CHF, RAD, EQP-C, EQP-S, LEIT |
| 6 | Linha de Visibilidade | Frontstage: contato telefônico + presencial; Backstage: decisões e registros |
| 7 | Suportes | Sistemas de TI + Gestão de Frota (Central de Leitos no Backstage) |
| 8 | Evidências Físicas | Lista validada por etapa |
| 9-14 | Etapas 1-6 | Atividades por camada validadas |
| 15 | Linha de Interação | 3 pontos de cruzamento |
| 16 | Fail Points | Consolidado validado |
| 17 | Internal Interaction | TI (2-6) e Frota (3,6) |
| 18 | Formato | Tabela conceitual Shostack |
