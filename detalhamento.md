Detalhamento dos reauisitos para a implementação do sistema de apuração:

1- Características do arquivo de entrada:
  - Arquivo texto com todos os registros do e-com (de todos os tipos, criados
    em qualquer data, por qualquer pessoa)
  - Formato: CSV
  - Delimitador de coluna: ; (ponto e vírgula)
  - Delimitador de campo: "" (aspas duplas)
  - Codificação: UTF-8
  - Finalização de linha: Windows

2- Campos:
  - ID: Identificador único da solicitação, composto por um prefixo + um
    número inteiro sequencial. Ex: BUG-2536, CHG-6598, AQ-1452
  - Tipo: Nome do template utilizado para gerar o registro. 
    Templates participantes: 
      Falha/erro (BUG)
      Mudança (CHG)
      Nova funcionalidade (NEW)
  - Estado: Situação em que o registro se encontra. O valor depende de cada
    template, mas para o sistema em questão apenas os seguintes são relevantes:
      ENV: Solicitação foi enviada mas não processada
      ACE, ADI: Solicitação processada e aguardando pela implementação
      CAN, REJ: Solicitação processada e rejeitada ou cancelada (inválida)
      ABE, RES, VER: Solicitação em desenvolvimento
      OFF: Solicitação fechada
  - Data da solicitação: Data em que a solicitação foi criada (DD/MM/YYYY)
  - Software/componente: Nome do software ou componente para o qual a 
    solicitação foi criada. Apenas as solicitações para os seguintes softwares são válidas:
      Facture-e
      Monnae
      School (desktop)
      School (web)
      Sicopri
      Geagro
  - Assunto: Descrição simples do registro
  - Autor: Nome do autor do registro (é por ele que serão apuradas as 
    solicitações e exclídos os não participantes)
  - Idade: Idade (em dias) da solicitação
  - Data do fechamento: Data em que o registro foi fechado (apenas para
    registros no estado OFF)
