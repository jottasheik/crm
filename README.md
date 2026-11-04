# ⚖️ JuriFlow CRM - Integração Oficial Busca Processos API

Aplicação Web completa de CRM para Escritórios de Advocacia integrada à **API Oficial do Busca Processos** (`https://docs.buscaprocessos.app.br/docs/getting-started`), incluindo **esteira de documentos do cliente**, **gatekeeper de contrato assinado (PDF obrigatório)**, **filtro de Execução de Título Extrajudicial**, **filtro por comarca** e **trava temporal de 5 dias**.

---

## 🚀 Como Executar

Abra diretamente no navegador (Google Chrome, Microsoft Edge, etc.):
- **[index.html](file:///C:/Users/jvmsa/.gemini/antigravity/scratch/juriflow-crm/index.html)**
- Pronto para uso imediato com React 18, Tailwind CSS e ícones sem necessidade de `npm install`.

---

## ⚡ Detalhes da Integração Oficial Busca Processos API

Conforme a documentação oficial (`docs.buscaprocessos.app.br/docs/getting-started`):
1. **Endpoint Oficial**: `https://api.buscaprocessos.app.br/v1/processos`
2. **Autenticação**: Header `x-api-key: bp_live_48f7ed32f7eb71955b548b8fa3628bbbaa801339`
3. **Parâmetros**:
   - `cpf_cnpj`: Apenas os dígitos do CPF (11 dígitos) ou CNPJ (14 dígitos).
   - `limit`: `50` ou `100`.
4. **Parser Oficial**:
   - A resposta oficial retorna a árvore `{ data: { processos: [...] } }`.
   - O leitor extrai diretamente os dados de tribunal (`numero_cnj`, `titulo_polo_ativo`, `titulo_polo_passivo`, `capa.classe`, `capa.comarca`, `capa.valor_causa`).
   - Não são mais injetados dados fictícios sem solicitação explícita.

---

## 🎯 Novas Funcionalidades Atendidas

### 1. Filtro da Classe "Execução de Título Extrajudicial"
- Adicionado com destaque na lista de classes judiciais selecionáveis e badges de filtro.

### 2. Filtro por Comarca
- Novo campo de busca/filtro por comarca (ex: "São Paulo", "Campinas", "Foro Central").
- Exibição da comarca de cada processo na tabela de resultados e nos cards do Kanban.

### 3. Trava de Contrato Fechado (PDF Obrigatório)
- Ao arrastar ou selecionar para mover o card para a 4ª etapa (**Contrato Fechado**):
  - O sistema **bloqueia o avanço imediato** e abre o modal obrigatório: *"Upload Obrigatório do Contrato Assinado (PDF)"*.
  - O usuário deve anexar o arquivo PDF do contrato assinado pelo cliente.
  - Somente após o anexo confirmado o lead avança para Contrato Fechado e sua contagem de 5 dias é **permanentemente congelada**.

### 4. Gestão e Anexo de Documentos do Cliente (Onboarding)
- Uma vez no estágio de Contrato Fechado (ou acessando a aba "Documentos" do card), o advogado tem a esteira completa para anexar:
  1. **Contrato de Honorários Assinado** (PDF já vinculado no fechamento)
  2. **Procuração Ad Judicia**
  3. **Declaração de Hipossuficiência**
  4. **Documento de Identidade (RG / CNH)**
  5. **Comprovante de Residência**
  6. **Certidão de Casamento (caso houver)**
  7. **Extrato Bancário dos 3 Últimos Meses**
- Cada documento conta com status de pendência/anexado, nome do arquivo, data, substituição e remoção.
