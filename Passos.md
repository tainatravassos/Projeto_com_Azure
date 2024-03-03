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


Criação do app.py
A instrução de importação inclui referências a Flask, que é o núcleo de qualquer aplicativo Flask. Usaremos render_template em alguns instantes, quando quisermos retornar o HTML.

app será o aplicativo principal. Nós o usaremos quando registrarmos nossas rotas na próxima etapa.