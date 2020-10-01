# 1. Visão geral
Este notebook é parte da documentação de uma exploração de dados realizada para o artigo _**O uso da Cloroquina no tratamento da Covid-19 debatido no Facebook**: um estudo em opinião pública com processamento de linguagem natural_. O artigo ainda é inédito e será disponibilizado assim que possível.

## Sobre os dados
Os dados usados aqui foram coletados de um grupo aberto do Facebook, usando técnicas de [web scraping](https://en.wikipedia.org/wiki/Web_scraping). Mesmo sem uso da API da plataforma, e mesmo com todos os impedimentos do Facebook para esse tipo de coleta, uma quantidade significativa de comentários, reações (curtidas etc), replies, emojis e outros dados do tipo gerados pelos usuários foram coletados. Para os propósitos da presente análise, a prioridade são os comentários textuais dos usuários.

Foram coletados dados de sete tópicos de discussão do grupo [_Coronavirus Brasil Covid-19_](https://www.facebook.com/groups/606967836766216) abordando o uso de Hidroxi/Cloroquina no tratamento da Covid-19, totalizando aproximadamente três mil comentários.

Os dados foram limpos usando uma combinação de técnicas manuais e automáticas ([Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/), [Web Scraper](https://www.webscraper.io/), [RegEx](https://regex101.com/)) e salvos em formatos abertos diversos. Os arquivos e dados usados nesse projeto estão disponíveis [neste repositório do GitHub](https://github.com/fabianelima/cloroquiners).

## Resumo teórico
Esse experimento vem de reflexões a respeito do papel jornalístico das organizações de mídia de dar o tom do debate público, estabelecendo a pauta e servindo de plataforma a essas discussões (PETERSEN, 2019; HANITZSCH et al., 2014). As redes sociais digitais, que competem com essas organizações como plataforma e acabam pautando também o jornalismo, trazem mais complexidade ao tema, sendo caracterizadas por heterogeneidade de opiniões e manifestações de seus usuários (SOARES e RECUERO, 2017). Os usuários, por sua vez, repercutem temas e servem como difusores, formando comunidades no entorno dessas discussões. “A própria construção da opinião pública, assim, depende das ações de difusão de informações que são tomadas pelos atores na rede” (SOARES & RECUERO, op cit. p. 21). Políticos se valem dessa permeabilidade das redes, se valendo da lógica do infoentretenimento do jornalismo político para fazerem uma espécie de "contra-agendamento" da pauta (CHAGRA, 2014; RIORDA, 2016).

A cloroquina, [descartada pela OMS como tratamento para a Covid-19](https://www.bbc.com/portuguese/internacional-53085371), tem sido um _prop_ nas redes sociais em contas de políticos como [Trump e Bolsonaro](https://noticias.uol.com.br/saude/ultimas-noticias/bbc/2020/07/10/lancada-por-trump-e-propagandeada-por-bolsonaro-hidroxicloroquina-esta-vetada-em-hospitais-nos-estados-unidos.htm). Usado no tratamento de lúpus e malária, logo [o remédio desapareceu das farmácias](https://www.uol.com.br/vivabem/noticias/redacao/2020/03/20/com-lupus-elas-temem-falta-de-cloroquina-dores-podem-voltar-mais-fortes.htm). A análise de discussões sobre esse uso em um grupo do Facebook pode ser interessante para observar esse fenômeno. O Facebook facilita a manutenção de relações sociais que o usuário já possui e movimenta um tipo de valor social diferente de outras plataformas (ELLISON et al, 2007).

# 2. Processando linguagem: sumário
## Nuvens de palavras
[Neste notebook](https://github.com/fabianelima/cloroquiners/blob/master/1-wordclouds.ipynb), foi documentado todo o processamento do texto para a geração de visualizações (tokenização, stopwords etc). Foram geradas nuvens de cada um dos tópicos coletados e de todo o dataset.

## Co-ocorrências e frequências
[Este notebook](https://github.com/fabianelima/cloroquiners/blob/master/2-frequencias.ipynb) contém a documentação do processo de levantamento das frequências relativas dos termos mais usados pelos usuários. [Neste aqui](https://github.com/fabianelima/cloroquiners/blob/master/3-coocorrencias.ipynb), está documentada a análise de co-ocorrências e, [neste](https://github.com/fabianelima/cloroquiners/blob/master/4-lexico.ipynb), as análises de léxico.

## Análise de sentimento e polarização
Esse experimento não saiu muito conforme o esperado, mas serviu como aprendizado, o que por si só já vale a inclusão dele aqui. [Neste notebook](https://github.com/fabianelima/cloroquiners/blob/master/5-sentimento-teoria.ipynb), a teoria que o embasa, e [neste](https://github.com/fabianelima/cloroquiners/blob/master/6-sentimento-pr%C3%A1tica.ipynb), a prática de uma tentativa frustrada. Como "prêmio de consolação", foram geradas nuvens de palavras a partir dos dados rotulados.

# 3. Finalizando
Muito ainda pode ser extraído dos dados coletados. Esta análise teve caráter exploratório e experimental, buscando as possibilidades das ferramentas e também desenvolver familiaridade com elas. É possível usar esse conteúdo em outras ferramentas de análise de conteúdo textual, conduzir análises de conteúdo de tipo mais tradicional, analisar as relações entre os temas e usuários por meio da criação de grafos, levantar as reações, emojis, uso de gifs e outras expressões gráficas para traçar o humor da discussão etc. O objetivo final desse projeto é auxiliar o embasamento e a construção de um artigo para a disciplina de _Jornalismo Político e Opinião Pública_ cursada na UFPR.

# 4 Referências bibliográficas
CHAGRA, Adrián. “El marketing político bajo la lógica del espectáculo: cómo persuadir en el marco de una política espectacularizada”. In RAFAELLI, Marina; MENDIETTA, Angelica. **IV Cumbre Mundial de Comunicación Política**. México: 2014.

ELLISON, Nicole B.; STEINFIELD, Charles; LAMPE, Cliff. “The Benefits of Facebook 'Friends': Social Capital and College Students’ Use of Online Social Network Sites”. **Journal of Computer-Mediated Communication**. V. 12. N. 4. Julho de 2007, p. 1143–116. Disponível em: https://academic.oup.com/jcmc/article/12/4/1143/4582961. Acesso em 21 de agosto de 2020.

HANITZSCH, Thomas; HANUSCH, Folker; LAUERER, Corinna. "Setting the Agenda, Influencing Public Opinion, and Advocating for Social Change: Determinants of journalistic interventionism in 21 countries". In: **Journalism Studies**. N. 17. V. 1. 2014. P. 1-20. Disponível em: <https://www.tandfonline.com/doi/full/10.1080/1461670X.2014.959815> — Acesso em 28 de junho de 2020.

PETERSEN, Thomas. “Journalists and Public Opinion”. In: VOS, Tim P.; HANUSCH, Folker (org.). **The International Encyclopedia of Journalism Studies**. Nova Jersey: John Wiley & Sons Inc, 2019.

RIORDA, Mario. “No creo en las ideologías, pero que las hay las hay”. In: **Cambiando**. Primeira edição. Buenos Aires: Planeta, 2016. P. 167-200.

SOARES, Felipe Bonow; RECUERO, Raquel. “Opinião Pública no Twitter: Análise da indicação de Alexandre Moraes ao STF”. **LOGEION**: Filosofia da informação, Rio de Janeiro, v. 3 n. 2, p. 18-37, mar./ago. 2017. Disponível em: http://revista.ibict.br/fiinf/article/view/3836. Acesso em 20 de agosto de 2020.