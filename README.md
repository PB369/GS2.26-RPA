# Assistente Inteligente de Agendamento e Zeladoria de Agenda

---

## 👥 Integrantes

RM550219 - Arthur Baldissera
RM97937 - Pedro Barros
RM550166 - Ricardo Vergani
RM551649 - Victor Kenzo

---

## 📋 Sobre o Projeto

O Assistente Inteligente de Agendamento e Zeladoria de Agenda é uma solução desenvolvida para auxiliar microempreendedores, profissionais autônomos e pequenos negócios na gestão eficiente de compromissos e eventos.

A solução tem como objetivo automatizar atividades administrativas relacionadas à agenda, reduzindo esquecimentos, melhorando a organização operacional e minimizando perdas financeiras decorrentes de cancelamentos, conflitos de horários e falhas de comunicação.

Por meio de uma interface conversacional no Microsoft Teams, os usuários podem interagir em linguagem natural para realizar agendamentos, consultas, reagendamentos e cancelamentos de compromissos. As informações são automaticamente registradas e sincronizadas com o Outlook Calendar, permitindo a visualização dos compromissos diretamente no calendário corporativo.

Além disso, a solução implementa mecanismos de zeladoria da agenda por meio de notificações automáticas de eventos futuros, auxiliando os profissionais na gestão do tempo e no cumprimento de seus compromissos.

---

## 🎯 Problema Resolvido

Muitos profissionais autônomos dependem diretamente da sua agenda para gerar renda, porém frequentemente realizam o gerenciamento de compromissos de forma manual.

Essa realidade gera problemas como:

- Esquecimento de compromissos;
- Dificuldade para acompanhar reagendamentos;
- Falta de organização dos atendimentos;
- Perda de produtividade;
- Horários ociosos;
- Falta de rastreabilidade dos eventos realizados.

O projeto busca democratizar o acesso à automação, oferecendo uma alternativa simples e acessível baseada em ferramentas amplamente utilizadas no ambiente corporativo.

---

## 🚀 Funcionalidades

### Agendamento de Eventos

Permite criar novos compromissos por meio de um formulário adaptativo no Microsoft Teams.

### Consulta de Agenda

Exibe os compromissos pendentes cadastrados na agenda do usuário.

### Reagendamento

Atualiza compromissos existentes mantendo a sincronização entre Outlook e base de controle.

### Cancelamento

Remove o compromisso do calendário e mantém o histórico na base de auditoria.

### Notificações Automáticas

Envia lembretes automáticos próximos ao horário do compromisso.

### Auditoria e Rastreabilidade

Mantém histórico completo dos registros em planilha Excel.

---

## 🏗️ Arquitetura da Solução

### Fluxo 1 - Agendamento Automatizado de Eventos

<p align="center">
  <img src="images/Fluxo 1 - Gerenciamento de Agenda.drawio.png" alt="Arquitetura do Fluxo 1" width="900">
</p>

### Fluxo 2 - Notificações Automáticas de Eventos Iminentes

<p align="center">
  <img src="images/Fluxo 2 - Notificação de Eventos Iminentes.drawio.png" alt="Arquitetura do Fluxo 2" width="900">
</p>

### Ferramentas Utilizadas

#### Microsoft Teams

Canal de interação entre o usuário e o assistente.

#### Power Automate

Responsável pela orquestração dos fluxos e automações.

#### Outlook Calendar

Responsável pela criação, atualização e gerenciamento dos eventos.

#### Excel Online

Base de dados utilizada para controle, auditoria e rastreabilidade.

---

## 🧠 Regras de Negócio

### Classificação de Intenção

As mensagens dos usuários são classificadas em:

- AGENDAR
- CONSULTAR
- REAGENDAR
- CANCELAR
- NULO

### Agendamento

- Cria evento no Outlook.
- Registra informações no Excel.
- Gera identificador único.
- Adiciona participantes opcionais.

### Reagendamento

- Localiza o compromisso pelo ID.
- Atualiza o evento no Outlook.
- Atualiza os registros de auditoria.

### Cancelamento

- Remove o evento do calendário.
- Preserva o histórico.
- Atualiza o status para "Cancelado".

### Consulta

- Retorna apenas compromissos ativos.
- Organiza os resultados por ordem cronológica.

---

## 📊 Auditoria

Todos os eventos são registrados em uma planilha Excel contendo informações para auditoria e rastreabilidade.

### Campos Registrados

| Campo |
|---------|
| ID |
| Título |
| Nome Cliente |
| Data Início |
| Data Fim |
| Status |
| EventoOutlookID |

### Benefícios

- Histórico completo das operações;
- Recuperação de informações;
- Rastreabilidade dos eventos;
- Evidências para auditoria.

---

## 🔒 Segurança e LGPD

A solução foi projetada respeitando os princípios da Lei Geral de Proteção de Dados (LGPD).

### Dados Utilizados no Projeto

- Nome e E-mails dos participantes;
- ID do Chat do Flow Bot;
- Informações do evento na agenda Outlook.

### Medidas Adotadas

- Autenticação corporativa Microsoft 365;
- Armazenamento em ambiente Microsoft;
- Uso mínimo de dados necessários;
- Uso de variáveis de ambiente;
- Controle de acesso por usuário;
- Registro de auditoria das operações.

---

## ⚠️ Limitações do MVP

O projeto foi construído utilizando o Flow Bot do Microsoft Teams para demonstrar a viabilidade técnica da solução.

Como limitação da plataforma utilizada, o Teams exibe automaticamente uma mensagem padrão do Flow Bot ao iniciar uma conversa, comportamento que não pode ser customizado utilizando apenas os recursos disponíveis no escopo do projeto.

Apesar dessa limitação de experiência do usuário, todas as funcionalidades da solução permanecem plenamente operacionais.

Em uma evolução de produção, a arquitetura poderá utilizar:

- Microsoft Copilot Studio;
- Microsoft Teams Apps;
- WhatsApp Business API;

---

## 🌱 ODS Atendidos

### ODS 9 – Indústria, Inovação e Infraestrutura

Democratização do acesso à automação para pequenos negócios.

### ODS 10 – Redução das Desigualdades

Disponibilização de tecnologias normalmente acessíveis apenas a grandes organizações.

### ODS 11 – Cidades e Comunidades Sustentáveis

Fortalecimento da economia local por meio da melhoria da eficiência operacional dos pequenos prestadores de serviço.

---

## 📖 Instruções de Utilização

### Pré-requisitos

- Conta Microsoft 365
- Microsoft Teams
- Power Automate
- Outlook
- Excel Online (OneDrive ou SharePoint)

### Configuração

1. Importar os fluxos do Power Automate.
2. Configurar as conexões Microsoft 365.
3. Criar a planilha de auditoria.
4. Ajustar os identificadores de calendário.
5. Validar os gatilhos e permissões.

### Utilização

#### Agendar

```text
Quero agendar um compromisso
```

#### Consultar

```text
Quero consultar minha agenda
```

#### Reagendar

```text
Quero reagendar um compromisso
```

#### Cancelar

```text
Quero cancelar um compromisso
```

---

## 🔗 Vídeo Demonstrativo

> [https://www.youtube.com/watch?v=HNA-qLBZfv8](https://www.youtube.com/watch?v=HNA-qLBZfv8)


---

## 📄 Licença

Projeto desenvolvido exclusivamente para fins acadêmicos no contexto do desafio CitizenTech.