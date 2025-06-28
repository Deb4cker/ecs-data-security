---
title: Art. 47º Segurança Contínua - Mesmo Depois que o Tratamento
parent: Capítulo VII - DA SEGURANÇA E DAS BOAS PRÁTICAS
nav_order: 2
---

## Art. 47º: Segurança Contínua - Mesmo Depois que o Tratamento Acaba

O Artigo 47 da LGPD deixa claro que a responsabilidade pela segurança dos dados pessoais não termina quando o tratamento desses dados é encerrado. Mesmo após a exclusão, arquivamento ou transferência dos dados, os agentes de tratamento continuam obrigados a garantir sua proteção contra acessos indevidos, vazamentos, alterações ou perdas.

A segurança deve ser pensada como algo contínuo, que atravessa todo o ciclo de vida do dado — da coleta à destruição. Isso reforça a importância de planejar e implementar mecanismos que garantam a proteção das informações mesmo quando elas não estão mais em uso ativo.

### O que isso significa para você, desenvolvedor?

Que não adianta desenvolver um sistema que apenas protege os dados enquanto estão sendo usados. Como desenvolvedor, você também é responsável por garantir que, mesmo depois que os dados forem arquivados, migrados ou descartados, eles continuem seguros. Isso exige um pensamento de segurança que vai além do uso imediato — é necessário cuidar do ciclo completo da informação.

### Impacto no Dev e Como Diminuir o Risco:

#### 1. Segurança durante todo o ciclo de vida dos dados

A segurança precisa estar presente desde o momento em que o dado é coletado até sua exclusão final. Pensar nisso desde o início do projeto evita vulnerabilidades mais difíceis de corrigir depois.

**Boas Práticas:**

- **Política de retenção e descarte:** Defina por quanto tempo os dados serão mantidos e como serão descartados de forma segura (exclusão definitiva, destruição de mídia, etc.).
- **Proteção de dados inativos:** Utilize criptografia ou anonimização para proteger dados que não estão em uso ativo, como backups e arquivos antigos.
- **Auditoria e rastreabilidade:** Mantenha logs de acesso e modificação, mesmo após o fim do uso dos dados, para possibilitar investigações de incidentes.

```go
// Exemplo simples de descarte seguro em Go
package main

import (
    "os"
    "log"
)

func deleteFileSecurely(filePath string) {
    err := os.Remove(filePath)
    if err != nil {
        log.Fatalf("Erro ao excluir arquivo: %v", err)
    }
    log.Println("Arquivo excluído com sucesso.")
}
```

#### 2. Proteção de dados em repouso e ambientes arquivados

Dados armazenados, mesmo sem uso frequente, podem ser alvo de ataques ou vazamentos. A proteção precisa continuar mesmo em cenários como desativação de sistemas ou migração.

**Boas Práticas:**

- **Criptografia de dados armazenados:** Garanta que bancos de dados, arquivos e backups estejam criptografados.
- **Controles de acesso rigorosos:** Aplique as mesmas restrições de acesso em dados arquivados que você aplicaria a dados em uso.
- **Backup seguro e testado:** Implemente rotinas de backup que garantam integridade e confidencialidade, e teste regularmente os processos de recuperação.

```go
// Exemplo de criptografia AES (simples) para dados em repouso
package main

import (
    "crypto/aes"
    "crypto/cipher"
    "crypto/rand"
    "io"
)

func encrypt(plainText, key []byte) ([]byte, error) {
    block, err := aes.NewCipher(key)
    if err != nil {
        return nil, err
    }

    cipherText := make([]byte, aes.BlockSize+len(plainText))
    iv := cipherText[:aes.BlockSize]
    if _, err := io.ReadFull(rand.Reader, iv); err != nil {
        return nil, err
    }

    stream := cipher.NewCFBEncrypter(block, iv)
    stream.XORKeyStream(cipherText[aes.BlockSize:], plainText)

    return cipherText, nil
}
```

#### 3. Documentação e atualização constante

A responsabilidade sobre os dados não termina com a entrega do sistema. A segurança contínua exige também controle sobre o que foi implementado e como os dados evoluem.

**Boas Práticas:**

- **Documentação técnica de segurança:** Registre como os dados são tratados, criptografados e protegidos, isso ajuda futuras manutenções e auditorias.
- **Treinamento de equipe:** Mantenha os times atualizados sobre boas práticas e os requisitos da LGPD.
- **Revisão periódica de políticas:** Atualize suas políticas de segurança com base nas mudanças tecnológicas, ameaças ou exigências legais.

### Conclusão do Art. 47

O Art. 47 mostra que proteger dados não é uma tarefa pontual, é um compromisso contínuo. O desenvolvedor, estando diretamente envolvido na criação de sistemas que lidam com dados pessoais, precisa projetar soluções que garantam essa segurança até o fim do ciclo de vida da informação. Não basta proteger durante o uso: é preciso pensar também no que vem depois, seja arquivamento, migração, descarte. A segurança precisa ser uma responsabilidade permanente, e o seu papel como desenvolvedor é essencial para isso acontecer.
