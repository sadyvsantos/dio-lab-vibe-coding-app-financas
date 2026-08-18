# 💸 App de Finanças Pessoais do Sady com Vibe Coding

PRD refinado no Gemini.

# Product Requirements Document (PRD) — MVP Finanças Conversacionais

## 1. Visão Geral do Produto
Um aplicativo web/mobile responsivo de finanças pessoais focado em eliminar a fricção do registro manual. O usuário gerencia seus gastos, receitas e metas conversando com um assistente virtual em linguagem natural amigável e educativa.

---

## 2. Problema & Oportunidade
* **Problema:** A maioria dos aplicativos de finanças exige preenchimento tedioso de formulários, categorização manual e telas cheias de números complexos, levando à desistência rápida do usuário.
* **Solução:** Uma interface conversacional inteligente que interpreta comandos de texto simples (ex: "Gastei R$ 35 na padaria hoje no débito"), processa a transação automaticamente, sugere metas e fornece dicas personalizadas de economia.

---

## 3. Público-Alvo
* Jovens e adultos iniciantes no controle financeiro.
* Pessoas que buscam praticidade e não gostam de preencher planilhas.

---

## 4. Personas e Casos de Uso Principais
* **Caso 1 (Entrada de Despesa/Receita):** O usuário digita ou grava "Paguei R$ 120 de conta de luz" -> O sistema registra, define categoria "Moradia/Contas" e responde com confirmação amigável.
* **Caso 2 (Criação de Meta Simples):** O usuário digita "Quero juntar 500 reais até o fim do mês que vem" -> O assistente cria a meta e sugere guardar R$ X por semana.
* **Caso 3 (Consulta Rápida):** "Quanto gastei com delivery este mês?" -> O assistente responde diretamente com o total e um gráfico mini.

---

## 5. Estrutura de Telas & Navegação (UX/UI)

### Tela 1: Conversa com o Agente (Tela Principal / Home)
* **Interface de Chat:** Campo de entrada de texto inferior com botão de envio e atalhos rápidos ("+ Gasto", "+ Receita", "Criar Meta", "Ver Resumo").
* **Card de Saldo Rápido (Topo):** Exibição sutil do saldo disponível no mês e progresso geral.
* **Mensagens do Bot:** Cartões ricos dentro da conversa que mostram confirmação de lançamento com opção de edição com 1 clique (caso o bot erre a categoria).

### Tela 2: Dashboard & Relatórios
* **Filtros Temporais:** Abas claras para visualização (Mensal, Trimestral, Semestral, Anual).
* **Gráficos Visuais:** 
  * Gráfico de rosca/pizza para distribuição por categorias (Alimentação, Transporte, Moradia, Lazer, etc.).
  * Linha do tempo de entradas vs. saídas.
* **Card de Economia / Dica do Dia:** Sugestão educativa do agente baseada no padrão de gastos.

### Tela 3: Metas Financeiras (Poupômetro)
* **Lista de Metas:** Cards visuais com barra de progresso (ex: "Reserva de Emergência: R$ 300 / R$ 1.000").
* **Botão "Adicionar Meta":** Abre formulário rápido ou direciona para criar via chat.

### Tela 4: Extrato / Transações
* Lista organizada de transações com data, descrição, valor e tag de categoria.
* Busca e filtros por tipo (despesa/receita) e categoria.

---

## 6. Regras de Negócio e Lógica da IA

1. **Classificação Automática:** O sistema deve inferir categoria automaticamente (ex: "almoço" -> Alimentação; "uber" -> Transporte).
2. **Fallback / Validação:** Se a mensagem for ambígua, o assistente deve pedir confirmação educadamente antes de salvar.
3. **Tom de Voz:** Linguagem empática, motivadora, simples e sem jargões contábeis complexos.
4. **Moeda e Formato:** Padrão brasileiro (R$, vírgula para decimais, DD/MM/AAAA).

---

## 7. Modelo de Dados Simplificado (MVP)

* **User:** id, nome, email, saldo_inicial.
* **Transaction:** id, user_id, tipo (despesa | receita), valor, categoria, descricao, data, criado_via (chat | manual).
* **Goal (Meta):** id, user_id, titulo, valor_alvo, valor_atual, data_limite.
* **ChatMessage:** id, user_id, remetente (user | bot), texto, metadata (payload da transação gerada).

---

## 8. Plano de Validação do MVP
1. **Teste de Compreensão:** Validar se o assistente interpreta corretamente 90%+ das variações comuns de frases de gastos informais.
2. **Engajamento:** Medir se os usuários preferem registrar via chat do que por botões normais.
3. **Retenção:** Verificar se as mensagens educativas de metas incentivam o usuário a voltar no 3º e 7º dia.



Link do site: https://santos-coins.lovable.app/

Imagens referentes ao site.
1 <img width="1146" height="706" alt="Captura de tela de 2026-08-18 17-40-04" src="https://github.com/user-attachments/assets/dc170055-76aa-4c61-97ad-474860030d01" />

2 <img width="1146" height="706" alt="Captura de tela de 2026-08-18 17-37-42" src="https://github.com/user-attachments/assets/ae19dcc5-229f-452e-8d84-3d58be493086" />

3 <img width="1146" height="706" alt="Captura de tela de 2026-08-18 17-40-11" src="https://github.com/user-attachments/assets/cc53424d-4d12-4353-81b9-b5941aab173c" />

4 <img width="1146" height="706" alt="Captura de tela de 2026-08-18 17-40-18" src="https://github.com/user-attachments/assets/4409c5ad-8c01-4cee-956e-db83ad3be8bd" />

Resumo do PRD

1. Conversa Inteligente (Core do App)
Registro em linguagem natural: Processamento de despesas e receitas por texto (ex: registrar cartão ou compras).
Classificação e confirmação: Reconhecimento automático da categoria (com tag visual editável via ícone de lápis) e pedido de confirmação antes de salvar.
Criação de metas guiada: O assistente identifica a intenção de poupar, pergunta os objetivos e cadastra as metas diretamente pelo chat.
Atalhos rápidos: Botões de sugestão com exemplos de comandos acima do campo de digitação para acelerar o uso.

2. Painel (Dashboard & Relatórios)
Métricas principais: Cards de resumo rápido com Entradas, Saídas e Resultado.
Filtros por período: Visualização flexível por abas (Mensal, Trimestral, Semestral e Anual).
Gráficos visuais: Áreas dedicadas para detalhamento por categoria (Onde seu dinheiro foi) e fluxo de caixa (Entradas x saídas).
Agente educativo: Card de Dica do dia para fornecer insights personalizados conforme o histórico do usuário.

3. Metas (Poupômetro)
Acompanhamento de progresso: Cards individuais por meta com barra percentual e valores (atual vs. alvo).
Aporte rápido: Campo embutido em cada card para registrar novos valores guardados com um clique.
Criação manual: Botão dedicado + Adicionar meta para cadastro direto sem depender exclusivamente do chat.

4. Extrato (Transações)
Filtros e busca: Barra de pesquisa por descrição e seletores para filtrar por tipo de lançamento ou categorias.
Listagem organizada: Histórico centralizado de movimentações financeiras geradas pelas conversas.

## Reflexão do app.

## O que funcionou bem?
O refinamento do PRD feito no Gemini ajudou muito.

## O que não funcionou como o esperado?
Esperava poder interagir mais com o Lovable.

## O que aprendeu sobre conversar com IAs?
Aprendi que é igual a conversar com uma pessoa, dando detalhes para executar os procedimentos.



## 💬 Conclusão

Vibe Coding é sobre clareza, curiosidade e criatividade, não sobre perfeição técnica. O verdadeiro objetivo aqui é aprender a pensar junto com a IA, transformando ideias em conceitos reais e enxergando a tecnologia como uma extensão do seu raciocínio criativo. Cada interação é um experimento, quanto mais clara for sua intenção, mais surpreendente será o resultado.
