# Relatório de UI Testing - Sauce Demo

## 1. Introdução
O presente documento apresenta o escopo, plano, execução e resultados dos testes de UI realizados na plataforma de e-commerce Sauce Demo, além de uma análise de riscos dos bugs e problemas encontrados. O objetivo é testar e validar os principais fluxos da  plataforma de e-commerce Sauce Demo (https://www.saucedemo.com) e identificar bugs e/ou possíveis melhorias de UX/UI antes do lançamento em produção.


## 2. Plano de Testes

### 2.1 Objetivo
Testar os principais fluxos da aplicação para garantir que os mesmos funcionem corretamente, identificando bugs e possíveis problemas de UX/UI.

### 2.2 Escopo
A cobertura de teste inclui:
- Login
- Ordenação e filtragem de produtos
- Fluxo de compra
- Fluxo de checkout
- Remoção de itens do carrinho
- Navegação entre páginas e menus
- Logout

### 2.3 Cenários de Teste
- ID: Cenário de Teste
  -Contexto
  -Passos
  -Resultado Esperado

- CT01: Login com usuário "standard_user"
  -Verificar credenciais do usuário;
  -Acessar a página de login > Inserir username "standard_user" e senha padrão "secret_sauce > Clicar em "Login";
  -Acesso bem-sucedido à plataforma.

- CT02: Login com usuário "locked_out_user" 
  -Verificar credenciais do usuário;
  -Acessar a página de login > Inserir username "locked_out_user" e senha padrão "secret_sauce > Clicar em "Login";
  -Acesso bem-sucedido à plataforma.

- CT03: Login com usuário "problem_user" 
  -Verificar credenciais do usuário;
  -Acessar a página de login > Inserir username "problem_user" e senha padrão "secret_sauce > Clicar em "Login";
  -Acesso bem-sucedido à plataforma.

- CT04: Login com usuário "performance_glitch_user" 
  -Verificar credenciais do usuário;
  -Acessar a página de login > Inserir username "performance_glitch_user" e senha padrão "secret_sauce > Clicar em "Login";
  -Acesso bem-sucedido à plataforma.

- CT05: Login com usuário "error_user" 
  -Verificar credenciais do usuário;
  -Acessar a página de login > Inserir username "error_user" e senha padrão "secret_sauce > Clicar em "Login";
  -Acesso bem-sucedido à plataforma.

- CT06: Login com usuário "visual_user" 
  -Verificar credenciais do usuário;
  -Acessar a página de login > Inserir username "visual_user" e senha padrão "secret_sauce > Clicar em "Login";
  -Acesso bem-sucedido à plataforma.
  
- CT07: Login com credenciais incorretas 
  -Verificar login com username e/ou senha incorretos;
  -Acessar a página de login > Inserir username diferente de "standard_user", "locked_out_user", "problem_user", "error_user" e "visual_user" e/ou senha diferente da padrão "secret_sauce";
  -Mensagem de erro informando que as credenciais são inválidas; Impossibilidade do acesso à plataforma.

- CT08: Ordenação de produtos por nome (de A a Z)
  -Validar filtro de ordenação "Name (A to Z)";
  -Acessar a página "Products" > Clicar no filtro no canto direito superior da tela > Selecionar ordenação por Nome (de A a Z);
  -Produtos ordenados de acordo com a ordem alfabética.

- CT09: Ordenação de produtos por nome (de Z a A)
  -Validar filtro de ordenação "Name (Z to A)";
  -Acessar a página "Products" > Clicar no filtro no canto direito superior da tela > Selecionar ordenação por Nome (de Z a A);
  -Produtos ordenados de acordo com a ordem de Z a A.

- CT10: Ordenação de produtos por Preço (de baixo a alto)
  -Validar filtro de ordenação "Price (low to high)";
  -Acessar a página "Products" > Clicar no filtro no canto direito superior da tela > Selecionar ordenação por Preço (de baixo a alto);
  -Produtos ordenados de acordo com o preço.

- CT11: Ordenação de produtos por Preço (de alto a baixo)
  -Validar filtro de ordenação "Price (high to low)";
  -Acessar a página "Products" > Clicar no filtro no canto direito superior da tela > Selecionar ordenação por Preço (de alto a baixo);
  -Produtos ordenados de acordo com o preço.

- CT12: Fluxo de compra
  -Testar o fluxo de compras desde a página de produtos até o início do checkout;
  -Acessar a página "Products" > Adicionar os produtos no carrinho > Clicar no carrinho no canto direito superior;
  -Visualizar os produtos adicionados ao carrinho.

 - CT12.1: Fluxo de compra a partir da página do produto
  -Testar o fluxo de compras pelo acesso da tela que exibe apenas o produto desejado;
  -Acessar a página "Products" > Clicar no produto desejado > Adicionar o produto no carrinho > Clicar no carrinho no canto direito superior;
  -Visualizar os produtos adicionados ao carrinho.

- CT13: Fluxo de checkout com 1 ou mais itens no carrinho
  -Testar o fluxo de checkout das compras adicionadas ao carrinho;
  -Clicar no carrinho no canto direito superior com 1 ou mais produtos adicionados > Clicar em "Checkout" >  Inserir dados solicitados > Clicar em "Continue" > Cicar em "Finish";
  -Resultado esperado: Mensagem de sucesso e finalização da compra.

- CT13.1: Fluxo de checkout com 0 itens no carrinho
  -Testar o fluxo de checkout das compras adicionadas ao carrinho;
  -Clicar no carrinho no canto direito superior com 0 produtos adicionados > Clicar em "Checkout";
  -Resultado esperado: Mensagem exibindo erro, indicando que não é possível finalizar uma compra vazia.

- CT14: Fluxo de checkout com dados vazios
  -Testar o fluxo de checkout com dados do usuário vazio ou com caracteres especiais;
  -Clicar no carrinho no canto direito superior com 0 produtos adicionados > Clicar em "Checkout" >  Não inserir dados de "First Name", "Last Name" e/ou Zip/PostalCode ou inserir caracteres especiais em qualquer um desses campos > Clicar em "Continue";
  -Resultado esperado: Mensagem exibindo erro, indicando que é necessário exibir as informações do(s) campo(s) que está(ão) em branco e/ou remover os caracteres especiais.

- CT15: Remoção de itens do carrinho
  -Validar o botão que remove produtos já adicionados ao carrinho;
  -Clicar no carrinho com ao menos 1 produto adicionado > Clicar no botão "Remove" do produto desejado;
  -Resultado esperado: Mensagem exibindo que o produto foi removido; Produto não mais presente no carrinho.

- CT16: Navegação entre páginas do menu lateral - Menu Principal
  -Validar o botão que retorna ao menu principal;
  -Clicar no botão com 3 barras horizontais no canto esquerdo superior da tela > Clicar em "All Items";
  -Resultado esperado: Ser redirecionado para a página principal da aplicação, a de exibição dos produtos.

- CT16.1: Navegação entre páginas do menu lateral - "About"
  -Validar o botão "About";
  -Clicar no botão com 3 barras horizontais no canto esquerdo superior da tela > Clicar em "About";
  -Resultado esperado: Ser redirecionado para a página https://saucelabs.com/.

- CT16.2: Navegação entre páginas do menu lateral - "Logout"
  -Validar o botão de logout;
  -Clicar no botão com 3 barras horizontais no canto esquerdo superior da tela > Clicar em "Logout";
  -Resultado esperado: Ser redirecionado para a página de login da plataforma.

- CT16.3: Navegação entre páginas do menu lateral - "Reset App State"
  -Validar o botão de reset;
  -Clicar no botão com 3 barras horizontais no canto esquerdo superior da tela > Clicar em "Reset App State";
  -Resultado esperado: Remover todos os itens do carrinho e resetar os filtros da página de produtos.


## 3. Resultados dos Testes

- CT01: Login com usuário "standard_user"
  -Resultado: Sucesso ✅
 
- CT02: Login com usuário "locked_out_user"
  -Resultado: Falha ❌
  -Observação: Mensagem de erro "Epic sadface: Sorry, this user has been locked out." exibida.

- CT03: Login com usuário "problem_user"
  -Resultado: Sucesso ✅

- CT04: Login com usuário "performance_glitch_user" 
  -Resultado: Sucesso ✅
  -Observação: Após clicar em "login", a página de login apresentou demora no redirecionamento e não permitiu cliques.
  -Anexo: Segue comparação do Lighthouse dos usuários performance_glitch_user e standard_user, exibindo a performance de ambas as páginas ![screenshotct04](imagens/image-2.png "CT04")

- CT05: Login com usuário "error_user" 
  -Resultado: Sucesso ✅

- CT06: Login com usuário "visual_user" 
  -Resultado: Sucesso ✅

- CT07: Login com credenciais incorretas 
  -Resultado: Sucesso ✅
  -Observação: Mensagem de erro "Epic sadface: Username and password do not match any user in this service".

- CT08: Ordenação de produtos por nome (de A a Z)
  -Resultado: Sucesso ✅
  -Observações:
    a.No usuário problem_user, as imagens exibidas dos produtos estão incorretas: 
    -Anexo: ![screenshotct08](imagens/image.png "CT08")
    b. No usuário visual_user, a imagem do produto "Sauce Labs Backpack" está incorreta na página de ordenação dos produtos e os preços se alteram a cada filtro selecionado ou a cada vez que a página é acessada novamente.
     
- CT09: Ordenação de produtos por nome (de Z a A)
  -Resultado: Falha ❌
  -Observações: 
    a. No usuário problem_user, o filtro não funcionou, além das imagens exibidas dos produtos estarem incorretas: -Anexo: ![screenshotct03](image.png)
    b. No usuário performance_glitch_user, a tela demorou para exibir a ordenação desejada dos produtos.
    c. No usuário error_user, ao selecionar este filtro, a plataforma exibiu a mensagem de erro "Sorting is broken! This error has been reported to Backtrace." Não foi possível utilizar o filtro.
    d.No usuário visual_user, a imagem do produto "Test.allTheThings() T-Shirt (Red)" está incorreta na página de ordenação dos produtos e os preços divergem conforme os filtros são alterados. 
    -Anexo: ![screenshotct09](imagens/image-4.png "CT09")

- CT10: Ordenação de produtos por Preço (de baixo a alto)
  -Resultado: Falha ❌
  -Observações: 
    a. No usuário problem_user, o filtro não funcionou, além das imagens exibidas dos produtos estarem incorretas: -Anexo: ![screenshotct03](image.png)
    b. No usuário performance_glitch_user, a tela demorou para exibir a ordenação desejada dos produtos.
    c. No usuário error_user, ao selecionar este filtro, a plataforma exibiu a mensagem de erro "Sorting is broken! This error has been reported to Backtrace." Não foi possível utilizar o filtro.
    d.No usuário visual_user, a imagem do produto "Sauce Labs Onesia" está incorreta na página de ordenação dos produtos; os preços divergem conforme os filtros são alterados e a ordenação de preços não está na ordem correta:
    -Anexo: ![screenshotct10](imagens/image-5.png "CT10")

- CT11: Ordenação de produtos por Preço (de alto a baixo)
  -Resultado: Falha ❌
  -Observações: 
    a. No usuário problem_user, o filtro não funcionou, além das imagens exibidas dos produtos estarem incorretas: -Anexo: ![screenshotct03](image.png)
    b. No usuário performance_glitch_user, a tela demorou para exibir a ordenação desejada dos produtos.
    c. No usuário error_user, ao selecionar este filtro, a plataforma exibiu a mensagem de erro "Sorting is broken! This error has been reported to Backtrace." Não foi possível utilizar o filtro.
    d.No usuário visual_user, a imagem do produto "Sauce Labs Fleece Jacket" está incorreta na página de ordenação dos produtos; os preços divergem conforme os filtros são alterados e a ordenação de preços não está na ordem correta:
    -Anexo: ![screenshotct11](imagens/image-6.png "CT11")

- CT12: Fluxo de compra
  -Resultado: Falha ❌
  -Observações: 
    a. No usuário performance_glitch_user o carrinho exibiu um ícone de 7 produtos, mesmo que apenas 6 tenham sido adicionados
    -Anexo: ![screenshotct12](imagens/image-9.png "CT12")
    b. Nos usuários error_user e problem_user não é possível adicionar os itens Sauce Labs Bolt T-Shirt, Sauce Labs Fleece Jacket e Test.allTheThings() T-Shirt (Red) ao carrinho por essa tela.

 - CT12.1: Fluxo de compra a partir da página do produto
  -Resultado: Falha ❌
  -Observações: 
    a. No usuário problem_user, não é possível adicionar nenhum produto ao carrinho por essa tela. Além disso, ao clicar no produto desejado, o usuário é redirecionado ao produto incorreto:
      I: Ao clicar em Sauce Labs Backpack, o usuário é redirecionado ao produto Sauce Labs Fleece Jacket;
      II: Ao clicar em Sauce Labs Bike Light, o usuário é redirecionado ao produto Sauce Labs Bolt T-Shirt;
      III: Ao clicar em Sauce Labs Bolt T-Shirt, o usuário é redirecionado ao produto Sauce Labs Onesie;
      IV: Ao clicar em Sauce Labs Fleece Jacket, o usuário é redirecionado a uma página que exibe a mensagem de erro "ITEM NOT FOUND", além de exibir o preço $√-1. Também é possível adicionar esse item  com erro ao carrinho.
      V: Ao clicar em Sauce Labs Onesie, o usuário é redirecionado ao produto Test.allTheThings() T-Shirt (Red);
      VI: Ao clicar em Test.allTheThings() T-Shirt (Red), o usuário é redirecionado ao produto Sauce Labs Backpack;
    b. No usuário performance_glitch_user, na página do produto, o botão "Back to products" demorou para redirecionar o usuário;
    c. No usuário error_user não é possível adicionar os itens Sauce Labs Bolt T-Shirt, Sauce Labs Fleece Jacket e Test.allTheThings() T-Shirt (Red) ao carrinho por essa tela.
    d. Também no usuário problem_user, caso o produto "ITEM NOT FOUND" seja adicionado ao carrinho por essa tela, não é possível abrir a página do carrinho, pois a mesma fica em branco: ![screenshot12d](imagens/image-11.png "CT12.1")

- CT13: Fluxo de checkout com 1 ou mais itens no carrinho
  -Resultado: Falha ❌
  -Observações: 
    a. No usuário problem_user, na tela de inserção das informações do usuário, não é possível adicionar texto no campo "Last Name". Ao tentar digitar algo nesse campo, a plataforma apaga o que estava escrito em "First Name" e insere a primeira letra digitada em "Last Name". Isso impede a finalização da compra, já que esse campo é obrigatório para continuar.
    b. No usuário performance_glitch_user, na página do produto, o botão "Back home" demorou para redirecionar o usuário;
    c. No usuário error_user o campo "Last Name" não é editável. Além disso, o botão "Finish" não finaliza a compra quando clicado.

- CT13.1: Fluxo de checkout com 0 itens no carrinho
  -Resultado: Falha ❌
  -Observações: Foi possível clicar no botão "Checkout", continuar o fluxo de checkout e finalizar a compra mesmo com 0 itens no carrinho. Também foi indevidamente exibida uma mensagem de sucesso e finalização da compra.
     -Anexo:![screenshotct13](imagens/image-7.png "CT13.1")
    
- CT14: Fluxo de checkout com dados vazios
  -Resultado: Falha ❌
  -Observação:No usuário error_user, não foi necessário inserir dados no campo "Last Name" para continuar o fluxo.

- CT15: Remoção de itens do carrinho
  -Resultado: Falha ❌
  -Observação: No usuário error_user e problem_user, não é possível remover um produto do carrinho pela página inicial ou pela página do produto, apenas pela página do carrinho.

- CT16: Navegação entre páginas do menu lateral - Menu Principal
  -Resultado: Sucesso ✅
  -Observação: No usuário performance_glitch_user, ao clicar no botão "All Items", a plataforma demora a redirecionar o usuário.

- CT16.1: Navegação entre páginas do menu lateral - "About"
  -Resultado: Falha ❌
  -Observações: 
    a. No usuário visual_user, ao ser redirecionado à essa página e tentar retornar à página anterior, o usuário é deslogado e é exibida uma mensagem de erro: "Epic sadface: You can only access '/inventory.html' when you are logged in.";
    b. No usuário performance_glitch_user, ao clicar no botão "About", a plataforma demora a redirecionar o usuário.
    c. No usuário problem_user, ao clicar no botão "About" o usuário é redirecionado para uma página que não existe (https://saucelabs.com/error/404) que exibe uma mensagem de "404 Not Found. The page you’re looking for doesn’t exist.It might have been moved, renamed, or deleted. Please check the URL and try again."

- CT16.2: Navegação entre páginas do menu lateral - "Logout"
  -Resultado: Sucesso ✅

- CT16.3: Navegação entre páginas do menu lateral - "Reset App State"
  -Resultado: Falha ❌
  -Observações:
    a. Nos usuários standard_user, visual_user, performance_glitch_user e problem_user a única informação resetada são os produtos inseridos no carrinho, bem como o ícone que exibia a quantidade de produtos no carrinho no canto direito superior da tela inicial. Mesmo assim, os produtos removidos do carrinho não tiveram seus botões "Add to cart" da tela inicial resetados.
    b. No usuário error_user, as informações resetadas ao clicar no botão só são refletidas após atualizar a página.


## 4. Sugestões de melhoria de UX/UI
- Adição de um botão, na tela de login, para manter o usuário conectado;
- Adição de um botão "Esqueci a senha";
- Inserir um botão que exiba as informações da conta do usuário, como seu username, informações de pagamento, endereço, etc.;
- Adicionar feedback ao clicar em botões, como animações ou transições;
- Ao remover um item do carrinho de compras na tela do carrinho, adicionar um feedback que informe que o produto foi removido;
- Possibilitar a edição da quantidade de um produto no carrinho;
- Impossibilitar a inserção de caracteres especiais nos campos "First Name" e "Last Name" na tela de dados do usuário;
- Adicionar um verificador de CEP para impedir que CEPs incompletos ou inválidos não consigam prosseguir com o fluxo de checkout, e sejam informados o porquê por meio de uma mensagem de erro;
- Especificamente no usuário visual_user:
  a. Corrigir o botão do menu lateral, que está inclinado;
  b. Corrigir a disposição do botão do carrinho, que está desalinhado do resto da página;
  c. Alinhar o botão "Add to cart/Remove" do produto "Test.allTheThings() T-Shirt (Red)" com os outros produtos;
  d. Padronizar o espaçamento antes do início do nome do produto;
  -Anexo: ![screenshotct08.1](imagens/image-3.png "SMUX")
  e. na tela do carrinho, mover o botão "Checkout" para o final da página, como nos outros usuários testados.
    -Anexo:![screenshotct12.1](imagens/image-10.png "SMUX2")


## 5. Bugs encontrados

- B01: Impossibilidade de login com o usuário "locked_out_user";
  - Exibido em CT02.

- B02: Problemas de desempenho com o usuário "performance_glitch_user";
  - Em diversos momentos durante os testes com esse usuário a performance da plataforma foi prejudicada;
  - Exibido em CT04,CT09, CT10, CT11, CT12, CT12.1, CT13, CT16 e CT 16.1.

- B03: Erro no funcionamento do filtro por Nome (de Z a A)
  - Exibido em CT09a e CT09d.

- B04: Erro no funcionamento do filtro por Preço (de baixo a alto)
  - Exibido em CT10a, CT10c e CT10d.

- B05: Erro no funcionamento do filtro por Preço (de alto a baixo)
  - Exibido em CT11a, CT11c e CT11d.

- B06: Impossibilidade de adicionar produtos ao carrinho
 - Exibido em CT12b, CT12.1a e CT12.1c.

- B07: Impossibilidade de remover produtos do carrinho nos usuários error_user e problem_user
  - Exibido em CT15

- B08: Produtos com redirecionamento incorreto
  - Ao clicar no produto desejado, o usuário é redirecionado ao produto incorreto;
  - Exibido em CT12.1a;

- B09: Produto com erro exibido no usuário problem_user 
  - A adição desse produto ao carrinho gera um bug ao tentar acessar a tela do carrinho;
  - Exibido em CT12.1d.

- B10: Campos obrigatórios de dados não são editáveis
  - Nos usuários problem_user e error_user os campos "Last Name" não são editáveis
  - Exibido em CT13a, CT13c e CT14.

- B11: Impossibilidade de finalizar compra
  - Botão "Finish" não completou o fluxo;
  - Exibido em CT13c.

- B12: Checkouts finalizados indevidamente
  - Foi possível avançar no fluxo de checkout mesmo com o carrinho vazio e/ou com dados do usuário incompletos ou ausentes;
  - Exibido em CT13.1 e CT14.

- B13: Botão "About" com redirecionamento incorreto
 - Exibido em CT16.1c.

- B14: Botão "Reset App State" com funcionamento incorreto
  - Informações como botões "Add to cart" não foram corretamente resetadas para os usuários standard_user, visual_user, performance_glitch_user e problem_user.
  - Exibido em CT16.3a.

- B15: Preços dos produtos inconsistentes para o usuário visual_user
  - Cada vez que a página era atualizada ou um novo filtro era inserido, os preços dos produtos exibidos variavam.
  - Exibido em CT11d


## 6. Análise de Riscos

6.1: Erro ao realizar login
- Probabilidade: Alta;
- Criticidade: Alta, afeta diretamente a experiência do usuário e a possibilidade de compra.
- Mitigação: Inserir logs que detalham as falhas de acesso.

6.2: Demora no carregamento das páginas
- Probabilidade: Alta;
- Criticidade: Média, afeta diretamente a experiência do usuário mas não impede a compra.
- Mitigação: Monitorar desempenho para identificar gargalos; aplicar melhorias nas consultas ao banco de dados.

6.3: Falta de validação dos dados inseridos nos formulários
- Probabilidade: Alta;
- Criticidade: Alta, expõe a segurança do site e pode afetar a experiência de compra do usuário;
- Mitigação: Adicionar validadores de input no backend; adotar o uso de máscaras para preenchimento do CEP.

6.4: Erros críticos visíveis ao usuário (ex.: produto "ITEM NOT FOUND")
- Probabilidade: Média;
- Criticidade: Alta, impede o funcionamento do fluxo de checkout, podendo levar ao abandono do carrinho pelo usuário e mau funcionamento da plataforma como um todo.
- Mitigação: Testes unitários e exploratórios para identificação e report dos erros.

6.5: Segurança ameaçada ao se utilizar uma mesma senha padrão a todos os usuários
- Probabilidade: Média;
- Criticidade: Alta, expõe a segurança do site e informações confidenciais dos usuários, podendo resultar em vazamentos de dados e violação da privacidade dos usuários.
- Mitigação: Exigência de senhas fortes aos usuários e criptografia das informações confidenciais.


## 7. Extras (diferenciais)

### 7.1 Testes de Responsividade
A plataforma respondeu bem aos testes de responsividade, se adaptando de forma eficiente a um grande range de dimensões de tela.
- Sugestão de melhoria: a partir do comprimento da tela de 478 pixels, as imagens começam a ficar adulteradas ao invés de manter a mesma dimensão:
  -Anexo: ![printscreen](imagens/www.saucedemo.com_inventory.html.png "R01")

### 7.2 Testes de Acessibilidade
- Página de produtos: os filtros não possuem uma label associada, o que impede um recurso de leitura de tela, por exemplo, de funcionar corretamente nestes filtros.

- No geral, os testes realizados apresentaram resultados positivos em todas as telas da plataforma, exceto nos filtros da página de produtos. Serão necessários ajustes para garantir que a experiência seja inclusiva a todos os usuários.
