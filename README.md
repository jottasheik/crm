# ⚖️ JuriFlow CRM - Renegociação de Dívidas & Gestão por Bancos

Aplicação Web completa de CRM para Escritórios de Advocacia especializada em **Defesa e Renegociação de Dívidas Bancárias**, integrada à **API Oficial do Busca Processos** (`api.buscaprocessos.app.br/v1/processos`), com **Demonstrativo Financeiro de Deságio**, **Aba de Bancos Credores com Transferência de Clientes**, e **Cadastro Rápido de Empresas/CNPJs**.

---

## 🚀 Como Executar Imediatamente

Basta abrir o arquivo diretamente em seu navegador (Google Chrome, Microsoft Edge, etc.):
- **[index.html](file:///C:/Users/jvmsa/.gemini/antigravity/scratch/juriflow-crm/index.html)**

---

## 📊 1. Demonstrativo Financeiro de Dívidas (Dashboard)

O novo Dashboard foi reformulado para exibir com clareza os 4 indicadores essenciais da operação de renegociação bancária:
1. **Valores Cadastrados**: Volume total original de dívidas e causas sob gestão do escritório.
2. **Valores Fechados**: Total original das dívidas que foram finalizadas em acordo.
3. **Desconto Total Conquistado**: Economia real gerada para os clientes (Dívida Original - Valor Pago).
4. **% Médio Pago pelo Cliente na Resolução**: Percentual médio que o cliente desembolsou para quitar a pendência bancária (ex: 28% pago, com 72% de deságio).

---

## 🏦 2. Aba Separada por Bancos Credores

- Aba dedicada **"2. Análise por Bancos"**:
  - Cards com volume cadastrado, volume fechado, desconto obtido e percentual pago para cada banco (Santander, Itaú, Bradesco, Banco do Brasil, Caixa, BTG, Safra, etc.).
  - **Alteração de Banco com 1 Clique**: Tabela com dropdown inline que permite transferir o cliente/processo de um banco para outro instantaneamente.
  - **Cadastro de Novos Bancos**: Botão para incluir novas instituições financeiras ou fundos (FIDCs).

---

## 🏢 3. Cadastro Dinâmico de Empresas e CNPJs

- Os botões estáticos de exemplo e o botão "teste" foram completamente removidos.
- No lugar, foi implementado o **Gerenciador de Empresas / CNPJs Salvos**:
  - Permite cadastrar qualquer Nome e CPF/CNPJ.
  - Ao clicar na empresa cadastrada, seu documento é automaticamente preenchido no campo de busca para consulta em 1 clique.
  - Itens salvos persistentemente no `localStorage`, com opção de remoção individual.

---

## 🔒 4. Webhook & Autenticação Integrados

Configurados e salvos no modal de configurações:
- **Token de Autorização Bearer**: `4ce52d5d7363b311a3875461ef948d2e47ea39ccc519a077d8cef00d94949b5c`
- **Chave Secreta HMAC SHA-256 (`X-BuscaProcessos-Signature`)**: `6b77fb635cd5477716975355f8ed5a0d825d214cf0999e7b404a83719721989e`
