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




