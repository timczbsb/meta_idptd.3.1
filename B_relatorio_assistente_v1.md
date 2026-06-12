Esta é uma síntese estruturada do Atendimento Pré-Hospitalar (APH) no Distrito Federal, desenhada para servir de base para o seu **Service Blueprint AS-IS**.

---

## 1. Jornada do Cidadão: A Perspectiva do Usuário

A jornada no DF é marcada pela **incerteza na escolha do canal**.

* **Decisão (O dilema 192 vs. 193):** O cidadão em crise não distingue "urgência clínica" (SAMU) de "emergência traumática/resgate" (CBMDF). Frequentemente, a escolha é baseada na percepção de rapidez ("Bombeiro chega mais rápido") ou pela cultura local de sempre chamar os bombeiros para qualquer sinistro. Não há campanha educativa robusta que oriente sobre a separação de competências.
* **Espera e Triagem:** O cidadão experimenta a chamada como uma barreira técnica. O tempo entre o "alô" e a coleta do endereço é crítico. Se a chamada cai no 193 e o caso é puramente clínico, a transferência de linha gera ansiedade (o cidadão sente que está "perdendo tempo").
* **Feedback:** Inexistente. O cidadão raramente recebe um número de protocolo claro ou acompanhamento do status (ex: "a viatura está a 2km"). O encerramento ocorre com a entrega da vítima ao hospital ou o encerramento da cena, sem comunicação pós-atendimento.

---

## 2. Processos de Bastidor (Backstage)

* **COCB (193):** Opera via sistema CAD (Computer-Aided Dispatch) próprio. O foco é o despacho rápido. Possui uma frota de viaturas de resgate (URs) equipadas com socorristas (nível técnico/intermediário). A tomada de decisão é baseada em protocolos de trauma e atendimento tático.
* **SAMU (192):** Foca na regulação médica. O TARM atende, coleta dados e repassa ao Médico Regulador. A decisão de enviar (ou não) uma unidade de suporte avançado (USA) ou básico (USB) é estritamente médica. Segue protocolos nacionais de regulação (Portaria 2.048/2002).
* **Integração:** Embora existam planos de contingência, a integração de sistemas de TI entre CBMDF e SES-DF é **limitada**. O "handoff" (transferência) de informações entre centrais ainda depende, em muitos casos, de contato telefônico direto entre operadores, e não de um sistema unificado em tempo real.

---

## 3. Evidências Físicas

* **Auditivas:** O "tom de chamada" e a URA das centrais. A voz do operador/médico (autoridade e calma). O som da sirene (sinal de alívio ou de agravamento da cena).
* **Documentais:** O **Relatório de Atendimento Pré-Hospitalar (RAPH)**, que é a peça jurídica principal. O cidadão raramente recebe uma cópia física imediata, exceto em casos onde é entregue um boletim ou declaração de atendimento.
* **Visuais:** O contraste entre a farda (CBMDF) e o uniforme (SAMU/SES). O veículo (viaturas grandes de resgate dos bombeiros vs. ambulâncias padrão do SAMU).

---

## 4. Normativos Aplicáveis

* **Portaria GM/MS nº 2.048/2002:** O pilar fundamental que define a organização do APH Móvel no Brasil.
* **Lei Distrital nº 8.255/1991:** Dispõe sobre a organização do CBMDF, garantindo o papel de resgate e APH.
* **Portaria nº 1.010/2012:** Institui as diretrizes para a implantação do componente do APH Móvel da Rede de Atenção às Urgências.
* **Acordos:** A operação no DF é guiada por protocolos operacionais internos, mas a falta de um "Convênio de Integração Única" atualizado e público com metas de desempenho cruzadas é um ponto de atenção comum em auditorias de órgãos de controle.

---

## 5. Fail Points (Pontos Críticos)

* **Despacho Duplo:** Ocorre quando o cidadão liga para os dois números simultaneamente. Sem um sistema de cruzamento de dados de georreferenciamento em tempo real entre 192 e 193, duas viaturas podem ser enviadas para o mesmo local, gerando desperdício de recursos públicos.
* **O "Ping-Pong" de Chamadas:** A falha na transferência de chamada entre 193 e 192 é um ponto de fricção. Se o operador do 193 não consegue passar a linha e apenas pede para o cidadão "ligar no 192", o tempo de resposta aumenta significativamente.
* **Sobrecarga Hospitalar:** O "travamento" de viaturas nas portas de hospitais públicos (devido à falta de leitos ou demora no recebimento da maca) retira as unidades das ruas, aumentando o tempo de resposta para novas chamadas (o gargalo não é o despacho, mas a recepção hospitalar).
* **Geografia do DF:** A dispersão das regiões administrativas cria tempos de resposta desiguais, onde a periferia sofre mais com a demora do que o Plano Piloto.

---

## Lacunas e Incertezas

Para o seu *Blueprint*, atente-se a estes pontos que não possuem transparência ativa clara no DF:

1. **Taxa de Abandono de Chamadas:** Não há divulgação pública e periódica do tempo médio de espera no 192/193 no DF.
2. **Protocolo de Interoperabilidade:** Não há um documento público que descreva o funcionamento técnico da API ou integração entre o software de despacho do CBMDF e o sistema do SAMU.
3. **Matriz de Responsabilidade:** Em casos de atendimento em rodovias (DFs e BRs), a linha que separa a competência de atuação entre SAMU e CBMDF é, por vezes, nebulosa e baseada em tradição operacional, não em manual técnico disponível ao cidadão.

---

**Sugestão para a próxima etapa:** Considerando que você busca montar o *Service Blueprint AS-IS*, você pretende focar a sua análise na experiência da "Regulação" (a decisão médica) ou no "Despacho de Campo" (a logística das viaturas)?
