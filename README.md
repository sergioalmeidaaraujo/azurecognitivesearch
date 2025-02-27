# azurecognitivesearch

Passo 1: Criar um Serviço no Portal do Azure
  Acesse o Portal do Azure.
  Pesquise por Azure Cognitive Search e clique em Criar.
  Preencha os detalhes:
  Nome do serviço: ex. meu-search-service
  Grupo de Recursos: escolha um existente ou crie um novo
  Localização: escolha a região mais próxima
  Camada de preço: Basic, Standard, ou Premium (depende da demanda)
  Clique em Revisar + Criar e aguarde a implantação.

Passo 2: Criar e Configurar um Índice
  No serviço criado, vá até Índices e clique em Adicionar Índice.
  
  Defina os seguintes campos:
  
  Nome do índice: meu_indice_dados
  Esquema do índice (definir campos para busca, filtros e ordenação):
  json
  Copy
  Edit
  {
      "name": "documentos",
      "fields": [
          { "name": "id", "type": "Edm.String", "key": true },
          { "name": "titulo", "type": "Edm.String", "searchable": true },
          { "name": "conteudo", "type": "Edm.String", "searchable": true, "analyzer": "standard.lucene" },
          { "name": "data_publicacao", "type": "Edm.DateTimeOffset", "filterable": true, "sortable": true },
          { "name": "categoria", "type": "Edm.String", "filterable": true, "facetable": true }
      ]
  }
  Salve e publique o índice.

