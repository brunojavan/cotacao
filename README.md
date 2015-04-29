Script Cotação em Tempo Real (Yahoo! Finances)

Autor: Bruno Javan
E-mail: brunojavan@gmail.com
URL: www.brunojavan.com.br
Versão: 0.290415 (Beta)
Última Atualização: 29/04/2015
Linguagem: JSON/jQuery


INSTRUÇÕES DE USO:

Os dados são puxados do Yahoo! Finances através desse link:
http://query.yahooapis.com/v1/public/yql?q=select%20*%20from%20yahoo.finance.xchange%20where%20pair%3D%22USDBRL%2CEURBRL%2CARSBRL%2CMXNBRL%2CGBPBRL%2CJPYBRL%2CCLPBRL%2CPENBRL%2CUYUBRL%2CCHFBRL%2CCNHBRL%22&format=json&diagnostics=false&env=store%3A%2F%2Fdatatables.org%2Falltableswithkeys


Atualmente, estão inclusos 11 tipos de moedas mas caso queira remover ou adicionar alguma outra moeda é bem simples:


- Entre no site do Yahoo! Finances e procure pela moeda que vocÊ deseja


- Copie a sigla dela (Ex.: Dólar para Real -> USDBRL)


- Nesse caso estamos pegando a cotação do Dólar para Real Brasileiro, ou seja, USD->Dólar e BRL->Real


- Feito isso, é só copiar esse código USDBRL dentro do link acima junto com as outras moedas, por exemplo:
  
  USDBRL%2CEURBRL%2CARSBRL%2CMXNBRL%2CGBPBRL%2CJPYBRL
  
  Note que temos ai 6 moedas sendo definidas (USDBRL, EURBRL, ARSBRL, MXNBRL, GBPBRL, JPYBRL), e o espaço entre elas é definido por "%2C", isso é MUITO IMPORTANTE!


- Outro ponto importante é a ordem das moedas, pois quando for chamá-las no jQuery vc vai utilizar a numeração delas, começando por 0 (zero), exemplo:

  var EUR = ''+(data.query.results.rate[1].Name)+'';
  Aqui estamos chamando o campo do nome da moeda, no caso o Euro. E ele está na segunda posição (Número 1).

- Por último, é só definir em qual elemento a informação será mostrada:

  $('#USD') .html(USD);  Nesse caso as informações com o nome "USD" serão exibidas no elemento com ID "USD";

  E no HTML é só definir essa ID em algum elemento: <div id="USD"></div>



É basicamente isso, qualquer dúvida é só entrar em contato, obrigado.
