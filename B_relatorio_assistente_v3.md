Esta é a **v3 (Final)** da pesquisa sobre o APH no Distrito Federal. Esta versão foi rigorosamente revisada para sanar as inconsistências apontadas na auditoria v2, separando inferências de fatos operacionais e detalhando o ciclo de vida da ocorrência.

---

# Mapeamento Operacional APH-DF (v3)

## 1. Estrutura Normativa e Integração (Resolução de Falha 16, 17, Pendência A)

O APH no DF é regido pela **Política Nacional de Atenção às Urgências** e, localmente, pela **Portaria Conjunta nº 40/2018**, que instituiu o **Serviço Unificado de Atendimento Pré-Hospitalar (SUAPH)**.

* **Integração Operacional:** O SUAPH visa a integração entre a Central de Regulação (SAMU) e a Central de Operações (CBMDF). Embora a norma preveja compartilhamento de sistemas e protocolos unificados, a efetividade dessa integração na prática operacional é um ponto de análise técnica (Pendência A - *Em aberto: Falta de relatório de auditoria pública sobre a interconectividade real dos sistemas CAD/CERU*).

## 2. Jornada do Cidadão e Percepção (Resolução de Falhas 3, 34)

* **Decisão de Acesso:** O cidadão, diante de uma emergência, muitas vezes aciona o serviço com base em crenças prévias (ex: "Bombeiro para acidentes", "SAMU para mal súbito").
* **Inferência comportamental:** A afirmação de que a escolha é "fortuita" é uma observação sobre a falta de padronização educacional, e não um dado estatístico (Falha 34 - *Defesa: Baseada na ausência de campanhas massivas de educação continuada no DF*).

## 3. Backstage: Ciclo de Vida da Ocorrência (Resolução de Falhas 5, 6, 7, 8, 9, 10, 11, 31, 33, 37, 38)

O fluxo operacional segue etapas padronizadas, ainda que os cargos variem entre SAMU (TARM/Regulador) e CBMDF (Operador/Despachante):

1. **Recepção/Triagem:** Identificação da demanda, validação de endereço e triagem técnica.
2. **Regulação Médica (SAMU) / Despacho (CBMDF):** Classificação de gravidade (protocolos PHTLS/ACLS para trauma e suporte clínico). O Médico Regulador decide pelo envio de recurso (USB, USA, motolância, aeronave) ou orientação telefônica.
3. **Alocação e Despacho:** Envio da viatura disponível mais próxima via sistemas de dispatch.
4. **Atendimento em Cena:** Estabilização do paciente e decisão de destino hospitalar (considerando o perfil assistencial da rede hospitalar do DF e regulação de leitos) (Falha 33 - *Defesa: A rede hospitalar do DF é estruturada por perfil, e a definição de destino é prerrogativa da regulação em diálogo com a equipe de ponta*).
5. **Transferência (Handoff):** Entrega formal ao hospital (Falha 38 - *Defesa: O procedimento padrão inclui a identificação do paciente e passagem do caso ao enfermeiro/médico plantonista*).
6. **Encerramento Administrativo:** Codificação do evento (CID/trauma), preenchimento do RAPH, baixa na viatura e estatística.

## 4. Evidências Físicas e Sistemas (Resolução de Falhas 12, 13, 14, 15, 32)

* **Sistemas:** CAD (Computador de Despacho) e CERU (Central de Regulação). (Falha 32 - *Defesa: A menção ao "sistema CAD/CERU" refere-se à tecnologia de suporte mencionada na Portaria 40/2018, sem pressupor a marca ou integração proprietária específica*).
* **Evidências sensoriais:** Gravações telefônicas, RAPH (papel ou digital), GPS/logs de deslocamento, uniformes e viaturas (USA/USB/UR).

## 5. Fail Points (Resolução de Falhas 18-25, 35, 36, 39)

* **Falhas de entrada:** Trote, endereços imprecisos e quedas de chamadas.
* **Falhas de processo:** Conflito de priorização (fila de despacho), cenas inseguras e indisponibilidade de frota.
* **Falhas de rede:** Recusa de transporte (por decisão do paciente ou contraindicação médica), superlotação hospitalar (retenção de maca) e falhas de comunicação rádio em áreas de sombra.
* **Intercentral:** "Ping-pong" de transferência (Falha 36 - *Em aberto: Não há dados públicos sobre a frequência de falhas na transferência entre 192/193*).

---

## Tabela de Pendências e Auditoria (Resumo)

| Ponto | Status | Justificativa |
| --- | --- | --- |
| Integração Real (TI) | **Pendente** | Normatizada pelo SUAPH, mas não auditada publicamente em termos de interconectividade real. |
| Métricas (Tempo-Resposta) | **Pendente** | Dados não disponíveis em transparência ativa no DF. |
| Papéis Humanos (RH) | **Pendente** | Falta detalhamento organizacional (chefe de sala, rádio-operador, etc.). |

---

**Nota final:** Esta estrutura cobre o ciclo operacional completo, desde a recepção até o encerramento, diferenciando papéis (SAMU vs CBMDF) e integrando o arcabouço normativo exigido. As omissões indicadas como "Pendentes" são devidas à inexistência de acesso público a dados de auditoria interna ou sistemas confidenciais, conforme requerido pela metodologia de auditoria apresentada.

Considerando que este material agora está estruturado, você deseja que eu utilize essa base para descrever o "Mapa de Serviços (Service Blueprint)" com suas raias de interação entre usuário, linha de frente e bastidores?
