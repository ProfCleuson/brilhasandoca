# ⭐ Brilha Sandoca | Show de Talentos

Sistema web (single-page, HTML/CSS/JS puro) para gerenciar a avaliação de participantes de um show de talentos escolar/municipal — cadastro de participantes via planilha Google, avaliação por critérios (rubrica), rankings por modalidade e etapa, e geração de relatórios.

Não requer backend próprio: os dados dos participantes vêm de uma **Google Sheets** (pública ou via **Google Apps Script**, para planilhas privadas), e as avaliações lançadas ficam salvas no **localStorage** do navegador, com exportação em CSV.

## ✨ Funcionalidades

- **Dashboard** — participantes, avaliados, classificados e pendentes, com resumo por modalidade (Canto, Dança, Instrumento, Teatro etc.) e ranking geral/por etapa e modalidade.
- **Avaliação** — formulário de rubrica por critérios com conceitos (ex.: Excelente/Bom/Regular/Insuficiente), itens obrigatórios (Sim/Não/Não informado), cálculo automático da nota e nota flutuante visível ao rolar a tela.
- **Relatórios** — geração e impressão de relatório individual por participante, com exportação em CSV.
- **Etapas** — controle de 1ª, 2ª e 3ª etapa, com corte de classificação entre fases.
- **Administração** (perfil Coordenador/Admin):
  - **Configurações** — conexão com a planilha (URL/ID) e, opcionalmente, com um Apps Script.
  - **Avaliadores** — cadastro dos avaliadores.
  - **Temas da 2ª Etapa** — definição de temas por modalidade.
  - **Gerenciar Avaliações** — edição/exclusão de avaliações já lançadas.
- **Dois perfis de acesso**: Avaliador e Coordenador/Admin, com alternância pelo botão "Trocar".
- **Menu lateral retrátil** — oculto por padrão em qualquer tamanho de tela (celular, tablet ou PC), abre por cima do conteúdo ao clicar no botão ☰.
- Interface 100% responsiva, sem dependências externas de framework (JS puro).

## 🗂️ Estrutura

Projeto de arquivo único:

```
index.html   → HTML + CSS + JavaScript (tudo em um só arquivo)
```

## 🚀 Como usar

1. Baixe o `index.html` (ou clone o repositório).
2. Abra o arquivo diretamente no navegador — não é necessário servidor.
3. Acesse **Configurações** (perfil Coordenador) e informe:
   - a **URL** ou **ID** da planilha Google com os dados dos participantes; ou
   - a **URL de um Google Apps Script** publicado como Web App (necessário para planilhas privadas ou para permitir gravação de dados na planilha).
4. Clique em **Carregar/Atualizar** para importar os participantes.
5. Alterne para o perfil **Avaliador** para lançar notas.

> 💡 Se a planilha for pública, basta o link normal do Google Sheets. Se for privada, use um Apps Script publicado como Web App para servir os dados via JSON.

## 🧾 Formato esperado da planilha

Colunas reconhecidas pelo sistema (nomes flexíveis/alternativos):

- `Código Brilha` (recomendado, evita colisão entre alunos com nome/turma/modalidade iguais)
- Nome, Turma, Turno, Modalidade
- Notas por etapa (`Etapa 1 - Nota`, `Etapa 2 - Nota`, `Etapa 3 - Nota final`, etc.)
- Decisão da banca por etapa

## 💾 Armazenamento

- **Participantes**: obtidos ao vivo da planilha Google configurada.
- **Avaliações, avaliadores, temas e configurações**: salvos no `localStorage` do navegador que fez o lançamento.
- **Exportação**: os dados de avaliação podem ser exportados em `.csv` a qualquer momento (botão de exportar / relatório individual).

> ⚠️ Como as avaliações ficam no `localStorage`, elas são locais a cada navegador/dispositivo, a menos que a integração com Apps Script também grave os lançamentos na planilha (dependendo de como o Apps Script foi configurado).

## 🛠️ Tecnologias

- HTML5, CSS3 (sem framework)
- JavaScript vanilla (ES6+)
- Google Sheets API pública / Google Apps Script (integração de dados)
- `localStorage` (persistência local de avaliações)

## 📄 Licença

Defina aqui a licença do projeto (ex.: MIT) ou remova esta seção se for de uso interno/restrito da escola/secretaria.
