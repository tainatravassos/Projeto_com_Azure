1. Criar um ambiente virtual para usá-lo: python -m venv venv
2. Ativar o ambiente: ./venv/scripts/activate
3. Criação do arquivo requirements.txt
O arquivo requirements.txt não é especial por si só. É um arquivo de texto em que listamos as bibliotecas necessárias para o aplicativo. Mas é a convenção normalmente usada por desenvolvedores e facilita o gerenciamento de aplicativos em que várias bibliotecas são dependências.
4. Instalo as ferramentas do requirements.txt: pip install -r requirements.txt

Há muitos métodos disponíveis para criar um aplicativo Web, mas os dois mais comuns (e em que nos concentraremos) são GET e POST. GET geralmente indica que o usuário está solicitando informações. POST indica que o usuário precisa enviar algo e receber uma resposta.
Um fluxo de aplicativo comum que usa GET e POST gira em torno do uso de um formulário. Digamos que criamos um aplicativo no qual o usuário deseja se registrar para uma lista de distribuição:
O usuário acessa o formulário de inscrição via GET
O usuário preenche o formulário e seleciona o botão enviar
As informações do formulário são enviadas de volta ao servidor usando POST
Uma mensagem de "êxito" é retornada ao usuário


Modelos:
HTML é a linguagem usada para estruturar as informações exibidas em um navegador, enquanto CSS (folhas de estilos em cascata) é usada para gerenciar o estilo e o layout. Ao criar um aplicativo, a maior parte do HTML será estática, o que significa que não será alterada. No entanto, para tornar nossas páginas dinâmicas, precisamos conseguir colocar informações de forma programática em uma página HTML. Quase todas as estruturas da Web dão suporte a esse requisito por meio de modelos.

Um modelo permite que você escreva o HTML principal (ou um modelo) e indique espaços reservados para as informações dinâmicas. Provavelmente, a sintaxe mais comum para espaço reservado é {{ }}. O Jinja, o mecanismo de modelagem para Flask, usa essa sintaxe.

< h1 >Welcome, {{ name }}</ h1>

No exemplo anterior, temos o HTML de h1 (um cabeçalho), com o texto que queremos exibir. O {{ name }} indica que queremos exibir uma variável chamada name logo após Bem-vindo. Com essa sintaxe, podemos escrever o HTML com nossas habilidades existentes e injetar as informações dinâmicas conforme necessário.


5. Criação do app.py
A instrução de importação inclui referências a Flask, que é o núcleo de qualquer aplicativo Flask. Usaremos render_template em alguns instantes, quando quisermos retornar o HTML.
app será o aplicativo principal. Nós o usaremos quando registrarmos nossas rotas na próxima etapa.

Adicionar a rota
Nosso aplicativo usará uma rota – /. Essa rota é chamada algumas vezes de default ou index, porque será usada se o usuário não fornecer nada além do nome do domínio ou do servidor.
Usando @app.route, indicamos a rota que queremos criar. O caminho será /, que é a rota padrão. Indicamos que ele será usado para GET. Se uma solicitação GET chegar para /, o Flask chamará de forma automática a função declarada imediatamente abaixo do decorador, index em nosso caso. No corpo de index, indicamos que retornaremos um modelo HTML chamado index.html para o usuário.


Criar o modelo HTML para o formulário
O Jinja, o mecanismo de modelagem para Flask, é muito focado em HTML. Como resultado, podemos usar todas as habilidades e ferramentas HTML que já temos. Vamos usar o Bootstrap para estruturar nossa página e melhorar o aspecto dela. Com o Bootstrap, usaremos diferentes classes CSS no HTML.
HTML (Hypertext Markup Language) é uma linguagem de marcação padrão utilizada para criar páginas da Web. O HTML consiste em uma série de marcas e atributos para criar títulos, parágrafos, listas, imagens, links e outros elementos que compõem uma página da Web. Quando um usuário solicita uma página da Web, o navegador lê o código HTML e o renderiza como uma página da Web visual com a qual o usuário pode interagir. Para saber mais sobre HTML, consulte HTML básico.



6. Testar o aplicativo
comando: set FLASK_ENV=development
 e: flask run

o número da porta padrão que o Flask usa para atender às solicitações HTTP é o 5.000



Felizmente, há muitas soluções já criadas, que podemos acessar assim como qualquer API (interface de programação de aplicativo). Com essa abordagem, podemos nos concentrar no código, em vez de focarmos na modelagem complexa.

O Azure fornece um conjunto de ofertas chamado serviços de IA do Azure, que inclui serviços de pesquisa visual computacional, conversão de texto em fala e fala em texto e tradução de texto. Você pode acessar qualquer um desses serviços por meio de SDKs (kits de desenvolvimento de software) ou chamando-os da mesma maneira que chamaria qualquer outro ponto de extremidade HTTP.



Gerenciamento de chaves:
Para chamar o serviço de Tradução (ou qualquer outro Serviço Cognitivo), precisaremos de uma chave. Essa chave será usada sempre que acessarmos o serviço. A chave é semelhante a uma senha. Qualquer um que tenha acesso à chave poderá chamar o serviço e, se estivermos usando uma versão paga, essa pessoa poderá ter que pagar uma conta alta!

Uma ótima solução para proteger a chave ao fazer o trabalho de desenvolvimento é usar uma biblioteca chamada python-dotenev, geralmente denominada dotenv. Com a dotenv, criamos um arquivo chamado .env, que contém pares chave-valor que não queremos como parte do nosso código-fonte. Verificaremos se o arquivo está listado em gitignore quando enviarmos o código para o GitHub, de modo que não o publiquemos acidentalmente para todo mundo ver.



7. segui o passo a passo que esta no pdf

8. Salve em .env a senha fornecida no site da microsoft
Essas chaves são usadas para acessar a API do OpenAI. Não compartilhe suas chaves. Armazená-los com segurança– por exemplo, usando Azure Key Vault. Também recomendamos regenerar essas chaves regularmente. Apenas uma chave é necessária para fazer uma chamada à API. Ao regenerar a primeira chave, você pode usar a segunda chave para acesso contínuo ao serviço.




Com o serviço de Tradução de back-end criado no Azure e as variáveis armazenadas prontas para uso, vamos voltar nossa atenção para a adição da lógica e do modelo necessários para o aplicativo traduzir o texto. Passaremos pelas seguintes etapas:

Adicionar código para chamar o serviço:
Criar o modelo para exibir resultados
Testar o aplicativo
Adicionar código para chamar o serviço
app.py contém a lógica para o aplicativo. Adicionaremos algumas importações necessárias para as bibliotecas que usaremos, seguidas pela nova rota para responder ao usuário.