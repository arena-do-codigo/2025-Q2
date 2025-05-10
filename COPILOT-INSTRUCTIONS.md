Você é um engenheiro líder responsável por criar um desafio técnico completo para um campeonato de desenvolvimento chamado “Arena do Código”.

O desafio é baseado no tema **Venda de Ingressos para Eventos**.

Gere uma especificação completa para participantes criarem tanto o **backend quanto o frontend**, com as seguintes exigências:

---

## 📌 Tema:
Arena do Código – Venda de Ingressos

---

## 🎯 Objetivo:
Construir uma aplicação capaz de gerenciar a venda de ingressos para eventos de forma segura, performática e escalável.

---

## 🔧 Backend

### Requisitos obrigatórios:
- Implementar uma API RESTful (ou GraphQL se preferir).
- Endpoints obrigatórios:
  - `POST /clientes` – cria um cliente
  - `POST /eventos` – cria um evento com quantidade limitada de ingressos
  - `POST /compras` – realiza a compra de 1 ingresso para um evento por um cliente
  - `GET /eventos/:id` – retorna status do evento (ingressos vendidos/disponíveis)
  - `GET /clientes/:id` – retorna compras do cliente
  - `GET /compras` – retorna todas as compras com cliente + evento (para exibição pública)

### Regras:
- Cada cliente só pode comprar **1 ingresso por evento**
- Não pode haver overbooking (mais vendas do que ingressos disponíveis)
- A operação de compra deve ser **atômica e segura sob concorrência**
- O sistema será testado sob carga com `wrk` ou `k6`
- Deve usar persistência (PostgreSQL, MongoDB, etc.)

---

## 🖥️ Frontend

### Requisitos obrigatórios:
- SPA usando React (ou similar)
- Páginas obrigatórias:
  - **Página de evento**:
    - Mostrar número de ingressos disponíveis e vendidos (atualização em tempo real)
    - Botão “Comprar ingresso”
  - **Lista de compradores (tempo real)**:
    - Exibe os últimos compradores em uma tabela
  - **Página de cliente**:
    - Mostra todas as compras daquele cliente (histórico)

### Regras do Frontend:
- Deve consumir a API do backend criado
- Deve se atualizar automaticamente quando:
  - Um novo ingresso for vendido
  - Um evento mudar de status (esgotado)
- Interface deve ser responsiva
- O frontend deve ser capaz de lidar com erros de forma amigável (ex: evento esgotado, falha na compra)
---

## ⚔️ Critérios de avaliação:
- Consistência e segurança dos dados sob carga
- Desempenho médio das APIs
- Latência p95/p99
- Estabilidade sob requisições concorrentes
- UX do frontend (responsividade, fluidez, uso em tempo real)
- Clareza e organização do código

---

## ⚙️ Ambiente de execução:
- Todos os projetos devem rodar em containers Docker
- Limite de 1 vCPU e 512MB de RAM
- Base de dados deve ser reinicializável com script (para testes automatizados)
- O frontend deve rodar em container separado e se conectar com o backend pelo hostname padrão (ex: `http://backend:3000`)

---

## 🏆 Regras da competição:
- Duração: 48 horas
