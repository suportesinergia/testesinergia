# 📦 ElasticSearch Endpoint

Este repositório armazena a definição e estrutura de um endpoint do Elasticsearch utilizado para indexação e busca de chamados no ServiceDesk.

## ⚙️ 

- O ambiente é recriado via Jenkins pela tarefa `elasticsearch-deploy-[ambiente]`, utilizando a tag específica do commit no Git.
- O arquivo `mapping.json` define a estrutura do índice (mapeamento, filtros e analisadores). Para aplicar mudanças, o índice precisa ser excluído previamente — caso contrário, o deploy não atualiza o mapping.
- A indexação de chamados é controlada pela tabela `para_indexar_es`.
- A indexação pode ser ativada ou desativada pelo parâmetro `ELASTICSEARCH_INDEXACAO_HABILITADA`.
- Informações relativas ao endpoint, credenciais e número de resultados na busca também são controladas via parâmetros.
- A versão do ElasticSearch utilizada é gerenciada pelo `Dockerfile` presente no repositório.
- Os dados do ElasticSearch são armazenados em volume separado. Alterações simples preservam o índice, evitando a necessidade de reindexação.

## 👁️ 

- Verificar espaço de armazenamento disponível para o índice;
