
# Mapa Mental: Inteligência Artificial no Quotidiano e na Educação
# Autor: [Seu Nome]
# Descrição: Geração de um mapa mental com Graphviz

from graphviz import Digraph

# Criar o diagrama
diagram = Digraph(comment='IA no Quotidiano e na Educação')

# Nó central
diagram.node('IA', 'Inteligência Artificial')

# Subtópicos principais
diagram.node('Chatbots', 'Chatbots e Assistentes Virtuais')
diagram.node('Speech', 'Reconhecimento de Fala')
diagram.node('Access', 'Acessibilidade')
diagram.node('Edu', 'Educação')
diagram.edges([('IA', 'Chatbots'), ('IA', 'Speech'), ('IA', 'Access'), ('IA', 'Edu')])

# Chatbots
diagram.node('CB', 'Chatbots (ChatGPT, Bard, Bing Chat)')
diagram.node('AV', 'Assistentes Virtuais (Siri, Alexa, Google Assistant)')
diagram.node('Func', 'Funções: agendar, pesquisar, controlar dispositivos')
diagram.edges([('Chatbots', 'CB'), ('Chatbots', 'AV'), ('Chatbots', 'Func')])

# Reconhecimento de fala
diagram.node('STT', 'Speech-to-Text: Legendas, transcrição')
diagram.node('TTS', 'Text-to-Speech: Leitura automática')
diagram.edge('Speech', 'STT')
diagram.edge('Speech', 'TTS')

# Acessibilidade
diagram.node('Leg', 'Legendas Automáticas')
diagram.node('Trans', 'Transcrições')
diagram.node('LS', 'Avatares de Língua Gestual')
diagram.node('Público', 'Pessoas com deficiência auditiva')
diagram.edges([('Access', 'Leg'), ('Access', 'Trans'), ('Access', 'LS')])
diagram.edge('Leg', 'Público')
diagram.edge('Trans', 'Público')
diagram.edge('LS', 'Público')

# Educação
diagram.node('Cria', 'Criação de conteúdos')
diagram.node('Rev', 'Revisão com IAs generativas')
diagram.node('Perso', 'Personalização da aprendizagem')
diagram.node('Trad', 'Tradução de conteúdos')
diagram.node('Imersiva', 'Experiência imersiva com avatares e voz')
diagram.edges([
    ('Edu', 'Cria'),
    ('Edu', 'Rev'),
    ('Edu', 'Perso'),
    ('Edu', 'Trad'),
    ('Edu', 'Imersiva')
])

# Gerar o arquivo
diagram.render('mapa_IA_Completo', format='png', cleanup=True)

print("Mapa mental gerado como 'mapa_IA_Completo.png'")
