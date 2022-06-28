# AD3

Esta es la **actividad dirigida 3** que consiste en hacer un ejercicio de programación literaria aprovechando el código que hemos usado en programación con Python donde realizamos *web scraping*. 

## Código fuente

Este es el código que se convertirá en programación literaria:


```python
import requests
import time
import csv
import re
from bs4 import BeautifulSoup
import os
import pandas as pd
from termcolor import colored

resultados = []

req = requests.get("https://resultados.elpais.com")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup = BeautifulSoup(req.text, 'html.parser')

tags = soup.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req2 = requests.get("https://elpais.com/internacional")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup2 = BeautifulSoup(req2.text, 'html.parser')

tags = soup2.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req3 = requests.get("https://elpais.com/opinion")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup3 = BeautifulSoup(req3.text, 'html.parser')

tags = soup3.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req4 = requests.get("https://elpais.com/espana/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup4 = BeautifulSoup(req4.text, 'html.parser')

tags = soup4.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req5 = requests.get("https://elpais.com/economia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup5 = BeautifulSoup(req5.text, 'html.parser')

tags = soup5.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req6 = requests.get("https://elpais.com/sociedad/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup6 = BeautifulSoup(req6.text, 'html.parser')

tags = soup6.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req7 = requests.get("https://elpais.com/educacion/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup7 = BeautifulSoup(req7.text, 'html.parser')

tags = soup7.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req8 = requests.get("https://elpais.com/clima-y-medio-ambiente/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup8 = BeautifulSoup(req8.text, 'html.parser')

tags = soup8.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req9 = requests.get("https://elpais.com/ciencia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup9 = BeautifulSoup(req9.text, 'html.parser')

tags = soup9.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req10 = requests.get("https://elpais.com/cultura/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup10 = BeautifulSoup(req10.text, 'html.parser')

tags = soup10.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req11 = requests.get("https://elpais.com/babelia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup11 = BeautifulSoup(req11.text, 'html.parser')

tags = soup11.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req12 = requests.get("https://elpais.com/deportes/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup12 = BeautifulSoup(req12.text, 'html.parser')

tags = soup12.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req13 = requests.get("https://elpais.com/tecnologia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup13 = BeautifulSoup(req13.text, 'html.parser')

tags = soup13.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req14 = requests.get("https://elpais.com/tecnologia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup14 = BeautifulSoup(req14.text, 'html.parser')

tags = soup14.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req15 = requests.get("https://elpais.com/gente/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup15 = BeautifulSoup(req15.text, 'html.parser')

tags = soup15.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req16 = requests.get("https://elpais.com/television/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup16 = BeautifulSoup(req16.text, 'html.parser')

tags = soup16.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req17 = requests.get("https://elpais.com/eps/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup17 = BeautifulSoup(req17.text, 'html.parser')

tags = soup17.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)


os.system("clear")

print(colored("A continuación se muestran los titulares de las páginas principales del diario El País que contienen las siguientes palabras:", 'blue', attrs=['bold']))
print(colored("Feminismo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "feminismo" in s]
print("\n".join(str_match))

print(colored("Igualdad", 'green', attrs=['bold']))

str_match = [s for s in resultados if "igualdad" in s]
print("\n".join(str_match))

print(colored("Mujeres", 'green', attrs=['bold']))

str_match = [s for s in resultados if "mujeres" in s]
print("\n".join(str_match))

print(colored("Mujer", 'green', attrs=['bold']))

str_match = [s for s in resultados if "mujer" in s]
print("\n".join(str_match))

print(colored("Brecha salarial", 'green', attrs=['bold']))

str_match = [s for s in resultados if "brecha salarial" in s]
print("\n".join(str_match))

print(colored("Machismo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "machismo" in s]
print("\n".join(str_match))

print(colored("Violencia", 'green', attrs=['bold']))

str_match = [s for s in resultados if "violencia" in s]
print("\n".join(str_match))

print(colored("Maltrato", 'green', attrs=['bold']))

str_match = [s for s in resultados if "maltrato" in s]
print("\n".join(str_match))

print(colored("Homicidio", 'green', attrs=['bold']))

str_match = [s for s in resultados if "homicidio" in s]
print("\n".join(str_match))

print(colored("Género", 'green', attrs=['bold']))

str_match = [s for s in resultados if "género" in s]
print("\n".join(str_match))

print(colored("Asesinato", 'green', attrs=['bold']))

str_match = [s for s in resultados if "asesinato" in s]
print("\n".join(str_match))

print(colored("Sexo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "sexo" in s]
print("\n".join(str_match))
```

    América Latina gira hacia una nueva izquierda
    Un multiciclo de protestas como catalizador 
    El mundo se hunde en una espiral conflictiva. Este es el balance de fuerzas
    El castellano es el fracaso 
    Abortar es un derecho: así hay que decirlo
    Dos mujeres besándose, esa bomba
    Parole, parole, parole…
    Timbiquí, el pueblo colombiano donde el 99% votó a Petro
    El estratega tranquilo que aupó a Petro al poder
    Petro exhibe su tono más conciliador en sus primeros movimientos
    Francia Márquez no rompe techos de cristal
    Colombia y la nueva izquierda latinoamericana
    El desplome de una tribuna de una plaza de toros en Colombia deja al menos cuatro muertos y decenas de heridos
    Los piratas acechan las embarcaciones de la petrolera estatal mexicana Pemex
    El acoso a la clínica de Misisipi que detonó la sentencia contra el aborto: “Los que matan bebés merecen morir”
    El aborto entra de lleno en la campaña electoral de las legislativas de Estados Unidos
    Las protestas pierden músculo en Ecuador desplazadas por la propuesta de destitución de Lasso
    El Gobierno de Boric se enreda con la figura de la primera dama
    Imágenes sexuales que destruyen y matan
    Ramón Estévez lamenta llamarse Martin Sheen
    Marruecos se apresura a enterrar a los migrantes del asalto a la valla entre críticas
    Petro Poroshenko, expresidente de Ucrania: “Es imposible lograr un acuerdo. Putin quiere matarnos” 
    La vida sin descanso de Nelsi Ayala: limpiar casas 12 horas al día para ganar 1.200 euros
    Orgullo y poderío de la diversidad sexual: el gran negocio de cuatro billones de dólares
    Noruega homenajea a las víctimas del ataque en la puerta de un bar gay de Oslo: “Esta lucha no ha acabado”
    ¿Merece la pena ver ‘La casa de papel: Corea’? Diferencias y semejanzas con la serie original
    Paul McCartney celebra sus 80 años con casi tres horas de concierto en Glastonbury
    Atracones de helado, culebrones, sexo y éxtasis: un libro y un documental sobre George Michael
    La semana de la moda masculina de París apuesta por el cambio tranquilo
    De París y Río de Janeiro a un pueblo de dos habitantes en Soria: la escritora que se lanzó a la literatura a los 73 años
    Del aplauso no se come: los problemas de los creadores para llegar a fin de mes
    Toreros, trenes voladores y ovaciones a Franco: las películas inéditas del ingeniero José Hernández
    Siri, Alexa, Sophia: ¿por qué las asistentes virtuales tienen nombre de mujer?
    Pío XII, un papa entre la santidad y Hitler
    24 series para este verano
    Tres años después, Nadal contra la amnesia
    Gareth Bale se va a EE UU a jugar en el equipo de Magic Johnson
    Los días de vino y rosas del ‘calciomercato’, el mercado de fichajes italiano
    Ledecky se convierte en la primera nadadora en ganar cinco mundiales seguidos
    Dentro o fuera de la metrópolis: ¿es posible un dinamismo artístico sin estar en las grandes ciudades?
    Repensar la función y el futuro del arte contemporáneo
    24 horas de plomo en la sierra Tarahumara de México
    Gustavo Petro: la victoria final
    Así fue el rescate de la nadadora Anita Álvarez
    El mejor sexo de tu vida
    US Supreme Court overturns ‘Roe v Wade,’ ending federal abortion rights
    How tracking your menstrual cycles on an app can land you in jail 
    Aspirin for cancer and thalidomide for leprosy: new life for old drugs
    The salad days of the culture war: Which foods are leftist and which are right-wing?
    Brad Pitt believes that the end of his career is near: ‘I consider myself on my last leg’
    Going to a concert or painting helps us with emotional recovery
    Letras Americanas: la actualidad literaria de un continente vista por el escritor Emiliano Monge
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Toda la actualidad científica en el boletín de Materia
    Ideas: reportajes y entrevistas para entender el mundo
    Trump trató de poner un títere al frente del Departamento de Justicia para que impugnara el triunfo de Biden
    La candidatura de Ucrania espolea la impaciencia de los Balcanes para ingresar en la UE 
    Le Pen pide a sus nuevos diputados menos ruido y vestir corbata en la Asamblea Nacional de Francia
    Los bancos centrales avisan del peligro de estanflación pero ven “improbable” una crisis como la de los setenta
    Latinoamérica muestra su músculo ante el inicio del alza en las tasas de interés
    La inflación en Canadá rompe todos los récords en casi 40 años 
    Un día para existir en las calles de Ciudad de México
    Por qué estamos cada vez más deprimidos
    Una mañana de luz blanca: relato de un médico tras su primera eutanasia
    Así suena ‘Break My Soul’, lo nuevo de Beyoncé 
    Michael J. Fox, Diane Warren, Peter Weir y Euzhan Palcy recibirán los Oscar honoríficos
    María Pagés: “A los lugares cercanos se va a seguir yendo, pero a los lejanos… quién va a poder comprar los billetes”
    Las personas que comparten el mismo olor tienen más probabilidades de forjar una amistad
    Se llama Lucas, pero yo ya le llamo Diazepam: así me ha sobrepasado que mi perro tenga ansiedad por separación
    ASMR: ¿Ciencia, sentimiento o efecto placebo?
    De ultra a presidente del Hertha de Berlín
    Gareth Bale se va a EE UU a jugar en el equipo de Magic Johnson
    Eugenio López Chacarra, del golf amateur a millonario fichaje saudí
    La inacción ante la pérdida de arena condena a las playas de Barcelona
    La trampa mortal del trasvase Tajo-Segura: así se ahogan corzos y jabalíes en el canal 
    Dos veranos sin playa, cerrada por contaminación: “Si esto fuera Barcelona, se arreglaba en dos días”
    Acelerando la ciencia a 314.000 billones de operaciones por segundo
    Inteligencia artificial ¿para qué?
    Christopher Mims: “Amazon sabe cómo bajar el ritmo de trabajo para prevenir lesiones. Pero quizá dejaría de ganar dinero” 
    Un bombero gana un primer juicio al Ayuntamiento de Madrid: no se puede estar 24 horas activable sin cobrar las horas extra
    Unidas Podemos acentúa su discurso contra la OTAN a pocos días de la cumbre en Madrid 
    Cientos de militares se manifiestan en Madrid a cuatro días de la cumbre de la OTAN 
    El espíritu de Balbín está por todas partes
    ¿Merece la pena ver ‘La casa de papel: Corea’? Diferencias y semejanzas con la serie original
    Los Romanoffs
    Los problemas crecen para los Bieber: Hailey, demandada por la marca de cosmética que lanzó hace una semana
    Guillermo de Inglaterra cumple 40 años como el candidato ideal para seguir la estela de Isabel II
    Los 40 años de Guillermo de Inglaterra en 16 fotos
    Volver a la escuela tras dos años de pandemia
    La discriminación contra las minorías sexuales limita el desarrollo de Latinoamérica
    Zombis de ‘apps’, mercenarios del ‘streaming’, hermanos de contraseña: la rebelión de los usuarios
    'Historia para los nietos', por Javier Marías 
    Guy Standing: “Hemos dejado que la derecha se apropie de la libertad”
    Así era América antes de que Colón la descubriera
    Ya no se viaja igual que antes de la pandemia: estas son las nuevas modas del turismo 
    El salto mortal de Estrella Galicia 
    LaMDA, Google y cuando jugar con una inteligencia artificial es posible
    En los sesenta, todo se vendía con fotos
    Historias de superación en un centro de formación de adultos en Ceuta
    La paz global vive su peor momento de los últimos 15 años
    Los 10 cráteres más impactantes del mundo causados por meteoritos, en imágenes
    Restaurante Voro, un dos estrellas Michelin con auténtico ‘finger food’ en Mallorca
    «María del Monte y su estilista contactaron conmigo por TikTok y me preguntaron por mis mantones»
    Ellos no bailaron solos: la mujer detrás de la loca historia de Locomía
    Eugenia Silva: “No he vivido situaciones extremas. Sabía qué quería y hasta dónde llegar”
    Las frustraciones de Wes Craven, el genio del terror que quería dirigir melodramas
    Rebelión en el bar: los restaurantes que pasan de estar siempre abiertos
    Menú semanal de El Comidista (27 de junio a 3 de julio)
    Marea alta de dividendos: 6.000 millones de euros este verano
    Fernando Tejero revela cómo Dani Martín le sacó de una pensión decadente tras llegar a Madrid para llevarle a vivir a casa de sus padres
    Ponte a prueba con nuestros crucigramas, sopas de letras, sudokus y juegos arcade
    Un histórico corresponsal de TVE saca los colores a Ayuso tras leer su última entrevista
    ‘El gesto más atlético de Luis’: episodio final ya disponible
    Hidrógeno verde, la coincidencia más feliz de Mallorca
    La OTAN decidirá en Madrid el mayor despliegue militar desde la Guerra Fría
    El G-7 estudia nuevos mecanismos para asfixiar la economía de Rusia
    El mundo se hunde en una espiral conflictiva. Este es el balance de fuerzas
    Putin teme a la UE más que a la OTAN
    Exiliados rusos
    Cambio en Colombia
    Las elecciones reparlamentarizan Francia
    Emmanuel Macron pierde las legislativas en Francia 
    La influencia de China preocupa al G-7
    Carlos de Inglaterra recibió en mano más de tres millones de euros de un jeque catarí 
    Noruega homenajea a las víctimas del ataque en la puerta de un bar gay de Oslo: “Esta lucha no ha acabado”
    La policía sudafricana investiga la muerte de al menos 21 personas en una discoteca en el sur del país
    José Manuel Albares, ministro de Exteriores: “Las mayores amenazas para la seguridad de los españoles vienen ahora del Este”
    Le Pen pide a sus nuevos diputados menos ruido y vestir corbata en la Asamblea Nacional de Francia
    El “verano del descontento” inglés que Europa mira de reojo
    Petro Poroshenko, expresidente de Ucrania: “Es imposible lograr un acuerdo. Putin quiere matarnos” 
    Jens Stoltenberg, líder de la OTAN: “Dar la paz por descontada en Europa puede terminar en una guerra”  
    Más de 4.000 soldados, 21 cazas y toneladas de artillería plantan cara a la amenaza rusa en los países bálticos
    Bolsonaro logra que Portugal le preste el corazón del emperador que independizó Brasil en 1822
    Trump trató de poner un títere al frente del Departamento de Justicia para que impugnara el triunfo de Biden
    El Supremo de Estados Unidos consagra el derecho a llevar armas en público
    La ayuda estatal a los más pobres en Argentina profundiza la disputa por el poder en la Casa Rosada
    Demócratas y republicanos alcanzan el primer acuerdo en décadas para el control de armas en Estados Unidos
    La Corte Suprema argentina deja libre el camino para juzgar a Cristina Kirchner en una causa por corrupción
    Nuevo paquete anticrisis
    La guerra de Putin es imprevisible
    El castellano es el fracaso 
    Parole, parole, parole…
    Vidas gitanas
    El leninismo reaccionario ha ganado
    Cierra las piernas, niña
    El aborto y la guerra fría
    Si la OTAN no existiera 
    América Latina, ‘quo vadis?’
    Perder el sentido de la oportunidad
    Boca abierta
    Aborto en EE UU: medio siglo hacia atrás
    El Roto
    Peridis
    Flavita Banana
    Riki Blanco
    Sciammarella
    Planeta de Plástico, por Malagón
    Envía tu carta
    Réquiem por la sierra de la Culebra  
    Harta de los negacionistas
    Desmantelando la sanidad, que es gerundio
    Opinar sin insultar
    Contra el conflicto de intereses, transparencia
    Entre los derechos de Esther López y los de los lectores
    El defensor del lector contesta
    Marruecos se apresura a enterrar a los migrantes del asalto a la valla entre críticas por la posible ocultación de las causas de la muerte
    Miles de personas salen a la calle en Madrid para protestar contra la OTAN a pocos días del arranque de la cumbre  
    Sánchez anuncia una ayuda de 200 euros para trabajadores y parados con bajos ingresos y una subida del 15 % de las pensiones no contributivas 
    La búsqueda de seguridad vence al cabreo
    Los errores se pagan
    Desborde popular en Andalucía
    Demasiado ruido en el Gobierno de coalición
    La ‘confederalización’ del PP
    Sánchez: “Este es un Gobierno incómodo para algunos sectores económicos. Pero no nos quebrarán”
    Las 100 horas que quemaron el corazón de la sierra de la Culebra
    El bipartidismo retorna en versión corregida
    ¿Y si hubiese elecciones generales? Un repaso a las encuestas después de Andalucía
    Tres flancos de presión forzaron el adiós de Mónica Oltra
    Los testigos del asalto a la valla de Melilla: “Todo era sangre, piel desgarrada, pies rotos, manos rotas…”
    Relato de uno de los migrantes que intentó entrar en Melilla: “La policía marroquí estaba muy violenta y ellos débiles y hambrientos”
    La tragedia bajo la valla de Melilla que nadie pudo tapar en Marruecos
    Los otros saltos masivos y mortales a la valla
    Unidas Podemos acentúa su discurso contra la OTAN a pocos días de la cumbre en Madrid 
    Cientos de militares se manifiestan en Madrid a cuatro días de la cumbre de la OTAN 
    Un paraíso en el que avistar más de 20 especies de cetáceos
    El secreto de Fuerteventura se hace viral: la ‘playa de las palomitas’
    Artesanía y cultura que conquista a las ‘influencers’
    Más allá de la capital. El triunfo de la vida rural madrileña
    Así lucha la tierra del cerezo para conseguir un nuevo florecimiento económico
    “Siempre me ha parecido que los que iban disfrazados eran los demás”
    “La herramienta más poderosa para salvar a la humanidad son las matemáticas”
    Los bancos centrales avisan del peligro de estanflación pero ven “improbable” una crisis como la de los setenta
    Medio centenar de vuelos cancelados en la tercera jornada de huelga en Ryanair
    La vida sin descanso de Nelsi Ayala: limpiar casas 12 horas al día para ganar 1.200 euros
    Marc Murtra: “Ni hay interferencias, ni habrá injerencias mientras sea presidente de Indra”
    Una espiral maldita llamada inflación 
    Lecciones posteriores al Brexit para España
    La fina línea entre inflación y recesión
    Crisis energética y precios del carbono
    No me gustan las cuotas
    El corte de gas ruso aboca a Europa al carbón
    Las energéticas francesas llaman a hogares y empresas a reducir su consumo “de inmediato”
    Orgullo y poderío de la diversidad sexual: el gran negocio de cuatro billones de dólares
    El G-7 estudia nuevos mecanismos para asfixiar la economía de Rusia
    Francisco Cuadrado: “Santillana ya no es una empresa de contenidos, da soluciones integrales a las escuelas”
    75 vuelos cancelados en la segunda jornada de huelga de los tripulantes de Ryanair
    Por qué el mejor inversor del mundo se rinde al petróleo
    La cuesta abajo de Netflix despierta a los tiburones (pero por desgracia no está en venta)
    LaLiga tiene un plan para conquistar América
    Daniel Sillman (Relevent): “El fútbol tiene oportunidades de negocio aún por explotar”
    Estas son las nuevas medidas acordadas por el Gobierno en el decreto anticrisis
    Ferrari corre hacia un mundo más verde y caro
    Vientres de alquiler: una boyante y turbia industria que aprovecha las rendijas legales para enriquecerse
    Ya no se viaja igual que antes de la pandemia: estas son las nuevas modas del turismo 
    El salto mortal de Estrella Galicia 
    No me gustan las cuotas
    Las rentas más bajas soportan una presión fiscal similar a la del 1% más rico
    La CNMV quiere que los inversores institucionales se impliquen a largo plazo en las cotizadas
    Las hipotecas a tipo fijo superan el 75% en abril y marcan un nuevo récord en plena escalada del euríbor
    Por qué el bitcóin ha caído un 70% desde máximos y por qué puede seguir a la baja
    Líos en la piscina comunitaria: normas y sentencias para un chapuzón seguro
    Parir en casa, educarlo por mi cuenta… ¿Qué puedo decidir sobre mi hijo y qué no?
    Saltarse un paso a nivel de camino a la oficina es accidente laboral
    Francisco Javier Blasco: “Llevamos años sin mejorar la eficacia de las políticas activas de empleo”
    ¿Es esta la edad dorada del emprendimiento universitario?
    Y después de la EBAU, ¿qué?
    Cancerberos del bienestar de la empresa
    Salud a golpe de clic con la cercanía del médico de cabecera
    Cómo garantizar la seguridad en un mundo de amenazas híbridas
    ¿Cuáles son los dilemas éticos del uso de la inteligencia artificial?
    Las aventuras de un par de calcetines que dan empleo a todo un pueblo
    Cultura financiera como punto de partida para volver a empezar
    Por qué digitalizar una pyme aporta más empleo
    Logística a bajas temperaturas, la revolución que vino del frío
    ‘Coopetir’: la actitud DFactory
    Así serán las ciudades de la (nueva) última milla
    PERTE Agroalimentario: ¿cómo acceder a los fondos europeos?
    Claves para internacionalizar mi negocio
    ¿Crisis de deuda mundial a la vista?
    ¿Está al frente España de la revolución del hidrógeno? 
    El momento de la energía solar
    Las principales reformas (con subvención europea) para ahorrar energía en la vivienda
    Gloria Ramos, cuando el afán de superación acaba en la alfombra roja 
    La importancia de la cultura financiera para tener una buena jubilación
    Hotmart y su plataforma 360 para creadores de contenidos
    Una aplicación para presentar la declaración desde casa y conseguir los máximos beneficios
    Miles de personas se manifiestan en Madrid contra el aborto: “La sentencia del Supremo en EE UU da esperanza”
    No se gobierna con el catecismo romano
    La ‘América pos Roe’: cómo la sentencia sobre el aborto agrava la polarización de Estados Unidos
    No se gobierna con el catecismo romano
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    El intento de suicidio de Juan y las somatizaciones de Carmen: ¿por qué los colegios necesitan un psicólogo educativo?
    El acoso a la clínica de Misisipi que detonó la sentencia contra el aborto: “Los que matan bebés merecen morir”
    Abortar es un derecho: así hay que decirlo
    El movimiento en defensa del derecho al aborto toma las calles de EE UU tras la decisión del Supremo
    El aborto en EE UU tras la decisión del Supremo: las claves
    El Tribunal Supremo deroga el derecho al aborto en Estados Unidos
    Un día muy triste para todas las mujeres
    Primero de carrera: los bachilleres de la escuela pública son los que más materias aprueban 
    El origen de la hepatitis aguda infantil es todavía un misterio después de 894 casos, decenas de trasplantes y 18 muertes
    La Iglesia insiste en que no abrirá sus archivos al Defensor, aunque cederá datos de casos concretos que le solicite
    El nuevo sistema para evaluar los conocimientos digitales de los profesores valdrá en toda España
    La OMS resuelve que de momento la viruela del mono no es una emergencia sanitaria internacional
    Mitos, falsedades, bulos y realidades sobre el VIH 40 años después
    Educadores con VIH para minimizar el impacto tras el primer diagnóstico
    El tremendo peso de la obesidad en España
    Interactivo | Los 14 cambios en los aeropuertos españoles que no ves y que ya están ocurriendo
    Encontrar empleo pese a los obstáculos. Por dónde empezar la búsqueda
    La fórmula de Carboneros para evitar el éxodo rural: trabajar cuidando a los vecinos 
    Consejos y cuidados para el primer verano con un gatito o un perrito
    ¿Qué tienen en común perros y gatos cuando son cachorros?
    La guía definitiva para alimentarnos mejor (y cuidar nuestra salud y la del planeta)
    Más vida después del cáncer de próstata avanzado 
    Cáncer de ovario, el más rebelde de los tumores ginecológicos
    El metro como refugio. De los andenes de Madrid en 1936 a los de Kiev en 2022
    La salud mental de los refugiados: cómo abrirse para cerrar las heridas
    El desconocido (y esencial) apoyo de los farmacéuticos a los pacientes crónicos
    El esfuerzo de una paciente por convertirse en su doctora
    Así es la vida de los refugiados ucranianos en España
    ¿Cómo será el envase para alimentos y bebidas del futuro?
    Primero de carrera: los bachilleres de la escuela pública son los que más materias aprueban 
    Universidad en reconstrucción 
    Volver a la escuela en América Latina tras dos años de pandemia
    El intento de suicidio de Juan y las somatizaciones de Carmen: ¿por qué los colegios necesitan un psicólogo educativo?
    El nuevo sistema para evaluar los conocimientos digitales de los profesores valdrá en toda España
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Solo un 3% de alumnos de Cataluña pidió hacer el examen de Selectividad en castellano
    Subirats reinterpreta la ley de Universidades: freno a la precariedad, facilidades para los alumnos extranjeros y ciencia abierta
    “Los profesores no van a cambiar de golpe su forma de trabajar el curso que viene por la nueva ley educativa”
    Trampantojo de pescado y lasaña vegetal en el comedor: cientos de colegios buscan fórmulas para que llevar la alimentación responsable a los niños
    Vídeo | Las recetas del cocinero escolar para que los niños de El Grau coman sano y rico 
    Sin currículos
    La escuela concertada ante las desigualdades: el debate pendiente
    La equidad frente a las políticas educativas de privatización en Andalucía
    No hay lunes al sol en la Universidad
    Ofrecer comedor gratis en todos los colegios públicos es “alcanzable y urgente”: costaría 1.664 millones al año, según la ONG Educo  
    Una fórmula para que la escuela pública compita mejor con la concertada
    La pérdida de alumnos por el descenso de la natalidad está afectando con más fuerza a la escuela pública que a la concertada
    El Ayuntamiento de Madrid guarda en un cajón una herramienta ya pagada para ver los datos de contaminación al detalle 
    La implantación del nuevo Bachillerato general fracasa pese a su demanda potencial: “Creímos que lo pedirían seis alumnos y lo han hecho 27”
    Toni Solano, director de instituto: “Veo mal a los niños, necesitan muchísima ayuda”
    Niños, Administraciones y redes sociales: prohibir su uso con una mano y enseñar a crear contenidos con la otra
    El Gobierno aprueba el decreto de bachillerato: los alumnos podrán terminar con un suspenso y desembocará en una nueva Selectividad
    La ley del silencio dentro y fuera del aula
    Las universitarias desertan del grado de Matemáticas ahora que tiene pleno empleo. ¿Por qué?
    Golpe a la temporalidad en las universidades: 25.000 profesores asociados serán indefinidos a tiempo parcial
    Antonio Abril: “Yo le decía a Castells: ‘Tienes que aguantar la presión, tienes que hacer la reforma universitaria”
    Los universitarios extranjeros podrán quedarse un año en España automáticamente al terminar la carrera
    Sierra de la Culebra: un incendio gigantesco que no pone en peligro a los lobos, pero sí un modelo de convivencia ejemplar
    La indignación crece sobre las ascuas del incendio en la sierra de la Culebra
    Jardines en los tejados, árboles africanos y calles pintadas de blanco: cómo adaptar la ciudad al calor extremo
    La construcción de 52 viviendas en una playa de Begur desata la indignación de las redes
    Un continente mortal para los defensores de la tierra
    Drama en la sierra de la Culebra, el paraíso del lobo ibérico que quedó abrasado por un rayo
    Alemania anuncia que recurrirá al carbón ante el recorte de suministro de gas ruso
    La inacción frente al cambio climático hará que sea habitual superar los 40 grados en junio en España
    Ibrahim Thiaw: “Hay que prepararse mejor frente a las sequías, los agricultores franceses están cultivando ya cereales africanos”
    La ola de calor provoca la caída de cientos de crías de vencejo en las calles de Sevilla y Córdoba
    “En Singapur ya se vende carne cultivada para alimentación” 
    La lección del martín pescador para afrontar la crisis ecológica
    Estocolmo+50: mirar atrás para tomar impulso
    El verano ya no es lo que era 
    Juan Serna, Premio Nacional de Medio Ambiente: un reconocimiento merecido
    Ríos imposibles: las 171.000 barreras que rompen el curso de agua en España
    La UE abraza las renovables para romper la dependencia de Rusia
    La lucha en un pueblo de Teruel para salvar su última montaña
    ¿Qué aire respiran los niños de Madrid y Barcelona? En el 46% de los colegios se supera la contaminación permitida
    Toreros, trenes voladores y ovaciones a Franco: las películas inéditas del ingeniero José Hernández Santorcuato
    Las personas que comparten el mismo olor tienen más probabilidades de forjar una amistad
    Así se puede ver la alineación de cinco planetas a simple vista, justo antes de cada amanecer
    Las vacunas contra el coronavirus salvaron 20 millones de vidas en su primer año
    Seis jóvenes científicos que han impulsado avances en la investigación matemática de vanguardia obtienen los Premios Vicent Caselles
    Así se puede ver la alineación de cinco planetas a simple vista, justo antes de cada amanecer 
    Fracciones egipcias
    El Congreso aprueba la reforma de la ley de la ciencia sin votos en contra
    Matemáticas para describir los remolinos, los taxis del océano
    Las incógnitas de la pastilla milagrosa contra un tipo de calvicie
    ¿Se puede dejar de roncar?
    El síndrome del hombre lobo y la realidad lógica de su fábula
    Muere Yves Coppens, uno de los descubridores del fósil más famoso del mundo 
    Ni patentes, ni firmar estudios: las científicas reciben mucho menos reconocimiento por su trabajo
    La metástasis del cáncer avanza durante el sueño
    A la caza de exolunas, la próxima frontera de exploración planetaria
    A la caza de exolunas, la próxima frontera de exploración planetaria
    Matemáticas para describir los remolinos, los taxis del océano
    Reaparece la tesis de María Wonenburger, la pionera matemática española que permaneció décadas en el olvido
    Técnicas criptográficas que se fundamentan en lo impredecible
    Las matemáticas de los juegos malabares
    El problema del huerto
    Números McNugget
    La moneda de Frobenius
    El síndrome del hombre lobo y la realidad lógica de su fábula
    La locura como juego; más allá del Quijote y de las novelas de Pérez Galdós
    El andar del borracho, las huellas del azar y el juego de dados en algunos libros malditos
    El campo vibratorio y las fronteras de la ciencia desde un punto de vista científico
    Paul Auster fluctuando entre el pudin de pasas y la nube de mosquitos
    ¿Son mejores las hormonas bioidénticas?
    ¿Qué surgió antes, el ARN o el ADN?
    ¿Por qué se sabe que los núcleos de la Tierra rotan?
    ¿Qué son los mini reactores nucleares?
    Invitados indeseables por Navidad: el muérdago y otras plagas que evitar durante las fiestas
    Las ‘apps’ nutricionales o cómo comer bien no debería depender de uno mismo
    Malnutrición invisible: el impacto de la pobreza en la salud infantil
    El óxido de etileno, la sustancia cancerígena que ha obligado a retirar miles de alimentos en la UE
    Que no te líen con los ingredientes: aceites y grasas de mala calidad nutricional
    Pío XII, un papa entre la santidad y Hitler
    Tom Jones, incólume al paso del tiempo con 82 años, enardece en los jardines de Pedralbes de Barcelona
    Del aplauso no se come: los problemas de los creadores para llegar a fin de mes
    Aventuras en el desierto con la daga y el escorpión
    “¿Cómo lo haría Tony?”
    La casa de Ana Frank: memoria del Holocausto, entre el comercio y la apropiación personal
    El libro que explica qué significa ‘votar normal’
    Paul McCartney celebra sus 80 años con casi tres horas de concierto en Glastonbury
    De París y Río de Janeiro a un pueblo de dos habitantes en Soria: la escritora que se lanzó a la literatura a los 73 años
    Christina Aguilera hace explosionar con pop carnal el Mallorca Live Festival
    La semana de los “segundones”: nueva entrega de las crónicas de Emmanuel Carrère desde el juicio por los atentados de París
    Los frescos de Goya en Madrid están en riesgo por el mal estado del tejado de la iglesia que los alberga 
    El mercado del arte mide sus fuerzas en la Feria de Maastricht 
    Joaquín Sorolla y Esteban Vicente: cómo convertir la pasión por los jardines en luz para su arte
    Vetusta Morla se agiganta en el Wanda  sin despegar los pies de la tierra 
    Guillermo Aguirre: “No hay nada más peligroso que meter a un adolescente en un sitio en el que no quiere estar”
    Nadie quiere el cuadro de Goya
    El Museo de Teruel afirma que el Torico actual es el mismo que había antes de la Guerra Civil, que ya no era de bronce  
    Juan Muñoz se descubre más allá de sus esculturas
    El cine quiere ser verde desde la alfombra roja a la basura de una sala
    El último atardecer de Europa se ve solo desde este lugar. Un viaje hacia el infinito por el Camino de Fisterra-Muxía
    Un paseo fluvial con museos y otro lleno de piscinas termales. Las sorpresas de la Vía de la Plata
    Lorca, en la ciudad al margen
    El Pirineo oscense, para entrar a vivir
    Toda la lectura del verano, en el bolsillo
    Harry Potter cumple 25 años: libros para revivir la magia de Hogwarts
    Los mejores libros recientes para reír a carcajadas
    Disfruta del Festival de Teatro Clásico de Mérida
    'Territorios de vanguardia' en el Museo Reina Sofía
    Últimas funciones de 'We Will Rock You'
    Nueva edición de Cibeles de cine 
    Una de Miura sin opciones
    Manzanares salva la tarde de San Juan
    La fiesta de los toros, una emocionante y apasionada polémica desde el siglo XIII
    La apabullante autoridad de Roca Rey
    Cada testimonio es único: se acaba el tiempo de los supervivientes del Holocausto
    Un Houellebecq sentimental, la fiesta de la imaginación de Garriga Vela y otros libros de la semana
    Los cajones de sastre de Néstor Sanmiguel Diest
    CaixaForum València: un paisaje no es un edificio
    Moderat: “El tecno es mala hierba, nunca morirá”
    Poyo Rojo, la sensación argentina de la danza teatro 
    Las Huecas, teatro alternativo de verdad
    Trampantojo: Batallas culturales
    ‘Aniquilación’, de Michel Houellebecq: confusión en el campo de batalla
    LaMDA, Google y cuando jugar con una inteligencia artificial es posible
    En los sesenta, todo se vendía con fotos
    Otros turismos (lejos y aquí cerca)
    Volver al cine
    Sin autor, da lo mismo
    Alex sin Ada
    ‘Horas muertas’, en un Dublín hipnótico
    ‘Prometeo’, trío de ases
    ‘La memoria del alambre’, ese algo misterioso que daba miedo
    ‘Tarradellas. Una cierta idea de Cataluña’: manual de resistencia
    Manuel Estrada: “Me agrada que me digan que gusta más la portada que el libro”
    Óscar Esquivias: “No hace falta ser creyente para leer la Biblia”
    Amelia Castilla: “Los ritos nos ayudan a hacer viable el trance de la muerte”
    Shuarma: “Me gusta de la poesía el silencio que encierra”
    Eva Orúe: “Haría cola por la firma de Margaret Atwood”
    Lanzado hacia los 18m, cada salto de Jordan Díaz es un récord, o casi
    Fernando Carro, del cielo al infierno, y regreso
    Italia, el modelo de natación que España no sabe imitar 
    El doble regalo del deporte a Girona
    Aquel homenaje a Zico
    El silencio en los fichajes
    El ‘Cuerdo’ Bielsa
    Bagnaia aprovecha el lío entre Quartararo y Espargaró para ganar el Gran Premio de los Países Bajos de Moto GP  
    De ultra a presidente del Hertha de Berlín
    Los días de vino y rosas del ‘calciomercato’
    Nakamura sorprende con un juego magnífico y tumba a Caruana
    Álex Márquez ficha por el Ducati Gresini
    GP de Assen: 30 años de la histórica victoria de Àlex Crivillé
    Tres años después, Nadal contra la amnesia
    Las criptomonedas saltan al deporte: una historia de conveniencia y desconfianza
    Pioneros para siempre
    Gareth Bale se va a EE UU a jugar en el equipo de Magic Johnson
    Eugenio López Chacarra, del golf amateur a millonario fichaje saudí
    Apoteosis de Italia, oro en el relevo de 4x100 estilos del Mundial de Natación
    La selección femenina de fútbol golea a Australia a dos semanas de la Eurocopa (7-0)
    La nueva gran atracción del fútbol español
    “Nunca acepto un no por respuesta”
    La mayor fábrica de baloncesto de Europa
    Crónica de dos ciudades moldeadas por la misma pasión 
    Aquel homenaje a Zico
    El desplome de Suzuki tras anunciar su retirada de MotoGP: un cuarto puesto, cinco ceros y tres caídas desde Le Mans
    Valverde regresa al Athletic con el triunfo presidencial de Jon Uriarte
    Ledecky se convierte en la primera nadadora en ganar cinco mundiales seguidos
    España denuncia la presunta alineación indebida de un jugador de Rumania para volver al Mundial
    Firouzja está flojo
    La FINA prohíbe a Anita Álvarez, la nadadora que se desmayó, participar en la final por equipos en los Mundiales
    El circuito europeo de golf multa con 116.000 euros a los fugados a la liga saudí
    Imágenes sexuales que destruyen y matan
    Tres cosas que hacemos mal con el teléfono móvil (y no sirven para nada)
    Christopher Mims: “Amazon sabe cómo bajar el ritmo de trabajo para prevenir lesiones. Pero quizá dejaría de ganar dinero” 
    ¿Sigue siendo imprescindible tener un antivirus? 
    Google News vuelve a España ocho años después de su cierre
    Mónica Ojeda, pedagoga: “Los adolescentes utilizan sus imágenes sexuales como moneda de cambio o como prueba de amor”
    Zuckerberg desvela cómo serán las gafas para entrar en el metaverso
    Por qué retuitear el vídeo sexual de Santi Millán también es delito: la desprotección de la intimidad en internet
    LaMDA, la máquina que “parecía un niño de siete años”: ¿puede un ordenador tener conciencia?
    La inteligencia artificial reconocerá el arte gracias a la ciencia ciudadana
    “Gano 1.500 euros al mes con los videojuegos”: así funciona el negocio de la compraventa de cuentas
    Cinco aplicaciones móviles, con aval científico, que salvan vidas o mejoran tu salud
    Cómo contarle tus ciclos menstruales a una app puede llevarte a la cárcel
    Bill Gates dice que las criptomonedas y los NFT están basados en encontrar a “alguien más tonto”
    El Princesa de Asturias de Investigación Científica distingue a cuatro expertos en sistemas que imitan al cerebro
    En defensa de la procrastinación. Elogio del tiempo perdido (frente al que las redes te roban)
    Instagram, el mejor de los mundos posibles
    Del terrorismo youtuber al influencer rabioso: el odio inunda la red
    Cronodiversidad. ¿Por qué el tiempo cada vez va más rápido?
    Herramientas que ayudan a crecer a las empresas (más allá de los pagos)
    La solución definitiva para vender más (y mejor) en la web
    La cámara de este ‘smartphone’ es pura magia
    Por qué todos hablan de este ‘smartphone’ de diseño atractivo y rendimiento prémium
    Un campus de programación para adquirir todas las habilidades ‘tech’
    Una catapulta para el talento de ‘kilómetro cero’
    Imágenes sexuales que destruyen y matan
    Tres cosas que hacemos mal con el teléfono móvil (y no sirven para nada)
    Christopher Mims: “Amazon sabe cómo bajar el ritmo de trabajo para prevenir lesiones. Pero quizá dejaría de ganar dinero” 
    ¿Sigue siendo imprescindible tener un antivirus? 
    Google News vuelve a España ocho años después de su cierre
    Mónica Ojeda, pedagoga: “Los adolescentes utilizan sus imágenes sexuales como moneda de cambio o como prueba de amor”
    Zuckerberg desvela cómo serán las gafas para entrar en el metaverso
    Por qué retuitear el vídeo sexual de Santi Millán también es delito: la desprotección de la intimidad en internet
    LaMDA, la máquina que “parecía un niño de siete años”: ¿puede un ordenador tener conciencia?
    La inteligencia artificial reconocerá el arte gracias a la ciencia ciudadana
    “Gano 1.500 euros al mes con los videojuegos”: así funciona el negocio de la compraventa de cuentas
    Cinco aplicaciones móviles, con aval científico, que salvan vidas o mejoran tu salud
    Cómo contarle tus ciclos menstruales a una app puede llevarte a la cárcel
    Bill Gates dice que las criptomonedas y los NFT están basados en encontrar a “alguien más tonto”
    El Princesa de Asturias de Investigación Científica distingue a cuatro expertos en sistemas que imitan al cerebro
    En defensa de la procrastinación. Elogio del tiempo perdido (frente al que las redes te roban)
    Instagram, el mejor de los mundos posibles
    Del terrorismo youtuber al influencer rabioso: el odio inunda la red
    Cronodiversidad. ¿Por qué el tiempo cada vez va más rápido?
    Herramientas que ayudan a crecer a las empresas (más allá de los pagos)
    La solución definitiva para vender más (y mejor) en la web
    La cámara de este ‘smartphone’ es pura magia
    Por qué todos hablan de este ‘smartphone’ de diseño atractivo y rendimiento prémium
    Un campus de programación para adquirir todas las habilidades ‘tech’
    Una catapulta para el talento de ‘kilómetro cero’
    La semana de la moda masculina de París apuesta por el cambio tranquilo
    Ramón Estévez lamenta llamarse Martin Sheen
    Piti Alonso: “Igual te organizo la alfombra roja de los Goya que la de la OTAN”
    Ana Rosa Quintana reaparece en un encuentro con sus compañeros de televisión
    Un libro y un documental revisitan la figura de George Michael: atracones de helado, culebrones, sexo y éxtasis
    Gracias, Locomía
    Las magnolias, grandes, blancas y fragantes, las flores que regala el verano
    María del Monte, en el pregón del Orgullo en Sevilla: “Jamás en mi vida me he escondido de nadie, ni lo voy a hacer por amor”
    De una pastelera de tartas en 3D a una creadora de café con huesos de dátil: estos son los próximos grandes talentos de la gastronomía global
    Denise Richards sigue los pasos de su hija y se crea una cuenta en OnlyFans
    Cuarto divorcio para Rupert Murdoch: el magnate y la modelo Jerry Hall se separan
    Sharon Stone: “Perdí nueve hijos por abortos espontáneos. Las mujeres no tenemos un espacio donde discutir la profundidad de estas pérdidas”
    De La Tasquería a El Lince, un homenaje a la casquería más popular con sorpresas
    Ha Ha Ha! La colección de Gucci que Harry Styles y Alessandro Michele han creado a partir de los memes que intercambiaban
    Nicky y Simone Zimmermann: “Nos dijeron que no nos dedicáramos a la moda y que no trabajáramos en familia. No les hicimos caso y nos fue bien”
    Viktor & Rolf, 30 años de moda y rebelión: “No puedes estar siempre arriba”
    Desembarco de celebridades internacionales en Sevilla para el desfile de Dior
    Kim Kardashian causó graves daños al histórico vestido de Marilyn Monroe que llevó en la gala del Met
    El publicista Miguel Olivares y la pasta del fin del mundo
    De La Tasquería a El Lince, un homenaje a la casquería más popular con sorpresas
    Al enemigo, ni ensaladilla: ¿qué comida es de izquierdas y cuál de derechas según las guerras culturales?
    La evolución de los modales al comer en la mesa
    24 series para este verano
    ¿Merece la pena ver ‘La casa de papel: Corea’? Diferencias y semejanzas con la serie original
    Pepón Nieto denuncia que TVE vetó una de sus películas en ‘Cine de barrio’ y la corporación recula: se emitirá este sábado
    El espíritu de Balbín está por todas partes
    Los Romanoffs
    Maria Ressa, la periodista filipina “no exenta de ser asesinada”
    ‘Supervivientes’ y la incultura general
    ‘La clave’ de Balbín, gloria y caída del programa que cambió la televisión española
    Un viaje en el tiempo con Kurt Vonnegut
    Muere José Luis Balbín, mítico presentador y creador del programa ‘La clave’
    El TSJ de Madrid declara nulo el despido del guionista de TVE que escribió el rótulo “Leonor se va de España, como su abuelo”
    ‘Legacy’: un Bosch sin placa y un poco perdido
    Claves de la nueva Ley General de Comunicación Audiovisual, más allá del enfado de los productores independientes
    ‘Sanditon’ resucita a Jane Austen
    Ciencia, tecnología y entrevistas en las novedades de la programación de verano en la Cadena SER
    Los abonados a las plataformas y televisiones de pago superan el número de hogares españoles 
    Mueren en un accidente de tráfico dos actores mexicanos durante el rodaje de la serie de Netflix ‘El Elegido’  
    ¿Qué ver hoy en TV? Domingo 26 de junio de 2022
    Nueve capítulos para recordar ‘The Wire’ en su 20º aniversario
    Harry Palmer: el tercer vértice del mágico triángulo de espías británicos
    Las series de junio de 2022: ‘The Boys’ en Amazon Prime Video; ‘Peaky Blinders’ en Netflix y otras
    La fuerza acompaña a ‘Obi-Wan Kenobi’, una serie deslumbrante
    Chanel, la vida después de Eurovisión: “No soy un títere”
    Farrell y McNamara: “Los edificios no son tan solo infraestructuras, representan sistemas de valores”
    La finca donde se resucita la tierra
    Acelerando la ciencia a 314.000 billones de operaciones por segundo
    Así fue nuestra experiencia de escribirnos con GPT-3, una máquina de inteligencia artificial
    El publicista Miguel Olivares y la pasta del fin del mundo
    Viaje al fin de Occidente, en la gran frontera entre Finlandia y Rusia
    Aprendizaje continuo para un mundo en cambio
    El piloto de ‘airbuses’ que se eleva componiendo pop barroco
    Siri, Alexa, Sophia: ¿por qué asistentes virtuales y humanoides tienen nombre de mujer?
    Inteligencia artificial ¿para qué?
    Voluntarios contra el abismo digital de los mayores
    Ir a un concierto o pintar nos repara emocionalmente
    Por qué ya no soy futbolero
    Ubicación exacta de la utopía
    Una pequeña historia
    Historia para los nietos
    Harina enriquecida para acabar con el “hambre oculta”
    Lugares de esperanza para salvar los océanos
    Los guardianes del clima que llevan medio siglo leyendo las advertencias de los glaciares
    Epidemia de violencia: claves del negocio de las armas en Estados Unidos
    Los ejecutivos voladores y la ética medioambiental
    Ibiza, entre la noche desenfrenada y el turismo tranquilo 
    Luz Casal: “Tengo el alma rockera. Nada ha doblegado mi rebeldía”
    Rashid Johnson: “Los pensadores y creadores negros estamos cansados de que nos nieguen un espacio autónomo”
    Sergio Hernández: “En el mundo, la gente ya no quiere verdades, quiere mentiras”
    Elvira Sastre: “No hay que perdonarlo todo”
    La trinidad del taco perfecto: “Buena tortilla, delicioso relleno y una salsa sabrosa”
    Bikôkô y Julio Peña, dos estrellas en ebullición  
    Cuando Chufy encontró a Rossy: dos amigas, una isla y una colección de moda
    La nueva edad de oro de la coctelería en Barcelona
    Riesgo, dolor y placer: cómo los humanos se aficionaron al picante 
    Ilusiones hipnóticas
    El poder del hormigón
    Maulévrier, Japón a la francesa
    ‘Fantasías en el Prado’, por Alberto García-Alix
    ¡‘Yee-haw’! Esto también es Brasil
    [1m[34mA continuación se muestran los titulares de las páginas principales del diario El País que contienen las siguientes palabras:[0m
    [1m[32mFeminismo[0m
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    [1m[32mIgualdad[0m
    La escuela concertada ante las desigualdades: el debate pendiente
    [1m[32mMujeres[0m
    Dos mujeres besándose, esa bomba
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    Un día muy triste para todas las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Sharon Stone: “Perdí nueve hijos por abortos espontáneos. Las mujeres no tenemos un espacio donde discutir la profundidad de estas pérdidas”
    [1m[32mMujer[0m
    Dos mujeres besándose, esa bomba
    Siri, Alexa, Sophia: ¿por qué las asistentes virtuales tienen nombre de mujer?
    Ellos no bailaron solos: la mujer detrás de la loca historia de Locomía
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    Un día muy triste para todas las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Sharon Stone: “Perdí nueve hijos por abortos espontáneos. Las mujeres no tenemos un espacio donde discutir la profundidad de estas pérdidas”
    Siri, Alexa, Sophia: ¿por qué asistentes virtuales y humanoides tienen nombre de mujer?
    [1m[32mBrecha salarial[0m
    
    [1m[32mMachismo[0m
    
    [1m[32mViolencia[0m
    Epidemia de violencia: claves del negocio de las armas en Estados Unidos
    [1m[32mMaltrato[0m
    
    [1m[32mHomicidio[0m
    
    [1m[32mGénero[0m
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    [1m[32mAsesinato[0m
    
    [1m[32mSexo[0m
    Atracones de helado, culebrones, sexo y éxtasis: un libro y un documental sobre George Michael
    El mejor sexo de tu vida
    Un libro y un documental revisitan la figura de George Michael: atracones de helado, culebrones, sexo y éxtasis
    

## Librerías y módulos

Vamos a usar los siguientes módulos y librerías:

### Módulos internos del sistema
- [time](https://docs.python.org/es/3/library/time.html), proporciona varias funciones relacionadas con el tiempo.
- [csv](https://docs.python.org/es/3/library/csv.html),  implementa clases para leer y escribir datos tabulares en formato CSV, es decir, valores separados por coma.
- [re](https://docs.python.org/es/3/library/re.html), proporciona operaciones de coincidencia de expresiones regulares similares a las encontradas en Perl.
- [os](https://docs.python.org/es/3.10/library/os.html), provee una manera versátil de usar funcionalidades dependientes del sistema operativo.
### Librerías externas
- [requests](https://requests.readthedocs.io/en/latest/), es una librería de Python para trabajar con `HTTP`.
- [bs4](https://www.crummy.com/software/BeautifulSoup/), facilita extraer información de páginas web.
- [pandas](https://pandas.pydata.org/), ofrece estructuras de datos y operaciones para manipular tablas numéricas y series de tiempo.
- [termcolor](https://pypi.org/project/termcolor/), permite imprimir textos coloreados.

### Instalamos librerías


```python
pip install requests bs4 pandas termcolor
```

    Requirement already satisfied: requests in c:\users\evole\anaconda3\lib\site-packages (2.27.1)
    Requirement already satisfied: bs4 in c:\users\evole\anaconda3\lib\site-packages (0.0.1)
    Requirement already satisfied: pandas in c:\users\evole\anaconda3\lib\site-packages (1.4.2)
    Requirement already satisfied: termcolor in c:\users\evole\anaconda3\lib\site-packages (1.1.0)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in c:\users\evole\anaconda3\lib\site-packages (from requests) (1.26.9)
    Requirement already satisfied: charset-normalizer~=2.0.0 in c:\users\evole\anaconda3\lib\site-packages (from requests) (2.0.4)
    Requirement already satisfied: idna<4,>=2.5 in c:\users\evole\anaconda3\lib\site-packages (from requests) (3.3)
    Requirement already satisfied: certifi>=2017.4.17 in c:\users\evole\anaconda3\lib\site-packages (from requests) (2021.10.8)
    Requirement already satisfied: beautifulsoup4 in c:\users\evole\anaconda3\lib\site-packages (from bs4) (4.11.1)
    Requirement already satisfied: python-dateutil>=2.8.1 in c:\users\evole\anaconda3\lib\site-packages (from pandas) (2.8.2)
    Requirement already satisfied: pytz>=2020.1 in c:\users\evole\anaconda3\lib\site-packages (from pandas) (2021.3)
    Requirement already satisfied: numpy>=1.18.5 in c:\users\evole\anaconda3\lib\site-packages (from pandas) (1.21.5)
    Requirement already satisfied: six>=1.5 in c:\users\evole\anaconda3\lib\site-packages (from python-dateutil>=2.8.1->pandas) (1.16.0)
    Requirement already satisfied: soupsieve>1.2 in c:\users\evole\anaconda3\lib\site-packages (from beautifulsoup4->bs4) (2.3.1)
    Note: you may need to restart the kernel to use updated packages.
    

### Importados librerías

Existen libreríass que las importamos tal cual, como en el caso de `requests`; otras que se importan cambiándoles el nombre que se utilizará para invocarlas, como en el caso de `pandas` y otras de las cuales importamos algunos componentes, como es el caso de `bs4`:


```python
import requests
import time
import csv
import re
from bs4 import BeautifulSoup
import os
import pandas as pd
from termcolor import colored
```

## Objetos/variables

Vamos a crear una serie de objetos o variables:


```python
resultados = []
```

Si le paso la función type() veremos que se trata de un objeto tipo list o "lista" de Python. Como vimos el otro día con la demostración de Doug Enfelbart, la lista es un elemento de organizaa información/datos básicos y fundemental.


```python
type(resultados)
```




    list



### Acceso a datos 

Se realiza una solicitud `req = requests.get("https://resultados.elpais.com")` para recoger la información de la URL.


```python
req = requests.get("https://resultados.elpais.com")
```

Se empleó la condicional if para que, cuando el status no sea 200 el valor de vuelta no pueda leerse. Este 200 es sinónimo de que el requerimiento fue exitoso y el rervidor respondió con la información solicitada.


```python
# Si el estatus no es 200 no se puede leer la página
if (req.status_code != 200):
    raise Exception("No se puede hacer Web Scraping en"+ URL)
```


```python
En el código se añadió una variable para buscar las etiquetas `<h2>`, las cuales significan título, dentro de la página.
```


      Input In [9]
        En el código se añadió una variable para buscar las etiquetas `<h2>`, las cuales significan título, dentro de la página.
           ^
    SyntaxError: invalid syntax
    



```python
tags = soup.findAll("h2")
```

Se le indicó, a través de un `for`, que imprima el texto que esta dentro de la etiqueta `<h2>`.


```python
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    América Latina gira hacia una nueva izquierda
    Un multiciclo de protestas como catalizador 
    El mundo se hunde en una espiral conflictiva. Este es el balance de fuerzas
    El castellano es el fracaso 
    Abortar es un derecho: así hay que decirlo
    Dos mujeres besándose, esa bomba
    Parole, parole, parole…
    Timbiquí, el pueblo colombiano donde el 99% votó a Petro
    El estratega tranquilo que aupó a Petro al poder
    Petro exhibe su tono más conciliador en sus primeros movimientos
    Francia Márquez no rompe techos de cristal
    Colombia y la nueva izquierda latinoamericana
    El desplome de una tribuna de una plaza de toros en Colombia deja al menos cuatro muertos y decenas de heridos
    Los piratas acechan las embarcaciones de la petrolera estatal mexicana Pemex
    El acoso a la clínica de Misisipi que detonó la sentencia contra el aborto: “Los que matan bebés merecen morir”
    El aborto entra de lleno en la campaña electoral de las legislativas de Estados Unidos
    Las protestas pierden músculo en Ecuador desplazadas por la propuesta de destitución de Lasso
    El Gobierno de Boric se enreda con la figura de la primera dama
    Imágenes sexuales que destruyen y matan
    Ramón Estévez lamenta llamarse Martin Sheen
    Marruecos se apresura a enterrar a los migrantes del asalto a la valla entre críticas
    Petro Poroshenko, expresidente de Ucrania: “Es imposible lograr un acuerdo. Putin quiere matarnos” 
    La vida sin descanso de Nelsi Ayala: limpiar casas 12 horas al día para ganar 1.200 euros
    Orgullo y poderío de la diversidad sexual: el gran negocio de cuatro billones de dólares
    Noruega homenajea a las víctimas del ataque en la puerta de un bar gay de Oslo: “Esta lucha no ha acabado”
    ¿Merece la pena ver ‘La casa de papel: Corea’? Diferencias y semejanzas con la serie original
    Paul McCartney celebra sus 80 años con casi tres horas de concierto en Glastonbury
    Atracones de helado, culebrones, sexo y éxtasis: un libro y un documental sobre George Michael
    La semana de la moda masculina de París apuesta por el cambio tranquilo
    De París y Río de Janeiro a un pueblo de dos habitantes en Soria: la escritora que se lanzó a la literatura a los 73 años
    Del aplauso no se come: los problemas de los creadores para llegar a fin de mes
    Toreros, trenes voladores y ovaciones a Franco: las películas inéditas del ingeniero José Hernández
    Siri, Alexa, Sophia: ¿por qué las asistentes virtuales tienen nombre de mujer?
    Pío XII, un papa entre la santidad y Hitler
    24 series para este verano
    Tres años después, Nadal contra la amnesia
    Gareth Bale se va a EE UU a jugar en el equipo de Magic Johnson
    Los días de vino y rosas del ‘calciomercato’, el mercado de fichajes italiano
    Ledecky se convierte en la primera nadadora en ganar cinco mundiales seguidos
    Dentro o fuera de la metrópolis: ¿es posible un dinamismo artístico sin estar en las grandes ciudades?
    Repensar la función y el futuro del arte contemporáneo
    24 horas de plomo en la sierra Tarahumara de México
    Gustavo Petro: la victoria final
    Así fue el rescate de la nadadora Anita Álvarez
    El mejor sexo de tu vida
    US Supreme Court overturns ‘Roe v Wade,’ ending federal abortion rights
    How tracking your menstrual cycles on an app can land you in jail 
    Aspirin for cancer and thalidomide for leprosy: new life for old drugs
    The salad days of the culture war: Which foods are leftist and which are right-wing?
    Brad Pitt believes that the end of his career is near: ‘I consider myself on my last leg’
    Going to a concert or painting helps us with emotional recovery
    Letras Americanas: la actualidad literaria de un continente vista por el escritor Emiliano Monge
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Toda la actualidad científica en el boletín de Materia
    Ideas: reportajes y entrevistas para entender el mundo
    Trump trató de poner un títere al frente del Departamento de Justicia para que impugnara el triunfo de Biden
    La candidatura de Ucrania espolea la impaciencia de los Balcanes para ingresar en la UE 
    Le Pen pide a sus nuevos diputados menos ruido y vestir corbata en la Asamblea Nacional de Francia
    Los bancos centrales avisan del peligro de estanflación pero ven “improbable” una crisis como la de los setenta
    Latinoamérica muestra su músculo ante el inicio del alza en las tasas de interés
    La inflación en Canadá rompe todos los récords en casi 40 años 
    Un día para existir en las calles de Ciudad de México
    Por qué estamos cada vez más deprimidos
    Una mañana de luz blanca: relato de un médico tras su primera eutanasia
    Así suena ‘Break My Soul’, lo nuevo de Beyoncé 
    Michael J. Fox, Diane Warren, Peter Weir y Euzhan Palcy recibirán los Oscar honoríficos
    María Pagés: “A los lugares cercanos se va a seguir yendo, pero a los lejanos… quién va a poder comprar los billetes”
    Las personas que comparten el mismo olor tienen más probabilidades de forjar una amistad
    Se llama Lucas, pero yo ya le llamo Diazepam: así me ha sobrepasado que mi perro tenga ansiedad por separación
    ASMR: ¿Ciencia, sentimiento o efecto placebo?
    De ultra a presidente del Hertha de Berlín
    Gareth Bale se va a EE UU a jugar en el equipo de Magic Johnson
    Eugenio López Chacarra, del golf amateur a millonario fichaje saudí
    La inacción ante la pérdida de arena condena a las playas de Barcelona
    La trampa mortal del trasvase Tajo-Segura: así se ahogan corzos y jabalíes en el canal 
    Dos veranos sin playa, cerrada por contaminación: “Si esto fuera Barcelona, se arreglaba en dos días”
    Acelerando la ciencia a 314.000 billones de operaciones por segundo
    Inteligencia artificial ¿para qué?
    Christopher Mims: “Amazon sabe cómo bajar el ritmo de trabajo para prevenir lesiones. Pero quizá dejaría de ganar dinero” 
    Un bombero gana un primer juicio al Ayuntamiento de Madrid: no se puede estar 24 horas activable sin cobrar las horas extra
    Unidas Podemos acentúa su discurso contra la OTAN a pocos días de la cumbre en Madrid 
    Cientos de militares se manifiestan en Madrid a cuatro días de la cumbre de la OTAN 
    El espíritu de Balbín está por todas partes
    ¿Merece la pena ver ‘La casa de papel: Corea’? Diferencias y semejanzas con la serie original
    Los Romanoffs
    Los problemas crecen para los Bieber: Hailey, demandada por la marca de cosmética que lanzó hace una semana
    Guillermo de Inglaterra cumple 40 años como el candidato ideal para seguir la estela de Isabel II
    Los 40 años de Guillermo de Inglaterra en 16 fotos
    Volver a la escuela tras dos años de pandemia
    La discriminación contra las minorías sexuales limita el desarrollo de Latinoamérica
    Zombis de ‘apps’, mercenarios del ‘streaming’, hermanos de contraseña: la rebelión de los usuarios
    'Historia para los nietos', por Javier Marías 
    Guy Standing: “Hemos dejado que la derecha se apropie de la libertad”
    Así era América antes de que Colón la descubriera
    Ya no se viaja igual que antes de la pandemia: estas son las nuevas modas del turismo 
    El salto mortal de Estrella Galicia 
    LaMDA, Google y cuando jugar con una inteligencia artificial es posible
    En los sesenta, todo se vendía con fotos
    Historias de superación en un centro de formación de adultos en Ceuta
    La paz global vive su peor momento de los últimos 15 años
    Los 10 cráteres más impactantes del mundo causados por meteoritos, en imágenes
    Restaurante Voro, un dos estrellas Michelin con auténtico ‘finger food’ en Mallorca
    «María del Monte y su estilista contactaron conmigo por TikTok y me preguntaron por mis mantones»
    Ellos no bailaron solos: la mujer detrás de la loca historia de Locomía
    Eugenia Silva: “No he vivido situaciones extremas. Sabía qué quería y hasta dónde llegar”
    Las frustraciones de Wes Craven, el genio del terror que quería dirigir melodramas
    Rebelión en el bar: los restaurantes que pasan de estar siempre abiertos
    Menú semanal de El Comidista (27 de junio a 3 de julio)
    Marea alta de dividendos: 6.000 millones de euros este verano
    Fernando Tejero revela cómo Dani Martín le sacó de una pensión decadente tras llegar a Madrid para llevarle a vivir a casa de sus padres
    Ponte a prueba con nuestros crucigramas, sopas de letras, sudokus y juegos arcade
    Un histórico corresponsal de TVE saca los colores a Ayuso tras leer su última entrevista
    ‘El gesto más atlético de Luis’: episodio final ya disponible
    Hidrógeno verde, la coincidencia más feliz de Mallorca
    

El procedimiento que se acaba de ejecutar se repite para las mismas URL de las secciones del diario español [*El País*](https://elpais.com) como Opinión, Internacional, Economía, España, Sociedad, Clima y Medio Ambiente, Ciencia, Educación, Cultura, Deportes, Tecnología, Babelia, Gente, Televisión y Eps. 

Para lograrlo, se realiza lo mismo, pero se cambian los nombres de las variables con números.


```python
req2 = requests.get("https://elpais.com/internacional")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup2 = BeautifulSoup(req2.text, 'html.parser')

tags = soup2.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req3 = requests.get("https://elpais.com/opinion")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup3 = BeautifulSoup(req3.text, 'html.parser')

tags = soup3.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req4 = requests.get("https://elpais.com/espana/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup4 = BeautifulSoup(req4.text, 'html.parser')

tags = soup4.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req5 = requests.get("https://elpais.com/economia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup5 = BeautifulSoup(req5.text, 'html.parser')

tags = soup5.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req6 = requests.get("https://elpais.com/sociedad/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup6 = BeautifulSoup(req6.text, 'html.parser')

tags = soup6.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req7 = requests.get("https://elpais.com/educacion/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup7 = BeautifulSoup(req7.text, 'html.parser')

tags = soup7.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req8 = requests.get("https://elpais.com/clima-y-medio-ambiente/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup8 = BeautifulSoup(req8.text, 'html.parser')

tags = soup8.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req9 = requests.get("https://elpais.com/ciencia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup9 = BeautifulSoup(req9.text, 'html.parser')

tags = soup9.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req10 = requests.get("https://elpais.com/cultura/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup10 = BeautifulSoup(req10.text, 'html.parser')

tags = soup10.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req11 = requests.get("https://elpais.com/babelia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup11 = BeautifulSoup(req11.text, 'html.parser')

tags = soup11.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req12 = requests.get("https://elpais.com/deportes/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup12 = BeautifulSoup(req12.text, 'html.parser')

tags = soup12.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req13 = requests.get("https://elpais.com/tecnologia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup13 = BeautifulSoup(req13.text, 'html.parser')

tags = soup13.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req14 = requests.get("https://elpais.com/tecnologia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup14 = BeautifulSoup(req14.text, 'html.parser')

tags = soup14.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req15 = requests.get("https://elpais.com/gente/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup15 = BeautifulSoup(req15.text, 'html.parser')

tags = soup15.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req16 = requests.get("https://elpais.com/television/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup16 = BeautifulSoup(req16.text, 'html.parser')

tags = soup16.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

req17 = requests.get("https://elpais.com/eps/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup17 = BeautifulSoup(req17.text, 'html.parser')

tags = soup17.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    La OTAN decidirá en Madrid el mayor despliegue militar desde la Guerra Fría
    El G-7 estudia nuevos mecanismos para asfixiar la economía de Rusia
    El mundo se hunde en una espiral conflictiva. Este es el balance de fuerzas
    Putin teme a la UE más que a la OTAN
    Exiliados rusos
    Cambio en Colombia
    Las elecciones reparlamentarizan Francia
    Emmanuel Macron pierde las legislativas en Francia 
    La influencia de China preocupa al G-7
    Carlos de Inglaterra recibió en mano más de tres millones de euros de un jeque catarí 
    Noruega homenajea a las víctimas del ataque en la puerta de un bar gay de Oslo: “Esta lucha no ha acabado”
    La policía sudafricana investiga la muerte de al menos 21 personas en una discoteca en el sur del país
    José Manuel Albares, ministro de Exteriores: “Las mayores amenazas para la seguridad de los españoles vienen ahora del Este”
    Le Pen pide a sus nuevos diputados menos ruido y vestir corbata en la Asamblea Nacional de Francia
    El “verano del descontento” inglés que Europa mira de reojo
    Petro Poroshenko, expresidente de Ucrania: “Es imposible lograr un acuerdo. Putin quiere matarnos” 
    Jens Stoltenberg, líder de la OTAN: “Dar la paz por descontada en Europa puede terminar en una guerra”  
    Más de 4.000 soldados, 21 cazas y toneladas de artillería plantan cara a la amenaza rusa en los países bálticos
    Bolsonaro logra que Portugal le preste el corazón del emperador que independizó Brasil en 1822
    Trump trató de poner un títere al frente del Departamento de Justicia para que impugnara el triunfo de Biden
    El Supremo de Estados Unidos consagra el derecho a llevar armas en público
    La ayuda estatal a los más pobres en Argentina profundiza la disputa por el poder en la Casa Rosada
    Demócratas y republicanos alcanzan el primer acuerdo en décadas para el control de armas en Estados Unidos
    La Corte Suprema argentina deja libre el camino para juzgar a Cristina Kirchner en una causa por corrupción
    Nuevo paquete anticrisis
    La guerra de Putin es imprevisible
    El castellano es el fracaso 
    Parole, parole, parole…
    Vidas gitanas
    El leninismo reaccionario ha ganado
    Cierra las piernas, niña
    El aborto y la guerra fría
    Si la OTAN no existiera 
    América Latina, ‘quo vadis?’
    Perder el sentido de la oportunidad
    Boca abierta
    Aborto en EE UU: medio siglo hacia atrás
    El Roto
    Peridis
    Flavita Banana
    Riki Blanco
    Sciammarella
    Planeta de Plástico, por Malagón
    Envía tu carta
    Réquiem por la sierra de la Culebra  
    Harta de los negacionistas
    Desmantelando la sanidad, que es gerundio
    Opinar sin insultar
    Contra el conflicto de intereses, transparencia
    Entre los derechos de Esther López y los de los lectores
    El defensor del lector contesta
    Marruecos se apresura a enterrar a los migrantes del asalto a la valla entre críticas por la posible ocultación de las causas de la muerte
    Miles de personas salen a la calle en Madrid para protestar contra la OTAN a pocos días del arranque de la cumbre  
    Sánchez anuncia una ayuda de 200 euros para trabajadores y parados con bajos ingresos y una subida del 15 % de las pensiones no contributivas 
    La búsqueda de seguridad vence al cabreo
    Los errores se pagan
    Desborde popular en Andalucía
    Demasiado ruido en el Gobierno de coalición
    La ‘confederalización’ del PP
    Sánchez: “Este es un Gobierno incómodo para algunos sectores económicos. Pero no nos quebrarán”
    Las 100 horas que quemaron el corazón de la sierra de la Culebra
    El bipartidismo retorna en versión corregida
    ¿Y si hubiese elecciones generales? Un repaso a las encuestas después de Andalucía
    Tres flancos de presión forzaron el adiós de Mónica Oltra
    Los testigos del asalto a la valla de Melilla: “Todo era sangre, piel desgarrada, pies rotos, manos rotas…”
    Relato de uno de los migrantes que intentó entrar en Melilla: “La policía marroquí estaba muy violenta y ellos débiles y hambrientos”
    La tragedia bajo la valla de Melilla que nadie pudo tapar en Marruecos
    Los otros saltos masivos y mortales a la valla
    Unidas Podemos acentúa su discurso contra la OTAN a pocos días de la cumbre en Madrid 
    Cientos de militares se manifiestan en Madrid a cuatro días de la cumbre de la OTAN 
    Un paraíso en el que avistar más de 20 especies de cetáceos
    El secreto de Fuerteventura se hace viral: la ‘playa de las palomitas’
    Artesanía y cultura que conquista a las ‘influencers’
    Más allá de la capital. El triunfo de la vida rural madrileña
    Así lucha la tierra del cerezo para conseguir un nuevo florecimiento económico
    “Siempre me ha parecido que los que iban disfrazados eran los demás”
    “La herramienta más poderosa para salvar a la humanidad son las matemáticas”
    Los bancos centrales avisan del peligro de estanflación pero ven “improbable” una crisis como la de los setenta
    Medio centenar de vuelos cancelados en la tercera jornada de huelga en Ryanair
    La vida sin descanso de Nelsi Ayala: limpiar casas 12 horas al día para ganar 1.200 euros
    Marc Murtra: “Ni hay interferencias, ni habrá injerencias mientras sea presidente de Indra”
    La fina línea entre inflación y recesión
    Una espiral maldita llamada inflación 
    Lecciones posteriores al Brexit para España
    Crisis energética y precios del carbono
    La cuesta abajo de Netflix despierta a los tiburones (pero por desgracia no está en venta)
    El corte de gas ruso aboca a Europa al carbón
    Las energéticas francesas llaman a hogares y empresas a reducir su consumo “de inmediato”
    Orgullo y poderío de la diversidad sexual: el gran negocio de cuatro billones de dólares
    El G-7 estudia nuevos mecanismos para asfixiar la economía de Rusia
    Francisco Cuadrado: “Santillana ya no es una empresa de contenidos, da soluciones integrales a las escuelas”
    75 vuelos cancelados en la segunda jornada de huelga de los tripulantes de Ryanair
    Por qué el mejor inversor del mundo se rinde al petróleo
    La cuesta abajo de Netflix despierta a los tiburones (pero por desgracia no está en venta)
    LaLiga tiene un plan para conquistar América
    Daniel Sillman (Relevent): “El fútbol tiene oportunidades de negocio aún por explotar”
    Estas son las nuevas medidas acordadas por el Gobierno en el decreto anticrisis
    Ferrari corre hacia un mundo más verde y caro
    Vientres de alquiler: una boyante y turbia industria que aprovecha las rendijas legales para enriquecerse
    Ya no se viaja igual que antes de la pandemia: estas son las nuevas modas del turismo 
    El salto mortal de Estrella Galicia 
    No me gustan las cuotas
    Las rentas más bajas soportan una presión fiscal similar a la del 1% más rico
    La CNMV quiere que los inversores institucionales se impliquen a largo plazo en las cotizadas
    Las hipotecas a tipo fijo superan el 75% en abril y marcan un nuevo récord en plena escalada del euríbor
    Por qué el bitcóin ha caído un 70% desde máximos y por qué puede seguir a la baja
    Líos en la piscina comunitaria: normas y sentencias para un chapuzón seguro
    Parir en casa, educarlo por mi cuenta… ¿Qué puedo decidir sobre mi hijo y qué no?
    Saltarse un paso a nivel de camino a la oficina es accidente laboral
    Francisco Javier Blasco: “Llevamos años sin mejorar la eficacia de las políticas activas de empleo”
    ¿Es esta la edad dorada del emprendimiento universitario?
    Y después de la EBAU, ¿qué?
    Cancerberos del bienestar de la empresa
    Salud a golpe de clic con la cercanía del médico de cabecera
    Cómo garantizar la seguridad en un mundo de amenazas híbridas
    ¿Cuáles son los dilemas éticos del uso de la inteligencia artificial?
    Las aventuras de un par de calcetines que dan empleo a todo un pueblo
    Cultura financiera como punto de partida para volver a empezar
    Por qué digitalizar una pyme aporta más empleo
    Logística a bajas temperaturas, la revolución que vino del frío
    ‘Coopetir’: la actitud DFactory
    Así serán las ciudades de la (nueva) última milla
    PERTE Agroalimentario: ¿cómo acceder a los fondos europeos?
    Claves para internacionalizar mi negocio
    ¿Crisis de deuda mundial a la vista?
    ¿Está al frente España de la revolución del hidrógeno? 
    El momento de la energía solar
    Las principales reformas (con subvención europea) para ahorrar energía en la vivienda
    Gloria Ramos, cuando el afán de superación acaba en la alfombra roja 
    La importancia de la cultura financiera para tener una buena jubilación
    Hotmart y su plataforma 360 para creadores de contenidos
    Una aplicación para presentar la declaración desde casa y conseguir los máximos beneficios
    Miles de personas se manifiestan en Madrid contra el aborto: “La sentencia del Supremo en EE UU da esperanza”
    No se gobierna con el catecismo romano
    La ‘América pos Roe’: cómo la sentencia sobre el aborto agrava la polarización de Estados Unidos
    No se gobierna con el catecismo romano
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    El intento de suicidio de Juan y las somatizaciones de Carmen: ¿por qué los colegios necesitan un psicólogo educativo?
    El acoso a la clínica de Misisipi que detonó la sentencia contra el aborto: “Los que matan bebés merecen morir”
    Abortar es un derecho: así hay que decirlo
    El movimiento en defensa del derecho al aborto toma las calles de EE UU tras la decisión del Supremo
    El aborto en EE UU tras la decisión del Supremo: las claves
    El Tribunal Supremo deroga el derecho al aborto en Estados Unidos
    Un día muy triste para todas las mujeres
    Primero de carrera: los bachilleres de la escuela pública son los que más materias aprueban 
    El origen de la hepatitis aguda infantil es todavía un misterio después de 894 casos, decenas de trasplantes y 18 muertes
    La Iglesia insiste en que no abrirá sus archivos al Defensor, aunque cederá datos de casos concretos que le solicite
    El nuevo sistema para evaluar los conocimientos digitales de los profesores valdrá en toda España
    La OMS resuelve que de momento la viruela del mono no es una emergencia sanitaria internacional
    Mitos, falsedades, bulos y realidades sobre el VIH 40 años después
    Educadores con VIH para minimizar el impacto tras el primer diagnóstico
    El tremendo peso de la obesidad en España
    Interactivo | Los 14 cambios en los aeropuertos españoles que no ves y que ya están ocurriendo
    Encontrar empleo pese a los obstáculos. Por dónde empezar la búsqueda
    La fórmula de Carboneros para evitar el éxodo rural: trabajar cuidando a los vecinos 
    Consejos y cuidados para el primer verano con un gatito o un perrito
    ¿Qué tienen en común perros y gatos cuando son cachorros?
    La guía definitiva para alimentarnos mejor (y cuidar nuestra salud y la del planeta)
    Más vida después del cáncer de próstata avanzado 
    Cáncer de ovario, el más rebelde de los tumores ginecológicos
    El metro como refugio. De los andenes de Madrid en 1936 a los de Kiev en 2022
    La salud mental de los refugiados: cómo abrirse para cerrar las heridas
    El desconocido (y esencial) apoyo de los farmacéuticos a los pacientes crónicos
    El esfuerzo de una paciente por convertirse en su doctora
    Así es la vida de los refugiados ucranianos en España
    ¿Cómo será el envase para alimentos y bebidas del futuro?
    Primero de carrera: los bachilleres de la escuela pública son los que más materias aprueban 
    Universidad en reconstrucción 
    Volver a la escuela en América Latina tras dos años de pandemia
    El intento de suicidio de Juan y las somatizaciones de Carmen: ¿por qué los colegios necesitan un psicólogo educativo?
    El nuevo sistema para evaluar los conocimientos digitales de los profesores valdrá en toda España
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Solo un 3% de alumnos de Cataluña pidió hacer el examen de Selectividad en castellano
    Subirats reinterpreta la ley de Universidades: freno a la precariedad, facilidades para los alumnos extranjeros y ciencia abierta
    “Los profesores no van a cambiar de golpe su forma de trabajar el curso que viene por la nueva ley educativa”
    Trampantojo de pescado y lasaña vegetal en el comedor: cientos de colegios buscan fórmulas para que llevar la alimentación responsable a los niños
    Vídeo | Las recetas del cocinero escolar para que los niños de El Grau coman sano y rico 
    Sin currículos
    La escuela concertada ante las desigualdades: el debate pendiente
    La equidad frente a las políticas educativas de privatización en Andalucía
    No hay lunes al sol en la Universidad
    Ofrecer comedor gratis en todos los colegios públicos es “alcanzable y urgente”: costaría 1.664 millones al año, según la ONG Educo  
    Una fórmula para que la escuela pública compita mejor con la concertada
    La pérdida de alumnos por el descenso de la natalidad está afectando con más fuerza a la escuela pública que a la concertada
    El Ayuntamiento de Madrid guarda en un cajón una herramienta ya pagada para ver los datos de contaminación al detalle 
    La implantación del nuevo Bachillerato general fracasa pese a su demanda potencial: “Creímos que lo pedirían seis alumnos y lo han hecho 27”
    Toni Solano, director de instituto: “Veo mal a los niños, necesitan muchísima ayuda”
    Niños, Administraciones y redes sociales: prohibir su uso con una mano y enseñar a crear contenidos con la otra
    El Gobierno aprueba el decreto de bachillerato: los alumnos podrán terminar con un suspenso y desembocará en una nueva Selectividad
    La ley del silencio dentro y fuera del aula
    Las universitarias desertan del grado de Matemáticas ahora que tiene pleno empleo. ¿Por qué?
    Golpe a la temporalidad en las universidades: 25.000 profesores asociados serán indefinidos a tiempo parcial
    Antonio Abril: “Yo le decía a Castells: ‘Tienes que aguantar la presión, tienes que hacer la reforma universitaria”
    Los universitarios extranjeros podrán quedarse un año en España automáticamente al terminar la carrera
    Sierra de la Culebra: un incendio gigantesco que no pone en peligro a los lobos, pero sí un modelo de convivencia ejemplar
    La indignación crece sobre las ascuas del incendio en la sierra de la Culebra
    Jardines en los tejados, árboles africanos y calles pintadas de blanco: cómo adaptar la ciudad al calor extremo
    La construcción de 52 viviendas en una playa de Begur desata la indignación de las redes
    Un continente mortal para los defensores de la tierra
    Drama en la sierra de la Culebra, el paraíso del lobo ibérico que quedó abrasado por un rayo
    Alemania anuncia que recurrirá al carbón ante el recorte de suministro de gas ruso
    La inacción frente al cambio climático hará que sea habitual superar los 40 grados en junio en España
    Ibrahim Thiaw: “Hay que prepararse mejor frente a las sequías, los agricultores franceses están cultivando ya cereales africanos”
    La ola de calor provoca la caída de cientos de crías de vencejo en las calles de Sevilla y Córdoba
    “En Singapur ya se vende carne cultivada para alimentación” 
    La lección del martín pescador para afrontar la crisis ecológica
    Estocolmo+50: mirar atrás para tomar impulso
    El verano ya no es lo que era 
    Juan Serna, Premio Nacional de Medio Ambiente: un reconocimiento merecido
    Ríos imposibles: las 171.000 barreras que rompen el curso de agua en España
    La UE abraza las renovables para romper la dependencia de Rusia
    La lucha en un pueblo de Teruel para salvar su última montaña
    ¿Qué aire respiran los niños de Madrid y Barcelona? En el 46% de los colegios se supera la contaminación permitida
    Toreros, trenes voladores y ovaciones a Franco: las películas inéditas del ingeniero José Hernández Santorcuato
    Las personas que comparten el mismo olor tienen más probabilidades de forjar una amistad
    Así se puede ver la alineación de cinco planetas a simple vista, justo antes de cada amanecer
    Las vacunas contra el coronavirus salvaron 20 millones de vidas en su primer año
    Seis jóvenes científicos que han impulsado avances en la investigación matemática de vanguardia obtienen los Premios Vicent Caselles
    Así se puede ver la alineación de cinco planetas a simple vista, justo antes de cada amanecer 
    Fracciones egipcias
    El Congreso aprueba la reforma de la ley de la ciencia sin votos en contra
    Matemáticas para describir los remolinos, los taxis del océano
    Las incógnitas de la pastilla milagrosa contra un tipo de calvicie
    ¿Se puede dejar de roncar?
    El síndrome del hombre lobo y la realidad lógica de su fábula
    Muere Yves Coppens, uno de los descubridores del fósil más famoso del mundo 
    Ni patentes, ni firmar estudios: las científicas reciben mucho menos reconocimiento por su trabajo
    La metástasis del cáncer avanza durante el sueño
    A la caza de exolunas, la próxima frontera de exploración planetaria
    A la caza de exolunas, la próxima frontera de exploración planetaria
    Matemáticas para describir los remolinos, los taxis del océano
    Reaparece la tesis de María Wonenburger, la pionera matemática española que permaneció décadas en el olvido
    Técnicas criptográficas que se fundamentan en lo impredecible
    Las matemáticas de los juegos malabares
    El problema del huerto
    Números McNugget
    La moneda de Frobenius
    El síndrome del hombre lobo y la realidad lógica de su fábula
    La locura como juego; más allá del Quijote y de las novelas de Pérez Galdós
    El andar del borracho, las huellas del azar y el juego de dados en algunos libros malditos
    El campo vibratorio y las fronteras de la ciencia desde un punto de vista científico
    Paul Auster fluctuando entre el pudin de pasas y la nube de mosquitos
    ¿Son mejores las hormonas bioidénticas?
    ¿Qué surgió antes, el ARN o el ADN?
    ¿Por qué se sabe que los núcleos de la Tierra rotan?
    ¿Qué son los mini reactores nucleares?
    Invitados indeseables por Navidad: el muérdago y otras plagas que evitar durante las fiestas
    Las ‘apps’ nutricionales o cómo comer bien no debería depender de uno mismo
    Malnutrición invisible: el impacto de la pobreza en la salud infantil
    El óxido de etileno, la sustancia cancerígena que ha obligado a retirar miles de alimentos en la UE
    Que no te líen con los ingredientes: aceites y grasas de mala calidad nutricional
    Pío XII, un papa entre la santidad y Hitler
    Tom Jones, incólume al paso del tiempo con 82 años, enardece en los jardines de Pedralbes de Barcelona
    Del aplauso no se come: los problemas de los creadores para llegar a fin de mes
    Aventuras en el desierto con la daga y el escorpión
    “¿Cómo lo haría Tony?”
    La casa de Ana Frank: memoria del Holocausto, entre el comercio y la apropiación personal
    El libro que explica qué significa ‘votar normal’
    Paul McCartney celebra sus 80 años con casi tres horas de concierto en Glastonbury
    De París y Río de Janeiro a un pueblo de dos habitantes en Soria: la escritora que se lanzó a la literatura a los 73 años
    Christina Aguilera hace explosionar con pop carnal el Mallorca Live Festival
    La semana de los “segundones”: nueva entrega de las crónicas de Emmanuel Carrère desde el juicio por los atentados de París
    Los frescos de Goya en Madrid están en riesgo por el mal estado del tejado de la iglesia que los alberga 
    El mercado del arte mide sus fuerzas en la Feria de Maastricht 
    Joaquín Sorolla y Esteban Vicente: cómo convertir la pasión por los jardines en luz para su arte
    Vetusta Morla se agiganta en el Wanda  sin despegar los pies de la tierra 
    Guillermo Aguirre: “No hay nada más peligroso que meter a un adolescente en un sitio en el que no quiere estar”
    Nadie quiere el cuadro de Goya
    El Museo de Teruel afirma que el Torico actual es el mismo que había antes de la Guerra Civil, que ya no era de bronce  
    Juan Muñoz se descubre más allá de sus esculturas
    El cine quiere ser verde desde la alfombra roja a la basura de una sala
    El último atardecer de Europa se ve solo desde este lugar. Un viaje hacia el infinito por el Camino de Fisterra-Muxía
    Un paseo fluvial con museos y otro lleno de piscinas termales. Las sorpresas de la Vía de la Plata
    Lorca, en la ciudad al margen
    El Pirineo oscense, para entrar a vivir
    Toda la lectura del verano, en el bolsillo
    Harry Potter cumple 25 años: libros para revivir la magia de Hogwarts
    Los mejores libros recientes para reír a carcajadas
    Disfruta del Festival de Teatro Clásico de Mérida
    'Territorios de vanguardia' en el Museo Reina Sofía
    Últimas funciones de 'We Will Rock You'
    Nueva edición de Cibeles de cine 
    Una de Miura sin opciones
    Manzanares salva la tarde de San Juan
    La fiesta de los toros, una emocionante y apasionada polémica desde el siglo XIII
    La apabullante autoridad de Roca Rey
    Cada testimonio es único: se acaba el tiempo de los supervivientes del Holocausto
    Un Houellebecq sentimental, la fiesta de la imaginación de Garriga Vela y otros libros de la semana
    Los cajones de sastre de Néstor Sanmiguel Diest
    CaixaForum València: un paisaje no es un edificio
    Moderat: “El tecno es mala hierba, nunca morirá”
    Poyo Rojo, la sensación argentina de la danza teatro 
    Las Huecas, teatro alternativo de verdad
    Trampantojo: Batallas culturales
    ‘Aniquilación’, de Michel Houellebecq: confusión en el campo de batalla
    LaMDA, Google y cuando jugar con una inteligencia artificial es posible
    En los sesenta, todo se vendía con fotos
    Otros turismos (lejos y aquí cerca)
    Volver al cine
    Sin autor, da lo mismo
    Alex sin Ada
    ‘Horas muertas’, en un Dublín hipnótico
    ‘Prometeo’, trío de ases
    ‘La memoria del alambre’, ese algo misterioso que daba miedo
    ‘Tarradellas. Una cierta idea de Cataluña’: manual de resistencia
    Manuel Estrada: “Me agrada que me digan que gusta más la portada que el libro”
    Óscar Esquivias: “No hace falta ser creyente para leer la Biblia”
    Amelia Castilla: “Los ritos nos ayudan a hacer viable el trance de la muerte”
    Shuarma: “Me gusta de la poesía el silencio que encierra”
    Eva Orúe: “Haría cola por la firma de Margaret Atwood”
    Lanzado hacia los 18m, cada salto de Jordan Díaz es un récord, o casi
    Fernando Carro, del cielo al infierno, y regreso
    Italia, el modelo de natación que España no sabe imitar 
    El doble regalo del deporte a Girona
    Aquel homenaje a Zico
    El silencio en los fichajes
    El ‘Cuerdo’ Bielsa
    Bagnaia aprovecha el lío entre Quartararo y Espargaró para ganar el Gran Premio de los Países Bajos de Moto GP  
    De ultra a presidente del Hertha de Berlín
    Los días de vino y rosas del ‘calciomercato’
    Nakamura sorprende con un juego magnífico y tumba a Caruana
    Álex Márquez ficha por el Ducati Gresini
    GP de Assen: 30 años de la histórica victoria de Àlex Crivillé
    Tres años después, Nadal contra la amnesia
    Las criptomonedas saltan al deporte: una historia de conveniencia y desconfianza
    Pioneros para siempre
    Gareth Bale se va a EE UU a jugar en el equipo de Magic Johnson
    Eugenio López Chacarra, del golf amateur a millonario fichaje saudí
    Apoteosis de Italia, oro en el relevo de 4x100 estilos del Mundial de Natación
    La selección femenina de fútbol golea a Australia a dos semanas de la Eurocopa (7-0)
    La nueva gran atracción del fútbol español
    “Nunca acepto un no por respuesta”
    La mayor fábrica de baloncesto de Europa
    Crónica de dos ciudades moldeadas por la misma pasión 
    Aquel homenaje a Zico
    El desplome de Suzuki tras anunciar su retirada de MotoGP: un cuarto puesto, cinco ceros y tres caídas desde Le Mans
    Valverde regresa al Athletic con el triunfo presidencial de Jon Uriarte
    Ledecky se convierte en la primera nadadora en ganar cinco mundiales seguidos
    España denuncia la presunta alineación indebida de un jugador de Rumania para volver al Mundial
    Firouzja está flojo
    La FINA prohíbe a Anita Álvarez, la nadadora que se desmayó, participar en la final por equipos en los Mundiales
    El circuito europeo de golf multa con 116.000 euros a los fugados a la liga saudí
    Imágenes sexuales que destruyen y matan
    Tres cosas que hacemos mal con el teléfono móvil (y no sirven para nada)
    Christopher Mims: “Amazon sabe cómo bajar el ritmo de trabajo para prevenir lesiones. Pero quizá dejaría de ganar dinero” 
    ¿Sigue siendo imprescindible tener un antivirus? 
    Google News vuelve a España ocho años después de su cierre
    Mónica Ojeda, pedagoga: “Los adolescentes utilizan sus imágenes sexuales como moneda de cambio o como prueba de amor”
    Zuckerberg desvela cómo serán las gafas para entrar en el metaverso
    Por qué retuitear el vídeo sexual de Santi Millán también es delito: la desprotección de la intimidad en internet
    LaMDA, la máquina que “parecía un niño de siete años”: ¿puede un ordenador tener conciencia?
    La inteligencia artificial reconocerá el arte gracias a la ciencia ciudadana
    “Gano 1.500 euros al mes con los videojuegos”: así funciona el negocio de la compraventa de cuentas
    Cinco aplicaciones móviles, con aval científico, que salvan vidas o mejoran tu salud
    Cómo contarle tus ciclos menstruales a una app puede llevarte a la cárcel
    Bill Gates dice que las criptomonedas y los NFT están basados en encontrar a “alguien más tonto”
    El Princesa de Asturias de Investigación Científica distingue a cuatro expertos en sistemas que imitan al cerebro
    En defensa de la procrastinación. Elogio del tiempo perdido (frente al que las redes te roban)
    Instagram, el mejor de los mundos posibles
    Del terrorismo youtuber al influencer rabioso: el odio inunda la red
    Cronodiversidad. ¿Por qué el tiempo cada vez va más rápido?
    Herramientas que ayudan a crecer a las empresas (más allá de los pagos)
    La solución definitiva para vender más (y mejor) en la web
    La cámara de este ‘smartphone’ es pura magia
    Por qué todos hablan de este ‘smartphone’ de diseño atractivo y rendimiento prémium
    Un campus de programación para adquirir todas las habilidades ‘tech’
    Una catapulta para el talento de ‘kilómetro cero’
    Imágenes sexuales que destruyen y matan
    Tres cosas que hacemos mal con el teléfono móvil (y no sirven para nada)
    Christopher Mims: “Amazon sabe cómo bajar el ritmo de trabajo para prevenir lesiones. Pero quizá dejaría de ganar dinero” 
    ¿Sigue siendo imprescindible tener un antivirus? 
    Google News vuelve a España ocho años después de su cierre
    Mónica Ojeda, pedagoga: “Los adolescentes utilizan sus imágenes sexuales como moneda de cambio o como prueba de amor”
    Zuckerberg desvela cómo serán las gafas para entrar en el metaverso
    Por qué retuitear el vídeo sexual de Santi Millán también es delito: la desprotección de la intimidad en internet
    LaMDA, la máquina que “parecía un niño de siete años”: ¿puede un ordenador tener conciencia?
    La inteligencia artificial reconocerá el arte gracias a la ciencia ciudadana
    “Gano 1.500 euros al mes con los videojuegos”: así funciona el negocio de la compraventa de cuentas
    Cinco aplicaciones móviles, con aval científico, que salvan vidas o mejoran tu salud
    Cómo contarle tus ciclos menstruales a una app puede llevarte a la cárcel
    Bill Gates dice que las criptomonedas y los NFT están basados en encontrar a “alguien más tonto”
    El Princesa de Asturias de Investigación Científica distingue a cuatro expertos en sistemas que imitan al cerebro
    En defensa de la procrastinación. Elogio del tiempo perdido (frente al que las redes te roban)
    Instagram, el mejor de los mundos posibles
    Del terrorismo youtuber al influencer rabioso: el odio inunda la red
    Cronodiversidad. ¿Por qué el tiempo cada vez va más rápido?
    Herramientas que ayudan a crecer a las empresas (más allá de los pagos)
    La solución definitiva para vender más (y mejor) en la web
    La cámara de este ‘smartphone’ es pura magia
    Por qué todos hablan de este ‘smartphone’ de diseño atractivo y rendimiento prémium
    Un campus de programación para adquirir todas las habilidades ‘tech’
    Una catapulta para el talento de ‘kilómetro cero’
    La semana de la moda masculina de París apuesta por el cambio tranquilo
    Ramón Estévez lamenta llamarse Martin Sheen
    Piti Alonso: “Igual te organizo la alfombra roja de los Goya que la de la OTAN”
    Ana Rosa Quintana reaparece en un encuentro con sus compañeros de televisión
    Un libro y un documental revisitan la figura de George Michael: atracones de helado, culebrones, sexo y éxtasis
    Gracias, Locomía
    Las magnolias, grandes, blancas y fragantes, las flores que regala el verano
    María del Monte, en el pregón del Orgullo en Sevilla: “Jamás en mi vida me he escondido de nadie, ni lo voy a hacer por amor”
    De una pastelera de tartas en 3D a una creadora de café con huesos de dátil: estos son los próximos grandes talentos de la gastronomía global
    Denise Richards sigue los pasos de su hija y se crea una cuenta en OnlyFans
    Cuarto divorcio para Rupert Murdoch: el magnate y la modelo Jerry Hall se separan
    Sharon Stone: “Perdí nueve hijos por abortos espontáneos. Las mujeres no tenemos un espacio donde discutir la profundidad de estas pérdidas”
    De La Tasquería a El Lince, un homenaje a la casquería más popular con sorpresas
    Ha Ha Ha! La colección de Gucci que Harry Styles y Alessandro Michele han creado a partir de los memes que intercambiaban
    Nicky y Simone Zimmermann: “Nos dijeron que no nos dedicáramos a la moda y que no trabajáramos en familia. No les hicimos caso y nos fue bien”
    Viktor & Rolf, 30 años de moda y rebelión: “No puedes estar siempre arriba”
    Desembarco de celebridades internacionales en Sevilla para el desfile de Dior
    Kim Kardashian causó graves daños al histórico vestido de Marilyn Monroe que llevó en la gala del Met
    El publicista Miguel Olivares y la pasta del fin del mundo
    De La Tasquería a El Lince, un homenaje a la casquería más popular con sorpresas
    Al enemigo, ni ensaladilla: ¿qué comida es de izquierdas y cuál de derechas según las guerras culturales?
    La evolución de los modales al comer en la mesa
    24 series para este verano
    ¿Merece la pena ver ‘La casa de papel: Corea’? Diferencias y semejanzas con la serie original
    Pepón Nieto denuncia que TVE vetó una de sus películas en ‘Cine de barrio’ y la corporación recula: se emitirá este sábado
    El espíritu de Balbín está por todas partes
    Los Romanoffs
    Maria Ressa, la periodista filipina “no exenta de ser asesinada”
    ‘Supervivientes’ y la incultura general
    ‘La clave’ de Balbín, gloria y caída del programa que cambió la televisión española
    Un viaje en el tiempo con Kurt Vonnegut
    Muere José Luis Balbín, mítico presentador y creador del programa ‘La clave’
    El TSJ de Madrid declara nulo el despido del guionista de TVE que escribió el rótulo “Leonor se va de España, como su abuelo”
    ‘Legacy’: un Bosch sin placa y un poco perdido
    Claves de la nueva Ley General de Comunicación Audiovisual, más allá del enfado de los productores independientes
    ‘Sanditon’ resucita a Jane Austen
    Ciencia, tecnología y entrevistas en las novedades de la programación de verano en la Cadena SER
    Los abonados a las plataformas y televisiones de pago superan el número de hogares españoles 
    Mueren en un accidente de tráfico dos actores mexicanos durante el rodaje de la serie de Netflix ‘El Elegido’  
    ¿Qué ver hoy en TV? Domingo 26 de junio de 2022
    Nueve capítulos para recordar ‘The Wire’ en su 20º aniversario
    Harry Palmer: el tercer vértice del mágico triángulo de espías británicos
    Las series de junio de 2022: ‘The Boys’ en Amazon Prime Video; ‘Peaky Blinders’ en Netflix y otras
    La fuerza acompaña a ‘Obi-Wan Kenobi’, una serie deslumbrante
    Chanel, la vida después de Eurovisión: “No soy un títere”
    Farrell y McNamara: “Los edificios no son tan solo infraestructuras, representan sistemas de valores”
    La finca donde se resucita la tierra
    Acelerando la ciencia a 314.000 billones de operaciones por segundo
    Así fue nuestra experiencia de escribirnos con GPT-3, una máquina de inteligencia artificial
    El publicista Miguel Olivares y la pasta del fin del mundo
    Viaje al fin de Occidente, en la gran frontera entre Finlandia y Rusia
    Aprendizaje continuo para un mundo en cambio
    El piloto de ‘airbuses’ que se eleva componiendo pop barroco
    Siri, Alexa, Sophia: ¿por qué asistentes virtuales y humanoides tienen nombre de mujer?
    Inteligencia artificial ¿para qué?
    Voluntarios contra el abismo digital de los mayores
    Ir a un concierto o pintar nos repara emocionalmente
    Por qué ya no soy futbolero
    Ubicación exacta de la utopía
    Una pequeña historia
    Historia para los nietos
    Harina enriquecida para acabar con el “hambre oculta”
    Lugares de esperanza para salvar los océanos
    Los guardianes del clima que llevan medio siglo leyendo las advertencias de los glaciares
    Epidemia de violencia: claves del negocio de las armas en Estados Unidos
    Los ejecutivos voladores y la ética medioambiental
    Ibiza, entre la noche desenfrenada y el turismo tranquilo 
    Luz Casal: “Tengo el alma rockera. Nada ha doblegado mi rebeldía”
    Rashid Johnson: “Los pensadores y creadores negros estamos cansados de que nos nieguen un espacio autónomo”
    Sergio Hernández: “En el mundo, la gente ya no quiere verdades, quiere mentiras”
    Elvira Sastre: “No hay que perdonarlo todo”
    La trinidad del taco perfecto: “Buena tortilla, delicioso relleno y una salsa sabrosa”
    Bikôkô y Julio Peña, dos estrellas en ebullición  
    Cuando Chufy encontró a Rossy: dos amigas, una isla y una colección de moda
    La nueva edad de oro de la coctelería en Barcelona
    Riesgo, dolor y placer: cómo los humanos se aficionaron al picante 
    Ilusiones hipnóticas
    El poder del hormigón
    Maulévrier, Japón a la francesa
    ‘Fantasías en el Prado’, por Alberto García-Alix
    ¡‘Yee-haw’! Esto también es Brasil
    

### Limpiar

Pasamos ahora, tras realizar el *web scrapping*, usar el `os.system("clear")` para limpiar la pantalla de Python. 

### Imprimir y colorear 

Se muestran caracteres en azul y en negrita para que sirva como que mostrarán los resultados.


```python
print(colored("A continuación se muestran los titulares de las páginas principales del diario El País que contienen las siguientes palabras:", 'blue', attrs=['bold']))
```

    [1m[34mA continuación se muestran los titulares de las páginas principales del diario El País que contienen las siguientes palabras:[0m
    

Imprimimos el contenido que se seleccionará. 


```python
print(colored("Feminismo", 'green', attrs=['bold']))
```

    [1m[32mFeminismo[0m
    

Se realiza una variable para identificar los resultados. La primera palabra es feministro. El mismo proceso se repite luego con los conceptos igualdad, mujeres, mujer, brecha salarial, machismo, violencia, maltrato, homicidio, género, asesinato y sexo.



```python
str_match = [s for s in resultados if "feminismo" in s]
print("\n".join(str_match))

print(colored("Igualdad", 'green', attrs=['bold']))

str_match = [s for s in resultados if "igualdad" in s]
print("\n".join(str_match))

print(colored("Mujeres", 'green', attrs=['bold']))

str_match = [s for s in resultados if "mujeres" in s]
print("\n".join(str_match))

print(colored("Mujer", 'green', attrs=['bold']))

str_match = [s for s in resultados if "mujer" in s]
print("\n".join(str_match))

print(colored("Brecha salarial", 'green', attrs=['bold']))

str_match = [s for s in resultados if "brecha salarial" in s]
print("\n".join(str_match))

print(colored("Machismo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "machismo" in s]
print("\n".join(str_match))

print(colored("Violencia", 'green', attrs=['bold']))

str_match = [s for s in resultados if "violencia" in s]
print("\n".join(str_match))

print(colored("Maltrato", 'green', attrs=['bold']))

str_match = [s for s in resultados if "maltrato" in s]
print("\n".join(str_match))

print(colored("Homicidio", 'green', attrs=['bold']))

str_match = [s for s in resultados if "homicidio" in s]
print("\n".join(str_match))

print(colored("Género", 'green', attrs=['bold']))

str_match = [s for s in resultados if "género" in s]
print("\n".join(str_match))

print(colored("Asesinato", 'green', attrs=['bold']))

str_match = [s for s in resultados if "asesinato" in s]
print("\n".join(str_match))

print(colored("Sexo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "sexo" in s]
print("\n".join(str_match))
```

    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    [1m[32mIgualdad[0m
    La escuela concertada ante las desigualdades: el debate pendiente
    [1m[32mMujeres[0m
    Dos mujeres besándose, esa bomba
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    Un día muy triste para todas las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Sharon Stone: “Perdí nueve hijos por abortos espontáneos. Las mujeres no tenemos un espacio donde discutir la profundidad de estas pérdidas”
    [1m[32mMujer[0m
    Dos mujeres besándose, esa bomba
    Siri, Alexa, Sophia: ¿por qué las asistentes virtuales tienen nombre de mujer?
    Ellos no bailaron solos: la mujer detrás de la loca historia de Locomía
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    Un día muy triste para todas las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Sharon Stone: “Perdí nueve hijos por abortos espontáneos. Las mujeres no tenemos un espacio donde discutir la profundidad de estas pérdidas”
    Siri, Alexa, Sophia: ¿por qué asistentes virtuales y humanoides tienen nombre de mujer?
    [1m[32mBrecha salarial[0m
    
    [1m[32mMachismo[0m
    
    [1m[32mViolencia[0m
    Epidemia de violencia: claves del negocio de las armas en Estados Unidos
    [1m[32mMaltrato[0m
    
    [1m[32mHomicidio[0m
    
    [1m[32mGénero[0m
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    [1m[32mAsesinato[0m
    
    [1m[32mSexo[0m
    Atracones de helado, culebrones, sexo y éxtasis: un libro y un documental sobre George Michael
    El mejor sexo de tu vida
    Un libro y un documental revisitan la figura de George Michael: atracones de helado, culebrones, sexo y éxtasis
    


```python

```
