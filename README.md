# GUIA RAPÍDO DE INTEGRAÇÃO CONSULTA NFE

A consulta da NFE da MULT IT SOLUTIONS foi desenvolvida para disponibilizar 100% das notas fiscais, usadas para otimizar a emissão do CTE para as transportadoras mesmo que não sejam citadas na NFE. As buscas das NFE são realizadas em tempo real no momento da requisição dos transportador. Entre as fontes de acessos estão Secretaria da Fazenda e SERPRO (Serviço Federal de Processamento de Dados).
Para garantir a busca em todas as fontes garantindo contingência, disponibilidade e consequentemente melhor operação as transportadoras, se faz necessário o certificado digital do transportador.
A alta disponibilidade e serviço, do certificado digital e respectiva senha são de propriedade e uso exclusivo do transportador. Para evitar o trafego e aumentar a segurança a MULT IT SOLUTIONS aplicou as medidas:
•	Utiliza protocolo de requisição segura “https”, certificado pela Amazon AWS. 
•	Não armazena certificado de transportador;
•	O Certificado do transportador é usando uma única vez na geração da “chave secreta“. A “chave secreta” é uma criptografia composta pelo certificado e chaves de codificação da MULT IT SOLUTIONS. Essa criptografia é de uso exclusivo da MULT IT SOLUTIONS e sua conversão é usada apenas no momento da consulta.


Etapa 1 : Solicite chave de acesso
Entre em contato através do email contato@multit.com.br com assunto SOLICITAÇÃO CHAVE DE ACESSO e informar no corpo do email seu nome e CNPJ que receberá retorno da chave de acesso, essa chave é de uso exclusiva da empresa solicitante.

Etapa 2 : Gere a chave secreta
Acesse o webservice: https://lbdfe.multit.cloud/wsmultitconsultas/servicoweb.asmx
Wsdl: https://lbdfe.multit.cloud/wsmultitconsultas/servicoweb.asmx?wsdl
Selecione o web método: GeraChaveSecreta
Nota: Informações de integração no próprio link. Maiores informações suporte@multit.com.br.
Informe os parâmetros:
CHAVECLIENTE: Chave solicitada na etapa 1.
CERTIFICADOBASE64: Seu arquivo de certificado digital convertido em base 64, para suporte ou maiores detalhe entre em contato com o suporte@multit.com.br.
SENHACERTIFICADO: Senha do seu certificado.
O retorno será uma chave secreta que será utilizada em todos as consultas. A chave secreta reforça a segurança o trafego do certificado da conexão entre cliente - MULT IT SOLUTIONS. A MULT IT SOLUTIONS não armazena o certificado apenas faz o trafico seguro entre as fontes governamentais.

Etapa 3 : Realize a consulta
Acesse o webservice: https://lbdfe.multit.cloud/wsmultitconsultas/servicoweb.asmx
Wsdl: https://lbdfe.multit.cloud/wsmultitconsultas/servicoweb.asmx?wsdl
Selecione o web método: GetNfe
Informe os parâmetros:
CHAVECLIENTE: Chave solicitada na etapa 1.
CHAVESECRETA: Chave gerada na etapa 2.
CHAVENFE: Chave de 44 dígitos da NFE.
O retorno segue o layout da NFE o qual os TMS e ERP já fazem a leitura, possibilitando fácil integração. 
Nota: O método getnfejson, tem o mesmo proposito retornando a mesma estrutura de dados no formato Json.

Etapa 4: Acompanhe seus créditos
Acesse o webservice: https://lbdfe.multit.cloud/wsmultitconsultas/servicoweb.asmx
Wsdl: https://lbdfe.multit.cloud/wsmultitconsultas/servicoweb.asmx?wsdl
Selecione o web método: VerificaSaldo
Informe os parâmetros:
CHAVECLIENTE: Chave solicitada na etapa 1.
A web método retorna o credito disponível e utilizado da chave cliente informada. Informações de extrato, poderão ser realizadas pelo portão de cliente. Contate suporte@multit.com.br para maiores informações.

