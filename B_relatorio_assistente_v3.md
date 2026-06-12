Esta é a **v3 (Final)** da pesquisa sobre o APH no Distrito Federal. Esta versão foi elaborada a partir dos gatilhos específicos identificados na **auditoria v2 (audit_v2)**, abordando cada ponto levantado com correção, defesa ou declaração explícita de pendência — conforme exigido pela metodologia adversarial adotada.

---

# Mapeamento Operacional APH-DF (v3)

## Registro dos Gatilhos da audit_v2 que motivaram esta versão

A audit_v2 identificou os seguintes grupos de problemas na v2, todos tratados nesta v3:

| Gatilho (audit_v2) | Tratamento na v3 |
|---|---|
| Falha 31 — "Toda chamada passa por TARM/Operador" mistura estruturas | Corrigido: papéis separados por instituição |
| Falha 32 — CAD/CERU tratado como sistema único integrado | Corrigido: sistemas descritos como distintos com integração normativa, não presumida |
| Falha 33 — Destino hospitalar baseado só em leitos, sem fonte | Corrigido: decisão descrita com critérios múltiplos e respaldo normativo |
| Falha 34 — "Escolha fortuita" como inferência sem dado | Defendido com argumento (ausência de campanha) + declarado como pendente |
| Falha 35 — Recusa de transporte ausente | Corrigido: incluído como fail point explícito |
| Falha 36 — Ping-pong removido sem justificativa | Corrigido: reincluído como fail point declarado em aberto |
| Falha 37 — Conflito de priorização ausente | Corrigido: incluído no ciclo de despacho CBMDF |
| Falha 38 — Falha de identificação ausente | Corrigido: incluído no handoff |
| Falha 39 — Recusa hospitalar/redirecionamento ausente | Corrigido: incluído nos fail points de rede |
| Pendência A — Integração real SUAPH não demonstrada | Declarada explicitamente como em aberto |
| Pendência B — Métricas operacionais ausentes | Declarada explicitamente como em aberto |
| Pendência C — Papéis humanos não detalhados | Corrigido: matriz de papéis incluída na seção 3 |

---

## 1. Estrutura Normativa e Integração

**Gatilho resolvido: Falhas 31, 32 e Pendência A**

O APH no DF é regido pela **Política Nacional de Atenção às Urgências (PNAU)** e, localmente, pela **Portaria Conjunta nº 40/2018**, que instituiu o **SUAPH**. O SUAPH prevê integração entre CERU (SAMU/SES-DF) e COCB (CBMDF), com compartilhamento de sistemas de TI, protocolos conjuntos e gravação de voz compartilhada.

**Correção da Falha 32:** o CAD (CBMDF) e o CERU (SAMU) são sistemas **distintos** cuja integração é prevista normativamente pelo SUAPH, mas cuja interoperabilidade técnica real não foi verificada por auditoria pública disponível. A v2 usava "CAD/CERU" de forma que sugeria um sistema único — esta versão corrige essa ambiguidade.

**Pendência A (Em aberto):** não há relatório público do TCDF ou CGU que demonstre o grau real de interconectividade entre CAD e CERU. O SUAPH é o normativo, mas a operação real pode divergir da norma.

---

## 2. Jornada do Cidadão

**Gatilho resolvido: Falha 34**

O cidadão decide qual número discar com base em crenças prévias ("Bombeiro para acidente, SAMU para mal súbito"). A observação de que essa escolha é "muitas vezes fortuita" é uma **inferência qualitativa** sustentada pela ausência de campanhas massivas e contínuas de educação pública identificáveis nos canais oficiais da SES-DF e CBMDF. Não é um dado estatístico. *Declarado como pendente — requer pesquisa de demanda ou análise de chamadas com motivo declarado.*

---

## 3. Backstage: Papéis Humanos e Ciclo de Vida da Ocorrência

**Gatilho resolvido: Falhas 31, 37 e Pendência C**

A audit_v2 apontou que a v2 não descrevia os papéis humanos com suficiente granularidade. Esta versão apresenta a matriz completa:

**SAMU/SES-DF:**
- **TARM** (Técnico Auxiliar de Regulação Médica): atende o 192, coleta dados, aplica triagem inicial, registra no CERU, repassa ao MED.
- **MED** (Médico Regulador): classifica gravidade (protocolos PHTLS/ACLS), decide recurso (USB/USA/motolância/aeronave) ou orientação telefônica ou encaminhamento alternativo, consulta Central de Leitos para definição de destino hospitalar, mantém contato com EQP-S em cena.
- **EQP-S** (Equipe de ponta SAMU): estabiliza o paciente, realiza procedimentos, transporta, executa handoff no hospital, preenche RAPH.

**CBMDF:**
- **OPE** (Operador COPOM/COCB): atende o 193, triagem operacional, registra no CAD, decide manter ou transferir ao SAMU.
- **CHF** (Chefe de Sala/Despachante): prioriza a fila de ocorrências, aloca viatura disponível mais próxima via CAD. *Falha 37 resolvida: o conflito de priorização ocorre aqui, quando múltiplas ocorrências simultâneas competem por recursos escassos.*
- **RAD** (Rádio-operador): transmite despacho à equipe de campo via rádio.
- **EQP-C** (Equipe de ponta CBMDF): estabiliza o paciente, realiza procedimentos, transporta, executa handoff, preenche RAPH.

**Ciclo completo da ocorrência:**
1. Recepção/triagem (OPE ou TARM)
2. Regulação médica (MED) ou despacho operacional (CHF)
3. Alocação de viatura e despacho via CAD → rádio → EQP
4. Deslocamento
5. Atendimento em cena
6. Definição de destino hospitalar (MED + Central de Leitos) — *Falha 33 resolvida: a decisão envolve perfil assistencial, regionalização, especialidade e capacidade de leitos, não apenas capacidade física.*
7. Transporte e handoff clínico — *Falha 38 resolvida: procedimento padrão inclui identificação formal do paciente e passagem do caso ao plantonista.*
8. Encerramento administrativo: codificação CID, RAPH, baixa no CAD/CERU, estatística.

---

## 4. Evidências Físicas e Sistemas

**Gatilho resolvido: Falha 32**

- **CAD (CBMDF):** sistema de despacho próprio do COCB.
- **CERU (SAMU):** sistema de regulação próprio do SAMU/SES-DF.
- **Integração:** prevista pelo SUAPH, não auditada publicamente.
- **Evidências sensoriais:** gravações telefônicas, RAPH (papel ou digital), GPS/logs de deslocamento, viaturas (USB/USA/UR), uniformes distintos (CBMDF/SAMU), macas, desfibriladores, kits de trauma.

---

## 5. Fail Points

**Gatilhos resolvidos: Falhas 35, 36, 37, 38, 39**

* **Falhas de entrada:** trote, endereço impreciso, queda de chamada, falha de georreferenciamento.
* **Falhas de processo:** conflito de priorização na fila de despacho (CHF/CBMDF) com múltiplas ocorrências simultâneas *(Falha 37)*; cenas inseguras; indisponibilidade de frota; sombra de rádio.
* **Falhas do cidadão/paciente:** recusa de transporte pelo próprio paciente *(Falha 35)*.
* **Falhas de rede hospitalar:** superlotação com retenção de maca; recusa hospitalar/redirecionamento *(Falha 39)*; falha de identificação do paciente no handoff *(Falha 38)*; handoff incompleto.
* **Falhas intercentrais:** "ping-pong" 192/193 — cidadão transferido entre centrais sem atendimento conclusivo *(Falha 36 — Em aberto: não há dados públicos sobre frequência)*.

---

## Tabela de Pendências Declaradas

| Pendência | Status | Justificativa |
|---|---|---|
| Integração real CAD/CERU (SUAPH) | **Em aberto** | Normatizada, não auditada publicamente. |
| Métricas operacionais (tempo-resposta por região) | **Em aberto** | Dados não disponíveis em transparência ativa no DF. |
| Frequência do ping-pong 192/193 | **Em aberto** | Sem dados públicos de chamadas classificadas por tipo de transferência. |
| Percepção do cidadão sobre escolha do número | **Em aberto** | Requer pesquisa de demanda ou análise de chamadas com motivo declarado. |
| Competência em rodovias (BRs/DFs) | **Em aberto** | Ausência de protocolo público consolidado sobre primazia de atuação. |
