# Criar um único mapa mental combinando todos os tópicos
combined_map = Digraph(comment='IA no Quotidiano e na Educação')

# Nó central
combined_map.node('IA', 'Inteligência Artificial')

# Subtópicos principais
combined_map.node('Chatbots', 'Chatbots e Assistentes Virtuais')
combined_map.node('Speech', 'Reconhecimento de Fala')
combined_map.node('Access', 'Acessibilidade')
combined_map.node('Edu', 'Educação')

combined_map.edges([('IA', 'Chatbots'), ('IA', 'Speech'), ('IA', 'Access'), ('IA', 'Edu')])

# Chatbots
combined_map.node('CB', 'Chatbots (ChatGPT, Bard, Bing Chat)')
combined_map.node('AV', 'Assistentes Virtuais (Siri, Alexa, Google Assistant)')
combined_map.node('Func', 'Funções: agendar, pesquisar, controlar dispositivos')
combined_map.edges([('Chatbots', 'CB'), ('Chatbots', 'AV'), ('Chatbots', 'Func')])

# Reconhecimento de fala
combined_map.node('STT', 'Speech-to-Text: Legendas, transcrição')
combined_map.node('TTS', 'Text-to-Speech: Leitura automática')
combined_map.edge('Speech', 'STT')
combined_map.edge('Speech', 'TTS')

# Acessibilidade
combined_map.node('Leg', 'Legendas Automáticas')
combined_map.node('Trans', 'Transcrições')
combined_map.node('LS', 'Avatares de Língua Gestual')
combined_map.node('Público', 'Pessoas com deficiência auditiva')
combined_map.edges([('Access', 'Leg'), ('Access', 'Trans'), ('Access', 'LS')])
combined_map.edge('Leg', 'Público')
combined_map.edge('Trans', 'Público')
combined_map.edge('LS', 'Público')

# Educação
combined_map.node('Criação', 'Criação de conteúdos')
combined_map.node('Revisão', 'Revisão com IAs generativas')
combined_map.node('Perso', 'Personalização da aprendizagem')
combined_map.node('Trad', 'Tradução de conteúdos')
combined_map.node('Imersiva', 'Experiência imersiva com avatares e voz')
combined_map.edges([('Edu', 'Criação'), ('Edu', 'Revisão'), ('Edu', 'Perso'), ('Edu', 'Trad'), ('Edu', 'Imersiva')])

# Renderizar o mapa combinado
combined_filename = "/mnt/data/mapa_IA_Completo"
combined_map.render(combined_filename, format='png', cleanup=True)
combined_filename + '.png'

