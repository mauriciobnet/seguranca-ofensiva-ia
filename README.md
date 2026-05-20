# Ataques Inteligentes na Prática: Como a IA está tornando Hackers mais Perigosos

> Palestra realizada no **Centro Universitário Campo Real** — Guarapuava, PR  
> Data: 20 de maio de 2026

Material de apoio para a atividade prática da palestra. Contém os slides, os repositórios com código vulnerável e o prompt pronto para análise com IA.

---

## Slides da Palestra

Acesse a apresentação completa pelo link abaixo (abre no navegador, sem necessidade de instalação):

**[Ver Slides](https://mauriciobnet.github.io/seguranca-ofensiva-ia/slides/)**

---

## Lab de Pentest com IA

Demonstração ao vivo apresentada na palestra: pipeline completo de ataque automatizado com IA rodando em dois containers Docker.

**[ai-pentest-lab](https://github.com/mauriciobnet/ai-pentest-lab)** — `nmap -sV` → Claude AI (análise de CVEs) → exploit automático do CVE-2011-2523 (vsftpd 2.3.4) → shell root interativo.

---

## Sobre a Atividade

Durante a palestra, você vai usar o **Claude (claude.ai)** para analisar código-fonte real de projetos simulados e identificar vulnerabilidades de segurança — o mesmo tipo de análise que atacantes e profissionais de segurança realizam no dia a dia.

Os repositórios abaixo foram desenvolvidos intencionalmente com falhas reais. Seu trabalho é usar a IA para encontrá-las, entender como seriam exploradas e como corrigi-las.

---

## Repositórios para Análise

Cada repositório simula um projeto real com uma vulnerabilidade diferente integrada naturalmente ao código:

| # | Repositório | Linguagem | Vulnerabilidade | CWE |
|---|-------------|-----------|-----------------|-----|
| 1 | [student-grade-api](https://github.com/mauriciobnet/student-grade-api) | Python / Flask | SQL Injection | CWE-89 |
| 2 | [tcc-upload-manager](https://github.com/mauriciobnet/tcc-upload-manager) | PHP | Path Traversal | CWE-22 |
| 3 | [server-backup-tool](https://github.com/mauriciobnet/server-backup-tool) | Bash | Command Injection | CWE-78 |
| 4 | [admin-panel-auth](https://github.com/mauriciobnet/admin-panel-auth) | Node.js | Hardcoded Credentials | CWE-798 |
| 5 | [iot-sensor-monitor](https://github.com/mauriciobnet/iot-sensor-monitor) | C | Stack Buffer Overflow | CWE-121 |

---

## Como Participar da Atividade

### 1. Acesse o Claude

Abra [claude.ai](https://claude.ai) no seu navegador. A conta gratuita é suficiente.

### 2. Cole o prompt abaixo

Copie o bloco completo e cole diretamente na janela de chat do Claude:

---

```
Você é um analista de segurança de software. Sua tarefa é analisar o código-fonte de repositórios GitHub e identificar vulnerabilidades de segurança reais.

Analise os seguintes repositórios públicos, um por vez, acessando os arquivos diretamente pelo GitHub:

1. https://github.com/mauriciobnet/student-grade-api
2. https://github.com/mauriciobnet/tcc-upload-manager
3. https://github.com/mauriciobnet/server-backup-tool
4. https://github.com/mauriciobnet/admin-panel-auth
5. https://github.com/mauriciobnet/iot-sensor-monitor

Para cada repositório, siga estas etapas:

**Etapa 1 — Reconhecimento**
- Leia o README.md para entender o propósito do sistema
- Liste os arquivos presentes no repositório
- Identifique a linguagem, framework e tecnologias usadas

**Etapa 2 — Análise de código**
- Leia cada arquivo de código-fonte
- Preste atenção especial em: entradas do usuário, operações com arquivos, queries de banco de dados, autenticação, comandos do sistema e gerenciamento de memória
- Procure por padrões inseguros conhecidos

**Etapa 3 — Relatório por repositório**

Para cada vulnerabilidade encontrada, informe:

- **Nome da vulnerabilidade** (ex: SQL Injection)
- **CWE correspondente** (ex: CWE-89)
- **Arquivo e linha exata** onde está o problema
- **Trecho de código vulnerável** (cite o código real)
- **Explicação** do que torna esse trecho inseguro
- **Exemplo de exploit** — como um atacante poderia explorar isso (input malicioso, payload, etc.)
- **Impacto** — o que o atacante consegue com a exploração bem-sucedida
- **Correção recomendada** — como o código deveria ser reescrito para ser seguro

**Etapa 4 — Resumo final**

Após analisar todos os repositórios, produza uma tabela com:

| Repositório | Linguagem | Vulnerabilidade | CWE | Arquivo | Severidade (Alta/Média/Baixa) |

Ordene por severidade, da mais crítica para a menos crítica.

---

Comece pelo repositório 1 (student-grade-api) e avance para os demais na sequência. Seja preciso nas citações de código — copie os trechos exatos dos arquivos, não parafraseie.
```

---

### 3. Acompanhe a análise

O Claude vai acessar cada repositório, ler os arquivos de código e produzir um relatório detalhado com as vulnerabilidades encontradas, exemplos de exploit e sugestões de correção.

**Dica:** antes de rodar o prompt, tente identificar a vulnerabilidade você mesmo lendo o código no GitHub. Depois compare com o que a IA encontrou.

---

## O que você vai aprender

- Como ferramentas de IA aceleram a análise de código para fins ofensivos e defensivos
- Como vulnerabilidades reais se parecem quando estão integradas a um projeto funcional — não isoladas como exemplos de livro
- As principais categorias de falhas de segurança (injeção, traversal, overflow, credenciais expostas) e seu impacto prático
- Como a mesma IA usada por atacantes pode ser usada por desenvolvedores para encontrar e corrigir falhas antes que alguém as explore

---

## Aviso

> ⚠️ Todos os repositórios listados contêm vulnerabilidades **intencionais** para fins exclusivamente educacionais.  
> O uso dessas técnicas contra sistemas reais sem autorização é ilegal. Este material destina-se apenas a ambientes controlados de aprendizado.
