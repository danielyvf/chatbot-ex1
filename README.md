# 🤖 Chatbot Básico com NLTK
Este é um projeto simples de um chatbot em Python, inspirado na famosa terapeuta virtual Eliza, utilizando a biblioteca NLTK (Natural Language Toolkit). 
Ele simula conversas básicas com o usuário, podendo reconhecer padrões e responder de forma personalizada em português.

---

# Pré-requisitos
Antes de rodar o chatbot, é necessário instalar a biblioteca nltk e fazer o download de seus recursos básicos:
- Python 3.7 ou superior
- pip install nltk
- import nltk
- from nltk.chat.util import Chat, reflections

# Execução do Eliza
O NLTK já possui um chatbot pronto chamado Eliza, que funciona em inglês. No entanto, também é possível criar uma versão personalizada em português,
utilizando o módulo Chat (chat = Chat(pares, reflections_pt)) junto com um dicionário de reflexões adaptado. Você pode testá-lo com o seguinte código:
- import nltk
- nltk.chat.eliza.demo()

---

# Executando o Chatbot em Português
Crie um arquivo chamado chatbot.py e cole o seguinte código:

from nltk.chat.util import Chat, reflections


    reflections_pt = 
                  {'eu': 'você',
                  'eu sou': 'você é',
                  'eu era': 'você era',
                  "eu iria": 'você iria',
                  "eu irei": 'você irá',
                  'meu': 'seu',
                  'você': 'eu',
                  'você é': 'eu sou',
                  'você era': 'eu era',
                  "você irá": 'eu irei',
                  'seu': 'meu'}

    pares = [ # formato lista
    [
     r'oi|olá|opa',
     ['olá', 'como vai?', 'tudo bem?']
    ],
    [
     r'qual é o seu nome?',
     ['Meu nome é Chat e eu sou um chatbot']
    ],
    [
     r'(.*) idade?', #(.*) o chat fica mais dinamico, respondendo associando com alguma palavra que reconheça
     ['Não tenho idade pois sou um chatbot']
    ],
    [
     r'meu nome é (.*)',
     ['Olá %1, como você está hoje?'] # completa com o nome que o usuario respondeu onde tem o (.*)
    ],
    [
     r'eu trabalho na empresa (.*)',
     ['Eu conheço a empresa %1']
    ],
    [
     r'(.*) (cidade|país)',
     ['Porto União, Brasil']
    ],
    [
     r'quit',
     ['Até breve', 'Foi bom conversar com você. Até breve!']
        ]
    ]

    print('Olá, sou o chat!')
    chat = Chat(pares, reflections_pt)
    chat.converse()


## Exemplo de uso

    Olá, sou o chat!
        >olá
    como vai?
        >em qual cidade você mora?
    Porto União, Brasil
        >meu nome é jones
    Olá jones, como você está hoje?
        >quit
    Até breve   



