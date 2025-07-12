---
title: Art. 53º Como a Multa é Calculada? Entendendo a Metodologia da ANPD
parent: Capítulo VIII - DA FISCALIZAÇÃO
nav_order: 2
---

## Art. 53: Como a Multa é Calculada? Entendendo a Metodologia da ANPD

O Artigo 53 da LGPD fala sobre como a Autoridade Nacional de Proteção de Dados (ANPD) vai definir as regras para calcular o valor das multas. Basicamente, a ANPD precisa criar um jeito claro e transparente, ou seja, uma metodologia para isso, de modo que qualquer um entenda o que deve ser publicado e passar por consulta pública. Essa metodologia vai detalhar como o valor-base das multas será calculado, levando em conta os critérios que vimos no Art. 52.

### O que isso significa para você, desenvolvedor?

Embora você não vá ficar calculando multas, é importante entender que existe uma metodologia e que ela é baseada em critérios específicos. É bom sempre ter documentadas as boas práticas de segurança de dados que você implementa. Se a empresa for alvo de uma fiscalização, mostrar que ela segue as melhores práticas e tem um bom histórico de conformidade pode fazer com que a multa seja menos pesada.

### Transparência na Metodologia: Pra que serve?

*   **Previsibilidade:** Empresas sabem o que esperar se errarem, e isso ajuda a se organizar.
*   **Justiça:** As regras são claras, e a punição é justa.
*   **Incentivo à Boa Conduta:** Se a empresa faz o certo, a multa pode ser menor. Isso faz com que todo mundo se esforce mais.

### 📰 Caso Real:
 Em 2023, a ANPD multou uma empresa de telemarketing por tratamento indevido de dados pessoais, reforçando a importância da metodologia de cálculo da multa prevista no Art. 53 da LGPD. [Saiba mais](https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-aplica-a-primeira-multa-por-descumprimento-a-lgpd)

<img style="border-radius:20px" src="../images/primeira_da_anpd.png" alt="Primeira multa com base na lgpd" width="300px"/>
<p style="font-size: 0.5em; color: #555;"><em>Disponível em: https://www.gov.br/anpd/pt-br/assuntos/noticias/anpd-aplica-a-primeira-multa-por-descumprimento-a-lgpd</em></p>

Em 2023, a ANPD multou a empresa Telekall por usar dados de WhatsApp de eleitores sem base legal, durante as eleições de 2020. A empresa também não tinha um encarregado de dados e ignorou determinações da fiscalização. Mesmo sendo microempresa, a falta de controle e documentação pesou na decisão da ANPD.

 Veja a multa aplicada [aqui](https://www.gov.br/anpd/pt-br/assuntos/noticias/sei_00261-000489_2022_62_decisao_telekall_inforservice.pdf)

#### Infrações cometidas pela Telekall Infoservice:
**Tratamento de dados sem base legal adequada**
 - Violou o Art. 7º da LGPD, que exige uma base legal (como consentimento, obrigação legal, execução de contrato etc.) para tratar dados pessoais.
 A empresa oferecia listas de contatos do WhatsApp de eleitores para fins eleitorais sem consentimento ou outra base legal válida.

**Ausência de Encarregado pelo Tratamento de Dados**
- Violou o Art. 41 da LGPD, que obriga empresas a nomearem um encarregado (DPO) — a pessoa responsável por intermediar a relação com titulares e a ANPD.
A Telekall não comprovou a nomeação desse encarregado, o que é exigido mesmo para microempresas, a menos que elas comprovem que não tratam dados de alto risco (o que também não foi feito).

### Como o Desenvolvedor Contribui Indiretamente:

Sua contribuição para a metodologia de cálculo de multas não é direta, mas isso não quer dizer que não exista. As informações que você ajuda a gerar e a proteger podem ser usadas para demonstrar a conformidade da empresa e, consequentemente, influenciar o peso da sanção.

*   **Registros de Atividades (Logs):** Logs detalhados e bem mantidos podem provar que a empresa agiu de boa-fé, que as medidas de segurança estavam em vigor e que houve cooperação em caso de incidente.

*   **Documentação de Segurança:** A documentação das medidas técnicas e administrativas implementadas (criptografia, controle de acesso, anonimização, etc.) é um fator que a ANPD leva em conta para deixar a sanção mais leve.

*   **Implementação de Políticas de Governança:** Se o seu código e os sistemas que você desenvolve refletem as políticas de boas práticas e governança da empresa, isso é um ponto positivo na avaliação da ANPD.

### Conclusão do Art. 53

O Art. 53 fala sobre a rigorozidade que a ANPD trata as infrações, mas também o quão claras terão de ser as infrações. Para quem é desenvolvedor, isso quer dizer que, quando se é comprometido com as boas práticas de segurança de dados na empresa, o castigo pode ser reduzido. Tal como alguém com poucas multas de transito tem chance de ser absolvido conforme o histórico.
