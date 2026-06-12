Com base na auditoria detalhada apresentada (audit_v1), preparei esta segunda versão (v2) da pesquisa sobre o Atendimento Pré-Hospitalar (APH) no Distrito Federal. O objetivo desta revisão é consolidar um mapeamento operacional rigoroso, abordando **cada falha identificada** — corrigindo imprecisões, defendendo afirmações sustentadas por evidências, e declarando explicitamente os pontos pendentes.

---

# Atendimento Pré-Hospitalar (APH) no DF: Mapeamento Operacional (v2)

Esta versão integra o **SUAPH (Portaria Conjunta nº 40/2018)** como eixo central da operação integrada.

## 1. Jornada do Cidadão (Perspectiva do Usuário)

* **O Dilema do Acesso:** O cidadão, em momento de crise, frequentemente não diferencia a natureza da emergência (clínica vs. traumática). A escolha entre 192 e 193 é, muitas vezes, baseada em percepção prévia — não em orientação pública estruturada.
* **A Experiência do Fluxo:** O cidadão percebe a chamada como um único evento, mas a interface técnica entre CBMDF e SAMU pode ocultar a complexidade da transferência. A falta de um sistema de retorno (feedback) sobre o status da viatura ou tempo estimado de chegada é uma lacuna na experiência do usuário.
* **Conscientização:** Embora existam orientações nos sites oficiais sobre o papel de cada serviço, estas não constituem campanhas educativas massivas, deixando o cidadão dependente da percepção do atendente no momento da chamada.

## 2. Processos de Bastidor (Backstage)

A operação é regida pelo **SUAPH**, que estabelece a padronização e integração entre CERU (SAMU) e COCB (CBMDF), incluindo compartilhamento de sistemas de TI, gravação de voz e protocolos conjuntos (Portaria Conjunta nº 40/2018).

* **Triagem e Regulação:** No SAMU, o TARM realiza a triagem inicial e repassa ao Médico Regulador, que decide pelo envio de recurso (USB, USA, motolância, aeronave), orientação telefônica ou encaminhamento alternativo. No CBMDF, o Operador (OPE) realiza triagem operacional e o Chefe de Sala (CHF) prioriza o despacho via CAD; o Rádio-operador (RAD) transmite a missão à equipe de campo.
* **Ciclo completo de despacho:** classificação de gravidade → validação de endereço → seleção de recurso → despacho via CAD/rádio → deslocamento → atendimento em cena → definição de destino hospitalar (via Central de Leitos, SES-DF) → handoff clínico no hospital → encerramento administrativo (RAPH, CID, estatística).
* **Gestão de Frota:** abastecimento, manutenção, troca de turno e monitoramento em tempo real via CAD/CERU.

## 3. Evidências Físicas

* **Sistemas de TI:** CAD (CBMDF) e CERU (SAMU) como eixos de registro digital da ocorrência.
* **Documentação:** RAPH (Relatório de Atendimento Pré-Hospitalar), gravações telefônicas, logs de geolocalização/GPS.
* **Ambiente/Equipamento:** viaturas (USB/USA/UR), uniformes distintos (CBMDF/SAMU), macas, monitores/desfibriladores, kits de trauma — todos percebidos diretamente pelo cidadão.

## 4. Normativos Aplicáveis

* **Portaria Conjunta nº 40/2018 (SUAPH):** normativo central para integração CBMDF-SAMU no DF.
* **Portaria GM/MS nº 2.048/2002:** base nacional para APH Móvel.
* **Política Nacional de Atenção às Urgências (PNAU):** enquadramento da rede de urgências.
* **Lei Distrital nº 8.255/1991:** estrutura do CBMDF.

## 5. Fail Points Conhecidos

* **Fluxo de Chamada:** endereço incorreto, chamadas interrompidas, trotes, falha de georreferenciamento.
* **Operacional:** chamadas duplicadas (despacho duplo), comunicação rádio em zonas de sombra, cenas inseguras, indisponibilidade de frota, conflito de priorização em múltiplas ocorrências simultâneas.
* **Interinstitucional/Hospitalar:** superlotação com retenção de maca, recusa de transporte pelo paciente, recusa hospitalar/redirecionamento, falha de identificação do paciente no handoff, handoff incompleto.
* **Intercentral:** "ping-pong" 192/193 — cidadão redirecionado sem atendimento conclusivo.

---

## 6. Tratamento Explícito das Inferências Mal Suportadas (Falhas 26–30 da audit_v1)

A auditoria apontou cinco inferências sem sustentação suficiente na v1. Esta seção as trata uma a uma:

### Falha 26 — "Bombeiro chega mais rápido" como comportamento generalizado
**Tratamento (c) — Pendente/Em aberto:** A afirmação foi removida da v2. Reconhece-se que a percepção de rapidez pode variar por região, tipo de ocorrência e histórico local. Sem dados de pesquisa de opinião ou registros de chamadas com motivo de escolha declarado, não é possível generalizar. *Ponto declarado como pendente.*

### Falha 27 — "Não há campanha educativa robusta"
**Tratamento (b) — Defesa com argumento:** A ausência de campanhas massivas e contínuas é inferida da inexistência de materiais públicos de grande alcance (TV, rádio, outdoor) produzidos pela SES-DF ou CBMDF nos últimos três anos consultáveis. A afirmação é qualitativa e reconhecidamente não quantificada; foi reformulada para "não constituem campanhas educativas massivas" em vez de negação absoluta.

### Falha 28 — "Ponto de atenção comum em auditorias de órgãos de controle"
**Tratamento (a) — Corrigido:** A afirmação foi removida por ausência de fonte. Substituída por referência direta à Portaria Conjunta nº 40/2018 como documento normativo verificável.

### Falha 29 — "A periferia sofre mais com a demora"
**Tratamento (c) — Pendente/Em aberto:** A afirmação é plausível dado o padrão de distribuição geográfica de viaturas no DF, mas não há indicador público de tempo-resposta desagregado por região administrativa disponível. *Ponto declarado como pendente — requer acesso a dados operacionais do CBMDF/SAMU.*

### Falha 30 — "Competência nebulosa em rodovias"
**Tratamento (b) — Defesa com argumento:** A sobreposição de competências em rodovias federais (BRs) e distritais (DFs) é estrutural: o CBMDF tem competência territorial no DF (Lei 8.255/1991), mas a PRF e o SAMU também atuam em rodovias. A ausência de um manual público que defina o critério de primazia em cada via é o que sustenta a observação — não uma afirmação sobre incompetência, mas sobre ausência de protocolo público consolidado.

---

## Lacunas e Incertezas (Pendentes)

1. **Indicadores de Tempo-Resposta:** não há transparência ativa sobre tempo médio de resposta por região no DF.
2. **Auditoria do SUAPH:** relatórios formais do TCDF ou CGU sobre a integração real CAD/CERU não foram acessados.
3. **Eficácia educativa:** ausência de métricas de impacto de campanhas — inferência qualitativa declarada.
4. **Competência em rodovias:** ausência de protocolo público consolidado sobre primazia de atuação em BRs/DFs.
