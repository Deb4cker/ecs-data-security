---
title: Art. 48º Comunicação de Incidentes de Segurança com Dados Pessoais
parent: Capítulo VII - DA SEGURANÇA E DAS BOAS PRÁTICAS
nav_order: 3
---

## Art. 48º: Comunicação de Incidentes de Segurança com Dados Pessoais

O Art. 48 da LGPD determina que o controlador (quem decide como e por que os dados são tratados) deve **comunicar a ocorrência de qualquer incidente de segurança** que possa causar risco ou dano relevante aos titulares dos dados, tanto à **Autoridade Nacional de Proteção de Dados (ANPD)** quanto aos próprios **titulares** afetados.

Essa comunicação precisa ser feita **em prazo razoável** (definido pela ANPD) e deve conter uma série de informações importantes, como:
- A natureza dos dados afetados,
- Quais titulares foram atingidos,
- Que medidas técnicas foram adotadas,
- Quais os riscos do incidente,
- Por que houve demora (caso a notificação não tenha sido imediata),
- E o que está sendo feito para reverter ou mitigar o problema.

A ANPD pode ainda determinar medidas adicionais, como **divulgação pública** e **ações específicas de mitigação**. Ela também vai avaliar se os dados estavam adequadamente protegidos, por exemplo, com criptografia.

<img style="border-radius:20px" src="../images/controlador_operador.jpeg" width="500px"/>

### O que isso significa para você, desenvolvedor?

Significa que **vazamento de dados é coisa séria**, e que o sistema precisa estar preparado para detectar, responder e reportar esse tipo de problema rapidamente. Mesmo que você não seja o responsável legal pelo tratamento dos dados, **seu código pode ser a origem do incidente**, e isso afeta diretamente a empresa e os usuários.

De forma bem direta: uma falha de segurança mal resolvida no seu código pode virar uma crise jurídica. E a sua habilidade de registrar, investigar e reagir rápido faz toda a diferença.

### 📰 Casos Reais:
- [CNN Brasil Money
XP informa "acesso indevido" a dados de clientes](https://www.cnnbrasil.com.br/economia/macroeconomia/xp-informa-acesso-indevido-a-dados-de-clientes/)
- [Adidas revela vazamento de dados de clientes](https://g1.globo.com/tecnologia/noticia/2025/05/26/adidas-revela-vazamento-de-dados-de-clientes.ghtml)
- [Dados ANPD](https://app.powerbi.com/view?r=eyJrIjoiN2QxOGJmMTUtMjBmMi00YjdlLTkxMDEtM2U2ZTJkN2I3Mjc3IiwidCI6IjVhYmEwNGExLWY4NjMtNGI1Ni04MTdkLTQ0MjkxYzkwZDFiOCJ9)

### Para Você, Dev: Como Atuar na Prática

#### 1. Preparar o sistema para detectar e registrar incidentes

Se não há logs, alertas e monitoramento, os incidentes passam despercebidos ou só são percebidos quando já é tarde demais. 

**Boas Práticas:**

- Registre todas as tentativas suspeitas de acesso aos dados (logs de segurança);
- Implemente alertas automáticos para comportamento fora do padrão;
- Use ferramentas de SIEM, APM ou observabilidade para rastrear anomalias.

**Exemplo de Código:**

Como exemplo, uma aplicação em Node.js que faz o registro de log de acessos suspeitos:

```javascript
function logAcessoSuspeito(usuarioId, ip, motivo) {
  const log = {
    usuarioId,
    ip,
    motivo,
    data: new Date().toISOString(),
  };

  db.collection('logs_incidentes').insertOne(log);
}
```

Explicação do código: uma função que captura o identificador do usuário, o IP de origem do mesmo e o motivo pelo qual o acesso é classificado como suspeito, registrando no banco de dados para análises e visualizações em tempo real.

#### 2. Ter um plano de resposta e comunicação de incidentes

Não basta detectar o problema. A empresa e o desenvolvedor precisam estar preparados para agir rápido, coletar as informações corretas e comunicar da forma adequada à ANPD e aos usuários afetados.

**Boas Práticas:**

- Documente um plano de resposta a incidentes (quem faz o quê, em quanto tempo);
- Garanta que os logs armazenem dados úteis e que possam fornecer todas as informações requisitadas pela ANPD em caso de incidentes;
- Implemente medidas de contenção (como revogação de tokens ou bloqueio de acessos).

**Exemplo de Código:**

Como exemplo, uma aplicação em Python que notifica os usuários do sistema sobre incidentes de segurança:

```python
def notificar_usuarios(lista_emails, descricao_incidente):
    for email in lista_emails:
        enviar_email(
            destinatario=email,
            assunto="Aviso de incidente de segurança",
            corpo=f("Identificamos um incidente que pode ter afetado seus dados."
                    "Estamos tomando medidas corretivas.")
        )
```

Explicação do código: uma função que recebe uma lista dos e-mails dos usuários registrados no sistema e faz o envio de um e-mail informando sobre o incidente de segurança e salientando que as medidas corretivas estão sendo tomadas.

#### 3. Criptografar dados e garantir ininteligibilidade

O §3º do artigo menciona que, caso os dados tenham sido protegidos com medidas técnicas que os tornem ininteligíveis (como criptografia), isso será considerado na avaliação da gravidade.

**Boas Práticas:**

- Criptografe dados sensíveis em repouso;
- Use hashing para senhas e outros dados não reversíveis;
- Garanta que apenas usuários autorizados consigam descriptografar os dados.

**Exemplo de Código:**

```javascript
String senha = "3lkjgS$g4k"; // Senha do usuário
String senhaHash = BCrypt.hashpw(senha, BCrypt.gensalt()); // Criptografia da senha
// Senha criptografada: $2y$10$VGDgZZOuj.RwxdtjLwA0W.b9JpA9CRUmkUOkQaa9fvM9mgEMC0Uta
```

### Conclusão do Art. 48

O Art. 48 da LGPD reforça que transparência e agilidade são essenciais quando há falhas de segurança. Para o desenvolvedor, isso significa logar, monitorar, reagir rápido e proteger os dados desde o início. Mesmo que o incidente nunca aconteça, a melhor maneira de se proteger e proteger os usuários é estar pronto como se ele fosse inevitável.
