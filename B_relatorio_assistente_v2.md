Com base na auditoria detalhada apresentada, preparei esta segunda versão (v2) da pesquisa sobre o Atendimento Pré-Hospitalar (APH) no Distrito Federal. O objetivo desta revisão é consolidar um mapeamento operacional rigoroso, corrigindo imprecisões e preenchendo as lacunas de processo, normativas e fail points identificadas.

---

# Atendimento Pré-Hospitalar (APH) no DF: Mapeamento Operacional (v2)

Esta versão atualiza o diagnóstico do APH no DF, integrando o **SUAPH (Portaria Conjunta nº 40/2018)** como o eixo central da operação integrada.

## 1. Jornada do Cidadão (Perspectiva do Usuário)

* **O Dilema do Acesso:** O cidadão, em momento de crise, frequentemente não diferencia a natureza da emergência (clínica vs. traumática). A escolha entre 192 e 193 é, muitas vezes, fortuita.
* **A Experiência do Fluxo:** O cidadão percebe a chamada como um único evento, mas a interface técnica entre CBMDF e SAMU pode ocultar a complexidade da transferência. A falta de um sistema de retorno (feedback) sobre o status da viatura ou tempo estimado de chegada é uma lacuna na experiência do usuário.
* **Conscientização:** Embora existam orientações nos sites oficiais sobre o papel de cada serviço (SAMU para casos clínicos e CBMDF para trauma/resgate), estas não constituem campanhas educativas massivas, deixando o cidadão dependente da percepção do atendente no momento da chamada.

## 2. Processos de Bastidor (Backstage)

A operação é regida pelo **SUAPH**, que estabelece a padronização e integração.

* **Triagem e Regulação:** Toda chamada passa por triagem inicial (TARM/Operador). No SAMU, o Médico Regulador exerce o papel central, decidindo o tipo de recurso (USB, USA, motolância, aeronave). No CBMDF, o processo segue protocolos de despacho operacional sob responsabilidade do COCB.
* **Ciclo de Despacho:** O processo completo abrange: classificação de gravidade, validação de endereço, seleção de recurso, despacho, deslocamento, atendimento em cena, definição de destino hospitalar (baseada em capacidade de leitos e perfil assistencial) e, finalmente, o handoff clínico no hospital.
* **Gestão de Frota:** O backstage inclui a gestão dinâmica de viaturas (abastecimento, manutenção, troca de turno) e o monitoramento em tempo real via sistema CAD/CERU.

## 3. Evidências Físicas

* **Sistemas de TI:** CAD (Computer-Aided Dispatch) e CERU (Central de Regulação) são os eixos onde a ocorrência ganha vida digital.
* **Documentação:** O RAPH (Relatório de Atendimento Pré-Hospitalar) é o artefato central, além dos registros de gravação telefônica e logs do sistema de geolocalização.
* **Ambiente/Equipamento:** Viaturas, uniformes distintos (CBMDF/SAMU), macas, monitores/desfibriladores e kits de trauma compõem a evidência sensorial do atendimento.

## 4. Normativos Aplicáveis

* **Portaria Conjunta nº 40/2018 (SUAPH):** O documento fundamental que define a integração, compartilhamento de TI e protocolos conjuntos no DF.
* **Portaria GM/MS nº 2.048/2002:** Base nacional para a organização de urgências.
* **Lei Distrital nº 8.255/1991:** Estrutura a atuação do CBMDF.

## 5. Fail Points Conhecidos

* **Fluxo de Chamada:** Erros no fornecimento de endereço, chamadas interrompidas, trotes e falhas na geolocalização.
* **Operacional:** Chamadas duplicadas (ambos os serviços acionados), dificuldade de comunicação rádio em zonas de sombra, cenas inseguras que impedem o acesso e indisponibilidade de frota.
* **Interinstitucional/Hospitalar:** O gargalo no "handoff" (transferência de cuidados) devido à superlotação hospitalar, que retém viaturas e reduz a disponibilidade operacional.

---

## Lacunas e Incertezas (Pendentes)

Para fins de auditoria, reconhecemos que as seguintes informações não foram confirmadas por dados públicos exaustivos:

1. **Indicadores de Tempo-Resposta:** Não há transparência ativa sobre o tempo médio de resposta segregado por região (periferia vs. plano).
2. **Dados de Auditoria:** Relatórios formais de auditoria do TCDF ou CGU sobre o SUAPH não foram acessados nesta fase.
3. **Eficácia Educativa:** A inexistência de medição de impacto de campanhas educativas é uma inferência baseada na ausência de materiais públicos, carecendo de comprovação via dados da SES/CBMDF.

---

**Nota de Auditoria:** Esta versão v2 incorporou a estrutura do SUAPH (Portaria 40/2018) para sanar a falha de integração, ampliou a descrição das etapas do ciclo de despacho (Fail Points 5-11, 18-25) e corrigiu a redução da atuação do CBMDF apenas ao trauma.

Considerando que este material será a base para o seu Service Blueprint, deseja que eu detalhe o fluxo de uma "ocorrência crítica com necessidade de apoio multiprofissional" (ex: acidente com múltiplas vítimas) para testar os limites dessa integração?
