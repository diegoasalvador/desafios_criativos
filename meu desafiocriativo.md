# 🚀 Desafio: Prompt de Análise de Feedbacks de Clientes Bancários

## 📌 Informações do Projeto
- **Desafio:** Criação de Prompt Inteligente para Análise de Feedbacks
- **Domínio:** Experiência do Cliente (CX) / Setor Bancário Digital
- **Objetivo:** Identificar temas recorrentes, sentimento dos clientes, pontos de atrito e gerar recomendações práticas para tomada de decisão.

---

## 🎯 Prompt Final Completo

```markdown
Atue como analista sênior de dados e experiência do cliente (CX) em uma instituição bancária.

Sua tarefa é analisar feedbacks de clientes sobre aplicativo bancário, Pix, cartão de crédito e atendimento por chat para identificar temas recorrentes, sentimento dos clientes e oportunidades de melhoria.

Contexto: A análise será utilizada pela equipe de Experiência do Cliente e pelos Product Managers dos canais digitais para priorizar correções no aplicativo, otimizar fluxos de autoatendimento e reduzir atritos no suporte. O objetivo principal é converter feedbacks desestruturados em planos de ação claros e acionáveis.

Dados disponíveis: A base de dados fornecida contém os seguintes campos:
- Data do comentário
- Canal de atendimento (ex: Chat, Reclame Aqui, App Store, Google Play)
- Produto citado (ex: Pix, Cartão de Crédito, Login, Transferências)
- Nota de satisfação (escala de 1 a 5)
- Texto original do feedback

Instruções de análise:
1. Classificação: Categorize cada comentário por Tema Principal, Sentimento (Positivo, Neutro ou Negativo), Nível de Urgência (Baixa, Média ou Alta) e Produto Citado.
2. Diagnóstico: Identifique os principais gargalos operacionais, falhas técnicas recorrentes, elogios e oportunidades de melhoria.
3. Evidências: Embase cada conclusão com trechos literais dos comentários fornecidos (sem alterar o sentido original).
4. Plano de Ação: Proponha recomendações práticas e priorizadas para a equipe de CX e os times de tecnologia/produto.

Formato da resposta:
- Resumo Executivo: Visão geral do cenário em até 5 linhas.
- Tabela de Análise Estruturada com as colunas:
  | Produto | Tema Principal | Sentimento | Nível de Urgência | Evidência (Trecho do Feedback) | Ação Recomendada |
- Top 3 Prioridades: Lista destacando as 3 ações mais críticas para implementação imediata.

Restrições e Diretrizes de Segurança:
- Use estritamente as informações presentes na base de dados fornecida.
- Não invente números, porcentagens, causas raízes ou conclusões não suportadas pelos dados.
- Não exponha nem replique dados pessoais identificáveis (PII) como CPF, números de cartão, nomes completos ou dados de contato.
- Se houver dados insuficientes para determinar causa ou sentimento, declare explicitamente a limitação.
- Mantenha tom profissional, executivo, analítico e orientado à ação.
```

---

## 📊 Demonstração de Aplicação do Prompt

### 📥 Exemplo de Base de Entrada (Inputs)
```json
[
  {
    "data": "2026-08-20",
    "canal": "Chat App",
    "produto": "Pix",
    "nota": 1,
    "feedback": "O Pix ficou fora do ar no sábado à noite quando eu precisava pagar o restaurante. Deu erro de conexão repetidas vezes."
  },
  {
    "data": "2026-08-21",
    "canal": "App Store",
    "produto": "Cartão de Crédito",
    "nota": 5,
    "feedback": "Adorei a nova função de ajuste de limite direto no app, super rápido e intuitivo!"
  },
  {
    "data": "2026-08-22",
    "canal": "Chat App",
    "produto": "Atendimento Chat",
    "nota": 2,
    "feedback": "O robô não entende minha dúvida sobre contestação de compra e demora muito para passar para um atendente humano."
  },
  {
    "data": "2026-08-22",
    "canal": "Google Play",
    "produto": "Login e Biometria",
    "nota": 1,
    "feedback": "Após a última atualização do aplicativo, o reconhecimento facial parou de funcionar no meu celular e agora fico bloqueado para acessar a conta."
  },
  {
    "data": "2026-08-23",
    "canal": "Reclame Aqui",
    "produto": "Fatura e Notificações",
    "nota": 2,
    "feedback": "Não recebi a notificação de vencimento da fatura por push nem por e-mail, e acabei pagando juros por um dia de atraso. O sistema de alertas precisa melhorar."
  },
  {
    "data": "2026-08-23",
    "canal": "Google Play",
    "produto": "Investimentos",
    "nota": 5,
    "feedback": "Muito simples investir em CDB direto pelo aplicativo, rendimento visível diariamente e resgate rápido. Parabéns à equipe!"
  },
  {
    "data": "2026-08-24",
    "canal": "Chat App",
    "produto": "Cartão Virtual",
    "nota": 3,
    "feedback": "O cartão virtual temporário para compras na internet é muito seguro, mas às vezes expira antes de eu conseguir concluir o checkout em sites lentos."
  },
  {
    "data": "2026-08-24",
    "canal": "Ouvidoria / E-mail",
    "produto": "Comprovantes",
    "nota": 3,
    "feedback": "Sinto falta de uma opção clara para exportar o extrato e comprovantes em formato PDF detalhado com autenticação bancária para declaração de imposto."
  }
]
```

### 📤 Exemplo de Resposta Gerada pela IA

#### Resumo Executivo
A análise dos 8 feedbacks identifica alta aprovação em investimentos e gestão de limite de crédito, enquanto aponta pontos críticos que impactam diretamente a satisfação: falhas no reconhecimento biométrico pós-atualização, indisponibilidade do Pix em fins de semana e atrito no transbordo do suporte via chat para temas de contestação.

#### Tabela de Análise Estruturada

| Produto | Tema Principal | Sentimento | Nível de Urgência | Evidência (Trecho do Feedback) | Ação Recomendada |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Login e Biometria** | Falha de acesso pós-update | Negativo | Alta | *"Após a última atualização (...) o reconhecimento facial parou de funcionar (...)"* | Lançar hotfix com rollback de biblioteca biométrica e habilitar login por senha/biometria digital como fallback imediato. |
| **Pix** | Instabilidade em horários de pico | Negativo | Alta | *"O Pix ficou fora do ar no sábado à noite (...) erro de conexão repetidas vezes."* | Reforçar escalabilidade da infraestrutura nos fins de semana e exibir alerta preventivo de status no app. |
| **Atendimento Chat** | Dificuldade no transbordo do bot | Negativo | Alta | *"O robô não entende minha dúvida (...) demora muito para passar para um atendente humano."* | Ajustar árvore de decisão do bot para transferir imediatamente casos de contestação de compra para atendimento humano. |
| **Fatura e Notificações** | Falha no disparo de lembretes | Negativo | Média | *"Não recebi a notificação de vencimento da fatura por push nem por e-mail (...)"* | Auditar serviço de mensageria (Push/E-mail) e enviar lembrete D-3 e D-1 antes do vencimento. |
| **Cartão Virtual** | Tempo de expiração curto | Neutro | Média | *"O cartão virtual (...) às vezes expira antes de eu conseguir concluir o checkout (...)"* | Aumentar tempo de vida do CVV temporário de 5 para 15 minutos ou permitir renovação com 1 clique. |
| **Comprovantes** | Exportação de documentos | Neutro | Baixa | *"Sinto falta de uma opção clara para exportar o extrato e comprovantes em formato PDF (...)"* | Adicionar botão de exportação nativa em PDF com QR Code de autenticação no histórico financeiro. |
| **Cartão de Crédito** | Usabilidade e autonomia | Positivo | Baixa | *"Adorei a nova função de ajuste de limite direto no app (...)"* | Manter padrão de UX adotado e usar o fluxo como modelo para outras funcionalidades de autoatendimento. |
| **Investimentos** | Facilidade de aplicação e clareza | Positivo | Baixa | *"Muito simples investir em CDB direto pelo aplicativo, rendimento visível diariamente (...)"* | Expandir portfólio de produtos de renda fixa mantendo a mesma interface simples e transparente. |

#### 🏆 Top 3 Prioridades
1. **Correção Crítica no Login (Biometria):** Liberar atualização emergencial para sanar a quebra do reconhecimento facial que impede o acesso de usuários à conta.
2. **Resiliência do Pix e Infraestrutura:** Implementar balanceamento de carga e monitoramento proativo para transações em horários de pico noturnos/finais de semana.
3. **Revisão da Rota de Contestação no Chat:** Configurar gatilho prioritário para que palavras-chave de segurança e contestação sejam roteadas sem atrito para operadores humanos.
