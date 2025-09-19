---
time: 2023-10-09 23:44
tags:
  - MOC
  - comunicacionYRedesII
links:
  - "[[Tercer Año]]"
estado: aprobada
código-materia: "07045"
correlativas:
  - "07040"
dictado: 1°C
año-carrera: Tercer año
fechaPrimerParcial: 2024-05-08
fechaSegundoParcial: 2024-06-14
fechaPrimerRecuperatorio: 2024-06-26
fechaFinal: 2024-07-10T18:00:00
fechaRegularizacion: 2024-06-26
color: "#86469C"
---
Comunicación y Redes II se encuentra en el 1°C del tercer año de la carrera de Licenciatura en Informática. Esta es la página de inicio para ingresar a cada uno de los módulos que se estudian en la materia.

El profesor a cargo es **Marcelo Estevez**.

---
## Bibliografía

+ Stalling William - Comunicaciones y Redes de computadoras. 2007, 7ma edición. Editorial: Prentice Hall
+ Lechtaler Castro, Antonio Ricardo, Fusario Rubén Jorge - Comunicaciones y Redes para Profesionales en Sistemas de Información. 1ra edición. Editorial: Alfaomega
+ Tanenbaum, Andrew - Redes de computadoras. 2003, 4ta edición. Editorial: Pearson
+ Halsall, Fred - Redes de computadores e Internet. 2006, 5ta edición. Editorial: Pearson
+ Forouzan Behrouz - Transmisión de datos y redes de comunicaciones. 2006. Editorial: Mc Graw Hill

---
## Clase 1

### Modelo OSI

<u>El modelo OSI (Open Systems Interconnection) es un marco de referencia conceptual utilizado para entender cómo funcionan las comunicaciones entre dispositivos en una red de computadoras</u>. Fue desarrollado por la Organización Internacional de Normalización (ISO) en la década de 1980. 

<u>El modelo OSI divide el proceso de comunicación en siete capas, cada una de las cuales se encarga de funciones específicas relacionadas con la comunicación de datos</u>. 

Estas capas son:

1. **Capa física**: Se encarga de la transmisión de bits a través de medios de comunicación físicos como cables o señales inalámbricas.
2. **Capa de enlace de datos**: Coordina la transferencia de datos entre dispositivos adyacentes en una red local y maneja errores en la transmisión física.
3. **Capa de red**: Se encarga de enrutar los datos a través de la red y gestionar el tráfico, determinando la mejor ruta para el transporte de datos.
4. **Capa de transporte**: Proporciona servicios de extremo a extremo para la transferencia confiable de datos entre aplicaciones en dispositivos finales. Esta capa garantiza la entrega de datos de manera ordenada y sin errores.
5. **Capa de sesión**: Establece, mantiene y finaliza conexiones entre aplicaciones en diferentes dispositivos. Controla el diálogo entre las aplicaciones y gestiona la sincronización y recuperación de errores.
6. **Capa de presentación**: Se encarga de la traducción, compresión y encriptación de los datos para que puedan ser interpretados por la aplicación receptora.
7. **Capa de aplicación**: Proporciona servicios de red directamente a las aplicaciones de usuario, como navegadores web, clientes de correo electrónico, etc. Esta capa interactúa con las aplicaciones y las convierte en datos entendibles por la red.

El modelo OSI facilita la comprensión de cómo funcionan las comunicaciones en redes de computadoras al dividir el proceso en capas bien definidas, lo que ayuda en el diseño, la depuración y la solución de problemas en sistemas de redes.

![[Pasted image 20240504144532.png|150]]

<u>Cuando la **capa de enlace de datos** está orientada a la conexión</u>. Una de las cosas que hace es establecer. Básicamente es, pedir los recursos a quien se los tenga que pedir para que estén asignados y luego poder utilizarlos. <u>La capa de enlace de datos está pensada para hablar en una única red</u>.

La **capa de red** se va a encargar de varias cosas. <u>La capa de red está pensada para hablar entre múltiples redes</u>. De una de las cosas que se va a encargar es, de como llego de una red hacía otra. A esto se le llama <u>encaminamiento o roteo</u>.

La **capa de transporte** es la que <u>se encarga de la comunicación extremo a extremo</u>. Allí, una computadora en un red, está hablando con otra computadora en otra red, recién en la capa de transporte es donde se están comunicando entre ellas. 

Tanto la capa de enlace, como la capa de red, hablan en redes. Una en una red única local y otra entre varias redes. Pero recién <u>en la capa de transporte es donde se habla entre un host y otro host</u>.

La capa de transporte permite que dos computadoras en diferentes redes se comuniquen directamente. Esta capa se encarga de:

1. Controlar el flujo de datos
2. Detectar errores
3. Ordenar los paquetes que llegan desordenados
4. Ofrecer comunicación con o sin conexión

A diferencia de las capas inferiores, que se centran en la comunicación dentro de una red o entre redes, la capa de transporte se enfoca en la comunicación entre los dispositivos finales.

Capa de **sesión**, **presentación** y **aplicación**: Si bien cada una tiene funciones bien definidas, como por de facto se utiliza el modo [[Transmission Control Protocol (TCP)|TCP-IP]] donde todo es una capa de aplicación, es mucho más fácil decir que estas 3 capas se consolidan en una sola donde uno tiene, desde la aplicación, una forma de conectarse a la red.

![[Modelo TCP-IP y OSI.webp|400]]

El modelo TCP IP es de facto, se apartó del modelo OSI el cual es bien genérico pero los definió con 4 grandes capas. 

Una **capa física o de interfaz**. Está capa integra lo que sería la capa de enlace y la capa física del modelo OSI. Fue definida de esta forma porque, tratando de abstraerse de la conexiones físicas, como manejarme las conexiones entre distintas redes. El modelo TCP IP es básicamente eso.

**El modo de transporte**. Que es la que se ve desde una máquina a la otra máquina físicamente. Si bien el protocolo que se utiliza generalmente es el TCP, que trata de simular la conexión entre dos redes distintas. También existe otro modo llamado ULP (creo o UDP) que es el que trabaja sin conexión entre ambas.

Después como **aplicación** tenemos todos los protocolos que utilizamos habitualmente el HTTP, FTP para archivos, etc. y así hay infinidad de aplicaciones de red.

El modelo TCP IP no sigue puramente el modelo OSI. <u>El modelo OSI dice que cada capa es totalmente independiente de la superior y la inferior, solo se comunican con los servicios</u>. Cuando veamos TCP IP vamos a ver que se mete un poco la capa de transporte en la de red. No es un modelo purista, es netamente practico.

TCP IP es del año 74. Originalmente concebido dentro de la imprenta Cerox.

Lo que tiene que quedar claro es que el modelo <u>OSI son 7 capas</u>. En donde cada una de ellas <u>se comunica con la otra a través de servicios</u>. En cada una de ellas <u>esos servicios están bien definidos y son bidireccionales</u>. Ósea las capas se comunican entre si de forma bidireccional.

Cada capa habla con la misma capa de la maquina remota. Para esas capas tienen significado. Los datos que van de una capa hacía otra no tienen significado, pero para la misma capa esos datos tienen algún tipo de sentido. 

El modelo TCP IP, el cual se utiliza para todas las comunicaciones hoy en día, no se adapta 100% al modelo OSI, pero se asemeja bastante para que sea más fácil analizarlo.

El modelo OSI es como las "buenas practicas".

+ [[Redes LAN (Local Area Network)]]

Es un conjunto de maquinas que está dentro de un ámbito reducido. Con reducido se refiere a una distancia cercana. Todos respetando las mismas conexiones de red, con el mismo tipo de medio. No tienen que estar físicamente en el mismo lugar. Aproximadamente $100 m$. Por ejemplo, un campus universitario, un laboratorio. Generalmente es un área donde todos tienen el mismo tipo de placa de red, el mismo tipo de cable con la misma velocidad, todos comparten recursos.

### ¿Qué medios de transmisión utiliza la red?

+ Par trenzado
	+ UTP (Unshield Twisted Pair)
	+ STP (Shielded Twisted Pair)
+ [[Cables coaxiales|Cable Coaxial]]: La impedancia de los cables es de 50 Ohms, la misma que se utiliza para las comunicaciones radioeléctricas. No como se utiliza en la televisión que es de 75 Ohms. Este fue uno de los primeros métodos que se utilizo en la red Ethernet para comunicar maquinas. Trajo problemas y se pasó al UTP.
	+ Grueso
	+ Fino
+ [[Fibras ópticas]]
	+ Multimodo
	+ Monomodo
+ Inalámbrico
	+ Radiofrecuencia
	+ [[Infrarrojo]]
	+ [[Microondas]]

### ¿Qué equipos se utilizan en una red LAN?

+ Hardware
	+ Terminales bobas: Conceptualmente se refiere a un teclado, un monitor y una interfaz de comunicaciones para comunicarse con su unidad de computo central. No tiene memoria, CPU, ni disco, solo un buffer chiquito en el teclado.
	+ Servidores de Infraestructura
	+ Hosts
	+ Placa de Red (NIC)
	+ Cableado
	+ Conmutadores/Concentradores(Hub o Switches)
	+ Router: Son los equipos que se van a encargar de, teniendo dos redes separadas, estas se puedan comunicar. 
	  Son los encargados de, si la velocidad una red es distinta a la velocidad de la otra red, bueno, tratar de ecualizar eso para que la información pueda fluir de un lado al otro.
	  Si hay múltiples redes conectadas. La información de que red a que red tiene que ir.
	  Firewall: Aplicarle seguridad al nivel de la red. No los vamos a configurar. 
+ Software
	+ Sistema Operativo de Red
	+ Protocolos de Comunicaciones

### ¿Tipos de topología que nos vamos a encontrar en una red?

+ Modos de transmisión
	+ Banda Base (Por ejemplo Ethernet)
	+ Banda Ancha (Modem)
+ Topología
	+ **Anillo**
		<u>Se utilizó en un tipo de red que se llamó Token Ring</u>. 
		
		<u>Todas las máquinas estaban conectadas como si fueran un gran anillo. Esa red tenía de particular que para poder empezar a hablar tenías que tener el Token. La maquina que tenía el Token podía cargar información en la red</u>. 
		
		Conceptualmente funciona bien cuando uno tiene procesos estándares y controlados. Funcionaba con una serie de prioridades.
		
		El problema de esta red es que, todos los usuarios creían que su mensaje era el de mayor prioridad y todo colapsaba.
		
		![[topologia-de-red-en-anillo.webp|300]]
	+ **Bus**
		<u>Conceptualmente todas las máquinas están conectadas a un mismo cable. Así es como funcionaba [[Redes Ethernet|Ethernet]] originalmente</u>.
		
		![[topologia-de-red-en-bus.webp|300]]
	+ **Estrella**
	  <u>Es como se utilizan hoy en día las redes Ethernet</u>.
	  
	  <u>El cable UTP que sale de los hosts va a un concentrador (Hub o Switch), que es quien distribuía la comunicación entre las distintas maquinas</u>.
	  
	  ![[topologia-de-red-en-estrella-2022.webp|300]]
	+ **Árbol o Estrella ramificada**
	  Son variaciones de distintos tipos de topologías que se implementaron.

---

Ethernet nació como una red en bus y las primeras que se utilizaron fueron:

+ **Ethernet (IEEE 802.3)**
	+ 10 Base 5
	+ 10 Base 2
	+ 10 BROAD 36
	+ 10 Base T (T es porque se utiliza cable UTP)
	+ 10 Base F (F porque se utiliza Fibra Óptica)
+ **Token Ring (IEEE 802.5)**: Funcionaba muy bien cuando los procesos trabajaban correctamente con las prioridades y las comunicaciones. Los problemas comenzaron con la alta prioridad.
+ **Token Bus (IEEE 802.4)**: Tenía el mismo tipo de funcionamiento que el token ring, pero en vez de ser en anillo funcionaba en Bus como Ethernet. No se aceptó mucho.

<u>La denominación 10 Base 5, 10 Base 2, significa 10 mega bits, modulación en banda base y el 5 hacía referencia el tipo de grosor del cable coaxial (5 grueso, 2 fino)</u>.

También vamos a ver que dice 100 Base T, 1000 Base T, eso quiere decir que puede andar a 100 o 1000 mega bits. También conocido como **Fast Ethernet** o **Giga Ethernet**.

Hoy en día evolucionó tanto Ethernet que también hay conexiones de 10 Giga bits, 25, 40, 100, y 400. 

<u>802 es el conjunto de normas del IEEE que se definen para lo que sea Networking. Luego el punto y el número define el grupo que está trabajando sobre una característica en particular.</u>

---

Así como definimos las redes LAN. También están las [[Redes WAN (Wide Area Network)]]. 

Son las redes que se utilizan para comunicar una red que está en un lugar con otra red que está distante. Distante puede ser a una cuadra de distancia, como en otra parte del mundo.

Cuanto más lejana la red, mayor cantidad de problemas podemos encontrar y distintos tipos de redes podemos tener en el medio.

Todas esas complejidades es lo que van a tratar de resolver los distintos protocolos de WAN, con los protocolos de IP, de transporte, y así sucesivamente. 

Tenemos dos grandes grupos de red, las LAN o locales y las WAN que son para comunicación redes extremadamente lejanas.

También se conocen las redes MAN. Para nosotros es un simple caso de red WAN.

### Cableado estructurado

<u>El cableado estructurado es un sistema de cableado diseñado para soportar múltiples servicios de comunicación, como voz, datos, video, entre otros, a través de un único sistema de cableado</u>. 

<u>Este enfoque organiza y administra los cables de red de una manera que facilita la administración, la expansión y el mantenimiento de una red de comunicaciones</u>.

---

El cableado estructurado nació para solucionar los problemas donde cada uno hacía lo que quería sin ningún tipo de regulación.

Por los años 80s, comienzan a nacer ciertas normas. Se generaron las normas ANSI, EIA/TIA 568, es la que indica como tiene que ser un cableado para todo el ámbito de las telecomunicaciones dentro de una oficina, edificio, centro de cómputos, un campus. 

**La idea de un cableado estructurado es**:

+ <u>Que sea durable en el tiempo</u>. 
	Tiene que ser lo suficientemente robusto para que aguante mucho tiempo.
+ <u>Debe estar bien documentado</u>. 
	Deben haber planos en donde se indiquen todas las conexiones, para que luego, si se deben hacer modificaciones, lidiar facilmente con esto.
+ <u>Tiene que ser común e independiente de las aplicaciones</u>. 
	Nosotros nos vamos a enfocar en las comunicaciones, pero el cableado estructurado abarca muchas más cosas. 
	Pero con respecto a las comunicaciones, uno tiene que proyectar que, por ejemplo, en un laboratorio tenemos 2 maquinas por escritorio pero que en un futuro, que pueda ser ampliado.
+ <u>Tiene que ser fácil de administrar</u>. 
	Esto significa que alguien desde algún lugar centralizado puede llegar a realizar algunos tipos de cambios con respecto a lo que tiene que ver con el cableado.
+ <u>Tiene que ser fácilmente ampliable, reducible y confiable</u>. 
	Con confiable nos referimos a que, una vez terminada la red, se deben medir cada uno de los puntos que la componen y verificar que está bien hecho.

<u>El sistema de cableado estructurado utiliza la topología de estrella extendida</u>. Esto significa que se encuentra en un lugar central y desde este se va a ramificar a $N$ lugares secundarios, y cada uno de ellos se van a ramificar por $N$ lugares terciarios y así sucesivamente.

#### Esquema del cableado estructurado

Cuando se tiene un servicio de red, este no solo tiene que abastecer la red de todo el edificio sino que tiene que interconectarse con el exterior. <u>Para ello existe un punto de interconexión el cual me permite conectar con otra red de un mismo campus, o con el ISP (Internet Service Provider)</u>.

<u>Este enfoque organiza y administra los cables de red de una manera que facilita la administración, la expansión y el mantenimiento de una red de comunicaciones</u>.

<u>Luego vamos a tener lo que se conoce como **cableado vertical**. Este es el que va a estar alimentando todos los pisos y va a llevar la señal de datos entre todos ellos</u>.

<u>En cada uno de estos pisos vamos a tener un **distribuidor**. Este se encarga de llevar la conexión del cableado vertical hacía toda la planta que estamos alimentando. A esa planta que estamos alimentando se le llama **cableado horizontal**, porque es el cableado que va a un piso en particular</u>.

Cada uno de los cableados tiene un nombre en particular. <u> **Área de trabajo**. Básicamente es donde esta la computadora, el teléfono</u>.

Después tenemos el cableado horizontal, que en el ejemplo el profe menciona el cableado que pasa por cada una de las computadoras.

<u>El **Jumper o conexión cruzada** es el cable de red que está puesto entre el dispositivo que hace la conexión entre el cableado vertical y horizontal, también se conoce como **patchcord**</u>.

<u>La entrada al edificio que es por donde entra la conexión de otra red o del ISP, se le suele llamar **acometida**</u>. Si es el ISP viene una bornera donde están los cables o una caja particular. <u>Esto se encuentra en la entrada del edificio, en la planta baja, el sótano o la terraza</u>.

#### Puertos fijos

Dependiendo de la cantidad de plantas, de maquinas y conexiones que uno tenga que hacer. El cuarto de equipos donde vamos a tener Routers, Switches, y todo los equipos de comunicaciones, va a ser más grande. Este lugar tiene ciertos requerimientos. Muchas veces estas cuentan con un rag, tienen doble puerta, una delante y otra detrás. El rag esta metido por lo general en el medio de la habitación para que tenga circulación por ambos lados. Muchas veces debe estar en una sala refrigerada. Estas cosas están especificadas en la norma.

<u>El cableado vertical, se acepta tanto que sea de **fibra óptica**, de **cobre (UTP)** o cable **coaxil**</u>, dependiendo del edificio y de las conexiones que vallamos a hacer.

<u>El cableado horizontal se puede hacer por **cables canales** o por **bandejas**. Las bandejas son unas canaletas de hierro suspendidas, por piso técnico</u>. 

El cableado vertical usualmente va por los que se llaman **montantes**. 

Los edificios de altura generalmente, si tienen ascensor, a los costados de este va una bandeja con todos los cables de conexión aprovechando los tubos del ascensor. Otra forma es utilizar una falsa columna que va pasando por todos los pisos y por ahí van todos los cables de comunicaciones.

#### Puntos importantes

**¿Que medidas tienen que tener los cables?**

<u>La norma dice que entre el dispositivo que va a hacer distribución en todo el piso y la placa de red del último equipo, no puede superar los 100m</u>.

<u>Entre la máquina y el conector que está en la pared, piso, etc., se llama **toma** o **periscopio** (si está en el piso técnico). La distancia máxima de este conector contra el computador no debe superar los 3m</u>.

<u>La distancia máxima entre la toma/periscopio y un elemento pasivo llamado **patchera** (no deja de ser un enchufe al lado del otro) que es donde van a ir apilados todos los cables desde la toma hasta ese lugar, es de 90m</u>.

<u>Entre la patchera y el dispositivo que va a hacer las comunicaciones dentro de el piso, la distancia máximo son otros 6m. Eso totaliza unos 99m. Está dentro del rango</u>.

#### Categoría de los cables

Los cables UTP tienen distintas categorías. Son dos parámetros los que hacen de esta. 

<u>Uno es la calidad del propio material que tiene puesto</u>. Si bien son de cobre, hay de distinta calidad y grosor.

<u>El segundo parámetro es el trenzado que tienen los pares</u>. Los trenzados de los cables UTP que son categoría $1$, los cuales son de telefonía, están apenas trenzados. Tienen una vuelta cada $10 \space cm$ ($10$ vueltas en un metro). Aquellos que se utilizan para conectar en las redes que son categoría $5$ o superior, tienen en un metro $50$ vueltas de trenzado ($5$ vueltas cada $10 \space cm$).

---
#### Certificación del cableado

<u>En grandes empresas, la norma exige que este cableado sea certificado. Esto significa que una persona idónea para el trabajo, la cual tiene las herramientas necesarias, se tome el trabajo de medir todas las conexiones una por una y de esta forma garantizar que el cableado está bien hecho</u>.

Obviamente es una tarea costosa, pero garantiza todos los parámetros establecidos en la norma. La garantía es para uno mismo.

Las mediciones se hacen con un instrumento donde uno conecta un medidor. Este es el que se va a conectar una a una en las bocas y del otro lado del cableado estructurado, se conecta otro instrumento parecido que lo único que hace es inyectar distintos tipos de señales para que el analizador pueda verificar que esas señales que emite el inyector lleguen correctamente al instrumento. Como estos están calibrados, por ejemplo, el inyector sabe que va a poner una señal cuadrada de un 1 volt pico a pico en cada uno de los pares y del otro lado se va a medir la atenuación. Sabiendo que atenuación tengo, no me va a llegar un volt, me va a llegar 0,95. Entonces si yo tengo ese valor en todos lo pares y la norma dice que la tolerancia es hasta 0,93, el cable funciona.

<u>También se mide el **CrossTalk** cercano. El crosstalk se refiere a la interferencia electromagnética no deseada entre pares de cables adyacentes. Estas se miden en los dos lados.</u>

Tipos:

- Near-End Crosstalk (NEXT): Interferencia medida en el mismo extremo donde se genera la señal.
- Far-End Crosstalk (FEXT): Interferencia medida en el extremo opuesto al que genera la señal.

<u>**Retardo**. A medida que el cable está mas trenzado, más largo es el recorrido. Al hacerse más largo voy a tener pequeñas diferencias de tiempo entre la señal que viaja por un par y la señal del otro par. Estás diferencias son mínimas, pero para algunas aplicaciones puede ser algún tipo de problema</u>.

---

### Tipos de cables de red

Hay dos tipos de cables de red. Cable de red **derecho** y **cruzado**.

<u>El **cable de red derecho** es el cable en donde yo tengo que la señal que envío por el par 1, llega en el par 1, el del par 2, al par 2, y así sucesivamente</u>.

El **cable de red cruzado** significa: Cuando yo envío por el par 1, 2, del otro lado me va a llegar en el par 3, 6. Cuando mando por el par 3, 6, del otro lado llega por el 1, 2. 

Esto sucede porque, <u>cuando se conectan dos equipos que son de distinta clase, saben que la transmisión va a ir por un lado y la recepción va a ir por el otro. Cuando conecto dos equipo de la misma clase, para poder interconectarlos se debe poner en un equipo la transmisión y en el otro la recepción, porque sino no se escuchan</u>.

<u>Si conecto equipos de distinta clase, utilizaré un cable derecho. Si conecto dos equipos de igual clase, utilizaré un cable cruzado</u>.

**¿Que equipos son de la misma clase?**

Las computadoras, tablets, teléfonos, se los conoce como hosts. Es un nombre genérico que identifica un equipo que es un terminal o cliente que se conecta a la red. 

<u>Si conecto un host con un equipo de red, en este caso va a ser un concentrador (Switch o Hub), el cable tiene que ser derecho, porque son de distinta clase</u>. 

<u>Cuando tengo que conectar dos equipos iguales, por ejemplo, dos equipos de red o dos equipos host/clientes, tiene que ir un cable cruzado</u>.

Hoy en día, los equipos auto censan la red. Ósea que funcionan igual con un cable cruzado o derecho, pero esto originalmente no sucedía. 

Hay una excepción. <u>El router es un equipo de red. El router se lo conoce como host especial</u>. Cuando tengo que conectar uno con una computadora debería poner un cable cruzado, porque son hosts especiales, trabajan a nivel cliente. <u>Tienen la peculiaridad de tener varias placas de red. Cada una de las placas es un host, entonces se debería poner un cable cruzado</u>.

En los cables derechos se conectan de la siguiente manera:

![[Pasted image 20240505173510.png|500]]

En los cables cruzados se conectan de la siguiente manera:

![[Pasted image 20240505173548.png|500]]

Uno puede utilizar cualquiera de las dos normas para construir el cable derecho, o utilizo la A o utilizo la B en ambas puntas.

Si quiero hacer un cable cruzado, pongo la norma A en una punta y la B en la otra punta. Esto hace que el 1, 2, apunte al 3, 6 y el 3, 6 apunte al 1, 2.

**¿Por qué hay un código de colores?**

Estos vienen de la telefonía. Todos los multipares telefónicos están codificados por colores. Cuando uno esta trabajando y tiene que hacer centenares de cables, uno siempre respeta los colores, porque si se presenta un problema y no respetas la distribución de colores, se vuelve un problema mucho más grande. 

Para verificar que haya continuidad se utiliza un tester de continuidad. Este no es una certificación, pero si verifica que haya continuidad entre uno lado y el otro.

### Fibra óptica

Tenemos de dos clases. Generalmente en los cableados se utiliza la fibra multimodo y se compran hechos los latiguillos para conectar la fibra multimodo. 

Es muy común que desde un servidor a un director (elemento que concentra multiples equipos de almacenamiento), ya utilicen un cable armado.

<u>La fibra monomodo se utiliza para comunicaciones de larga distancia</u>.

---
## Clase 2 - Capa de Enlace de datos

Objetivos de la capa de enlace de datos:

+ Que exista una transmisión libre de errores o que puedan ser controlados
+ Que haya un control de acceso al medio (MAC). Ósea control de acceso a la capa física.
	Esto se refiere a verificar si está ocupada, libre, si podemos transmitir, si hay señal o no. etc.
+ Tener direcciones físicas. Aquellas que nos permiten llegar de una maquina a otra.
	En otras palabras, direccionamiento local con las direcciones físicas (MAC Address)

<u>El bloque de información (lo que vamos a transmitir en la capa de enlace de datos) se llama **trama** o **frame**</u>.

### ¿Qué redes LAN o redes de capa 2 se conocen?

En un momento eran múltiples redes LAN, hoy en día hay una sola que es Ethernet (cuando hablamos de cableado). 

+ **Ethernet**
+ **Token Ring**
+ **FDDI**: Similar a Token Ring per con tasas de transferencias más altas porque usan Fibra.
+ **ATM**: Fueron populares en los 90s y los 2000s en redes WAN también estaban las tarjetas para utilizar en redes LAN. Su problema es que eran costosas.
+ **Wifi**: Saliendo del mundo cableado (todas las anteriores mencionadas son cableadas).
	También hay otros medios inalámbricos además del Wifi (luz infrarrojas, señales de microondas).

### Tipos de redes Ethernet

+ [[Redes Ethernet|Red Ethernet]]

Nace a fines de los 70s. Se populariza como un estándar en los 80s. Desarrollada por xerox (creo que se escribe así).

+ [[Ethernet DIX v2 (Digital, Intel, Xerox)]]

Ethernet IEEE 802.3 es similar y compatible con DIX. La diferencia es que DIX quedó para dominio público.

Ambos se basan en el principio de funcionamiento del protocolo [[CSMA-CD (Carrier Sense Multiple Access - Collision Detection)]].

### Tramas Ethernet

+ [[Ethernet DIX v2 (Digital, Intel, Xerox)#Trama Ethernet DIX v2|Trama Ethernet DIX v2]]
+ [[Ethernet 802.3]]

#### Ejemplo de una trama Ethernet con analizador de paquetes

![[Pasted image 20240507180939.png|600]]

### Dirección Unicast, Multicast y Broadcast

Esta dirección tiene más usos que simplemente marcar la dirección de origen o destino.

#### Unicast

<u>Es aquella que identifica a una sola dirección</u>. Esto quiere decir que <u>la máquina va a colocar en la dirección de destino la MAC Address de la máquina con la cual se quiere comunicar</u>.

El primer byte de la dirección MAC es un número par. Por ejemplo:

+ **f2:3e:c1:8a:b1:01 es una dirección Unicast porque $f2_{16}$ ($242_{10}$) es un número par**.

#### Broadcast

<u>Broadcast permite que un solo frame sea recibido por todas las estaciones que "vean" el frame</u>.

Sucede cuando necesito preguntarle a todas las máquinas de la red algo en particular. 

Por ejemplo: saber a quien pertenece, que direcciones lógicas puede tener, etc.

+ **Tiene todos los $48$ bits en uno (ff: ff: ff: ff: ff: ff:)**
+ Una dirección Broadcast es un caso especial de dirección Multicast

Es similar a una transmisión radio o de televisión, en donde uno tiene un transmisor y transmite a todos los que puedan escuchar.

Se identifica que se quiere mandar un mensaje de broadcast poniendo en la dirección destino (MAC Address) todos los bits en $1$. En hexadecimal todos los valores en ff.

#### Multicast

<u>Multicast permite que un solo frame Ethernet sea recibido por varias estaciones en forma simultanea</u>.

+ El primer byte de la dirección MAC es un número impar, por ejemplo: 01:00:81:00:01:00 es multicast pues 01 es un número impar.

Es similar al broadcast. En este caso, <u>le vamos a enviar el mismo mensaje a un montón de máquinas pero no a todas</u>. 

Para saber a que máquinas si y que máquinas no se encargan en las capas superiores.

#### Conformación de la MAC Address

Como se conforma la MAC Address: 

+ Los primero 3 bytes corresponden a la empresa que las fábrica. 
	Establecido y asignado por la IEEE.
+ Los últimos 3 bytes es el número de serie que le asigno el proveedor o fabricante a esa placa de red.

### [[CSMA-CD (Carrier Sense Multiple Access - Collision Detection)]]

Notas tomadas en clase:

+ No existe un control centralizado, las señales son transmitidas en forma serial al medio compartido.
+ Los equipos antes de enviar “escuchan el medio (CS - Carrier Sense)” para verificar que el mismo este libre.
+ Si está libre transmiten (MA - Multiple Access) en los dos sentidos. 
  La máquina a quien le interese la información la va a leer y procesar en capas superiores.
+ Si el medio esta ocupado los equipos que quieren transmitir escuchan para detectar cuando se libera.
  Para Tx no debe haber señal (carrier durante 9,6 microsegundos - 12 bytes a 10 Mbps).
+ Si dos equipos verifican que el medio esta libre, ambos transmiten y se produce la colisión CD (Collision Detection).
+ Si la colisión ocurre, los equipos transmiten una **señal de interferencia (JAM)** para asegurar que todos los equipos se enteren de la colisión y a continuación paran de transmitir.

	El Jamming es una secuencia de bits que lo que hace es generar más ruido sobre la línea. Generalmente son 32 bytes que se envían. Esto garantiza que del otro lado, quien esta transmitiendo, escuche que hay una colisión.
+ Para evitar la colisión los equipos esperan un tiempo aleatorio y transmiten nuevamente (Backoff).
+ **Importante**: La trama debe ser lo suficientemente larga como para permitir la detección de la colisión antes de que finalice la transmisión.

Lo primero que hace es verificar/escuchar que nadie este hablando, utilizando el medio (CS). 

Controla el Multiple Access, todos tienen la posibilidad de hablar. El primero que hable y gane el medio va a poder hablar.

Por último identifica si se produjo una colisión al utilizar el medio.

Diagrama de flujo del algoritmo exponencial binario.

![[Pasted image 20240327154554.png|600]]

<u>En el caso en que se produzca una colisión se transmite la señal JAM. Luego inicia el contador de colisiones que se utiliza como exponente en el siguiente paso</u>.

<u>El tiempo que va a esperar es N veces el **time slot**. El time slot es el tiempo que demora la trama más corta en transmitirse según la velocidad del medio. Ese time slot se multiplica por el número random que devuelve el cálculo del **algoritmo exponencial**</u>.

Una vez que se espero el time slot se pone a escuchar la línea y la máquina del otro lado hará lo mismo.

<u>La cantidad de intentos límites para transmitir es 16</u>. Cuando el contador $n$ llega a $16$ la red ya no estará disponible y no transmite más.

**Consideración**: Cuando $n$ llega a $10$, ese número al calcular la $N$ lo fija en $10$. Mientras tanto $n$ va a seguir incrementándose hasta llegar a $16$, pero al calcular $N$ se mantendrá en $10$.  Por lo tanto, el random será un número entre 0 y 1023. 1023 multiplicado por el time slot es una eternidad en el contexto de las redes.

De esta forma se intenta resolver el problema cuando ocurre una colisión.

No todas las redes tienen el mismo time slot.

![[Pasted image 20240622155034.png|400]]

### [[Dominio de colisión y Dominio de broadcast]]

Para comprender estos dominios tenemos que pensar que la red es un único y gran cable coaxial donde conectamos las maquinas.

El primero de los problemas del cable es que, si quisiera agregar una máquina debería cortarlo. Al hacerlo y agregar la máquina, estoy cortando la red completa. Esto no es algo deseado.

El segundo problema es que el coaxial se corte. 

Los problemas de estos dominios es:

Por un lado el dominio de Broadcast, cuando una máquina envía un mensaje, le esta pidiendo a todas las máquinas que le contesten algo. Entonces, <u>un gran problema de estas redes es que cuando una máquina de forma maliciosa o no, empezaban a mandar mensajes de broadcast y todas las demás tenían que contestar. Esto generaba un tráfico en la red extremadamente alto</u>.

Por otro lado el dominio de Colisión, donde se evidencia más es en las máquinas de las puntas que tienen una distancia de cable bastante grande. Esto podía generar que dos máquinas bien alejadas que quieran transmitir información en la misma red al mismo tiempo, tenían muchas tramas que colisionaban, lo que causaba la efectividad de la red.

### Topología 543

<u>El valor **5** establece que voy a tener 5 líneas de cables coaxil</u>. Cada trama puede tener como máximo unos 300mt.

<u>El valor **4** significa que tenemos 4 [[Operación de un repetidor regenerativo|repetidores regenerativos]] vinculando esos cables coaxiles</u>. Cada uno de estos repetidores regenerativos tiene cierto tiempo funcionamiento para regenerar la señal.

<u>El valor 3 es que solamente en 3 de los coaxiles que tenemos hay un host</u>.

Fue usada muy a principios de los 80s.

<u>El principal problema acá es que la máquina que esta en el tramo de arriba tenga que comunicarse con la que esta más lejana, por debajo. Si cada troncal tiene 300mt va a tener una demora en llegar desde la máquina de arriba a la de abajo. Además del tiempo que le ponga el repetidor regenerativo en el medio</u>.

### Longitud Máxima de Ethernet Teórica (sin repetidores regenerativos)

La red Ethernet tiene básicamente 3 medios de comunicación. Coaxil, UTP y fibra óptica. 

A nivel de cable coaxil:

+ Tiene una velocidad de transmisión de unos $200 \space m/\mu s$. 

#### Ethernet (10 Mbps)

Teniendo una trama corta de unos $50 \mu s$ nos da que una red Ethernet de cable coaxil como de máximo $5000 m$. Pero la norma 10 base 5 (coaxil grueso), 10 base 2 (coaxil fino), impone como máximo unos $500m$ en el cable grueso y unos $200 m$ en el cable fino.

#### Fast Ethernet (100 Mbps)

Da que la distancia máxima que podría tener una conexión son $500m$ 

#### Giga Ethernet (1000 Mbps)

Da que la distancia máxima son $50m$. Pero, si nos acordamos de cableado estructurado.  El cable horizontal, la distancia máxima son $90m$ si la máxima teórica son $50m$, algo no esta funcionando.

En el año $96$ sale el estándar de Gigabit y este estándar debía cumplir los siguientes requisitos.

+ Que la red sea compatible con Ethernet o Fast Ethernet. Para que sea compatible la trama. Ósea que cada uno de los campos que vamos a enviar sean iguales. 
+ Utilizar el mismo método de acceso CSMA/CD
+ Debe soportar half y full duplex.
+ Utilizar cables UTP, STP y fibra óptica (tanto multimodo como monomodo). Descarta el coaxil.

**Mención**: Las redes de 10Mb coaxil son todas half duplex. Esto significa que o transmito o escucho. No puedo hacer las dos cosas al mismo tiempo.

Yo estoy siempre escuchando. Si no hay ruido en la línea, si no hay transmisión en la línea, transmito cuando quiero. Termino de hacerlo y vuelvo a escuchar.

### Trama Giga Ethernet

![[Pasted image 20240507221713.png|500]]

<u>El tamaño de trama es aumentado a 512 bytes. Tanto para DIX v2 y la IEEE 802.3 lo mínimo que podía transmitir eran 46 bytes</u>. Sumando todos menos la cabecera de sincronización son 64 bytes.

<u>A esos 512 bytes se los denomina **Carrier Extension**</u>.

Lo mínimo que va a tener es CE: 512 bytes - 64 bytes (de la trama Ethernet) = 448 bytes

Si hacemos la cuenta, para mandar $46$ bytes de datos, estuvimos enviando $512$ bytes, eso me da un rendimiento del $\frac{64 \text{ bytes}}{512 \text{ bytes}} * 100 = 12.5\%$, una porquería.

Para solucionar este problema <u>se agrupan varias tramas cortas hasta completar 1500 bytes, más el frame de transmisión final, a esta técnica se la denomina **Packet Bursting**</u>.

Cuando se trata de enviar tramas cortas, la sobrecarga del "Carrier Extension" puede resultar en un bajo rendimiento de la red debido al uso ineficiente del ancho de banda. La técnica de "Packet Bursting" se utiliza para abordar este problema. En lugar de enviar tramas cortas individualmente, las tramas cortas se agrupan o se "acumulan" en un solo paquete más grande antes de ser transmitidas. Esto significa que múltiples tramas cortas se combinan en un solo paquete para aprovechar mejor el ancho de banda disponible y reducir la sobrecarga del "Carrier Extension". Esto mejora significativamente la eficiencia de la transmisión, ya que se maximiza el uso del ancho de banda disponible y se reduce la sobrecarga de la red.

El objetivo es enviar más de un frame durante un tiempo de transmisión de equipo. La primer transmisión limpia el canal y asegura que no se produzcan colisiones. De esta forma mejoramos el rendimiento de la red.

![[Pasted image 20240507225313.png|500]]

### Concentrador y conmutadores

#### [[Concentrador]]

<u>Tengo múltiples entradas en un dispositivo electrónico y las consolido en una única salida</u>. Es eléctricamente como un cable coaxial lo único que tiene la conversión de que cada una de las bocas del concentrador es una conexión RJ-45 para conectar máquinas a través del hub. 

Intenta solucionar el corte de la red. Tiene la ventaja de que puedo agregar una máquina sin necesidad de cortar la red.

Como el hub, está pensado para reemplazar el cable coaxial y se pensó para trabajar a $10 \text{ Mbs}$. El hub funciona a $10 \text{ Mbs}$ half duplex. En este caso es UTP (fotos del pdf).

![[Pasted image 20240403210046.png|500]]

En este ejemplo, la maquina $A$ se quiere comunicar con la maquina $C$.

La maquina $A$ manda el paquete por el conector $1$. Luego el [[Hub|hub]] recibe esa comunicación, y retransmite por todos los puertos el mismo paquete.

Todas las máquinas que estén conectadas van a poder recibir el mismo paquete.

El dominio de colisión y el dominio de broadcast de este dispositivo es exactamente el mismo que el del coaxial. Cualquiera que envíe un paquete se va a transmitir a todos los puertos, cualquiera que envíe un broadcast se va a transmitir a todos los puertos. Entonces <u>el dominio de colisión y broadcast son todos los puertos que tiene el hub</u>.

#### [[Switch-Conmutador]]

El switch va a analizar el paquete que le llega a cada una de sus bocas para saber a que boca le tiene que enviar el paquete a la salida.

Al tener este comportamiento. Si la máquina $A$ se quiere comunicar con la $C$. Lo que hace es que la máquina $A$ envía el mensaje, pero como el switch no sabe que MAC Address tiene la máquina $C$, lo primero que hace es enviar ese mensaje a todos los puertos anotándose las MAC Address de cada una de las máquinas. 

Una vez hecho esto, cada vez que $A$ se quiera comunicar con $C$, solamente esos puertos van a estar comunicados y la maquina $B$ y $D$ no escuchan absolutamente nada.

<u>El switch tiene la ventaja de que su dominio de colisiones solo es el puerto donde nosotros estamos transmitiendo</u>. Con el único que colisiona es con quien quiera estar comunicado.

<u>El dominio de broadcast es todo el switch</u>. Cuando una máquina manda un broadcast el switch envía el paquete a cada una de las máquinas que estén conectadas. 

---
## Clase 3 - Redes Inalámbricas

En una red [[Redes LAN (Local Area Network)|LAN]] tradicional los clientes y el servidor tienen una ubicación fija.

### Ventajas del mundo inalámbrico

1. **Flexibilidad y movilidad**: Permiten la conexión a Internet y a otros dispositivos sin necesidad de cables, lo que brinda libertad de movimiento y flexibilidad para trabajar desde cualquier lugar dentro del rango de la red.
2. **Fácil instalación y escalabilidad**: Configurar una red inalámbrica es generalmente más sencillo que instalar una red cableada, ya que no requiere la colocación y gestión de cables. Además, es más fácil agregar nuevos dispositivos a la red sin necesidad de extender cables adicionales.
3. **Reducción de costos**: A largo plazo, el mantenimiento de una red inalámbrica puede ser más económico que mantener una red cableada debido a la reducción de costos de instalación y mantenimiento de cables.
4. **Acceso remoto**: Las redes inalámbricas permiten el acceso remoto a la red y a los recursos compartidos, lo que facilita el trabajo desde casa o desde ubicaciones remotas.
5. **Escalabilidad**: Las redes inalámbricas pueden escalar fácilmente para soportar un mayor número de dispositivos y usuarios, lo que las hace ideales para entornos empresariales en crecimiento.
6. **Mayor cobertura**: Las redes inalámbricas pueden extender su alcance mediante la instalación de repetidores o puntos de acceso adicionales, lo que las hace adecuadas para áreas donde no es práctico o posible tender cables.
7. **Facilidad de acceso para dispositivos móviles**: Los dispositivos móviles, como teléfonos inteligentes, tabletas y computadoras portátiles, se pueden conectar fácilmente a redes inalámbricas, lo que permite una conectividad constante mientras se está en movimiento.
8. **Tecnología en evolución**: Las tecnologías inalámbricas están en constante evolución, lo que significa que las redes inalámbricas pueden beneficiarse de mejoras y actualizaciones tecnológicas más rápidas que las redes cableadas.

+ Nos permite movernos por cualquier mientras estemos sobre el alcance de la red, nuestros dispositivos pueden tener servicios.
+ Aparenta no importar la cantidad de dispositivos. Aunque no es tan así. Tiene sus pros y contras.
+ A medida que ponemos más maquinas tenemos una peor calidad de servicio. La potencia influye en el ancho de banda. Todo ruido que haya en el ambiente perturba mucho para las aplicaciones.

Aplicaciones: La primera de las aplicaciones que tienen las redes inalámbricas es extender el cableado actual que tenemos. 

Si pensamos en una empresa en la cual armamos un cableado estructurado. Cada empleado tiene su posición de trabajo pero pueden, llegar proveedores, invitados o lo que sea que necesiten trabajar con una conexión a la red. 

En este punto la conexión inalámbrica es ideal porque estamos dentro de nuestro lugar de trabajo y con especificar un par de parámetros, se le puede dar servicio. 

Una de las primeras cosas que nos permiten es darnos flexibilidad para ampliar la propia red LAN que tenemos armada.

Para otra cosa que nos sirve es para hacer una comunicación entre dos edificios. Supongamos que tenemos otra sucursal de la empresa a cierta distancia y necesitamos vincularlas con una red de datos. Uno de los grandes problema es que no podemos cruzar unos cables por cuestiones técnicas. Entonces, generar una conexión inalámbrica entre estos dos lugares sería posible. A través de de varios km y si no hay líneas de vista se pueden conectar repetidores. El alcance es bastante grande con ciertas consideraciones.

Acceso a viajeros. El mismo caso de personal externo que necesita trabajar en la empresa.

+ Mayor cantidad de usuarios móviles. 
	Todas las redes están diseñadas para abastecer un amplio margen de usuarios. El protocolo que vamos a ver no establece un límite físico de cantidad de usuarios que vamos a tener. Pero cuando analicemos el protocolo nos vamos a dar cuenta que a medida que agreguemos más usuarios la red va a degradar su performance.
+ Edificios difíciles de cablear. 
	Suponer que estamos en un edificios históricos en los cuales uno no puede romper las paredes para pasar cableado ni hacer un pasaje de cables prolijamente sin desvirtuar la belleza del lugar. En este caso es muy beneficioso utilizar redes inalámbricas. 

### Conexión ad hoc

+ Definición: [[Red Ad Hoc]]

<u>Este tipo de conexión es cuando queremos conectar dos equipos entre si sin que intervenga un tercero</u>. En el caso de una red cableada lo que haríamos sería poner los dos [[Host]] juntos a través de un cable cruzado y establecemos un vinculo entre estos dos.

En el mundo inalámbrico es prácticamente lo mismo. Hay dos topologías de red que nos permiten hacer esto. Una es [[Red Ad Hoc|Ad Hoc]] y las otras, que se llaman conexiones de infraestructura donde si interfiere un tercero en el medio, por ejemplo cuando nos conectamos todos a un Switch o a un Hub el cual es un punto donde se concentran todas las comunicaciones (en el mundo inalámbrico hay algo similar a eso).

### ¿Qué vamos a necesitar de una red inalámbrica?

<u>Primero rendimiento. Cuando hablamos de rendimiento nos referimos al ancho de banda que le vamos a dar a los usuarios, tiempos de respuesta, latencia</u>. La idea es que la red sea lo más parecido a tener una performance de una red cableada.

<u>Poder abastecer una gran cantidad de nodos</u>.

<u>Poder conectar la red inalámbrica a la red local de la empresa, edificio lo que sea</u>. Que la red nos permita hacer una especie de extensión de la red local. Esto no quiere decir que sea su único propósito. Podemos tener una red inalámbrica totalmente separada de otra red.

Esta ligada al consumo de energía. Lo vivimos a diario con nuestro celular. A medida que levantamos más cantidad de redes, ya sean de tipo. Si empezamos a tener fluctuaciones en las redes de datos que pasa de la 2g, 3g, 4g, si se activa o desactiva el wifi, si activamos o desactivamos cosas el consumo de energía se hace evidente. <u>Poder conectar la red inalámbrica a la red local de la empresa, edificio lo que sea</u>.

### Seguridad

Cuando nosotros estamos en una red cableada, salvo que alguien corte el cable o se meta dentro de un equipo nuestro, las comunicaciones son totalmente privadas, nadie las ve. 

En cambio en una comunicación inalámbrica, <u>cualquier receptor que este dentro del radio de cobertura podría tener la capacidad de ver los datos que estamos transfiriendo</u>. Hay tecnologías que permiten mejorar esto haciéndolo prácticamente similar a la red cableada. Pero siempre tener en cuenta de que no es lo mismo.

Dispositivos que funcionan en un rango de frecuencias y con un nivel de potencia que las secretarías de comunicaciones de todos los países del mundo lo declararon como frecuencias que no se licencian. Son libres para que se utilicen para este tipo de servicios. A la frecuencia con la cual están trabajando con la potencia especifica, no perturban a vecinos. 

Si nos fijamos con detectores de redes wifi en nuestras casa, la señal que más potencias tiene es la propia y va a capturar la red de algún vecino, pero no la de todos los vecinos, solo algunas. Esto es porque se maneja un nivel de potencia muy corto. Pero cuando debemos hacer un enlace radioeléctrico de mucha distancia, por ejemplo 20 km, primero no se utilizan las mismas bandas de frecuencias sino que son otras parecidas, y lo segundo es que se utilizan niveles de potencias superiores a lo que podrían ser un dispositivo para un edificio o una casa. 

Entonces para ese tipo de servicios hay que pagarle al estado una licencia para el uso del espacio radioeléctrico. Eso es parte de las licencias que hay que pagar en un sistema inalámbrico. Otro podría ser algún servicio particular. Por ejemplo, empresas como motorola, siemens, ya tenían compradas al gobierno ciertas bandas de frecuencias. Hoy en día por ejemplo personal, movistar, claro, ellos tienen compradas las bandas de frecuencias para brindar el servicio 2g, 3g, 4g, 5g, etc.

### Itinerancia

<u>La itinerancia significa que yo voy a pasar de una red a otra red y voy a seguir teniendo servicio sin necesidad de hacer nada</u>. Es como cuando hablamos por teléfono y estamos haciendo varios km y la llamada no se corta. O estamos navegando en internet mirando un video y el video no se corta. En el trayecto estamos pasando por un montón de redes distintas, antenas distintas. Es una de las cosas que las redes inalámbricas tengan. 

### Configuración dinámica

Una de las cosas que debe permitir el medio inalámbrico es que no tengamos que configurar nada y esto se haga solo y funcione correctamente. Vamos a ver que eso relativo. Aunque son mínimas las cosas que se deben configurar.

### ¿Qué medios físicos utilizan las redes inalámbricas?

Bien sabemos que las ondas electromagnéticas viajan a través de los campos. <u>El campo eléctrico y el campo electromagnético y se propagan a través de un medio, el aire, el vacio, un gas, un cable, etc</u>.

#### Infrarrojo

Los medios inalámbricos tienen que utilizar un medio físico o una forma de utilizar ese medio físico. Un medio que se utilizó y se sigue utilizando hoy en día es el [[Infrarrojo]]. Este podría considerarse un tipo de comunicación [[Red Ad Hoc|Ad Hoc]] ya que es necesario que los dispositivos que se comuniquen estén cercanos entre si y no existe un intermediario. 

El problema de los infrarrojo es que si algo se interpone en el camino entre el transmisor y el receptor, la comunicación se corta. Otro inconveniente es que si estamos en un lugar donde hay mucha luz solar, como esta tiene componentes de longitudes de onda infrarroja, muchas veces satura al receptor y cuando intentamos transmitir, el receptor, al estar saturado, no escucha nada.

#### Radiofrecuencia

Básicamente una conexión bluetooth, wifi, WiMAX, cualquier conexión inalámbrica vía radiofrecuencia. Su ventaja es que no sufre lo mismo que el infrarrojo. 

Por más que tapemos el receptor, si la señal electromagnética atraviesa el material, la comunicación va a seguir funcionando. Lo que si se vera afectado es que los distintos materiales que estén atravesados entre el transmisor y el receptor absorben cierta cantidad de señal y puede hacer que no lleguemos a excitar al receptor del otro lado.

### Infraestructura

Cuando hablamos de infraestructura estamos hablando de que existe un componente intermedio que es quien nos facilita la comunicación entre los diversos nodos que se quieran conectar a la red inalámbrica.

Si por ejemplo tenemos 3 nodos (computadora, celular, tablet, cualquier cosa que tenga una conexión inalámbrica), A, B, C. Se tienen que conectar a la red para poder traficar información entre ellos. Para lograrlo, <u>necesitan un dispositivo intermedio que se llama **Access Point (AP)**. Es quien se va a encargar de toda la comunicación entrante y saliente, entre los distintos nodos y el AP y viceversa</u>.

<u>Este conjunto (AP y los nodos), se los llama **conjunto de servicios básicos**. Eso lo que hace es que únicamente esos nodos se conecten entre si y que no hayan comunicaciones con ningún otro</u>.

Podría tener otros 3 nodos que forman otra red con su propio AP y forman otro conjunto de servicios básicos número 2.

Son dos conjuntos básicos separados. Entre ellos no se ven.

<u>Hay una forma de vincular ambos conjuntos básicos a través de un dispositivo o de varios dispositivos y formar un conjunto de **servicios básicos distribuido o extendido**</u>.

<u>Cada uno de los servicios básicos y el conjunto de los servicios extendidos, lo que me va a permitir es tener parte de las características que estábamos requiriendo. Rendimiento, movilidad, itinerancia, etc</u>.

#### [[Espectro ensanchado]]

Es una forma de transmitir un mensaje a través de una red dentro de un espectro electromagnético. <u>Lo que sucede es que, uno no manda el mensaje por una única frecuencia, sino que esta va cambiando de cierta manera con cierto patrón</u>. 

Entonces, si yo estoy transmitiendo en una única frecuencia, cualquier ruido que yo tenga en esa frecuencia el mensaje no llega, pero si voy variando la frecuencia en la cual estoy transmitiendo el mensaje, puede ser que un pedacito me llegue pero lo demás va a llegar. Se utiliza en wifi, bluetooth, entre otros.

---
### Norma IEEE 802.11

La Norma IEEE 802.11 <u>es un conjunto de estándares que define los protocolos de redes inalámbricas locales (WLAN, Wireless Local Area Network)</u>. Estos estándares son desarrollados por el Instituto de Ingenieros Eléctricos y Electrónicos (IEEE, por sus siglas en inglés) y establecen las especificaciones para las tecnologías de redes Wi-Fi.

La norma IEEE 802.11 ha evolucionado a lo largo del tiempo con diversas revisiones para abordar mejoras en velocidad, alcance, seguridad y otras características. 

Algunas de las revisiones más comunes incluyen:

1. IEEE 802.11b: Introdujo velocidades de hasta 11 Mbps en la banda de frecuencia de 2.4 GHz.
2. IEEE 802.11a: Operaba en la banda de frecuencia de 5 GHz, ofreciendo velocidades de hasta 54 Mbps.
3. IEEE 802.11g: Compatible con el estándar 802.11b pero con velocidades mejoradas de hasta 54 Mbps en la banda de 2.4 GHz.
4. IEEE 802.11n: Introdujo tecnologías como MIMO (Multiple Input, Multiple Output) para mejorar el rendimiento y la cobertura, con velocidades de hasta 600 Mbps.
5. IEEE 802.11ac: Conocido como Wi-Fi 5, ofrece velocidades de hasta varios gigabits por segundo y opera en la banda de frecuencia de 5 GHz.
6. IEEE 802.11ax: También conocido como Wi-Fi 6, es la última revisión de la norma hasta la fecha (2022), diseñada para mejorar la eficiencia y el rendimiento en entornos con alta densidad de dispositivos.

Estos estándares definen cómo los dispositivos WLAN se comunican entre sí, incluyendo la modulación, la codificación, el acceso al medio, la autenticación y la encriptación. La norma IEEE 802.11 ha sido fundamental para el desarrollo y la adopción generalizada de las tecnologías Wi-Fi en una variedad de dispositivos y aplicaciones.

---

Definen ancho de banda, velocidad de operación, qué frecuencias maneja, qué canales va a tener, etc. Pero el concepto de como funcionan todos los wifi es el mismo.

La diferencia entre $5\text{ Ghz}$ es que tenemos distintos anchos de banda que podemos utilizar a nivel de frecuencia. Hay canales con 20Mhz, 40Mhz, 80Mhz y 160Mhz. Están todos en la misma banda de frecuencia pero los canales son más grandes. 

Es importante tener en cuenta que el uso de anchos de banda más amplios también puede aumentar la probabilidad de interferencia entre canales adyacentes.

### Dos grandes problemas en el mundo inalámbrico

En el mundo alámbrico conectamos la PC a la red y todos los que están en la red pueden verme y al igual que yo a ellos.

<u>En el mundo inalámbrico tenemos dos grandes problemas llamados, el problema del **nodo oculto** y el problema del **nodo expuesto**</u>. 

#### Nodo oculto

<u>En el nodo oculto, yo creo que el canal está libre y voy a transmitir. Pero realmente el canal se encuentra ocupado y mi comunicación es frustrada</u>.

##### Ejemplo de nodo oculto

En este ejemplo, el nodo $\text{A}$ quiere comunicarse con el nodo $\text{B}$ y, de la misma forma, el nodo $\text{D}$ quiere comunicarse con el nodo $\text{B}$. Ambos en forma simultanea. 

Como el nodo $\text{A}$ y el nodo $\text{D}$ no se escuchan entre si porque están bastante lejos, los dos pueden transmitir al mismo tiempo y el nodo $\text{B}$ no sabe a quien escuchar y a quien contestar.

![[Pasted image 20240508001855.png|250]]

Este es el problema de los nodos ocultos. <u>Son dos nodos que entre si no se escuchan, pero al tercero, al que se quieren transmitir cada uno de ellos si llegan</u>.

#### Nodo expuesto

<u>En el nodo expuesto, yo quiero transmitir, pero como escucho ruido en la línea, no lo hago, aún teniendo la posibilidad de transmitir al nodo que yo necesito hacerlo</u>.

##### Ejemplo de nodo expuesto

En este ejemplo, el nodo $\text{B}$ quiere comunicarse con el nodo $\text{A}$. El nodo $\text{C}$ sabe de está comunicación porque escucha a $\text{B}$. 

Sería erróneo suponer para $\text{C}$ que no pueda transmitir a cualquier otro nodo solo por escuchar a $\text{B}$.

![[Pasted image 20240508002056.png|250]]

#### Protocolo CSMA-CA

La forma de resolver este problema es a través de un protocolo llamado [[CSMA-CA (Carrier Sense Multiple Access With Collission Avoidance)|CSMA-CA]].

En el mundo inalámbrico lo que voy a tratar de evitar es que se produzca una colisión, ¿lo voy a cumplir? No. Pero por lo menos lo voy a intentar evitar. 

Imaginemos que tengo 2 computadoras, $\text{A}$ y $\text{B}$ que se quieren comunicar, cada una tiene su línea de tiempo. <u>Cuando yo me quiero comunicar le voy a mandar un mensaje a la máquina diciéndole RTS (Request To Sed - una petición diciendo que estoy listo para enviar datos)</u>.

La computadora $\text{B}$, si está escuchando y otra computadora le está enviando datos no podrá contestar pero, si está dispuesta a capturar esos datos, <u>me va a contestar con un mensaje CTS (Clear To Send)</u>.

Luego de recibir el CTS, se envían el o los paquetes de datos (DATA) y una vez que los paquetes llegaron sin inconvenientes. 

Recordar que estamos en un protocolo de capa 2. Esta capa es la unica que maneja el encabezado, los datos y la cola detrás que generalmente es un CRC o algún método de verificación que nos especifica si lo que nos llega es correcto. 

Si esto se produce con éxito se envía un $\text{ACK}$ (Acknowledgement).

![[Pasted image 20240622201150.png|200]]

Características:

+ El mensaje $\text{RTS}$ contiene la dirección de destino y la duración de la transmisión
+ Las estaciones conocen el tiempo que deben esperar antes de intentar transmitir
+ El destino envía un mensaje corto llamado $\text{CTS}$
+ El mensaje $\text{CTS}$ indica a la fuente que puede enviar la información sin que se presenten colisiones

### Trama

![[Pasted image 20240508003303.png|600]]

La longitud de los campos es en Bytes. La trama es muy similar a la trama Ethernet.

**Frame Control (Control de trama - 2 bytes)**: En Ethernet, el protocolo no incluye mecanismos de negociación previa a la transmisión o confirmación explícita de recepción como parte de su operación estándar. CSMA/CA, en cambio, requiere un sistema más elaborado de control de acceso al medio para evitar colisiones en entornos inalámbricos. 

El campo Frame Control en CSMA/CA cumple esta función, permitiendo:

- Negociación previa a la transmisión (como RTS/CTS)
- Confirmación de recepción (ACK)
- Identificación del tipo de trama (datos, control, gestión)

<u>Va a establecer si es una trama de datos, si es una trama de supervisión, de control, etc</u>.

**Duration ID (2 bytes)**: Dependiendo de los datos que vengan en el frame control, este campo <u>va a tener la duración que va a tener la trama, o un ID que está muy relacionado con el tipo de dato que venga en el primer campo</u>.

**3 MAC Address consecutivas (6 bytes)**: Es nivel dos por lo que las únicas direcciones que se manejan son MAC Address. 

Tenemos $3$ direcciones:

+ Dirección de **destino**
+ Dirección de **origen**
+ Dirección del **AP**

Ahí generamos un conjunto de servicios básicos. 

**Sequence Control (2 bytes)**: Cuando yo estoy mandando muchas tramas de datos le especifico que "esta es la primer trama, esta es la segunda, esta es la tercera", etc. En definitiva <u>le voy pasando la cantidad de tramas que le voy a enviando</u>. 

Lo que puede suceder es que me lleguen tramas repetidas, pero como tiene número de secuencia, las descarta.

**MAC Address 4 (6 bytes)**: <u>Es la dirección del conmutador del servicio</u>. Es lo que nos permite generar un conjunto de servicios extendido y que todas las comunicaciones entre AP y los nodos se pueda generar sin problemas.

**Datos (Frame Body - entre 0 y 2312 bytes)**: Es un campo variable.

En algunas ocasiones, cuando se trata de tener la menor cantidad de fragmentación posible. Lo que se hace es ajustar el tamaño máximo de datos que se puede mandar por trama a los $1500$ bytes que tiene Ethernet por cuestiones de compatibilidad.

**CRC (4 bytes)**: Verifica la integridad de cada trama y si hay errores en la transmisión. Si llegó mal se descarta.

#### Tipos de tramas

Hablamos ya como es la trama genérica para el envío de datos en el protocolo 802.11. 

También mencionamos que teníamos distintos tipos de tramas y que dependiendo del tipo, cambia un poco el formato de la misma.

<u>Los tipos de tramas que tenemos son</u>:

+ **Tramas de control**
	+ Sondeo de ahorro de energía
	+ Solicitud para transmitir (RTS)
	+ Permiso para enviar (CTS)
+ **Tramas de supervisión**
	+ Utilizadas para gestionar las comunicaciones entre las estaciones y los AP
+ **Trama de datos**
	+ Existen 8 tipos, pero solamente 4 transportan datos de las capas superiores

#### Métodos de acceso al medio

Hay dos métodos de acceso al medio:

+ **Método de acceso por coordinación distribuida (DIFS)**: Es un método probabilístico, más parecido a lo que es el mundo Ethernet en donde todos tienen la misma probabilidad de tomar el medio.
+ **Coordinación puntual**: Es más parecido al mundo de Token Ring (cuando una máquina tiene el Token, recién en ese momento puede transmitir y mientras no lo tenga no puede). La función puntual tiene este tipo de funcionamiento en cuanto el acceso al medio.

Por lo general, todas las conexiones wifi que vamos a ver son todas distribuidas. 

##### Funcionamiento de la forma distribuida - DIFS

Algunas definiciones:

+ **DIFS (Distributed Interframe Space)**: Intervalo de tiempo que espera una estación después de detectar que el medio está libre antes de iniciar el contador de **backoff**. Es utilizado para asegurarse de que el medio esté realmente libre.
+ **SIFS (Short Interframe Space)**: Intervalo de tiempo más corto que DIFS, <u>utilizado entre la transmisión de una trama y la recepción de su ACK, o entre una trama de datos y su respuesta (por ejemplo, RTS/CTS)</u>.
+ **Backoff**: Tiempo de espera aleatorio que una estación utiliza para reducir la probabilidad de colisiones. Cada estación selecciona un valor aleatorio dentro de un rango predefinido y espera ese tiempo antes de intentar acceder al medio.

![[Captura de pantalla 2024-06-22 204927.png|400]]

Paso por paso:

1. **Inicio**: Todas las estaciones (A, B y C) comienzan con un periodo DIFS (Distributed Inter-Frame Space). Este es un tiempo de espera estándar antes de cualquier transmisión.
2. **Primera transmisión (A a B)**:
    + Estación $\text{A}$ transmite una trama a la estación $\text{B}$.
    + Después de la trama, hay un breve periodo SIFS (Short Inter-Frame Space).
    + $\text{B}$ responde con un $\text{ACK}$, confirmando la recepción exitosa de la trama de $\text{A}$.
3. **Segunda fase**:
    + Todas las estaciones observan otro periodo DIFS.
    + $\text{A}$ y $\text{C}$ entran en periodos de backoff (tiempo de espera aleatorio).
    + El backoff de $\text{C}$ es más corto, por lo que termina primero.
4. **Segunda transmisión (C a B)**:
    + $\text{C}$ transmite su trama a $\text{B}$.
    + Después de la trama de $\text{C}$, hay otro SIFS.
    + $\text{B}$ responde con un $\text{ACK}$ para la trama de $\text{C}$.
5. **Tercera fase**:
    + Nuevamente, todas las estaciones observan un periodo DIFS.
    + $\text{A}$ y $\text{C}$ entran en nuevos periodos de backoff.

<u>El Slot Time depende de cada una de las normas que estemos usando</u>. Entonces, cada una de las máquinas va a calcular su Back Off.

**Ese Back Off depende de 2 cosas**:

+ De la cantidad de veces que lo calculó.
+ Del Slot Time (depende de la norma que utilice)

$\text{Back Off = Random (0 ; CW)} \text{ × } \text{Slot Time}$

Donde:

+ CW: $\large2^{i} - 1$ con $\large i \geq 3$ hasta $8$.
	$i$ es la cantidad de veces que lo calculó al Back Off. Ese número va entre 3 y 8.

En el primer intento, vemos que el Back Off va a calcular entre 0 y 7 slot time. El segundo intento va a ser entre 0 y 15 ($2^{4} - 1$), después va a ir incrementando. 8 es el máximo. Entonces, entre 0 y 255 van a ser todas las retransmisiones que siguen. 

<u>La ventana de contención funciona estableciendo un rango de tiempo durante el cual los dispositivos deben esperar antes de transmitir sus datos</u>.

### Aspectos de seguridad

Originalmente, la red 802.11 no tenía seguridad. Para mejorarla, <u>se implementó el algoritmo **WEP**, que utilizaba una clave de 64 o 128 bits configurada manualmente tanto en el origen como en el destino para todas las transmisiones</u>.

En 2001, se demostró que WEP era vulnerable. Entonces, nació el **WPA** (Acceso Protegido de WiFi). WPA utilizaba algoritmos de hashing (SHA, RSA, MD5) y agregaba una clave aleatoria a la clave manual para cada conexión, mejorando la seguridad aunque no fue muy usado.

<u>Actualmente, se utiliza **WPA2**, que emplea el concepto de clave pública y privada, ofreciendo mayor seguridad que WEP y WPA, aunque no es completamente inviolable</u>. La configuración de todos estos protocolos es similar, diferenciándose en el nivel de seguridad.

Finalmente, los distintos protocolos WiFi incluyen el original 802.11, y sus versiones sucesoras como 802.11a, 802.11b, etc. Esta información se puede encontrar organizada en cuadros comparativos.

### ¿Por qué el servicio del wireless o del 802.11 tiene menor tasa de transferencia?

<u>Por todos estos tiempos que perdemos entre cada uno de los frames que mandamos, además de todo el overhead de control y supervisión que estamos haciendo. El RTS, el CTS, por más que sean tramas pequeñas, es tiempo que estamos perdiendo. En cambio en Ethernet, escucho el canal libre y puedo transmitir. Es mucho mejor</u>.

El Access Point, tenemos que interpretarlo como si fuera el hub de Ethernet. Que es un cable en donde mi dominio de colisión y de broadcast, son todas las máquinas. En Ethernet nosotros tenemos la posibilidad de, en vez de poner un hub que se comporta de esa forma, poner un Switch que lo que hace es que, mi dominio de colisión sea nada más que el puerto, aunque el broadcast es todo. Entonces tengo una alta probabilidad de siempre estar transmitiendo a la máxima velocidad posible, sobre todo si voy entre dos máquinas que solo están hablando entre ellas. 

---
## Clase 4 - Capa de red

La finalidad de la capa de red es <u>proporcionar un mecanismo para enrutar los datos a través de una red de manera eficiente y confiable</u>. 

Esta capa se encuentra en la tercera posición del modelo OSI y se encarga de varias funciones clave:

1. **Enrutamiento**: <u>Determina la mejor ruta para que los datos viajen desde el origen hasta el destino a través de la red</u>. Utiliza algoritmos de enrutamiento para tomar decisiones sobre cómo enviar los datos de manera óptima, teniendo en cuenta factores como la congestión de la red, la velocidad de los enlaces y la disponibilidad de rutas alternativas.
2. **Direccionamiento**: <u>Cada dispositivo en una red tiene una dirección única para identificarlo</u>. La capa de red utiliza direcciones lógicas (como direcciones IP en el modelo TCP/IP) para identificar los dispositivos y enrutar los datos hacia ellos.
3. **Fragmentación y reensamblaje de paquetes**: <u>Cuando los datos son demasiado grandes para ser transmitidos en un solo paquete, la capa de red se encarga de dividirlos en fragmentos más pequeños, enviarlos a través de la red y luego reensamblarlos en el destino</u>.
4. **Control de flujo**: <u>La capa de red puede controlar el flujo de datos para evitar la congestión en la red</u>, utilizando técnicas como la regulación del flujo y el control de la congestión para garantizar una transmisión suave y eficiente de datos.

### IP (Internet Protocol)

El término "IP" significa "Protocolo de Internet" (Internet Protocol, en inglés). <u>Es un conjunto de reglas y normas que permiten que los dispositivos se comuniquen entre sí a través de una red de computadoras, como Internet</u>. 

El Protocolo de Internet (IP) es un componente fundamental del modelo TCP/IP, que es el conjunto de protocolos utilizado para la comunicación en Internet y en muchas redes locales.

El Protocolo de Internet (IP) se encarga principalmente de dos funciones clave:

1. **Direccionamiento de red**: <u>Cada dispositivo conectado a una red tiene una dirección única, llamada dirección IP, que le permite ser identificado y localizado en la red</u>.
   
   Las direcciones IP pueden ser IPv4 (version 4) o IPv6 (version 6), y son utilizadas para dirigir los paquetes de datos a su destino.
2. **Enrutamiento de paquetes**: El Protocolo de Internet (IP) determina cómo se envían los paquetes de datos desde el origen hasta el destino a través de una red. 
   
   Utiliza direcciones IP para encaminar los paquetes a través de routers y switches, siguiendo la mejor ruta disponible hacia su destino final.

<u>El servicio es "no confiable" dado que la entrega no está garantizada</u>. Los paquetes (datagramas) se pueden, perder, duplicar, retrasar o entregar sin orden. IP no informará de esto ni al receptor ni al emisor.

<u>El servicio es sin conexión, dado que cada paquete es tratado en forma independiente de todos los demás, no hay circuitos virtuales</u>.

Por lo tanto es **NO orientado a la conexión** y **NO confiable**.

#### Formato del [[Datagrama IP]]

### Protocolos ARP/RARP

+ [[Protocolo ARP (Address Resolution Protocol)]]
+ [[Protocolo RARP (Reverse Address Resolution Protocol)]]

### Direcciones IPv4

+ [[Protocolo IPv4]]

---
## Clase 5

### ¿Como una máquina descubre a otra dentro de una red?, ¿Que mecanismo hay para que dos máquinas en una red o dos máquinas en distintas redes puedan encontrarse? 

Hay un protocolo llamado [[Protocolo ARP (Address Resolution Protocol)|ARP]]. Lo que hace es como encuentro una máquina dentro de la red.

El protocolo lo que va a tratar de hacer es, internamente en cada uno de los host, generar una pequeña tanda, en donde lo que hace es una <u>asociación entre la dirección física o MAC Address (nivel 2 - Capa de enlace de datos), con la dirección lógica o IP (nivel 3 - Capa de red)</u>.

#### ¿Como funciona?

Suponer que A quiere comunicarse con C. La máquina A ya conoce cual es la dirección lógica o IP de la máquina C. 

¿Que metodología podría utilizar para descubrir cual es la dirección física a la cual tiene que mandar esta información?

Lo que hace la máquina A va a ser enviar un Broadcast diciendo "¿Quién tiene la dirección física de tal dirección IP?", y si alguna tiene esa dirección física va a contestar, "soy yo, tengo esa MAC Address".

El paquete que va a mandar el protocolo ARP tiene 4 campos:

+ La **MAC de destino** es el broadcast: La MAC Address de broadcast es cuando todos sus bits están en 1, lo mismo que decir, por ejemplo FF:FF:FF:FF:FF:FF (es un ejemplo, en este caso son solo $6$ bytes).
+ La **MAC de origen**. La que tengo <u>grabada en la propia placa de red</u>.
+ **IP de origen**.
+ **IP destino**. Para saber que MAC Address tiene la IP destino.

Eso viaja en un broadcast a través de la red a todos los host. Entonces la máquina C dice "escuche un broadcast en la red y tiene como IP destino la IP que yo tengo asignada". La máquina B no contesta nada, pero la máquina C contesta con un paquete que tiene las mismas característica pero con una pequeña salvedad.

+ **MAC de origen** (del host C)
+ **IP de origen** (del host C)
+ **MAC de destino** (del host A)
+ **IP de destino** (del host A)

La máquina A va a tener una pequeña tabla con la MAC Address y la IP del host C.

![[Pasted image 20240423221258.png|500]]

Hay otro protocolo que se llama [[Protocolo RARP (Reverse Address Resolution Protocol)|RARP]] que lo que hace es lo contrario. A través de la posición física obtener la posición lógica. Entonces puedo preguntar por IP o por MAC Address.

---
### Varias redes LAN

Lo anterior era un ejemplo en base a una única red que podría ser una red LAN. Yo estoy en un único segmento de red por lo que cualquier mensajería entre ellas siempre está dentro de la misma LAN y es alcanzado por un broadcast (de nivel 2).

Cuando tengo varias redes que comunicar debemos recordar que el modelo OSI dice que, solo me puedo comunicar en forma horizontal en el mismo nivel o capa en el cual estoy hablando, ósea que una red LAN únicamente se puede comunicar con otra red LAN si hay un equipo físico que los vincula, por ejemplo, un equipo físico de nivel 2 puede ser un [[Switch-Conmutador|Switch/Conmutador]] o un [[Hub]].

Si yo tengo que comunicar dos redes que no están en el mismo segmento sino que están separadas física y lógicamente, necesito poner un dispositivo de nivel 3, porque quien comunica entre diferentes redes es la capa de red. Ese dispositivo se llama [[Router]].

El Router no deja de ser un [[Host]] especial. Le decimos especial porque el router tiene multiples interfaces. Generalmente dos o más. Los host comunes como una PC tienen una única interfaz aunque no es del todo cierto, pero usualmente es así. 

<u>En el router tienen la misma importancia cada una de las interfaces y lo que hace es manejar el tráfico de red de una interfaz a la otra</u>.

El router habla en nivel 3, entonces un broadcast hecho en nivel 2, el router lo va a cortar. 

### Aplicación del protocolo ARP en redes diferentes

¿Como haría una máquina que esta en una red con otra máquina que está en la otra red?, ¿Cómo lograría aplicar el protocolo ARP?

![[Pasted image 20240423223649.png|500]]

Hay una solución que permite que esto funcione de esa manera. 

Por ejemplo, suponer que la máquina A quiere comunicarse con la maquina Y. 

Lo que va a hacer la máquina A es tirar un broadcast a su propia red ya que este es de capa 2 y el router pertenece a capa 3. La máquina A conoce la dirección lógica de Y.

<u>Cuando el broadcast llega al router. Si ninguno de los equipos de la propia LAN contesta que tiene esa dirección lógica, el router lo que va hacer, aunque sepa como llegar o no, es contestar con su propia MAC Address, luego evalúa como resolverlo</u>.

Los paquetes de petición y respuesta serán los siguientes:

![[Pasted image 20240424132938.png|500]]

![[Pasted image 20240424133204.png|100]]

<u>Una vez que la máquina A obtuvo la MAC Address del router le va a enviar el paquete para el host Y y este se va a encargar de hacerlo llegar. Luego el router le dirá si conoce la dirección</u>.

Cuando tenemos una red, el router va a encontrar el broadcast y su dominio va a quedar confinado en cada una de las interfaces del mismo. Si tenemos un hub el dominio de broadcast y colisión son todos los puertos que tenga dicho hub. Si es un switch, el dominio de colisión es únicamente el puerto y el dominio de broadcast es todos lo que tenga el switch conectado. 

### [[Protocolo DHCP (Dynamic Host Configuration Protocol)]]

Hasta ahora vimos como hacía una máquina para, conociendo la dirección lógica, obtener la dirección física del dispositivo. <u>Requisito indispensable para una comunicación de nivel 2</u>.

Ahora lo que tenemos que ver es, <u>¿Cómo tenemos nosotros una dirección lógica/IP?</u>

Una dirección lógica se puede establecer de varias formas. La primera forma es asignarlo manualmente. La segunda forma es que alguien mas las asigne por nosotros. El protocolo que lleva a cabo está acción se llama [[Protocolo DHCP (Dynamic Host Configuration Protocol)|DHCP]].

<u>Lo que hace este protocolo es escuchar peticiones de los distintos hosts para poder asignarles una IP</u>. Generalmente hay un servidor que trabaja en este protocolo el cual tiene algo llamado pool de direcciones de IP. Básicamente es, "yo te voy a asignar dentro de esta red una dirección IP que está desde tal dirección hasta tal dirección. Un rango de direcciones IP validas".

Parámetros que puedo asignar desde el servidor DHCP: <u>Las básicas son la propia IP de la máquina con la mascara y el default gateway</u>. Lo cual es lo mínimo e indispensable para comunicarse.

+ Dirección del servidor [[DNS (Domain Name System)]]
+ Dominios DNS
+ Default Gateway
+ Broadcast Address
+ Máscara de subred
+ Tiempo máximo de espera del [[Protocolo ARP (Address Resolution Protocol)|ARP]]
+ MTU (Maximum Segment Size - Unidad de Transferencia Máxima) para la interfaz
+ Servidores NTP: Network Time Protocol. Es un protocolo que permite tener sincronizado los relojes de las máquinas. Esto es importante para poder tener la misma fecha y hora al hacer una transacción.
+ Servidor SMTP
+ Nombre del servidor de nombres de Windows (WINS)

#### ¿Cómo funciona el protocolo DHCP?

El protocolo DHCP está compuesto por 4 palabras:

+ **Discovery**: El cliente le dice al servidor DHCP que no tiene una IP y que
   necesita una.
+ **Offer**: El servidor contesta con un paquete llamado "Offer" que contiene cierto rango de direcciones IP's disponibles.
+ **Request**: Obtenida está respuesta, el host cliente le va a contestar con un ok, y le pide una de las IP's que le ofreció el servidor.
  
   El ofrecimiento y el pedido se hace porque en medio de esta secuencia, puede haber otro pedido por parte de otros hosts, a quienes les ofrece el mismo abanico de opciones.
+ **Acknowledge**: Si la elección es posible, el host que realizó el pedido recibe un ACK, de lo contrario, debe volver al punto de discovery.

![[Pasted image 20240424144559.png|150]]

### [[Subnetting]]

Como ya vimos tenemos clases que tienen muy pocas redes, pero muchos hosts, y clases con muchas redes, pero pocos hosts. Entonces hay un desperdicio muy grande de direcciones IP.

#### [[CIDR (Classless Inter Domain Routing)]]

---

Básicamente significa dejar de utilizar clases y comenzar a manipular con las mascaras de distintas maneras para poder partir redes muy grandes en redes más chicas para poder administrar de forma más eficiente esos rangos de direcciones.

Al igual que el CIDR el VLCM tiene el mismo propósito aplicado de manera diferente. 

#### Ejemplo

Una IP v4 sin clase.

Voy a tener estos 3 octetos fijos y el cuarto octeto que son los últimos 8 bits que va a tener esa dirección IP es donde yo tengo los distintos tipos de hosts.

$192.168.1.$\__ \__ \__ \__ $\space$ \__ \__ \__ \__

Esa es una única red. Si trabajamos con clase sería una única red y todo lo que esta dentro pertenece a esa única red.

Pero ahora tenemos una problemática. Tengo solo ese rango de IP's y tengo 5 sectores distintos a los cuales yo tengo que dividir esa red para que estos sectores no se comuniquen entre si.

**Sectores**: Sistemas, cobros, facturación, RRHH, Administración.

Entonces. En la parte del host (el último octeto), lo que vamos a hacer, de alguna forma con las **mascaras**, trabajar para que, <u>unos bits indiquen lo que es la red y otros bits indiquen el host</u>.

¿Cuantos bits? La cantidad de bits va a depender de cuantos sectores yo tengo que dividir. En cuanto voy a dividir esa red que tengo. En este caso tengo 5 sectores. 

¿Cuantos bits voy a necesitar elegir para poder seleccionar 5 redes distintas? $2^{3}$. 

Entonces, lo primero que hacemos es <u>partir 3 bits de la dirección IP los cuales van a indicar lo que es la red</u>.

$192.168.1.$\__ \__ \__ | \__ $\space$ \__ \__ \__ \__

Por lo tanto:

|  1  |  2  |  3  |     |                |
| :-: | :-: | :-: | :-: | -------------- |
|  0  |  0  |  0  |  0  |                |
|  0  |  0  |  1  |  1  | Sistemas       |
|  0  |  1  |  0  |  2  | Cobros         |
|  0  |  1  |  1  |  3  | Facturación    |
|  1  |  0  |  0  |  4  | RRHH           |
|  1  |  0  |  1  |  5  | Administración |
|  1  |  1  |  0  |  6  |                |
|  1  |  1  |  1  |  7  |                |
Pequeña salvedad: Solo por compatibilidad, la red que tiene todos los bits 0 y la que tiene los bits en 1, no se utilizan. Originalmente estas no se utilizaban. Pero se pueden utilizar igualmente, en esta materia trabajaremos así.

<u>A la redes las llamaremos por su numero en binario</u>. 

Después lo que vamos a tener, de la parte siguiente a las redes, voy a tener $2^{n}-2$ hosts. Porque hay dos hosts que no se pueden usar. El que tiene todos sus valores en 0, porque ese indica la red y el que tiene todos los bits en 1, ese indica el broadcast de IP (no confundir el [[Broadcast de capa 2 y broadcast de capa 3|broadcast de capa 2 con el broadcast de capa 3]]).

A partir de esta distribución, voy a tener $2^{3}$ redes y $2^{n}-2$ hosts. Por lo tanto, por cada red (6 redes) voy a tener 30 hosts para poder asignarles IP.

Ejemplo:

$192.168.1. \textcolor{#cd9324}{0 1 0}$ | \__ $\space$ \__ \__ \__ \__

En este ejemplo es, para la red de cobros, la cual tiene asignado el número 2 en binario, quiero saber cual es el host número 1.

Lo que hago es escribir el 2 en la parte red y del lado host voy a poner el primer host valido, que es el número 1.

$192.168.1. \textcolor{#cd9324}{0 1 0} \space | \space \textcolor{#85EF47}{00001}$

¿Esto que dice?

Primero, hay dos formas de clasificar las mascaras. Utilizando como van configuradas las computadoras 255:255:255:0 por ejemplo una mascara natural de clase C o también lo que se suele poner para abreviar es barra (/) y la cantidad de bits que están en la mascara.

En este caso, si fuera la clase natural de la clase C, sería barra 24, porque la clase C tiene 24 bits hasta llegar a los siguientes 8 de host (filmina 2 PDF direcciones IPV4), pero como además robe 3 bits más para la red, sería barra /27.

$192.168.1. \textcolor{#cd9324}{0 1 0} \space | \space \textcolor{#85EF47}{00001} /27$

Finalmente convertimos a decimal la parte binaria y quedaría, en este caso:

$192.168.1.65/27$

En otro caso, si quisiera el host 8 de la red de facturación sería:

$192.168.1. \textcolor{#cd9324}{0 1 1} \space | \space \textcolor{#85EF47}{01000} /27$

$192.168.1.104 /27$

## Trabajos prácticos

+ [[TP - Subnetting]]

---
## Clase 6 - Tecnología VLAN y protocolo STP

Tanto el protocolo STP como la tecnología VLAN son de la capa de enlace.

Ambos se utilizan para resolver algunos problemas que teníamos cuando configurábamos o teníamos equipos en capa 2, en este caso los Switches.

### Tecnología VLAN

Habíamos visto que, cuando un host en un Switch mandaba un broadcast, este se propagaba por todos los puertos del Switch y el único host que detiene eso, cuando estoy vinculando varios Switches a través de un router, el único que lo detiene es el router. 

Recordar que, en el [[Protocolo ARP (Address Resolution Protocol)]], cuando un host quería preguntar por una IP de otra red que no es la de él, lo que hacía era enviar un ARP y el router le contesta con su propia IP.

<u>En el protocolo VLAN, una de las cosas que permite hacer es reducir, dentro del Switch, el dominio de colisiones [[Dominio de colisión y Dominio de broadcast#Dominio de colisión|dominio de colisiones]]</u>.

Otra cosa que permite el Switch es, supongamos que tenemos un Switch de $48$ bocas y nosotros queremos hacer $3$ redes separadas. Estamos en un edificio, el Switch de $48$ bocas está conectado al cableado estructurado y queremos que en un piso, las oficinas estén separadas. En las diferentes oficinas tengo cierta cantidad de hosts. Si yo conecto, todas las máquinas en un mismo Switch, estarían todas en la misma red LAN y se verían todas con todas, pero las oficinas deben estar separadas.

Entonces, <u>lo que nos permite este protocolo VLAN es, partir los puertos del Switch que necesitemos y hacer un Switch más pequeño con la cantidad de puertos que se necesitan para cada una de las oficinas. Esa partición no es física sino que es lógica</u>.

Entonces, podemos dividir un Switch físico en varios "mini Switches" lógicos que nos permiten tener más de una red dentro del mismo equipo físico.

Una recomendación es que por cada VLAN, solo pongamos una red IP. <u>Recordemos que VLAN es capa 2, y la red IP es capa 3</u>. La recomendación es poner, en cada Switch, en cada VLAN que armemos, un segmento de IP separado.

¿Podría poner en un Switch distintos segmentos de IP? Si. Lo que pasa es que estaría pasándoles por ejemplo, mensajes de broadcast a los puertos que no son necesarios.

Lo que conviene es que, por cada VLAN, por cada partición lógica que haya que hacerle a ese Switch, a cada una le asigno una subred IP diferente. Obviamente que, para poder interconectar las distintas redes, voy a tener que poner un router para que las pueda comunicar.

#### Motivos de uso de VLAN's 

Razones por las cuales utilizamos VLAN:

+ **Adaptación a diferentes estructuras organizacionales**: Suponer que en este piso tengo varias oficinas donde cada oficina es una empresa distinta. Si el día de mañana, una empresa que esta en este mismo piso, compra otra oficina de al lado, a través de las VLAN's, con solo configurar el Switch, ya se pueden ver todas las máquinas de las dos oficinas. Como es una partición lógica, se puede manejar por comandos y es algo bastante simple de hacer. 
+ **Reducir la contención por el uso de red**: Si yo particiono el Switch en varios pedazos pequeños, <u>el broadcast queda contenido por los puertos en donde la VLAN está actuando</u>. 
  
	Si el switch tiene $48$ puertos y no tuviera VLAN, mando un broadcast por el puerto 1 y lo va a mandar a todos los demás $47$ puertos que me quedan. Si tengo VLAN hecha, y la VLAN abarca $10$ puertos, cuando mando el broadcast por ese puerto de la VLAN, solo se van a esos $10$. Los otros $38$ puertos van a estar sin ningún tipo de tráfico. Entonces reduzco la contención del uso de red.
+ **Permite balancear la carga de red**: Permiten balancear la carga de red principalmente debido a su capacidad para segmentar el tráfico en redes lógicas separadas dentro de una misma red física.
+ **Facilita agregar y cambiar de lugar las computadoras, reduciendo así costos de administración**: El mismo caso de una empresa que alquilo otra oficina más y solo con configurar los puertos que van hacía la otra oficina, entran dentro de la misma red.
+ **Ayuda a implantar políticas de seguridad**: Esto tenemos que verlo como políticas que se pueden aplicar a la capa de enlace de datos. Más adelante cuando analicemos protocolos de capa 4, vamos a ver algún tipo de dispositivo que permite ajustar más la seguridad.
   
  En este caso particular, lo que dice es si yo circunscribo mi red a los puertos pura y exclusivamente donde tengo conectado mis equipos, cualquiera que se conecte en otro puerto del Switch, no va a escuchar nada.
  
  Las redes Ethernet al principio eran con un cable coaxial y lo que transmite la computadora, lo ve todo el que este conectado al cable coaxial. Lo mismo pasa si en vez de un cable coaxial pongo un hub, porque el hub lo que hace es poner en electronica, el mismo funcionamiento que si fuera el cable coaxial. Entonces, cualquier que se enchufe en un hub con una computadora y la pusiera a escuchar, podría ver todos los paquetes que están pasando por la red y podría sacar información de esa forma. 
  
	Con los Switches es un poco más difícil porque únicamente tiene trafico entre los puertos que se están llamando. Lo único que podría ver una computadora conectada a un puerto del Switch que no pertenezca a la red, serían los mensajes de broadcast. Pero después los mensajes entre hosts, no los vería.
  
	Si solo activo los puertos de donde tengo computadoras validas, dentro de la VLAN's, ninguno de los otros puertos va a ni siquiera escuchar el broadcast. Entonces la seguridad se entiende por ese lado.
+ **Permite reubicar servidores en lugares físicamente apropiados**: Necesito cambiar un servidor que esta en una oficina, lo llevo a otra, pero que tiene que seguir perteneciendo a la red anterior, lo configuro del otro lado, es de la VLAN tal y el servidor se sigue viendo perfectamente.

#### Ejemplo de VLAN

Hoy en día, yo tengo una fábrica, en donde tengo un switch con $8$ hosts conectados de las $16$ bocas habilitadas. 

Luego tengo una oficina de sistemas con otro switch con $16$ bocas y estoy utilizando $8$ bocas.

Para poder vincular al area de sistemas con la fábrica, como son dos redes separadas, es necesario colocar un router.

Si se agranda la empresa, colocamos un área de administración y RRHH con $8$ hosts cada una, y las colocamos al router para que este comunicada con las demás.

![[Pasted image 20240501142445.png|500]]

Cada uno de estos Switches a nivel 2 es una red y a nivel 3 se vinculan todos a través del router.

Si se quisiera crear un nuevo lugar, por ejemplo facturación y cobros, podría otro Switch, debería apagar el router, ponerle otra placa, encender el router y hacer el cable entre router y Switch de facturación y cobros.

¿Cuál es el problema?, <u>los Routers no tienen placas infinitas</u>. Están limitados.

##### ¿Como resolvería esto con VLAN's?

Primero, tendría un único Router. Si bien se muestra como una única interfaz, pensemos que el router podría tener del otro lado otra interfaz con Ethernet.

Tengo un Switch para cada sector con la cantidad de maquinas que necesite cada uno.

![[Pasted image 20240501152224.png|500]]

<u>Cada uno de los puertos en donde se conectan las máquinas se llaman Access Port (puertos de acceso), estos son únicamente para que se conecten hosts</u>. El protocolo que hablan estos puertos es Ethernet.

<u>Después, desde el Switch de la fábrica hasta el router está conectado por un puerto que se llama trunk o puerto de transito</u>. Lo que permite este puerto es que por esa interfaz viajen todos los paquetes de la VLAN que está configurada. Allí viaja, <u>no solo la trama Ethernet sino un par de campos adicionales con la información de las VLAN's</u>.

Luego, cada uno de los demás Switches está conectado al Switch de la fábrica a través de un puerto trunk también. Con esto logro que la información que está en una de las VLAN's pueda pasar por el Switch de la fábrica hasta llegar al router.

##### ¿Como resolvemos el ejemplo anterior realmente empleando VLAN's? 

En el ejemplo anterior. La única diferencia fue que sacamos el router central con las interfaces de red y pusimos un router con una única interfaz en donde, de forma virtual, reciben información de todas las VLAN's y poder procesarlas.

¿Cómo reducimos este hardware?, porque colocar $4$ Switches o 4 interfaces en el router es desperdiciar plata, no estamos aprovechando todas los puertos. 

Lo que vamos a hacer es que, con los 2 Switches que tenemos, tratar de dar el mismo servicio.

![[Pasted image 20240501154119.png|600]]

<u>La topología que se esta utilizando es la siguiente</u>: Tenemos dos Switches conectados entre si por la boca $1$ a la $16$ del otro en modo trunk. De la misma forma el SW2 esta conectado a la interfaz del router.

Luego comenzamos a separar las bocas de los Switches en grupos que conforman las diferentes VLAN's que necesitamos. Para ello obviamente debo configurar cada uno de estos grupos para que pertenezca a la VLAN que necesitamos.

#### Trama 802.1Q para el manejo de VLAN's

A fines de los 80s, principio de los 90s, el IEEE (recordemos que el 802 es todo lo que tiene que ver con networking), se preguntó como se podría hacer para segmentar lógicamente el Switch.

![[Pasted image 20240501162231.png|500]]

<u>Por lo que creó fue un protocolo que se llama **802.1Q** que corresponde a las VLAN's</u>.

Este funciona de la siguiente manera. Se parte la trama Ethernet. Después, de los dos campos de dirección, el Switch los separa y le agrega los campos de las VLAN's y al terminar, concatena los campos siguientes.

#### ¿Dónde se hace esta transformación?

<u>Los hosts, establecidos como **Access Port**, no entienden del protocolo 802.1Q. Entonces los puertos conectados en modo Access, lo que hacen es procesar los paquetes Ethernet.</u> 

<u>Cuando el Switch recibe un paquete Ethernet desde afuera hacía adentro, hace el siguiente trabajo</u>:

+ <u>Toma el paquete Ethernet, separa las direcciones y le agrega la etiqueta de la VLAN y luego continua con el paquete</u>.
+ <u>Luego cuando viene un paquete desde adentro del Switch hacía afuera, ósea hacía un host. Lo que hace es abrir el paquete, quitarle lo correspondiente a la VLAN, y vuelve a concatenar con lo que corresponde a la trama Ethernet y el paquete sigue su rumbo</u>.

<u>Un puerto en modo **Trunk**, maneja la trama 802.1Q directamente</u>. Por lo que no debe hacer nada, no debe modificarlo.

<u>Por eso, un hosts especial, en este caso un router, puede interpretar el paquete 802.1Q</u>.

#### ¿Qué agrega la trama 802.1Q?

Primero le agrega:

+ **Tag de protocolo (16 bits)**: El valor en el hexadecimal que coloca ahí es el **X'81 00'** correspondiente a la trama 802.1Q.

**¿Porque está este campo si sería el mismo paquete?**

<u>Lo que puede pasar es que haya un Switch que esta trabajando con Ethernet y otro Switch trabajando con otro tipo de protocolo</u>. Entonces, ese campo de protocolo sirve para indicar que tipo de protocolo es el que estoy manejando.

En los Switches vamos a ver el 81 00, pero hay que entender que puede venir otro número en este lugar.

La siguiente etiqueta se divide en 3 partes.

+ **Bits de prioridad (3 bits)**: <u>Como son 3 bits tengo 8 niveles de prioridad distintos. Es para mejorar un poco el trafico, no influye mucho</u>.
+ **Después está el campo CFI (1 bit)**: <u>Identifica el tipo de red que viene por ahí. Si está en 0 es Ethernet, si es 1 es token ring</u>.
+ **Número de VLAN (12 bits)**: <u>Las VLAN's son números. Generalmente las trabajamos con nombre, pero son números que la identifican. Si tengo 12 bits podría tener 4096 diferentes, con algunas excepciones</u>.

Esta es la configuración de VLAN que tienen los Switches Cisco. La VLAN 1 es la que viene por defecto, no puede ser borrada ni nada. Cuando uno enciende un Switch por primera vez, todos ellos están en la VLAN 1.

![[Pasted image 20240501164740.png|600]]

Luego de 2 al 1005 uno puede crear cualquiera de esas VLAN's sin ningún tipo de problema. 

Del 1006 al 4094, se pueden crear y usar pero siempre se manejan con un estado siempre activo y la VLAN está siempre habilitada.

Después están los puertos particulares utilizados internamente como se ve en la imagen.

#### Anotación - Aclaración

**Tema broadcast**: <u>Si yo mando un broadcast en la red de Sistemas dicho paquete se va a replicar en el puerto 1, 2, 3, en el 2 del otro Switch. Va a viajar por el enlace de trunk y también va a viajar hacía el router. El dominio de broadcast de esa red de sistemas son estos puertos que se mencionan</u>.

Lo mismo la fábrica. El broadcast que se mande en la fábrica no va a salir de ese switch, solo va a ir hacía esos puertos y hacía el router.

Una comunicación entre el host A de sistemas y el host D de sistemas, entra en el puerto 1 del SW1, ahí le va a grabar las etiquetas de su VLAN, va a pasar por el puerto trunk, hasta el puerto 2 ahí le va a sacar el paquete de VLAN, lo va a convertir de nuevo a Ethernet y se lo va a mandar a la maquina D.

<u>Además, en cada uno de los Switches tenemos una base de datos de VLAN's (VLAN database). Esa base de datos generalmente tiene el nombre con el número</u>.

Por ejemplo la VLAN de sistemas es la 10, la de fábrica es la 11, la de Administración es la 1115, y la de rrhh es la 3027. Los números no tienen que ser correlativos, solo tienen que tener un significado para el administrador. El nombre es de fantasia, el protocolo no maneja nombres.

**Otro punto importante es el puerto trunk**: <u>En el puerto trunk viajan los paquetes de la 802.1Q con la información de las VLAN's. Pero no necesariamente viaja la información de todas las VLAN's</u>. 

¿Qué sentido tiene que un paquete que está en el Switch 1 que corresponde a la fábrica, viaje hacía el otro Switch si no tiene maquinas de fábrica?

Entonces lo que se hace es lo siguiente. Se especifica en el puerto trunk del Switch 2 que se comunique con el Switch 1 únicamente para las VLAN0s de Sistemas, RRHH y administración, para lo que Fábrica no. De esta forma se reduce el tráfico de red entre Switches.

<u>Al router le vamos a decir que se comunique con todas las VLAN's juntas</u>.

### [[STP (Spanning Tree Protocol)|Protocolo STP (Spanning Tree Protocol)]]

<u>¿Que sucede si se rompe el enlace entre los Switches, o entre los Switches y el router?</u>

Estamos en un problema. La IEEE, para solucionar la pérdida de un enlace, lamentablemente no queda otra que agregar otro enlace. <u>Aunque no es tan simple como parece manejar redundancia</u>. 

Tenemos que contar dos cosas:

+ <u>Incremento en costos</u>, porque para tener alta disponibilidad debo duplicar equipamiento, Switches, enlaces, servidores, etc. La administración de algo en alta disponibilidad requiere de muchos cuidados.
+ A nivel red básicamente lo que vamos a hacer es generar, entre el Switch y el router (en este ejemplo, pero podría ser otro enlace), vamos a poner, en el router, dos placas de red y en el Switch utilizar dos puertos del mismo. 

Si yo tengo que conectar un Switch con el otro, voy a tener que colocar otro enlace entre el SW1 y el SW2. Si tuviera más Switches tengo que ver que tipo de topología utilizo, pero básicamente es aplicar redundancia de distintos enlaces.

<u>El protocolo del Spanning Tree es el **802.1D**</u>.

Se utiliza para:

+ <u>Se utiliza para alta disponibilidad en redes a nivel capa de enlace</u>.
+ <u>Bucles físicos</u>. Si yo tengo dos dispositivos que están transmitiendo información y se puede dar el caso de que transmitan información por varios puertos al mismo tiempo, se podría llegar a generar un bucle.
+ <u>Inconsistencias en tabla MAC/Puerto</u>. La VLAN database me indica el número de VLAN y a que puertos está asignado. El Switch guarda una pequeña tabla que dice en este puerto tengo asignada esta MAC Address, eso es para que cuando venga un paquete hacía dicha MAC Address vaya directamente a ese puerto y no tenga que ir a buscarlo.
  
	Si tenemos varios enlaces físicos por donde ven las MAC Address, ¿A cuál se lo tiene que mandar? Eso es otro problema.
+ <u>No existe en capa 2 el equivalente al TTL</u>. En capa 3 teníamos el campo TTL (Time To Live). Que, a medida que pasaba por los routers iba decrementando 1, y cuando llegaba a cero el datagram IP se dropeaba. Como no tenemos esto, el paquete podría llegar a vivir de por vida en nuestra red, ocupando recursos y saturándola.

#### Ejemplo de STP

El STP funciona con VLAN's. Los ejemplos que vamos a ver son <u>sin VLAN</u>.

En este ejemplo, el host A se quiere comunicar con el B y B se quiere comunicar con A. Simple.

El SW1, en su tabla de puerto/Mac, va a registrar la MAC Address de la maquina A (puerto 3). 

El paquete va a pasar por el puerto trunk del SW1 hacía el SW2. Pregunta a las máquinas cual es la maquina B.

El SW2, en su tabla de puerto/Mac va a registrar que la máquina A viene del puerto 1 porque viene desde el trunk y va a decir que la máquina B está en el puerto 2, va a llegar el paquete y así se va a hacer la comunicación completa.

![[Pasted image 20240501185341.png|400]]

##### ¿Qué sucede si agregamos otro enlace?

Tenemos el mismo caso. A se quiere comunicar con B.

Todo es igual, pero cuando A envía el paquete, este viaja por las dos interfaces trunk. Viaja por la interfaz que está en el puerto 1, y por la del puerto 8.

![[Pasted image 20240501184208.png|600]]

Ahora tengo que la maquina A viene desde el puerto 1 y 8 en el SW2. 

<u>Ahora la máquina B, ¿Cómo resuelve este problema?, porque me está llegando el mismo mensaje por dos puertos distintos</u>.

<u>A parte, suponer que envío un broadcast. Este estaría enviando por todos los puertos y cuando llega al SW2, le envía por todos los puertos también. Esto generaría una mega tormenta de broadcast de forma indefinida porque no tenemos el TTL</u>.

##### Funcionamiento del protocolo STP

Cuando el Switch enciende, lo primero que hace es tomar su MAC Address. <u>Con la MAC Address lo que hace es calcular su número de identificación. Ese número le va a permitir, dentro del Spanning Tree, quien va a ser el va a comandar el protocolo en si</u>. 

<u>Cuando el nodo enciende, tiene su propia MAC Address o sus propios datos de equipo y el que tenga el número más chico va a convertirse en el nodo raíz o nodo root de la red</u>. Esto pasa cada vez que haya enlaces redundantes.

Cuando pasa esto, <u>el nodo va a agarrar y va a generar un paquete que se llama BPDU que es quien informa el protocolo de STP</u>.

Una vez que el SW levanta, calcula su identificador, que lo hace con la prioridad que tiene y su propia MAC Address, lo que hace es mandar un paquete de **BPDU** a los puertos del SW a los cuales está conectado. 

![[Pasted image 20240501185945.png|300]]

El que tenga el número más pequeño es el que se convierte en el SW raíz. <u>Una vez que esté designado el SW raíz lo que va a hacer es obtener los puertos designados (PD) y los puertos raíz (PR)</u>.

Lo primero que va a hacer es establecer los puertos designados (PD). <u>Los primeros puertos designados son los puertos del SW raíz que tienen conexión con otros Switches</u>.

<u>Luego, los otros Switches van a designar como puerto raíz (PR), aquellos que están conectados contra el SW raíz y también aquellos que estén más cerca del SW raíz, los demás serán todos PD</u>.

<u>Hay un puerto nuevo que es el **puerto bloqueado**. Son aquellos puertos por el cual no va a pasar tráfico de datos. Van a pasar los paquetes (BPDU), pero no paquetes de datos</u>.

<u>La finalidad del puerto bloqueado es para que no se generen bucles</u>. Recordar el problema que había con el broadcast en el caso anterior.

<u>El puerto bloqueado será el que tenga la MAC Address más alta. La prioridad más alta</u>.

Como todos los puertos se manejan a nivel VLAN, si yo tengo VLAN's hechas en los Switches voy a tener que manejar el protocolo de Spanning Tree por cada una de las VLAN's que tenga.

Si yo tengo los Switches sin VLAN's, es una única configuración de STP.

###### ¿Que sucede si se cae un enlace?

Supongamos que, el enlace entre el SW1 y el SW2 se cae. Los paquetes de BPDU van a detectar que ese enlace se cayó y van a empezar a pasar por todos los demás puertos para encontrar un camino y seguir manteniendo la redundancia.

En ese caso, los BPDU van a salir del SW raíz, van a pasar por el SW3, por el SW4, van a llegar al SW2 y no siguen pasando más. Entonces, <u>el puerto bloqueado en el SW4 se va a desbloquear y va a quedar como un puerto raíz, porque es el que más cerca del SW raíz</u>. El puerto 1 del SW4 se va a cambiar como puerto designado y así sucesivamente.

##### Problema del STP

Toda esta secuencia de detectar que el enlace se cayó, reasignar y cambiar puertos, etc. <u>Es un proceso que demora maso menos 40s, 50s, 1 minuto, dependiendo la complejidad de la topología</u>. 

Eso significa que durante un minuto, no tenemos red. <u>Por eso es altamente crítico que los cables de red estén bien hechos</u>. 

<u>Un cable de red que vincule 2 Switches y que este haciendo falso contacto (en la jerga se llama flapeo), te tira la red. Porque se la pasa recalculando los caminos</u>.

#### Estados de los puertos

Como ya se dijo, el protocolo designa a los puertos en diferentes estados.

Estos son:

+ **Bloqueados (blocking)**: Solo pueden recibir BPDU, los datos se descartan. No aprenden (20 Seg). Este es el tiempo en que llegan estos mensajes por ese puerto.
+ **Escucha (listening)**: Analiza los BPDU para asegurarse la no existencia de loops (15 Seg).
+ **Aprendizaje (learning)**: No se envían datos, analiza los BPDU y aprende rutas y MAC Address (15 Seg).
+ **Envío (forwarding)**: Se reciben y envían tramas Ethernet. Puertos comunes.
+ **Inhabilitado (disable)**: Port apagado por el administrador (shutdown). Una buena practica es tener los puertos que no usamos apagados. Esto se hace de forma lógica.

---
## Clase 7 - Capa de red - IPv6

Recordemos el subnetting. Este había nacido porque trabajar con clase dejaba un segmento muy grande donde teníamos pocas redes y muchos hosts. 

Luego teníamos las clase A, B, C y eso desperdiciaba muchas direcciones IP's.

Luego de esto apareció el [[Subnetting]] donde se trataba de optimizar un poco esto, pero teníamos el siguiente problema.

La cantidad máxima direccionable (teóricamente, ya que esto no es del todo cierto), es $2^{32}$, lo que da más de 4 mil millones de direcciones. Para los 70s, 80s, era enorme, pero con el tiempo se agotaron.

Está de más decir que existió IPv3, IPv2, IPv1, solo que fueron experimentales. La que llegó al mercado fue IPv4.

Cuando las direcciones quedaron cortas, en los años 90s comenzaron a trabajar en otro protocolo.

El primer protocolo en el cual se pusieron a trabajar fue IPv5. Estaba más avanzado que IPv4. Muy orientado a lo que hoy llamamos el streaming. Pero este no llegó a ver la luz, porque se pusieron a trabajar en IPv6 y se dieron cuenta de que este tenía más flexibilidad para manejar las cosas.

### ¿Qué tiene de importante IPv6?

Las direcciones son de $128$ bits. $2^{128}$ es un número enorme.

Trajo mejoras en cosas que IPv4 no tenía como:

+ **Calidad de servicio**
+ **Seguridad**
+ **Movilidad**

Todavía le cuesta un poco a IPv6 generarse globalmente por muchas cuestiones. Pero de a poco toma terreno.

El LACNIC anunció que no entrega más direcciones IPv4. Cuando uno es un ISP, o una empresa grande que tenga suficiente porte para pedir un bloque de direcciones IP y tiene que brindar servicio a sus clientes, debe ir al LACNIC, comprarlos, y estos eran asignados.

A partir del 2020, no asigna más bloques IPv4 y asigna IPv6.

<u>¿Esto trae problemas a la empresa?, en principio no. Si uno comienza desde 0, trabaja directamente con IPv6</u>.

El gran problema que tienen las grandes empresas, ISP, laboratorios, etc., es la convivencia entre IPv6 e IPv4.

<u>En IPv6 NO existe el subnetting</u>. Si bien existe rangos de direccionamiento privado, hoy en día se le puede dar direcciones públicas a todos.

Por ejemplo: Yo soy un ISP y entrego una dirección IP en tu modem router y dentro se distribuye con algún direccionamiento IP privado. Generalmente $192.168.1.0/24$ y ese modem router debe hacer una operación que se llama nand, es una traducción de direcciones de red de las direcciones privadas a la pública para poder navegar por internet.

Con IPv6 directamente a cada una de esas maquinas, en vez de darles una dirección privada, les doy una dirección pública. Entonces las máquinas es como que están conectadas derecho a internet. No necesitan ninguna traducción de direcciones.

### Terminología

+ Nodo: Dispositivo que implementa IPv6
+ Router: Nodo que reenvía paquetes IPv6
+ Host: Cualquier otro nodo que no sea un router
+ Capa Superior: Protocolo que está por encima de IPv6 (TCP, UDP, ICMP, etc.). 
	Es cuando hablamos de capa 4, capa 5, capa 6, capa 7.
+ Enlace: Medio o entidad de comunicaciones
+ Vecino: Nodo conectados al mismo enlace
+ Interfaz: Conexión del nodo al link (enlace). Es la placa de red.
+ Dirección: Identificación IPv6 de una interfaz o conjunto de interfaces de un nodo. 
	Es una dirección IPv6.
+ Paquete: Una cabecera IPv6 junto a los datos
+ MTU de Enlace: Unidad de transmisión máxima.
  Es el MTU de la capa 2.
+ MTU de ruta: MTU mínima en el camino que recorren los paquetes entre 2 nodos finales

### Paquete o datagrama IPv6

![[Pasted image 20240510131838.png|500]]

**Cabecera**: La cabecera es fija y siempre está presente. Tiene $40$ bytes, siempre.

**Extension/es de cabecera**: Este campo no es siempre el mismo, porque en realidad, una de las cosa que maneja IPv6, al contrario de IPv4, recordemos que en IPv4 teníamos la cabecera, y después teníamos opciones que las indicábamos diciendo, "tengo una longitud de cabecera más grande y el campo de opciones, dependiendo de las opciones que ponía, podía crecer o decrecer (la cabecera), pero tenía un valor fijo".

<u>Acá la extensión de cabecera se van apilando y puede tener la longitud que necesite</u>. Lo importante acá es que las extensiones de cabecera se van apilando. 

Ejemplos:

+ Si necesito que los datos que voy a manejar vayan encriptados. Entonces le pongo una cabecera de encriptación.
+ Si quiero que los datos estén fragmentados, entonces le pongo una cabecera de fragmentación. 
+ Si quiero que los datos sigan una ruta en particular, entonces le pongo una cabecera de enrutamiento.

Esto es lo que tiene de bueno el protocolo. Me permite extenderlo de forma dinámica. Le puedo decir que haga lo que yo necesite.

<u>Tener en cuenta que las extensiones tienen un orden y hay restricciones</u>.

**Datos de la capa superior (protocolos de nivel superior)**: Cuando hablamos de los datos de la capa superior, ¿Qué va por ahí?, nosotros con un paquete de capa 3, lo que estamos mandando como dato es, la cabecera de capa 4 + los datos de capa 4. Los datos de capa 4 tienen la cabecera de capa 5 + los datos, y así sucesivamente, se van apilando.

<u>Otra cosa que tiene este paquete es el tamaño de la carga útil</u>. Acá son $65.535$ bytes ($2^{16}$), pero <u>hay una opción que se llaman **jumbo frames** que se utiliza cuando uno tiene ciertas condiciones de capa 2 que te permita mandar paquetes extremadamente grandes y con los jumbo frames podríamos llegar hasta paquetes de 4GB, depende mucho de como es la capa 2</u>.

Todo esto conforma el datagram IPv6.

<u>Los jumbo grams es cuando tenes un protocolo de capa 2 que te lo permita utilizar. La ventaja de tener paquetes tan grandes es que el rendimiento del protocolo es mucho más eficiente</u>. ($\text{Cant. Datos Reales Enviados} / \text{Cant. Total del Paquete Enviado}$). Cuanto más grande es la cantidad reales de datos sobre el paquete total, mejor rendimiento se tiene.

#### Cabecera IPv6

![[Pasted image 20240510141038.png|500]]

**Version (4 bits)**: Como es IPv6 se envía el número 6.

**Clase de trafico (8 bits)**: Los primeros 6 bits es algo similar al servicio diferenciado de IPv4. Lo único es que se agregan 2 bits que tienen que ver con la congestión. 

En IPv4 lo que puedo decir es, "tengo congestión en mi camino ascendente (cuando estoy transmitiendo) o tengo congestión en mi camino descendente (cuando estoy recibiendo)". Hay dos bits que explícitamente indican la congestión, dentro de este mismo campo obviamente.

**Etiqueta de flujo (20 bits)**: Identifica el paquete dentro de un camino. 

Entre el host A y el host B yo estoy mandando siempre paquetes con datos, bueno, ese flujo de paquetes con datos lo identifico con una etiqueta. Esto ayuda a que el trafico sea más rápido, ya que no tengo que analizar toda la cabecera, sino que se ese flujo y lo mando, no tengo que mirar los demás campos que vienen en la cabecera. Sobre todo cuando tengo un flujo continuo de información.

**Longitud de carga útil (16 bits)**: Al ser 16 bits, son los 65.536 bytes que puede transportar IPv6. Si la longitud de carga útil está en 0, ósea todos los bits están en $0$ es que estamos mandando jumbo grams, y esto significa que va a haber una cabecera de jumbo grams.

**Próxima cabecera (8 bits)**: Indica cual es la cabecera que sigue. Si ese campo tiene un valor significa que hay más que le van a seguir. Obviamente cada cabecera tiene un tag de próxima cabecera. Depende el número que vaya ahí es la cabecera que va a seguir a continuación de está. Ósea entre la dirección de destino y la carga útil va a haber otra cabecera.

**Límite de saltos (8 bits)**: Es similar al TTL. Cada vez que voy pasando por un router descarto uno, y cuando llego a 0, el datagrama IPv6 se liquida.

**Dirección Origen (128 bits - 16 bytes)**: Está llevando 4 palabras de 32 bits.

**Dirección de Destino (128 bits - 16 bytes)**: Se está llevando 4 palabras de 32 bits.

**Carga útil**.

#### Próxima cabecera

Las cabeceras son examinadas en el nodo destino, salvo cuando el valor del campo es "0". 

Cada nodo que llegue va a analizar la cabecera.

Existen cabeceras especificas por función:

+ Salto a salto (0)
+ Encapsulado de Cabecera IPv6 (41)
+ Ruteo (43)
+ Fragmentación (44)
+ Encriptación (50)
+ Autenticación (51). Garantizar que el paquete lo estoy mandando yo.
+ Que no hay próxima cabecera(59)
+ Si es una cabecera de algún protocolo superior: 
	+ TCP (6)
	+ UDP (17)
	+ ICMPv6 (58). Es el protocolo con el que se envía el PING por ejemplo.
+ Opciones para el destino (60)
+ Movilidad (135)

Las cabeceras se procesan en orden riguroso. No hay forma de que uno pueda escribirlas mal, sino el paquete se descarta.

#### Diferencias entre la cabecera IPv6 - IPv4

+ En IPv6 tiene un tamaño fijo de 40 bytes. En IPv4 el tamaño era dinámico.
+ Direcciones de 32 a 128 bits.
+ No existe campo de tamaño de cabecera. La cabecera es fija así que no tiene sentido.
+ No existen campos de fragmentación. Para eso generamos una cabecera a parte.
+ No existe campo de suma de verificación. No existe el Checksum.
+ Nuevo campo, la Etiqueta de flujo.
+ TOS o DSF pasa a llamarse Clase de tráfico e incluye la congestión.
+ El campo Protocolo pasa a tener Cabecera de extensión.
+ Cambia el TTL por el campo de Próximo salto.
+ Las cabeceras no son compatibles. Entonces, cuando la placa de red levanta el stack de protocolo y el mismo va a decidir si va para un lado o para otro y eso lo hace con campo de versión.

#### Extensión de Cabecera IPv6

Según RFC8200 las siguientes cabeceras deben aparecer, de existir, en el siguiente orden:

+ Encabezado IPv6 (obligatoria)
+ Salto a salto. Los datos que tiene de salto a salto tiene que ser examinado por cada uno de los saltos para poder tener un análisis de las rutas.
  Entonces en cada salto voy a estar examinando como fue el ruteo que estuvo teniendo ese paquete.
+ Opciones de destino (procesada por todos los nodos)
+ Ruteo. Generalmente se utiliza más que nada cuando estamos utilizando movilidad. El algoritmo va a tratar de buscar la forma más eficiente de hace llegar el paquete a destino. De eso se trata.
+ Fragmentación. Para fragmentar el datagrama. Tengo una red para abajo que no me aguanta el paquete y bueno, lo voy a tener que fragmentar.
+ Autenticación. Que los datos sean auténticos.
+ Seguridad. 
  Que los datos vayan cifrados. Lo hace el propio protocolo, no debo preocuparme en capas superiores de hacerlo.
  Obviamente lo va a hacer en el nodo donde lo transmite.
+ Opciones de destino (procesado por el destino final)
+ Encabezado capas superior (TCP, UDP, etc.)

Cada extensión de cabecera tiene un límite de $8$ bytes ($64$ bits). En realidad puede ser más pequeña pero este es el límite máximo.

Las extensiones de cabecera que tiene tamaño fijo son múltiplo de $8$ bytes.

Las extensiones de cabecera que tiene tamaño variable, se agrega un relleno para que sean múltiplo de $8$.

---

En IPv4 el paquete más chico podía ser de 64 bytes. Cuando uno trabaja en IPv6, creo que el más chico es de 1280 bytes. Ósea que en redes viejas no funciona.

##### Como vamos apilando las cabeceras

![[Pasted image 20240510145134.png|400]]

Tengo una cabecera IPv6 en la cual dice que la próxima es una cabecera TCP. Entonces voy a tener una cabecera TCP y los datos.

Esa es una cabecera IPv6 sin próxima cabecera. Ósea, le estoy diciendo, la próxima es una de TCP, datos de capa 4 que ya van a venir en los datos. 

---

![[Pasted image 20240510145223.png|400]]

¿Qué sucede si tengo una cabecera más compleja?

+ Tengo una cabecera IPv6, que indica que le sigue una cabecera de Ruteo. 
+ Esa cabecera de ruteo va a tener todos los campos que necesita y en su campo de próxima cabecera va a decir, por ejemplo, tengo una cabecera TCP.
+ Y por último los datos.

---

![[Pasted image 20240510145522.png|500]]

Otro ejemplo sería.

+ Una cabecera IPv6 donde viene ruteo. 
+ Después viene otra cabecera con ruteo y fragmentación.
+ Después viene otra cabecera con fragmentación y TCP.
+ Después viene la cabecera de TCP.
+ Datos.

Fijémonos que las cabeceras se van apilando. Las voy anexando una detrás de la otra dependiendo de lo que se necesite. Pero tienen un orden.

#### Ejemplo IPv6 - Analizador de protocolo

Este es un paquete que no tiene extensiones. Es bastante breve el paquete.

Podemos ver la dirección de origen. Son dos bytes (o 4 nibbles). Básicamente las direcciones se manifiestan de está forma. Tanto destino como de origen.

![[Pasted image 20240510145936.png|500]]

También es un paquete de IPv6 pero que tiene una extensión de cabecera que es el salto a salto con los datos que lleva.

Alerta de router, PadN es el relleno. Distintas cosas que podemos llegar a ver.

![[Pasted image 20240510150010.png|500]]

Vamos a tener practica con el analizador de protocolo.

#### Tipo de tráfico IPv6

En IPv6 tenemos 3 tipos de tráfico.

##### Unicast

Se refiere a máquina a máquina.

![[Pasted image 20240510150744.png|250]]

##### Multicast

Es para enviar un paquete a múltiples destinos. Este paquete multicast, me permite mandarle a multiples host a múltiples redes.

<u>No existe el broadcast en IPv6, lo que existe es un multicast hacía todos los nodos</u>.

Todos los nodos tienen una denominación particular.

![[Pasted image 20240510150809.png|250]]

##### Anycast

<u>Es para mandarle datos pero a un grupo particular de máquinas. Puede ser por distintos criterios</u>.

Por ejemplo, para un servicio que necesite balanceo de carga, por proximidad a un nodo, etc.

![[Pasted image 20240510150826.png|250]]

#### Direcciones IPv6

![[Pasted image 20240510162338.png|500]]

Estas son las direcciones IPv6.

La que está primero es una dirección de un host especifico. Cada letra es un nibble (medio byte), cada parte esta formada por $2$ bytes.

**Luego tenemos reglas de simplificación**: Estas reglas tienen que ver con los ceros. 

<u>La primer regla dice que se pueden suprimir los ceros a la izquierda. Entonces, podemos ver en el ejemplo que estos son suprimidos</u>.

Cada dos octetos separamos con dos puntos. Esta separación es simplemente para que sea más fácil de leer.

<u>Otra regla dice que, si tengo muchos ceros seguidos, puedo agregar dos puntos sin ningún número</u>. Eso me dice que es una cadena de ceros consecutivas, pero <u>esa cadena solo se puede utilizar una única vez dentro de la palabra IPv6. La supresión de ceros a la izquierda puede ser las veces que quiera</u>.

En este ejemplo hay nada más que dos, pero podría haber más paquetes con 0000. 

Por más que tenga más de dos conjuntos de ceros, si por ejemplo tengo 3 conjuntos de ceros, igualmente se utilizan solo ::, no :::, ni nada raro. 

Se da cuenta ya que tenemos 8 conjuntos de 2 octetos por cada dirección de 128 bits. Entonces, por ejemplo, si me llegan 5 conjunto de 2 octetos, me faltan 3. 

#### Direcciones globales IPv6

![[Pasted image 20240510163857.png|500]]

Cuando el LACNIC le entrega a un ISP un bloque de direcciones, cuando era IPv4, generalmente los bloques eran un /24, /23, etc.

Ahora el LACNIC, directamente entrega un /32. Esto significa que los primeros 32 bits, ósea lo que antes era todo el direccionamiento IP, ahora es nada más para 1 ISP. 

A eso se le llama **NET ID (32 bits)**. Esto le entrega un organismo como el LACNIC a un ISP.

**Subnet id (16 bits)** y **división (16 bits)** lo maneja el ISP o LIR. Con esto el ISP lo que va a hacer es subdividirlo en distintas porciones que a él le convenga.

**Interface ID**. Me quedan los últimos 64 bits para la IP que le voy a dar a cada uno de los hosts. Generalmente la MAC Address de la placa o generado por el sistema operativo.

##### Ejemplo de división de una IPv6

Con el Subnet ID y con la división, lo que puede hacer el propio ISP es manejar dos Nibbles (4 bits) para diferenciar el país, imaginemos una empresa como Telefonica que tiene servicios en varios países, otros dos para Departamento/Provincia/Estado, etc.

![[Pasted image 20240621003127.png|400]]

#### Plan de numeración IPv6

Longitudes de prefijo IPv6:

1. Cualquier LAN con varios hosts es un /64.
	Es el mismo concepto que en IPv4. La barra solo es para decir los bits que usaré como red. La barra lo que hace, el LACNIC le da un /32, /64 es responsabilidad del ISP. Los 64 bits que me quedan son para asignar a la placa de red.
2. Direcciones loopback es un /128.
	Loopback es como cuando hacemos un servicio localhost en la propia máquina. En IPv6 es una /128. 
3. Punto a punto entre operador y CPE de usuario es un /64.
	CPE de usuario es la computadora del propio usuario.
4. Punto a punto entre 2 routers es un /64
5. Prefijo delegado a usuarios finales es un /48 estático

#### Ejemplo de direccionamiento IPv6

![[Pasted image 20240621011028.png|500]]

### Direcciones unicast local IPv6

Prefijo: FC00::/7

L: flag

+ 0 - Reservado para uso futuro
+ 1 - El prefijo es asignado localmente

Global ID - es un pseudo random no secuencial

Subnet ID - identifica la subred

Interface ID - generalmente la MAC Address de la placa o sistema operativo

![[Pasted image 20240621011205.png|600]]

Aquellas direcciones que empiezan con el prefijo FC00 se les llaman direcciones libres de estado. Es una IP que no va a rutear por internet, no va a tener tráfico, pero por lo menos le va a poner un sentido de IP a la máquina.

Lo genera con la MAC Address de la placa o del sistema operativo.

### Direcciones especiales IPv6

Hay un problema de convivencia entre IPv4 e IPv6. Como son incompatibles las cabeceras, en las redes hay que poner un host que permita hacer la traducción.

¿Cómo hace una máquina IPv4 para comunicarse con una máquina IPv6?, este host en el medio lo que va a hacer es, hacía un lado enviarlo como si fuera IPv6, hacía el otro lado corta el IPv6 y deja el IPv4. Esto genera un cuello de botella. No es agradable tener redes mixtas.

![[Pasted image 20240621011643.png|600]]

Todos estos no son ruteables, son todos para trabajar como si fuera a nivel local.

Si bien, yo como empresa le puedo dar a todas las máquinas una dirección pública, por ahí yo no quiero esto. Entonces tengo direccionamiento, los que empiezan con ff que me permiten hacer una red interna con IPv6.

![[Pasted image 20240621012025.png|600]]

### Importante de IPv6

+ Son 128 bits en lugar de 32
+ La cantidad de direcciones IP son monstruosas
+ Tiene campos preparados que el ruteo o para el tráfico en la red sea bastante más ágil. El campo de flujo.
+ Por defecto no tiene fragmentación. Para fragmentar tengo que agregar una cabecera adicional.
+ Puedo manejar seguridad que con IPv4 no puedo. Tanto en autenticación como en encriptación.
+ La extensión de cabecera me permite agregarle funcionalidad al paquete dependiendo del caso de uso que tenga que hacer.
+ Tenemos los Jumbo grams que permite manejar paquetes de 4GB. Hay que agregar una cabecera especifica para esto. Lo debe permitir la red de transporte que estemos teniendo en capa 2.
+ Cuando el organismo de registro de internet nos asigna nuestro propio bloque lo podemos subdividir como nos sea más comodo.

---
## Clase 8

Cuando interconectamos varias redes LAN utilizando routers, que actúan como dispositivos intermedios. Para que esto funcione, necesitamos configurar cómo se va desde un host en una red hacía otro host en una red diferente. <u>De alguna forma los routers tienen que saber como hacer ese camino</u>. 

Ya sabemos que en los hosts se configura el [[Default gateway|default gateway]]. Este indica que, cualquier dirección IP que no corresponda a su red, debe dirigirse hacía allí.

Una vez que configuramos la IP del host y la mascara, todo lo que no este dentro de esa red, va a salir por el default gateway y de alguna forma, este default gateway que es por lo general un router, tiene que saber como llegar a la maquina de destino.

### Enrutamiento

El método para poder lograrlo se lo conoce como enrutamiento, routing, ruteo, etc.

Esto se refiere al proceso en el que los enrutadores (routers) aprenden sobre **redes remotas**, encuentran todas las rutas posibles para llegar a ellas y luego escogen las mejores (las más **rápidas**) para intercambiar datos entre ellas.

Al comienzo, el enrutador no conoce ninguna otra red que sea la que está directamente conectada al router mismo. Para que este pueda llevar a cabo el enrutamiento, primero debe saber de la existencia de redes remotas. Para que esto suceda, el router tiene que estar configurado con **enrutamiento dinámico** y/o **enrutamiento estático**.

Básicamente hay dos formas de hacer esto:

Algoritmos de ruteo:

+ **Estáticos**: <u>El administrador agrega manualmente las redes remotas</u>.
	
	Básicamente es crear una regla dentro del dispositivo indicando que la red de destino sale por cierta interfaz. Le tengo que decir de alguna forma por cual de las interfaces voy a alcanzar a la red que yo estoy indicando.
	
	Es muy eficiente.
+ **Dinámicos**: <u>Las redes remotas son descubiertas automáticamente por medio de un protocolo</u>.
	
	Con algún método, protocolo, algoritmo, los routers se van a comunicar entre si y van a empezar a descubrir o empezar a saber por qué interfaz puedo alcanzar alguna red de destino.
	
	Estos métodos son varios. Tienen distintas estrategias para lograr el mismo objetivo.

#### Ruteo estático

¿Cuándo y donde utilizar ruteo estático?

![[Pasted image 20240515161747.png|400]]

Para alcanzar desde el router que se encuentra arriba, que tiene la dirección $192.168.1.0/24$, para llegar a la $192.168.2.0/24$, voy a tener que salir por la interfaz que se encuentra a la derecha, y para llegar a la red $10.167.67.0/24$, voy a generar otra regla que me diga que debo salir por la parte izquierda. Eso lo genero en el router $192.168.1.0/24$ que tiene 2 interfaces.

En el router 2, por ejemplo, le voy a decir que para alcanzar la red $192.168.1.0/24$, tengo que salir por la única interfaz que tiene, y para dirigirme a la red $192.168.2.0/24$, también tengo que salir pro la misma interfaz. 

¿Qué sucedería si tengo que agregar un nuevo router?

<u>Tengo que generar más reglas en los distintos routers que me indiquen como llegar de un lado al otro</u>.

##### Ventajas y desventajas del ruteo estático

| Ventajas                                                                                                                      | Desventajas                                                                                            |
| :---------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------- |
| Fácil de implementar en una red pequeña.                                                                                      | Adecuado solamente para topologías simples o fines específicos, como una ruta estática predeterminada. |
| Muy seguro. No se envían anuncios, a diferencia del caso del ruteo dinámico.                                                  | La complejidad de la configuración aumenta significativamente cuando el tamaño de la red es mayor.     |
| La ruta al destino siempre es la misma.                                                                                       | Se requiere intervención manual para volver a enrutar el tráfico.                                      |
| Dado que no se requieren algoritmos de ruteo ni mecanismos de actualización, no se necesitan recursos adicionales (CPU / RAM) |                                                                                                        |

###### Ventajas del ruteo estático

<u>Una vez creada la regla, ya no debo preocuparme</u>. La única causa de que no funcione es que se haya caído el enlace. 

Otra ventaja es que <u>el consumo de recursos es mínimo</u>, ya que el router no tiene que "pensar". Hace lo que dice la regla y se envía.

<u>Cuando se habla de seguridad, en realidad, como esa regla la puso el administrador y no hay nadie que la pueda cambiar, solo él, le da cierto grado de seguridad</u>. 

Como es una regla, <u>el consumo de recursos es mínimo</u>. Básicamente es un `if`.

###### Desventajas del ruteo estático

<u>Si se agregan nuevas interfaces o routers, voy a tener que empezar a generar distintas reglas en los componentes para que el ruteo funcione</u>. 

<u>Cuanto más grande sea la red que voy a hacer, la cantidad de reglas que voy a tener que crear va a crecer demasiado</u>.

#### Ruteo Dinámico

![[Pasted image 20240515163312.png|500]]

Los protocolos de enrutamiento dinámico se dividen en dos:

+ **Protocolos de gateway interior (IGP)**: <u>Son los protocolos que vamos a utilizar en nuestras propias redes</u>.
	+ **Protocolos de enrutamiento vector distancia**
		+ RIP v1
			+ RIP v2
		+ IGRP
			+ EIGRP
	+ **Protocolos de enrutamiento estado del enlace**
		+ OSPF
		+ IS-IS
+ **Protocolos de gateway exterior (EGP)**: <u>Son los que vamos a utilizar en nuestra comunicación con otras redes de otras personas, ya sea de otras empresas o contra nuestro ISP</u>.
	+ **Protocolos de enrutamiento Vector Ruta**
		+ **BGP**: Es el que vamos a ver. Se utiliza de facto. Todos los ISP utilizan este protocolo para comunicarse entre si. No tiene mucho sentido ver otro.

**¿Se pueden utilizar protocolos internos para hacer un vinculo externo?** 

<u>Si, se puede, pero no se recomienda</u>.

**¿Se puede utilizar un protocolo externo como el BGP, dentro de nuestra propia red?**

<u>Si, se puede, lo que pasa que es un poco más tediosa la configuración del protocolo. Por lo general se opta utilizar otro para la interna</u>.

---

![[Pasted image 20240515164520.png|500]]

Los protocolos funcionan tanto en IPv4 como en IPv6. 

Solo cambia en la diferencia de nombre. Funcionan igual solo que las direcciones son de $32$ y $64$ bits.

### Protocolos internos (IGP) vs externos (EGP)

![[Pasted image 20240515164737.png|400]]

+ **Protocolos de gateway interior (IGP)**: Se utilizan para el ruteo dentro de un Sistema Autónomo (SA). 
	Ejemplo RIP, EIGRP, OSPF e IS-IS.
+ **Protocolos de gateway exterior (EGP)**: Se utilizan para el ruteo entre Sistemas Autónomos (SA).
  
	Ejemplo BGP también se utiliza en Internet.

#### Sistema Autónomo (AS)

<u>Un Sistema Autónomo se refiere a una red (o un grupo de redes) que está bajo una sola administración. Podría ser una empresa, un grupo de edificios pertenecientes a la misma empresa, tu propio proveedor de servicios de Internet, o incluso tu red doméstica. La mismísima Internet está formada por sistemas autónomos conectados entre sí</u>.

Los paquetes de datos son transmitidos, de un nodo a otro, dentro de un mismo SA hasta que necesiten llegar a otro nodo en un SA diferente.

Grupo de redes IP que comparten una política de ruteo propia e independiente.

Política de ruteo propia:

+ Áreas a conectar
+ Dispositivos visibles
+ Protocolos de comunicación
+ Direcciones IP

Desde fuera, el Sistema Autónomo es visto como una entidad única. Tiene su propia política de ruteo interna (IGP) y su propia política de ruteo externa (EGP).

---

<u>Un Sistema Autónomo es un conjunto de direcciones IP que se le da a una empresa</u>. Puede ser una empresa grande, o un ISP. Dentro de esa gran red se utiliza un protocolo de red interior.

Si recordamos, en IPv6, nos había mostrado dos casos típicos donde Claro y Telecentro, se ven los diferentes grupos de IP's que se les asignaron a esas empresas.

Dentro del AS, el dueño del AS, puede rutear como quiera. Si tiene ganas de hacer todo estático, lo puede hacer. Pero, para conectarse entre Sistemas Autónomos, por regulación se utiliza BGP. Uno en el BGP, puede publicar las redes que quiera.

#### Grupos que administran los Sistemas Autónomos

![[Pasted image 20240517155430.png|300]]

Los grupos que administran los Sistemas Autónomos, son los que entregan los pool de direcciones IP.

Los organismos están regulados por el [[IANA (Internet Assigned Numbers Authority)]], el cual esta compuesto por:

+ [[LACNIC (Latin America and Caribbean Network Information Centre)]]
+ ARIN
+ AFRINIC
+ APNIC
+ RIPE

Esas organizaciones son las que definen a las empresas qué números de Sistema Autónomo tienen.

Hay algunos números particulares:

| Número de AS/bloque          | Asignación                                |
| ---------------------------- | ----------------------------------------- |
| 0 y 65.535                   | Reservados                                |
| Entre 1 y 64.495             | Internet Pública (ISP y empresas grandes) |
| Entre 64.496 y 64.511        | Documentación para ASN 16 bits - RFC 5737 |
| Entre 64.512 y 65.534        | Uso sólo privado                          |
| Entre 65.536 y 65.551        | Documentación para ASN 32 bits - RFC 5398 |
| Entre 65.552 y 4.294.967.295 | Internet pública                          |
Caso típico de un uso de AS privado es cuando queremos conectar nuestra propia red con una suscripción o un tenan generado en una nube de internet. Para poder generar eso, nosotros desde nuestra red, lo que vamos a poner es nuestro AS, pero en la nube configuramos un AS privado.

Por ejemplo, si nos conectamos a google, el AS de google. Esa es una comunicación por IP pública. Nosotros lo que vamos a comunicar son las IP's privadas de nuestras propias redes. 

Entonces para hacer eso configuramos el AS de la nube a la que nos hayamos conectado, uno de los AS privados. Que son los especificados en el cuadro.

#### Nombres de los distintos protocolos

Ruteo Interno IGP (Interior Gateway Protocol)

+ **RIP (Routing Information Protocol)**: Vector distancia, saltos.
+ **IGRP (Interior Gateway Routing Protocol)**: Cisco. Tiene en cuenta Ancho de banda, retardos, confiabilidad y carga de los enlaces.
+ **EIGRP (Enhance Interior Gateway Routing Protocol)**: Cisco. Es IGRP mejorado ya que consume menos ancho de banda para las actualizaciones.
+ **IS-IS (Intermediate System Intermediate System)**: Estado de enlace.
+ **OSPF: Open Shortest Path First**: Estado de enlace, genera áreas.

**Rutero Externo EGP (Exterior Gateway Protocol)**

+ **BGP**: Border Gateway Protocol. Comunicación entre Sistemas Autónomos.

---

Los que más vamos a usar en las practicas o que podemos llegar a utilizar en algún trabajo es el RIP. Que es el más básico.

El EIGRP que es un protocolo de Cisco, que si bien es un protocolo propietario, Cisco lo liberó para que sea usable por cualquier persona.

Otro protocolo abierto es OSPF. Es de estado, también es bastante usado. Generalmente cuando la cantidad de router's es grande.

BGP es el que se usa de facto en internet. Generalmente vamos a tener uno o dos router's que se comunican con BGP con nuestro proveedor o si somos un ISP, son nuestras fronteras para comunicarnos hacía el mundo, hacía internet.

### Convergencia

+ <u>Cuando todos los routers tienen información completa y precisa sobre toda la red, están en **convergencia**</u>.
+ <u>EI tiempo de convergencia es el tiempo que los routers tardan en compartir información, calcular las mejores rutas y actualizar sus tablas de ruteo</u>.
+ Una red no es completamente operativa hasta que la convergencia sea total.
+ Las propiedades de convergencia incluyen la velocidad de propagación de la información de ruteo y el cálculo de los caminos óptimos.
  
	La velocidad de propagación se refiere al tiempo que tardan los routers dentro de la red en reenviar la información de ruteo.
+ <u>Generalmente, los protocolos más antiguos, como RIP, tienen una convergencia lenta, mientras que los protocolos modernos, como EIGRP y OSPF, la realizan más rápidamente</u>.

![[Pasted image 20240517161752.png|300]].

### Enrutamiento Dinámico

El enrutamiento Dinámico se basa en estos 3 pilares.

#### Estructura de datos

<u>Las estructuras de datos que manejan los equipos pueden ser pilas, colas, listas, listas doblemente enlazadas</u>. 

Generalmente arman una base interna en la cual tienen la información para poder hacer el ruteo. 

#### Mensajes del protocolo de ruteo

Los mensajes son la estructura que va a tener el protocolo. Así como en un datagram IP, o en una trama Ethernet tenemos los diferentes bytes, <u>los mensajes de los protocolos de ruteo están estructurados para que lleven la información desde un router a otro</u>.

#### Algoritmos de ruteo

<u>Una vez tomado ese mensaje, de alguna forma, yo voy a tener que empezar a hacer cálculos para determinar cual es el mejor camino para llegar desde A hasta B</u>.

No lo pensemos como que es para llegar de un router hasta el otro. Yo tengo una red que tiene 20 routers que por ahí están interconectados entre sí por el mejor camino.

---
#### Protocolos

Se utilizan para facilitar el intercambio de información de ruteo entre los routers.

Objetivos:

+ **Descubrir redes remotas**: A medida que llegan esos mensajes, voy a poder completar mi tabla de ruteo con las redes que está publicando el router remoto.
+ **Mantener la información de ruteo actualizada**: Cuanto más rápido lo haga, menos mensajes voy a perder y más destinos voy a alcanzar.
+ Buscar el mejor camino hacia las redes de destino.
+ Encontrar otro camino nuevo si la ruta actual deja de estar disponible.

Métricas:

+ <u>Valor medible que el protocolo asigna a las distintas rutas</u>
+ <u>Se utiliza el costo para determinar la mejor ruta</u>

El administrador de red generalmente no administra. Si es una red interna puede ser que lo haga, pero si es el mundo de internet no lo hace. Entonces, cuando alguien crea una nueva red, los distintos mensajes que nos van a llegar van a hacer que nuestras redes sean capaces de alcanzar las redes remotas. 

#### Ventajas y desventajas del ruteo Dinámico

| Ventajas                                                                             | Desventajas                                                                                        |
| ------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- |
| Adecuado en todas las topologías donde se requieren varios routers.                  | La implementación puede ser más compleja.                                                          |
| Por lo general, es independiente del tamaño de la red.                               | Menos seguro. Se requieren opciones de configuración adicionales para proporcionar protección.<br> |
| Si es posible, adapta automáticamente la topología para volver a enrutar el tráfico. | La ruta depende de la topología actual.                                                            |
|                                                                                      | Requiere CPU, RAM y ancho de banda de enlace adicionales.                                          |

---

Generalmente es independiente del tamaño de la red. Hay algunos peros en esto. Hay algoritmos que funcionan mejor en ciertos tipos de redes que otros. En redes pequeñas no hay problema, son todos iguales. El problema está cuando hablamos de redes muy grandes (por ejemplo 500 routers). Ya vamos a ver un protocolo que se adapta mejor a este tipo de redes grandes.

<u>La desventaja es que es menos seguro</u>. Si yo tengo un router que me está información mal las redes que él tiene asociada puede ser que a mi me cambie mi algoritmo de ruteo y que los paquetes que quiero hacer llegar a distintas redes, no lleguen, porque hay un router que esta informando mal las redes que tiene asociadas.

Hay formas de mitigar este tipo de cosas. Tengamos en cuenta que en internet, cuando uno mismo administra generalmente es por un error y se soluciona. Pero en internet suele haber grupos que se dedican a publicar redes apócrifas para traer algún tipo de problema en la navegación normal.

Acá da el ejemplo de lo que ocurrió en pandemia porque facebook, isntagram, wp. Se equivocaron en alguna configuración de los routers que comunican hacía el mundo de internet. 

Esto deja en evidencia lo crítico que puede ser una infraestructura como está y un ruteo dinámico. El router de Facebook desparramo por todo el mundo que las redes eran otras. Esto sucede mucho en internet, pero está bastante controlado. Pero si alguien legitimo hace mal las cosas, es un problema.

### Protocolo vector distancia

+ <u>Comparten actualizaciones entre los vecinos</u>.
+ No tienen conocimiento de la topología de la red.
+ RIP v1 envía actualizaciones periódicas a la dirección IP $255.255.255.255$ de difusión, incluso si la topología no se modificó.
+ <u>Las actualizaciones consumen ancho de banda y recursos de la CPU del dispositivo de red</u>.
+ RIP v2 y EIGRP utilizan direcciones de multidifusión ($224.0.0.9$ y $224.0.0.10$ respectivamente).
+ <u>EIGRP envía solamente una actualización cuando la topología se modifica</u>.

![[Captura de pantalla 2024-05-21 202835.png|250]]

<u>Los protocolos vector distancia, son aquellos que calculan las rutas dependiendo de cuan lejos estoy del destino, y eso se hace con una métrica muy simple, cuantos saltos tengo que hacer para llegar al destino (cuantos routers debo pasar antes de llegar a destino)</u>.

En IP tenemos el TTL, y ese TTL cuando llega a cero el paquete se dropea. En este protocolo va calculando los distintos tramos que se debe hacer dependiendo de la cantidad de saltos que tengo.

El primero de los protocolos que usó este método es el protocolo llamado RIP. La gran diferencia entre RIP v1 y RIP v2, es que el RIP v1 solo funciona con las mascaras naturales. En v1 no debería o no puedo usar subnetting, para ello debo utilizar RIP v2.

<u>RIP es un protocolo que solo va a mirar los saltos. En cambio IGRP es uno más avanzado y tiene una convergencia mucho más rápida que RIP</u>.

<u>Lo que tiene que quedar claro es que los protocolos vector distancia lo que hacen es calcular su métrica principal a través de la cantidad de saltos</u>.

---

IGP vector distancia IPv4:

+ **RIP v1**: protocolo antiguo de primera generación
+ **RIP v2**: protocolo de ruteo vector distancia simple
+ **IGRP**: protocolo exclusivo de Cisco de primera generación (obsoleto)
+ **EIGRP**: versión avanzada de ruteo vector distancia

![[Pasted image 20240521204043.png|250]]

Para el R1, $172.16.3.0/24$ está a un salto (distancia). Puede alcanzarse a través del R2 (vector).

#### Características de RIP y EIGRP

**RIP**:

+ <u>Las actualizaciones de ruteo se difunden cada 30s</u>. Esto quiere decir que desde el router va a salir un paquete indicando la red cada 30s.
  
	<u>Por lo tanto, ante alguna caída de un enlace o un cambio en la topología con la cantidad de routers, etc., voy a tardar 30s en darme cuenta. Si la red es muy grande, esos 30s se multiplican bastante</u>.
+ Las actualizaciones utilizan el puerto UDP 520.
+ <u>Realiza 15 saltos como máximo</u>. Esto quiere decir que, podría tener en línea hasta 15 routers seguidos. Si tengo una red más grande, voy a tener que cambiar de protocolo.
+ La distancia administrativa de 120.

**EIGRP**:

- <u>Actualizaciones dirigidas limitadas. Cuando nace el protocolo publica hacía todo el mundo. Únicamente empieza a mandar paquetes cada vez que detecta un cambio de estado en la topología (por caída del enlace o lo que sea que haya pasado)</u>.
- <u>Mecanismo de saludo de keepalives</u>. Esto es nada más que para mantener entre los router informados que está vivo.
- <u>Mantenimiento de una tabla de topología</u>.
- <u>Convergencia rápida</u>. Si yo lo único que informo es en un cambio en la topología, ante cualquier problema me entero rápido, no espero los 30s, el que esta al lado mío se entera y comunica de la misma forma.
- <u>Compatibilidad con varios protocolos de capa de red</u>. No solo sirve para IP sino que sirve para cualquier otro protocolo más. Podría ser IPx o cualquier otra red de capa 3 que estemos usando.

**Distancia Administrativa**: <u>Podemos pensar en DA como un "valor de confiabilidad" con los que se miden los diferentes tipos de ruta. Este valor va desde 0 hasta 255, y cuanto menor sea el valor, más confiable será la ruta</u>. 

<u>Básicamente, cuando el enrutador tiene más de una ruta a una misma red, optará por seleccionar la ruta más confiable, la que tenga menor Distancia Administrativa</u>.

Cada tipo de ruta tiene su propio valor de distancia administrativa, aquí está la tabla:

![[Pasted image 20240625204833.png|300]]

### Protocolo de estado de enlace

IGP de estado de enlace IPv4:

+ **OSPF**: protocolo de routing muy popular basado en estándares
+ **IS-IS**: popular en redes de proveedores

![[Pasted image 20240521205155.png|400]]

---

<u>Básicamente lo que informa este protocolo es el estado de sus enlaces, es lo que va a informar hacía los router que tenga conectado</u>. No si está vivo o muerto, sino el estado de sus enlaces.

Hay estos dos protocolos (OSPF, IS-IS).

El OSPF es el que se utiliza comúnmente dentro de las redes, el IS-IS en un momento fue popular, hoy en día no lo usa nadie prácticamente.

### Protocolo de Ruteo con clase

+ No envía información de la máscara de subred en las actualizaciones de ruteo.
+ <u>Solo RIP v1 e IGRP son con clase</u>. Como no envío la mascara de red, solo se puede trabajar con clase. No hay forma de trabajar ningún tipo de Subnetting.
  
	<u>Por ende, si yo tengo algún tipo de Subnetting, todos los routers dentro de la red deberán utilizar otro protocolo</u>. Si yo utilizo por ejemplo, todas direcciones clase C, puedo utilizar el RIP v1. No sería aconsejable porque es muy viejo.
	
	Cuando prendemos un router, por defecto está en RIP v1, que es lo mínimo que se necesita.
	
	En el TP de VLAN todos routers con sus interfaces y las distintas VLAN eran clase C. Como el router levanto internamente RIP v1 es que se pudo conectar de una red a la otra. Porque sin un algoritmo de ruteo, el router no hace nada. No sabe que hacer.
+ Se crean cuando se asignan las direcciones de red según las clases (clase A, B o C).
+ No pueden proporcionar máscaras de subred de longitud variable (VLSM) ni ruteo entre dominios sin clase (CIDR).
+ Generan problemas en las redes no contiguas.

### Protocolo de ruteo sin clase

+ Incluyen información de máscara de subred en las actualizaciones de ruteo. No solo pasa la red, sino que también pasan la mascara. Por lo tanto al informar la máscara, los otros routers saben a que subnet están enviando los datos.
+ <u>RIP v2, EIGRP, OSPF e IS-IS. Estos todos trabajan sin clase</u>.
+ Admiten VLSM y [[CIDR (Classless Inter Domain Routing)]] .
+ Protocolos de ruteo IPv6. Estos mismos protocolos (RIPv2, EIGRP, OSPF e IS-IS) se utilizan para IPv6.
	Cuando uno tiene una red mixta, con equipos IPv6 y IPv4, generalmente se les pone a todos el mismo protocolo de versión 6 para que haga el manejo, porque los protocolos de v4 no pueden direccionar los 128 bits de las direcciones de IPv6.

### Algoritmo vector distancia

+ Enviar y recibir actualizaciones.
+ Calcular la mejor ruta e instalar rutas.
+ Detectar cambios en la topología y reaccionar ante ellos.

![[Pasted image 20240521210400.png|350]]

+ <u>RIP utiliza el algoritmo de Bellman-Ford como algoritmo de ruteo</u>. Es un algoritmo del estilo Dijkstra. Elije el mejor camino con la menor cantidad de saltos posibles.
  
	Al comienzo todos los enlaces eran de la misma velocidad de 64k era un lujo, entonces no tenía mucho sentido tener otra métrica. A medida que los enlaces se fueron haciendo de distintas velocidades, tener enlaces de 100M, 1GB, etc,. ya comenzaron a usar otras métricas (ancho de banda, latencia, entre otros).
+ <u>IGRP y EIGRP utilizan el algoritmo de actualización por difusión (DUAL) como algoritmo de ruteo, desarrollado por Cisco</u>. Este algoritmo DUAL no solo utiliza el vector distancia sino que también utiliza otros datos de la interfaz.

### Protocolo vector distancia RIP - Funcionamiento

En la imagen podemos ver como se llenan las tablas internas de los distintos routers a medida que va pasando el tiempo. Recordar que, el router informa y recibe información cada 30s.

<u>Lo primero que va a hacer el router es informar que redes tengo conectadas directamente</u>. En el router tengo una interfaz y el router sabe que IP y mascara le puse a dicha interfaz.

<u>Informa que redes tiene conectadas a todos los que estén conectados a él</u>.

Entonces, en la primera vuelta, guardan en sus tablas las redes que tienen conectadas directamente:

+ EI R1 agrega la red $10.1.0.0/16$ disponible a través de la interfaz $\text{Fe 0/0/0}$ y $10.2.0.0/16$ disponible a través de la interfaz $\text{Se 0/0/0}$, con un salto de 0 (ya que vienen de sus propias interfaces).
+ EI R2 agrega la red $10.2.0.0/16$ disponible a través de la interfaz $\text{Se 0/0/0}$ y $10.3.0.0/16$ disponible a través de la interfaz $\text{Se 0/0/1}$, las dos con un salto de 0 (ya que vienen de sus propias interfaces).
+ EI R3 agrega la red $10.3.0.0/16$ disponible a través de la interfaz $\text{Se 0/0/1}$ y $10.4.0.0/16$ disponible a través de la interfaz $\text{Fe 0/0/0}$, las dos con distancia 0 ya que provienen de sus propias interfaces.

![[Pasted image 20240521210931.png|500]]

---

<u>Luego viene un primer intercambio</u>. Ósea, qué puede informarle al router que tiene hacía el lado.

En realidad lo informa hacía todas las interfaces. Uno puede decirle en el router, no informes hacía dentro, no tiene sentido que informes hacía dentro de la red donde lo único que yo tengo son máquinas que no les interesa el paquete.

En redes muy congestionadas que tienen muchos host, si encima mando paquetes de RIP hacía dentro cada 30s aumenta la congestión.

Hay un comando que se aplica en el router que indica que en cierta interfaz no comunique el protocolo de ruteo. Entonces, ¿Por donde voy a comunicar?, por la placa serie.

<u>Básicamente, cada router le dice a los demás como llegar a las redes que tiene en sus interface</u>.

Entonces:

El R2 informa al R1 que, pasando por su interfaz $\text{Se 0/0/0}$ (la del R2) puede llegar a la red $10.3.0.0/16$, pero con un salto de 1.

El R2 le indica al R3 que, pasando por su interfaz $\text{Se 0/0/1}$ (la del R2) puede llegar a la red $10.2.0.0/16$ con un salto de 1. 

Luego, el R1 le indica al R2 que, pasando por su interfaz $\text{Se 0/0/0}$ (la del R1) puede llegar a la red $10.1.0.0/16$ con un salto de 1.

Luego, el R3 le indica al R2 que, pasando por su interfaz $\text{Se 0/0/1}$ (la del R1) puede llegar a la red $10.4.0.0/16$ con un salto de 1.

Y la tabla quedaría de esta forma.

![[Pasted image 20240521211715.png|500]]

---

Intercambio siguientes.

Ahora, de la misma forma, el R2 al tener una tabla más grande se la va a informar al router 1 y al router 3.

Entonces:

El R2 le informa al R1 que, para llegar a la red $10.4.0.0/16$ va a llegar por la la placa $\text{Se 0/0/0}$ (la misma que conecta R1 y R2), pero el salto es 2. Deberá pasar por 2 dos routers.

De la misma forma, R2 le informa a R3 que, para llegar ala red $10.1.0.0/16$ va a llegar por la placa $\text{Se 0/0/1}$ (la misma que conecta R2 y R3), pero el salto es 2. Deberá pasar por 2 routers.

![[Captura de pantalla 2024-05-21 215530.png|450]]

Llegado este momento las redes se encuentran en convergencia, ya que se conocen entre si. Para hacer esto, cada uno de los intercambios, son cada 30s, entonces para detectar esto que hicimos a mano tardo 1 minuto y medio o dos minutos.

No es uno de los protocolos más rápido pero para redes pequeñas funciona.

### Protocolo de estado de enlace

![[Pasted image 20240515163312.png|500]]

Proceso de enrutamiento de link-state:

+ <u>Cada router obtiene información sobre cada una de sus propias redes conectadas directamente</u>.
+ <u>Cada router tiene la responsabilidad de "saludar" a sus vecinos en redes conectadas directamente</u>. Lo que está haciendo es presentarse a él mismo con todas sus redes conectadas.
	
	<u>Ese paquete, con todas las redes conectadas, se publican por todas las interfaces que tienen con la intención de comunicarle a todos sus vecinos lo más rápido posible su información de ruteo</u>. En cada uno de los enlaces no calcula el vector distancia sino el ancho de banda o mejor dicho una métrica que no solo depende del ancho de banda, sino que tiene en cuenta varios aspectos. Puedo tener un ancho de banda grande pero por ahí tengo una latencia muy grande.
+ <u>Cada router crea un Paquete de link-state (LSP - Link State Packet) que incluye el estado de cada enlace directamente conectado</u>.
+ <u>Cada router satura con el LSP a todos los vecinos, que luego almacenan todos los LSP recibidos en una base de datos</u>.
+ <u>Cada router utiliza la base de datos para construir un mapa completo de la topología y calcula el mejor camino hacia cada red de destino</u>.

#### Algoritmo de estado de enlace

Open Shortest Path First - Dijkstra 

![[Pasted image 20240522140934.png|400]]

<u>El algoritmo de estado de enlace utiliza Dijkstra</u>. El otro era el Belman Ford. Este es un poco más avanzado.

**¿Cómo se calcula el algoritmo de estado de enlace?**

<u>Lo que va a hacer el protocolo es tratar de calcular cual es el costo más chico para llegar, en este caso, desde la red que está conectada al R2, con la red que está conectada al R3</u>.

Todos los routers al mismo tiempo diseminan el paquete con todas las redes que tienen conectadas y que métrica tiene cada uno de sus enlaces. Obviamente la métrica es la misma. Ósea dentro del valor del camino están consideradas todas las métricas.

Si se llegara a cortar la conexión entre dos enlaces, seguramente esto recalculará rápido la nueva mejor ruta.

#### Descubrimiento

<u>EI primer paso en el proceso de ruteo de estado de enlace es que cada router descubra sus propios enlaces (interfaces) y sus propias redes conectadas directamente y publicarlas</u>.

![[Pasted image 20240522141952.png|300]]

![[Pasted image 20240522142030.png|300]]

#### Saludo

<u>EI segundo paso en el proceso de ruteo de estado de enlace es que cada router asume la responsabilidad de encontrarse con sus vecinos en redes conectadas directamente</u>.

![[Pasted image 20240522142311.png|300]]

![[Pasted image 20240522142343.png|300]]

<u>En el saludo va diciendo cuales son las redes con el costo que tiene cada una y después una vez que el router recibió todos los saludos con todas las redes empieza a hacer los costos, buscando el camino de menor costo</u>.

Lo que van a hacer los otros routers es exactamente lo mismo, que es presentarse con toda la información que contienen.

#### Armado del LSP

<u>EI tercer paso en el proceso de ruteo de estado de enlace es que cada router cree un paquete de estado de enlace (LSP) que contiene el estado de cada enlace conectado directamente</u>.

![[Pasted image 20240522142629.png|400]]

Los routers luego de obtener esas métricas, el protocolo empieza a hacer los cálculos y llenar la tabla de ruteo con sus propias cuentas.

#### Saturación con LSP

<u>EI cuarto paso en el proceso de ruteo de estado de enlace es que cada router satura con LSP a todos los routers, quienes luego almacenan todos los LSP recibidos en una base de datos</u>.

![[Pasted image 20240522142804.png|400]]

#### Armado de la base de datos

<u>EI paso final en el proceso de ruteo de estado de enlace es que cada router utiliza la base de datos para construir un mapa completo de la topología y calcula la mejor ruta para cada red de destino</u>.

![[Pasted image 20240522142942.png|450]]

#### Armado del árbol

<u>Cuando hablamos de las estructuras de datos, en este caso utiliza un árbol. Entonces da una forma fácil de calcular los costos para cada router</u>.

![[Pasted image 20240522143527.png|450]]

![[Pasted image 20240522143606.png|450]]

### Características de los protocolos de Ruteo

Como nos mencionaba, RIP es lento porque comunica cada 30s.

IGRP no se usa más. Fue el primer protocolo que hizo cisco. En realidad se usa EIGRP, y ese como informa cada vez que hay un cambio en la topología es más rápido en lograr la convergencia.

OSPF cuando tengo redes muy grandes se utiliza porque permite sectorizar pero es más complejo en su utilización.

![[Pasted image 20240522143817.png|550]]

### Ventajas y desventajas del estado de enlace

##### Ventajas

+ Cada router arma su propio mapa topológico de la red para determinar la mejor ruta.
  Cada router decide cual es su mejor ruta con toda la información que recaba.
+ Se logra una convergencia más rápida mediante la saturación inmediata con LSP
+ Los LSP se envían solo cuando hay un cambio en la topología y contienen únicamente la información relacionada con el cambio.
+ Se utiliza un diseño jerárquico al implementar varias áreas.

**Área Única**:

+ Alto consumo de RAM y CPU
+ Toma mucho tiempo de CPU y recursos para correr el algoritmo SPF en todas las bases de datos
+ Un simple cambio de estado en una interfaz provoca que se deba recalcular el SPF en todos los routers.
+ Impacta en el tiempo de convergencia.

![[Pasted image 20240522144515.png|450]]

Cada una de estas áreas, lo que hace es tener información de sus redes internas y el router que está entre areas, lo que hace es comunicar el paquete resultado.

¿Por qué hace eso?

Porque como el protocolo de estado de enlace siempre está saludando, ósea siempre está enviando paquetes para tener la información actualizada. Si tengo áreas muy grandes, esos paquetes van a generar bastante ruido sobre toda la red, entonces al segmentarlos sobre areas más pequeñas, lo que hago es que el tiempo de convergencia se reduzca bastante y que ante cualquier cambio no este saturando a toda la red sino que solo lo informe dentro del área.

**Recomendaciones para la construcción de áreas en OSPF**:

+ Área (cualquier numero de área) - para menos de 30 - 50 routers.
  Por cada área no se recomienda poner más de 30 o 50 routers. 
  Como están los paquetes dando vueltas, cuanto más grande es la red, tiene más tiempo de convergencia.
+ Dos o más áreas - Debe existir un área 0.
  Hay un área que se llama área 0. Es como el core de la red, generalmente se le llama backbone, que es por donde van a pasar todos los mensajes intra-redes o intra-areas.
+ Todas las áreas no backbone deben conectarse al área 0.
+ Al menos un router de borde por área. Por 10 menos una interface en ambas áreas.
  Los routers que se comunican entre áreas, tienen que tener el mismo número de área para poder comunicarse y tiene que haber por lo menos 1 router por área que haga el vínculo, porque sino es una red estanca.
+ Las interfaces en ambos routers deben estar en la misma área.

Siempre que usemos OSPF hay un área que va a ser la 0.

---

**Desventajas en comparación con los protocolos de ruteo vector distancia**:

+ Requisitos de memoria
+ Requisitos de procesamiento
+ Requisitos de ancho de banda

### Distancia administrativa

La distancia administrativa es un valor que utilizan los routers para seleccionar la mejor trayectoria cuando hay dos o más rutas diferentes hacia el mismo destino desde dos protocolos de ruteo distintos. 

La distancia administrativa define la confiabilidad de un protocolo de ruteo. 

Se da prioridad a cada protocolo de ruteo en orden de mayor a menor confiabilidad (credibilidad) usando un valor de distancia administrativa.

![[Pasted image 20240522151300.png|300]]

Los routers pueden tener varios algoritmos de ruteo al mismo tiempo.

Imaginemos un router de frontera que hacía una interfaz es la interfaz hacía internet y está utilizando BGP y otra interfaz hacía dentro y está utilizando OSPF o EIGRP y tiene otra interfaz que está utilizando RIP.

Entonces, los algoritmos de ruteo tienen distintos pesos, en cuanto a la preferencia que le voy a dar a la ruta. 

Si una ruta fue calculada por ejemplo por OSPF, le voy a dar prioridad a una ruta calculada por RIP. Siempre el número más chico es la preferencia que voy a tener. Si yo administrador hice una ruta estática, mi importa poco los demás algoritmos de ruteo, por eso tiene como distancia administrativa 1. Es lo primero que le va a dar bola, lo demás se ignora.

### BGP (Border Gateway Protocol)

+ Funciona sobre TCP - puerto 179.
  Esto es anecdótico, cuando veamos TCP vamos a ver que son los puertos.
+ Protocolo de Vector de Trayectoria.
  Utiliza el algoritmo de vector de ruta. Son distintas formas de decir lo mismo.
+ Actualización incremental.
+ BGP "Interno" y "Externo".
	Puede utilizarse tanto como BGP externo que es su funcionamiento por defecto, como BGP interno. Puedo usar este protocolo dentro del SA como hacía afuera. Hacía fuera es obligatorio pero hacía dentro podría elegirlo.

**¿Por qué es importante BGP?**

Porque es el protocolo que se utiliza en internet. Básicamente cualquier comunicación que sale desde un sistema autónomo hacía otro sistema autónomo, se comunica por BGP.

**¿Que diferencia BGP a el resto de los protocolos de ruteo?**

Acá si entra el concepto del sistema autónomo. Lo que hace BGP es publicar sus AS. Si bien pública las rutas, pero son pertenecientes o asociadas a un AS.

Cuando hago la publicación de rutas del AS, puedo elegir que rutas publicar y cuales no. No es obligatorio informar todas las rutas.

#### BGP - Operación

+ Acumula múltiples trayectorias de BGP anunciadas por routers internos y externos
+ Escoge la mejor trayectoria para cada prefijo de red anunciada, y la instala en la tabla de reenvío
+ La mejor trayectoria su vez se envía a los routers BGP vecinos
+ Las políticas se aplican modificando la selección de la mejor trayectoria

Básicamente BGP opera de la siguiente forma:

Agarra y se aprende las rutas, porque va aprendiendo de todos los routers que tiene asociados, ósea con el cual tiene vinculo. 

Por lo general un AS tiene vínculos con varios AS. Por ejemplo, Telecentro tiene un router que pública el AS de Telecentro contra el AS de Telefonica. Otro o el mismo que pública contra Telecom, otro contra Claro, y así sucesivamente con distintos sistemas autónomos. 

**¿Qué es lo que hace BGP que sea elegido por defecto en internet?**

<u>Lo que hace BGP es calcular la mejor trayectoria para cada ruta que tiene, y eso es lo que le informa a los otros. No es que, como EIGRP o RIP, o cualquiera que informaba todo lo que tenía conectado y la demás información. Lo único que hace es informar la mejor trayectoria desde ese router, o mejor dicho desde ese punto BGP hacía otro</u>. 

Entonces eso es lo que lo hace extremadamente potente en internet. <u>Porque si cada router hiciera una entrada por todas las rutas que tiene publicadas, las tablas de ruteo serían gigantes</u>. En este caso lo único que hago es solamente publicar la mejor trayectoria. Con eso gano muchísima tasa de "acierto".

---

BGP tiene dos procesos. Un proceso **aprender** y otro **anunciar**.

**Proceso de "entrada" de BGP (Aprender)**: <u>Lo que hace es capturar cuales son las mejores trayectorias de cada lado, hacer el calculo y meterlos dentro de su propia tabla</u>.

+ Recibe información de trayectoria de sus enrutadores pares (peers).
	Recibe la trayectorias de sus pares. Los pares son los routers con los cuales está conectado directamente y de ahí aprende las mejores rutas.
	
	Si yo tengo, en el mismo router, una interfaz que conecta Telecentro con Claro, otra con Fibertel, entonces lo que yo voy aprendiendo, es como llegar de un lado hacía el otro, las voy acumulando y voy buscando cual es la mejor trayectoria.
	
	Una vez que tengo la mejor trayectoria, eso es lo que voy a publicar hacía fuera.
+ EI resultado de la selección de trayectoria de BGP se coloca en la tabla de rutas de BGP.
+ Se marca la "mejor trayectoria".

**Proceso de "salida" de BGP (Anunciar)**: <u>Siempre anuncia las mejores trayectorias para llegar a las redes y dentro de las tablas se van a mandar primero las mejores trayectorias cuyo registro y longitud son únicos</u>. Registro y longitud significa, es la red que están anunciando. Y que tenga la menor distancia a destino.

+ Anuncia "mejor trayectoria" a sus pares.
+ Las mejores trayectorias se instalan en la tabla de reenvío si:
	+ EI prefijo y su longitud son únicos
	+ Tienen la menor "distancia al destino" desde el punto de vista del protocolo

![[Pasted image 20240522160040.png|400]]

El proceso es bastante simple, pero la configuración de BGP tiene ciertas complicaciones.

Primero, como es un protocolo que se utiliza como se dice "in the wild" (en el mundo salvaje de internet), la configuración del protocolo requiere, no solo conocer mi AS, sino ponerme de acuerdo con quien me estoy conectado de una clave para poder vincular las redes.

<u>Es por esto que, si yo estoy publicando mi AS se lo público a alguien, con ese alguien, nos pusimos de acuerdo una clave para que los mensajes que pasen por ahí sean privados y autenticados. Quiere decir que, yo soy el dueño de este sistema autónomo y te estoy publicando estas redes</u>.

Después el protocolo, cuando está en funcionamiento permanente es muy eficiente, los cálculos de las mejores trayectorias es costoso a nivel de computo. Sobre todo porque esta todo encriptado.

Es mandatorio hacía internet sino no podes comunicarte con nadie. Puede usarse para adentro, pero no es aconsejable. Se puede utilizar hacía adentro sin necesidad de usar encriptación ni password para que tenga vinculo. 

---
## Clase 9 - Capa de transporte

![[Pasted image 20240504144532.png|150]]

Un proceso, cuando quiere enviar un paquete hacía otro host de otro lugar, lo que hace es pedirle al stack de protocolos, en este caso TCP-IP, que establezca la comunicación.

Para hacer eso, como vimos, cada una de las capas le va a agregar su propio encabezado (excepto la capa de enlace, que agrega encabezado y cola de paquete), y después va por el enlace físico como diferentes niveles de señal.

![[Pasted image 20240524154006.png]]

Lo que es importante saber es que, TCP-IP es capa internet, hacía abajo es la capa de enlace (link), tiene que ver con todos los dispositivos de capa 2 (hub, switch), todos esos equipos nos permiten comunicarnos dentro de una red interna. Si tenemos que ir de una red a otra, necesitamos utilizar la capa de internet (la capa 3), y para eso necesitamos un router.

Tanto la capa de enlace, como la de red, lo que hacen es vincular redes. <u>Recién la capa 4 es la que vincula un host con otro host. Es en el único momento en el que la dos máquinas se ven y se hablan. Antes de eso, las capas inferiores, son todas para redes</u>.

---

Provee comunicación entre sistemas finales (extremo a extremo).

+ Orientado a la conexión (TCP)
+ No orientado a la conexión (UDP)

Esto sería un compendio de lo que uno ve con un analizador de protocolo, viendo un paquete cualquiera de red. 

![[Pasted image 20240524154515.png|500]]

En estos está el encabezado de capa 2, luego el encabezado de IP, el encabezado amarillo que es TCP/UDP que son los dos protocolos que se utilizan en la capa de transporte y luego los datos (aquellos que vienen de capas superiores), y por último el CRC de siempre.

Así como en la capa 2, teníamos el MTU era lo que limitada el máximo tamaño de paquete que íbamos a poder enviar sin fragmentar. <u>En el segmento TCP o UDP, ese tamaño máximo es el MSS (Maximum Segment Size)</u>.

<u>Tenemos dos formas de comunicarnos. Un protocolo que es orientado a la conexión (TCP) y otro no orientado a la conexión (UDP)</u>.

### [[Puertos]]

### UDP (User Datagram Protocol) - RFC 768

**NO orientado a la conexión**: No se establece una conexión entre los extremos.

**NO confiable**: La información que envía el emisor puede perderse o dañarse antes de llegar al receptor.

La unidad de datos es el byte (octetos). Los bytes se agrupan en segmentos

---

Empezamos por el protocolo más simple y sencillo que tenemos en la capa de transporte. 

Este protocolo es del año 80. Desde ese entonces hasta hoy no tuvo ningún cambio.

Es no orientado a la conexión porque no debo establecer ningún tipo de sesión contra nadie. Es igual que IP, que Ethernet. Manda el paquete, si llega o no llega, no interesa.

Es no fiable porque, al no establecer conexión. Manda el paquete y no le interesa si llega o no.

#### Campos del paquete UDP

![[Pasted image 20240524160714.png|450]]

Tenemos:

+ **Puerto Origen (16 bits)**: Por lo general, tienen un número que va entre el 1025 y el 65536, porque, al no se un puerto registrado que lo usa el sistema operativo, utilizo cualquiera de esos puertos para establecer la conexión.
+ **Puerto Destino (16 bits)**: Va el puerto que va a tener la máquina. 
  Supongamos que queremos hacer una consulta DNS a los servidores de google. En el puerto de destino ira el número 53, que es el puerto de DNS. Este funciona bajo UDP.
  También, por lo general, tiene un número que va entre el 1025 y el 65536.
+ **Longitud del mensaje (16 bits)**: Tamaño total del mensaje.
+ **Checksum (16 bits)**: Acá tenemos el primer problema.
  En la primer clase se mencionó que, el estándar de facto es el protocolo TCP-IP, pero que no adhiere, si bien las capas parecen bastante acercarse al modelo de OSI de las 7 capas, hay en algún punto donde no se cumple. Uno de esos puntos es el checksum.
  
  El checksum hace una suma complemento a 1, pero al paquete le agrega una pseudo cabecera.
  
  **¿Qué es está pseudo cabecera?**
  
  En el modelo OSI, las capas no conocen los datos de las otras capas y lo único que hacen es pasarse los datos a través de interfaces.
  
  Esta pseudo cabecera, conoce los datos de la capa 3. Incluye: Dirección de origen, dirección IP de destino, el protocolo y (algo más que no recuerda). Pero es básicamente eso.
  
  Con eso calcula el checksum, ¿Por qué?
  
  Porque como los protocolos de la capa 4, uno lo puede utilizar para comunicarse, no entre una máquina y otra máquina, sino que, entre una máquina y muchísimas máquinas (lo que sería una multiplexación), de alguna forma tiene que diferenciar en el checksum ese tipo.
  
  Entonces, de alguna forma tiene que ser capaz de diferenciar el paquete, y una de esas diferenciaciones están dentro del checksum.
  
  Por lo tanto, el checksum no solo tiene la suma del complemento a 1, incluye los campos de la capa 3.
  **Datos**: 

<u>Acá no hay control de flujo, ni de congestión, nada</u>.

### TCP (Transmission Control Protocol) - RFC 9293

**Orientado a la conexión**: Es necesario establecer una conexión entre los extremos.

**Confiable**: La información que envía el emisor llega en forma segura al receptor.

La unidad de datos es el byte (octetos) - Los bytes se agrupan en segmentos 

Es orientado a la conexión. Recordar que, la capa 3, la capa 2 son no orientadas a la conexión. <u>Este protocolo establece mecanismos, no para reservar recursos en toda la red, pero si para que entre la capa 4 de un host y la capa 4 de otro, se reserven recursos ellos para poder hacer la transmisión</u>.

Es fiable. Esto significa que si yo envío un mensaje, este es recibido y luego se envía una respuesta de "ok" (a esto se le llama Acknowledgement).

---

La forma de establecer una comunicación fiable es asegurando que los segmentos llegaron a su destino. Para esto <u>los extremos envían confirmación o **acknowledgement** (ACK)</u> por cada paquete que se pide.

![[Pasted image 20240524162639.png|400]]

Tenemos un problema. Yo envío un paquete, pero este puede o tardar mucho en ir, y obviamente que la respuesta puede tardar mucho también. 

Cuando se habla de tiempo es porque hay un temporizador que va contando el tiempo que pasa desde que se envío el paquete.

Esto es para que no se quede colgada la conexión.

![[Pasted image 20240605121735.png|400]]

El primer tema es el camino "feliz". Ósea, envío un paquete, me llega el ACK dentro del tiempo establecido.

<u>Segundo problema. Envío un paquete y ese ACK me llega tarde. Tengo que pensar algún tipo de metodología para ver si eso que llegó tarde está bien o está mal</u>.

<u>Lo tercero. Enviar el paquete y que nunca llegue</u>.

De alguna forma voy a tener que hacer ciertos mecanismos para que ese paquete se vuelva a retransmitir y me garantice que llegue a destino.

---

Supongamos el camino "feliz". Yo envío un paquete y me llegan los ACK: Hay un mecanismo llamado **ventana deslizante**, que lo que me permite es, enviar muchos paquetes de datos y yo recibir, con un último ACK, por ejemplo envío 3 paquetes y del otro lado contestan que recibió los 3 paquetes bien. <u>Hay dos mecanismo, uno es contestar el ACK paquete por paquete y el otro es confirmar todos los paquetes juntos</u>.

![[Pasted image 20240605122714.png|400]]

<u>Enviar varios paquetes sin esperar la confirmación, hace que la tasa de transferencia sea un poco mejor</u>.

---
#### Campos del protocolo TCP - Trama TCP

![[Captura de pantalla 2024-06-05 131959.png|500]]

El **puerto origen** y **puerto destino** es exactamente igual que el UDP. El puerto Origen debe ser un puerto mayor a 1025, el puerto destino puede ser cualquier puerto (caso común, típico, es el puerto 80 del HTTP server). 

**Número de secuencia**: Es un número expresado en bytes por el cual yo estoy enviando el paquete. En el analizador de protocolo, vamos a ver que, cuando iniciamos la sesión por primera vez, nos pone un número de fantasía que es el 1, pero en realidad el número de secuencia es gigantesco de 32 bits. Este número se va incrementando no en 1 (hay un caso en que si), sino que se va incrementando con la cantidad de datos que envío.

**Número de acuse de recibo**: Índica el número de secuencia del siguiente byte que estoy esperando recibir.

Tanto emisor como receptor tienen estos números de secuencia y acuse de recibo. Yo te voy a informar mi número de secuencia con mi cantidad de datos y vos me vas a mandar como acuse de recibo, la suma de esas dos cosas + 1 porque es el byte que yo estoy esperando que venga. Es un juego entre emisor y receptor en cuantos bytes te mande, yo estoy esperando recibir esos bytes. Siempre es un número que se va a acumulando.

**HLEN**: Longitud de cabecera. Esto es igual que en IP, la longitud de cabecera son 4 bits. Como mínimo vamos a tener el número 5. Pero podría ser más porque hay opciones.

**RES**: 4 bits que están sin uso, reservados.

**Bits de control**: Debemos entender que, así como teníamos en IP el X, Y, Z, que uno era más fragmentos, el otro era no fragmentar, en este caso vamos a tener 8 flags distintos que cada uno significa algo.

Estos 8 flags son:

+ **CWR** (Congestion Window Reduced): Se encarga de controlar la congestión
+ **ECN** (Explicit Congestion Notification): Se encarga de controlar la congestión
+ **URG** (Urgent Pointer field significant): Puntero que me indica que hay que prestarle atención a un campo posterior que se llama urgente. 
+ **ACK** (Acknowledgment field significant): Quiere decir que, cuando este este bit prendido, yo te voy a informar que te estoy enviando un ACK.
+ **PSH** (Push Function): Se utiliza cuando estoy mandando datos.
+ **RST** (Reset the connection): Para cerrar una conexión.
+ **SYN** (Synchronize sequence numbers): Para sincronizar los números de secuencias.
+ **FIN** (No more data from sender): No tengo más data para enviar.

![[Pasted image 20240605131924.png|300]]

**Ventana**: Esta ventana es, <u>la cantidad de bytes que estoy dispuesto a aceptar como receptor</u>. 

Todo el stack TCP IP (en realidad todo el stack de red), se maneja con buffers. Yo tengo un tamaño establecido para los buffer que puedo utilizar para llenar con los datos que me van llegando de las distintas capas. Por ejemplo, tengo un paquete que está fragmentado, bueno yo tengo que tener el espacio suficiente dentro de los buffers para poner los pequeños fragmentos que me van llegando y después unirlos y pasarlos a la capa 4.

En este campo de ventana yo le digo cuantos bytes tengo disponibles, o que me podrías mandar, para hacer una comunicación.

Esto porque, supongamos que, yo emisor, estoy conectado en una red Ethernet. Entonces yo puedo mandar hasta 1500 bytes por paquete. IP y TCP, puede mandar 65.000. Tengo una maquina potente, buffer grande, podría recibir lo que quiera.

Del otro lado tengo una maquina vieja que está conectada a una red vieja y que su MTU por ejemplo es de 536 bytes y tengo muy poca memoria. Entonces no te puedo decir mándame 65.000 bytes porque no los puedo resolver mi lado. Entonces, en este factor de ventana te digo mándame 1.024 y mas de 1.024 no va a mandar.

El tamaño de la ventana en TCP (Window Size) es un valor que indica la cantidad máxima de datos que el receptor está dispuesto a aceptar antes de enviar una confirmación. Es crucial para el control de flujo, asegurando que el emisor no abrume al receptor enviando demasiados datos demasiado rápido.

**Checksum**: Es la suma complemente a 1. <u>Tiene la misma pseudo cabecera que se incluye (esta cabecera son 4 campos - IP origen y destino, protocolo y longitud del paquete TCP)</u>.

**Puntero de urgencia**: Indica cual es el último byte urgente que estoy mandando. Es un puntero que se suma al número de secuencia que yo mande. Este puntero lo que me dice es, a partir del número de secuencia, cual es el fin de los datos urgentes.

**Opciones + rellenos**: <u>Pueden no estar al igual que en IP. Pero si están es por palabra completa. La opción debe tener los 32 bits</u>. Hay varias opciones, una de ellas es por ejemplo, en maquinas nuevas y con mucha memoria, podría negociar, en vez de mandar paquetes de hasta 64 k podría mandar paquetes más grandes. Entonces hay una opción donde puedo extender el MSS a un valor mucho más grande. 

Otra opción es opción de **timestamp**. Yo quiero saber exactamente cuanto tiempo tarda un mensaje en llegar de un lado al otro. Entonces dentro de la opción puedo mandar mi timestamp para que del otro lado cuando lo reciben saben que exactamente cuanto tiempo tardó el mensaje en llegar de un lado al otro. Para hacer eso se supone que las maquinas están sincronizadas. El servicio MTP se encarga de mantener las maquinas actualizadas a milisegundos.

**Datos**: El mismo paquete editado de datos que viene de las capas superiores.

---
##### Consideraciones

Tenemos que pensar en algunas cosas. La capa de transporte se va a encontrar con varios problemas y estos van a estar dados dependiendo del tipo de red al cual estemos conectados. 

**Si estamos conectados a una red** [[Redes LAN (Local Area Network)|LAN]]: Las redes LAN por lo general tienen baja latencia, ancho de bandas adecuados, pocos errores. Entonces, los temas con los cuales va a tener que lidiar en este caso TCP, van a ser problemas triviales, algo muy fácil de solucionar.

**Las redes** [[Redes WAN (Wide Area Network)|WAN]]: Aquí estamos en algún lugar bastante más "salvaje". Tenemos ancho de banda variable (hay gente que todavía sigue funcionando con un modem conectado en la línea telefónica a 56Kb por segundo) y gente que tiene conexiones de ancho de banda de 10 Gb, 100 Gb. Entonces, ya tenemos estas diferencias. 

<u>El segundo problema es la latencia</u>. Si yo tengo que conectarme, vamos al caso más favorable. Yo tengo mi conexión de internet en mi casa que me da telecentro y quiero hablar con otra computadora fuera de mi red, pero también esta dentro del mismo ISP. Este sería el caso más favorable porque es donde menos latencia voy a tener. Los problemas de ancho de banda serán los mismos. Pero la latencia será mínima ya que estamos dentro del mismo ISP.

Pero supongamos que nos queremos conectar con una computadora que esta muy lejos, en otro continente. La latencia será muy alta si utilizamos el enlace por el pacifico o el atlántico. <u>El problemas de las redes WAN no es solo el ancho de banda variable sino que la latencia</u>.

<u>Por último, las redes móviles</u>. Con las redes móviles pasa un efecto adicional de las redes WAN. Con las redes móviles vamos a tener el mismo problema de ancho de banda distinto (no es lo mismo alguien que utiliza 2G, 3G, 4G y 5G), cada una de estas tecnologías tiene distintos anchos de banda. Mas o menos latencia. Pero tienen otro problema que es que, como es una red móvil y yo me estoy moviendo, puedo tener una especie de micro cortes en mi conexión que, ante el uso cotidiano es indetectable, pero estos existen. 

De alguna forma TCP contempla todos estos casos y dificultades.

##### Problemas con los que tendrá que lidiar TCP

**TCP tendrá que lidiar con**:

+ **Pérdida de paquetes**
+ **Alta latencia**: Si bien es algo que no podemos combatir (porque es específicamente por la distancia). Entonces, como ajustar los distintos temporizadores que va a tener TCP dependiendo de esta latencia.
+ **Fluctuaciones de Throughput**: Como los paquetes pueden seguir cualquier camino. 
+ **Injusticia en la asignación de recursos**: Imaginemos que, una sola conexión TCP se consumiera todo el ancho de banda de un router y nadie pueda navegar por esa red. Lo que va a intentar TCP es no comerse todos los recursos para que los demás puedan trabajar. No quiere decir que no vaya a tratar de usar el máximo disponible, pero dejara un hueco de trabajo para que los demás se puedan conectar. Cuantos más haya conectados, menor tasa de transferencia van a tener todos. Trata de ser "equitativo".

---

Acá debemos diferenciar dos cuestiones:

+ **Control de Flujo**: Tiene que ver con la relación emisor receptor. Soy el que transmite y voy a transmitir con lo que vos me hayas dicho que yo puedo transmitir, la famosa ventana.
  Si tu ventana es de 64K yo voy a transmitir como máximo eso.
+ **Control de congestión**: <u>Es entre el emisor y la red</u>. Es como voy a tratar de no consumir todos los recursos y que los demás puedan trabajar con esa red. Y si detecto algún tipo de problema, voy a tratar de reducir mi velocidad de transferencia (la cantidad de datos por unidad de tiempo), para evitar que se congestione la red (si la red está congestionada nadie puede hablar).
  Cada uno de los emisores controla la congestión. No es un ente jerárquico o centralizado, son los emisores.

---

#### Camino de 3 vías - Handshake

<u>El profesor menciono que TCP era orientado a la conexión. El camino de 3 vias es lo que genera el establecimiento de la conexión</u>.

En inglés se lo suele llamar **Handshake**.

![[Captura de pantalla 2024-06-05 142125.png|300]]

Host A y Host B. Hablamos directamente de Host's. 

El Host A envía un paquete que le indica a B que se quiere comunicar con él. Esa indicación de que se quiere conectar con el host B, a parte del número de secuencia que tiene, es el el flag de syn en 1. 

El host B contesta que también quiere comunicarse con él. Pone el bit de sync en 1 y un ack en 1 es la confirmación del paquete anterior.

Luego el host A contesta con el ack en 1. Esto significa que ya tienen la comunicación hecha.

Yo te mando un mensaje, vos me lo confirmas y yo confirmo tu confirmación. Ya establecimos el camino de 3 vías y la sesión está abierta. A partir de ahí van todos los datos.

---

Esquema de ejemplo.

![[Pasted image 20240605145232.png|500]]

Un host A con una ip particular, sale a través de un router. Ese router a través de una interfaz serie que tiene otra IP distinta, hacía otro router en donde tiene la interfaz serie que será el destino.

El comando telnet va a ser entre el host A y el router 2, hacía la IP de la placa serie. La aplicación telnet es para enviar comandos hacía un terminal remoto. En este caso el router. Y podría configurar los datos que necesito del router.

---

![[Captura de pantalla 2024-06-05 145712.png|400]]

Tenemos el host A y el router 2 que es al router donde nos vamos a conectar.

Salgo desde el puerto origen 1764 del host A y voy a puerto destino 23, que es el puerto conocido para telnet en el router destino.

Host A:

+ Puerto origen 1764
+ Puerto destino 23
+ MSS = 1480
+ W = 64512
+ ACK = 0. Porque yo establezco la conexión
+ ISN = 4149664824. Número de secuencia.
+ El bit de syn está prendido.
+ No envío ningún dato

Router 2:

+ Puerto origen 23
+ Puerto destino 1764
+ MSS = 536. Su red por debajo no es IP, seguramente es otra red.
+ W = 4128. El router no tiene mucha memoria. Su ventana es pequeña.
+ ACK = 4149664825. Es un número más que el número ISN del origen anterior.
+ ISN = 1514625064. Envía su propio número de secuencia.
+ El flag de de syn está prendido.
+ El flag ack está prendido.
+ No envío ningún dato

Host A:

+ Puerto origen 1764
+ Puerto destino 23
+ W = 64512
+ ACK = 1514625065. Es el número de secuencia anterior + 1.
+ ISN = 4149664825. Número de secuencia.
+ El bit de ack está prendido.
+ No envío ningún dato

A partir de acá ya establecieron la comunicación.

Router 2:

+ Puerto origen 23
+ Puerto destino 1764
+ W = 4128
+ ACK = 4149664825. Es el número de secuencia anterior + 1.
+ ISN = 1514625065. Número de secuencia.
+ El bit de ack está prendido. Confirmación de lo anterior.
+ El bit de push está prendido. Voy a empezar a enviar datos.
+ La cantidad de datos que manda son 12.

Recordemos que, la ventana es de 536 y tiene 537 bytes para enviar (12 + 525). Entonces manda un pedacito chiquito y después un segmento completo.

Router 2:

+ Puerto origen 23
+ Puerto destino 1764
+ W = 4128
+ ACK = 4149664825. Sigue siendo el mismo. Es el número que espera del lado del host. 
+ ISN = 1514625077. Número de secuencia. Es el número anterior más los 12 bytes que envié.
+ El bit de ack está prendido. Confirmación de lo anterior.
+ El bit de push está prendido. Voy a empezar a enviar datos.
+ La cantidad de datos que manda son 525.

Esa fue la primer parte. 

La segunda parte del envío es:

En el ISN al comienzo de este nuevo envío de datos es la suma del ISN anterior más los 525 bytes enviados anteriormente (la suma en la imagen esta mal, debería ser 1514625602, en ves de 1514625906).

Se puede ver que se envían 6 bytes más.

![[Captura de pantalla 2024-06-05 152138.png|400]]

¿Cómo hace el control de los paquetes?

Se hace con los números de secuencia y los número de ACK más los flags de sincronismo y ACK. Con eso se hacen los controles de ACK.

##### Finalización

Ya vimos el inicio, ya vimos el envío y ahora tenemos que cortar la transmisión.

Hay dos formas de hacerlo. Uno es, la forma en que el cliente le manda al servidor "termino la conexión", prende el flag de fin, eso llega al servidor y si este no tiene nada que transmitir manda el flag de fin a mi también y se cierra la conexión.

![[Pasted image 20240605155601.png|400]]

Puede darse el caso de que el cliente quiera cerrar la transmisión, ósea no tiene más datos para enviar pero que el servidor si. Entonces el cliente envía el flag de fin pero el servidor envía el ACK. Comienza a enviar los datos, mientras tanto el cliente enviará los ACK y cuando termina el servidor, envía el fin y espera el ACK del cliente.

![[Pasted image 20240605155625.png|300]]

#### Temporizadores y estados

##### Temporizadores

Yo mando un paquete y me pongo a contar cierto tiempo. Si dentro de ese tiempo no me llego el ACK, voy a volver a enviar el paquete, y si me sigue sin llegar el ACK, lo vuelvo a enviar (hay un límite pero es así).

Si tengo un timeout que es muy corto voy a tener muchas retransmisiones, lo que significa poca tasa de transferencia porque reenvío el paquete un montón de veces.

Siu tengo un timeout muy largo, tardo mucho tiempo en darme cuenta que tengo un problema. Entonces de alguna forma tengo que determinar el timeout adecuado.

+ Un Timeout demasiado corto -> Timeouts prematuros -> Mayor cantidad de retrasmisiones
+ Un Timeout demasiado largo -> Lenta reacción a los segmentos perdidos

Disminución del throughput (rendimiento)

**¿Qué utilizar para determinar un timeout adecuado?**

Uno podría pensar en el RTT. El RTT es el tiempo que tarda un paquete entre que va hasta el lugar y vuelve. El tema es que el RTT, si tengo una red orientada a la conexión, el RTT es siempre el mismo. Pero en una red como IP o Ethernet que no son orientadas a la conexión, el RTT puede variar bastante. 

EI RTT (Round Trip Time) no es estable a lo largo de una conexión TCP. Aunque es una métrica que se tiene en cuenta.

**RTT medido**: Tiempo transcurrido desde el envío de un segmento hasta que se recibe su ACK.

Entonces lo que se hace es utilizar, para el calculo de los temporizadores un timeout que considera ciertos desvíos estadísticos para hacer una mejor estimación. Para cada paquete que envío y recibo, voy tomando el RTT y lo voy recalculando de forma permanente.

Y con los parámetros que se ven en la formula, lo que hago es calcular qué timeout voy a tener que configurar en cada uno de los temporizadores. Son varios, no es un único temporizador.

![[Pasted image 20240605160952.png|400]]

##### Máquina de estados y temporizadores

Los puertos TCP pasan por varios estados.

Como ya sabemos, a UDP no le importa nada, envía y listo o recibe y listo. Pero en TCP pasa por varios estado.

---

Temporizador de retransmisión: Cuando no se recibe ningún ACK, se retransmitirá regularmente.

Temporizador de persistencia: El remitente utiliza el temporizador de persistencia para consultar periódicamente al receptor el tamaño de la ventana para evitar la pérdida de mensajes con una ventana de notificación distinta de 0.

Temporizador de mantenimiento: Detecta regularmente si el otro extremo de la conexión se bloquea o se reinicia.

EI temporizador de 2MSL (tiempo de vida máximo del segmento) mide si una conexión está en TIME WAIT. La duración de 2MSL no se puede modificar a menos que se vuelva a compilar el Kernel. Es el tiempo en que una conexión va a estar en espera.

---

Los puertos, como ya se mencionó, pueden pasar por varios estados:

+ El estado closed quiere decir que ese puerto esta disponible para ser utilizado.
+ El estado listen. Cuando yo levanto un servidor, por ejemplo un servidor web, el puerto queda. en estado listen esperando peticiones de un cliente para poder hacer alguna acción.
+ Estado de SYN-SENT o SYNC-RCVD. Estado de sincronismo de envío o de recepción. Quiere decir que, o está esperando que yo le mande el sincronismo o sincronismo + ACK cuando estamos haciendo la conexión por primera vez.
  SYN-SENT está hecho desde el lado del cliente. El SYN-RCVD está desde el lado del servidor.
+ **Established**. Cada vez que se cumplió el camino de 3 vías, la máquina de estados interna del stack TCP va a estar en estado established. Quiere decir que la conexión está abierta y dispuesta para la transferencia. Cuando está en este estado es cuando podemos hacer todo el intercambio de datos.
+ FIN-WAIT1. Es, yo cliente le estoy enviando al servidor mi condición para finalizar la comunicación y el FIN-WAIT2 es, espero la terminación del servidor remoto. Cuando recibo el fin remoto paso el TIME-WAIT que es donde voy a estar esperando este temporizador que lleva dos veces el maximun server lifetime y después recién ahí, libero todos los recursos y cierro físicamente ese puerto. Eso es cuando yo tengo datos que vayan esperando entre, osea el cliente cierra la conexión pero el servidor sigue mandando datos, entonces tengo el FIN-WAIT 1 y el FIN-WAIT 2.
  Si vamos por el otro lado que es donde yo no tengo ningún dato es el CLOCK wait que es directamente entre cliente y servidor no tienen más datos para enviar, en cuanto me llega el FIN el último ACK, cierro las cosas y no espero.

![[Captura de pantalla 2024-06-12 194028.png|300]]

Ahora bien, hubo un momento en que hubo una especie de ataque que era, cuando vos te querías conectar había un par de servers maliciosos en el cual vos te conectabas, vos le dabas el fin y nunca te cerraban la conexión, siempre enviaban un dato para que no se cerrará la conexión.

Si vos tenes todas las conexiones abiertas llega un momento donde no podes aceptar más conexiones. Recordemos que solo podemos llegar a tener hasta 65000 conexiones. Se ocuparon todos los puertos y no hay más servicios. 

Esto se soluciono ajustando mejor los tiempos del maximum lifetime. Ese tiempo es un tiempo que está configurado dentro del stack de TCP. No se puede cambiar excepto que uno recompile el kernel o el stack.

---
#### TCP - Mecanismos

Estos mecanismos son para controlar de alguna forma la congestión en la red.

Estos son:

+ Slow Start
+ Congestion Avoidance
+ Fast Retransmit
+ Fast Recovery

El primero de los mecanismos que se utilizan para trata de evitar que se congestione la red es el **Slow Start**. <u>Como su nombre lo indica es un inicio lento, lo que significa que yo voy a empezar a enviar datos de una forma lenta y cada vez voy a estar enviando mayor cantidad de datos</u>. Es para encontrar el punto de máximo de velocidad de transferencia sin saturar la red desde el momento 0.

**Congestion Avoidance**. Sería algo así como evasión de la congestión. Eso quiere decir que <u>cuando llego a la ventana de congestión, que es un umbral, de alguna forma voy a tener que trabajar para reducir la tasa de transferencia y no saturar la red</u>.

**Fast Retransmit**. En cuanto yo recibo ACK's duplicados, que quiere decir. Yo mando un paquete, mando otro paquete, y lo único que hacen es llegarme los ACK's del paquete anterior, lo que hago es, en forma rápida retransmitir el paquete que me está faltando, no sigo esperando el vencimiento del paquete de retransmisión. Cuando me llegan ACK's duplicados de paquetes anteriores directamente retransmito los paquetes sin esperar el vencimiento del temporizador. Con eso pierdo menos tiempo. Porque si tengo que esperar a que temporizador se termine para poder mandar el paquete que tengo que retransmitir porque el ACK no llega, <u>con el Fast Retransmit, cuando me llegan ACK's repetidos, directamente retransmito los paquetes de los cuales no me llegaron ACK y ya mande</u>.

**Fast Recovery**. Lo que hace es. Una vez que retransmitió un paquete perdido, en vez de bajar la tasa de transferencia bruscamente, porque, que pasa, si a mi me llegan ACK's repetidos y yo retransmito el paquete, lo que tengo que hacer es retransmitirlo inmediatamente pero tengo que empezar a bajar la tasa de transferencia porque, que yo reciba ACK's repetidos quiere decir que hay congestión en algún lado. Entonces de alguna forma tengo que empezar a limitar el ancho de banda. Que hacían los primeros protocolos. <u>Cuando recibía ACK's repetidos, retransmitía pero bajaba a 0 la tasa de transferencia y empezaba con un Low Start de nuevo. Las distintas mejoras fueron que, en vez de empezar con un Low Start de 0, era bajar hasta cierto umbral y comenzar de ahí hacía arriba, también con Low Start</u>.

Con estos cuatro mecanismos y distintos ajustes es como funcionan los protocolos de TCP. 

Tenemos varias versiones:

+ Tahoe
+ Reno y New Reno
+ CUBIC
+ BBR (Bottleneck Bandwidth y RTT)

El **Tahoe** fue el primero que implemento el Fast Retransmit y el Fast Recovery. El Slow Start, el aumento de tasa de transferencia empieza en 0 y el aumento de tasa de transferencia es exponencial. Siempre duplica la velocidad.

El Tahoe cuando encontraba congestión, lo que hacía era volver a empezar desde 0.

**Reno y New Reno**. Hace lo mismo pero en vez de comenzar desde 0 utiliza el Fast Recovery y comienza desde un umbral un poco más arriba. Entonces la tasa de transferencia no cae a 0 de golpe.

**CUBIC**. Se llama así porque para hacer el calculo, en vez de empezar exponencialmente, en este tiene una fórmula elevada al cubo. Esta forma se recupera más rápido que la anterior. Es más adecuado a redes que están más ayornadas a las velocidades actuales. Es el algoritmo que se utiliza por defecto en Linux desde hace 15 años aproximadamente y en Windows hace 7 y 8.

Se adapta mucho mejor a las redes actuales.

**BBR (Bottleneck Bandwidth y RTT - Roundtime trip)**. Considera el ancho de banda y el tiempo de ida y vuelta. Lo hizo google, tiene pocos años. Al ser más moderno se adapta mejor a las redes actuales. Gestiona mejor la congestión pero aún no es muy utilizado.

---

Está forma es en el Tahoe. Es la forma más común.

Eso que se ve ahí entre 0 y 5. Esa subida que crece en forma exponencial lo que va haciendo es aumentar el ancho de banda hasta que llega a un umbral que se llama "umbral del arranque lento" en donde, a partir de ahí, empieza a crecer linealmente hasta que llega a una ventana que es la ventana de congestión. 

La ventana de congestión es una ventana que tiene el emisor internamente. Esa es con la cual controla la cantidad de bytes enviados hacía la red. Cuando detecta el primer Timeout, Tahoe mandaba la tasa de transferencia a 0 y empezaba el arranque lento de nuevo.

Y así hasta que reciba el segundo Timeout. Cuando lo recibe, vuelve a bajar la tasa de transferencia pero ya seteó su ventana de congestión en un número más bajo y así sucesivamente. 

![[Captura de pantalla 2024-06-12 202658.png|550]]

¿Se va a recuperar en algún momento?, cuando empiece otra transferencia.

---
## Clase 10

Hoy vamos a empezar a ver algunos protocolos de redes WAN.

Hasta ahora lo que habíamos visto eran todos protocolos de redes LAN. Vimos Ethernet, tanto en su versión Dix V2 como la 802.3 y también vimos lo que comúnmente se conoce como wifi que es la 802.11. <u>Estos protocolos de red LAN son de la capa de enlace. Ambos son no orientados a la conexión y no confiables y están pensados para trabajar en una red donde el medio físico es relativamente accesible</u>. 

En uno tenemos cable coaxial, UTP o fibra y el otro funciona a través de ondas electromagnéticas. En una utilizamos el protocolo CSMA/CD (para la 802.3 o la Dix V2) y el CSMA/CA (para el 802.11).

Todos estos protocolos se utilizan en redes que son redes LAN. En el cual estamos hablando de una oficina, una empresa, un campus universitario. Distancias cortas.

<u>Hay otros protocolos que se utilizan para mayores distancias</u>. Por ejemplo, si tenemos que hacer una conexión desde la sede Cordoba al rectora que esta en Padua o al campus que se encuentran a un par de kilómetros, tenemos que empezar a utilizar otro tipo de protocolos, ya que no cumplen con lo que es una red LAN.

### WAN - HDLC

Para ello hay protocolos de redes [[Redes WAN (Wide Area Network)|WAN]]. Las redes WAN originalmente se utilizaban para conectar edificios distantes, y cuando hablamos de distantes nos estamos refiriendo de algunos pocos kilómetros a recorrer el planeta completo.

Wide Area Network, Red de área extendida, se utiliza para vincular edificios

+ En forma privada. Vínculos internos.
  Cuando queremos vincular dos edificios utilizamos también este tipo de redes.
+ En forma pública. Lo que conocemos hoy como Internet. En realidad son varios vínculos de redes WAN que vinculan un ISP con otros ISP y así uno puede navegar en esta red de forma pública.

![[Pasted image 20240617195126.png|450]]

En este gráfico podemos ver que la comunicación WAN se produce, entre un router que está conectado a una LAN y otro router que está conectado a otra LAN.

Las distintas tramas van a ir pasando a través de los routers por está red LAN hasta que llega al destino.

#### Protocolos de red WAN

+ **High Level Data Link Control (HDLC)**
+ Point to Point Protocol (PPP)
+ **Asynchronous Transfer Mode (ATM)**
+ **Frame Relay (FR)**
+ Synchronous Data Link Controller (SDLC)
+ Logical Link Control (LLC)

Los que veremos en esta materia serán el HDLC, FR y ATM.

Hay más protocolos de WAN, pero estos 3 engloban las características genéricas que pueden tener cualquier tipo de protocolo. Cada uno tiene sus particularidades.

### Modelo OSI

<u>Los protocolos de WAN siempre están en la capa de enlace. En la capa de enlace es donde estamos transportando las tramas que es justo el paso anterior al medio físico que lo va a hacer</u>.

Por arriba de esta capa de enlace vamos a tener la capa de red que es la que vincula las multiples redes y la capa de transporte que es la que nos vincula de un host al otro con el protocolo que nosotros queramos. 

Recordar que las capas en teoría son agnósticas, en el cual si uno le pide servicios a una capa no importa el protocolo que sea, los servicios son genéricos. Entonces, <u>podemos tener una capa de enlace de datos que tenga HDLC, FR o ATM y por arriba podemos tener en la capa de red IP o IPx y en la capa de transporte TCP, UDP, etc</u>.

### Protocolo HDLC

Características:

+ <u>Es un protocolo de comunicaciones punto a punto y punto a multipunto</u>.
+ <u>Proporciona recuperación de errores</u>.
+ <u>Ofrece una comunicación confiable entre transmisor y receptor</u>.
+ <u>Protocolo orientado al bit y sincrónico</u>.
+ Permite una transmisión transparente, independientemente del código de nivel superior. Podemos tener cualquier protocolo de la capa de red (casi) que para HDLC no le importa.

Es un protocolo que se origino a fines de los 70s. Se basa en otro protocolo que es propietario que es de IBM.

Originalmente nació para conectar los mainframes con las terminales bobas. 

---

**Punto a multipunto**: Acá, la comunicación HDLC, la van a hacer entre dos routers o más. Generalmente lo que se utiliza es que, vamos a tener varias placas serie.

En el TP de ruteo, a los routers le pusimos varias placas series. En este caso lo que hicimos fueron conexiones **punto a punto**, porque un router se conectaba por un enlace hacía otro router y así sucesivamente.

<u>Cuando estamos aplicando que, por cada interfaz serie, solo tenemos del otro lado un unico router es un punto a punto. El otro caso sería que, sobre una unica interfaz serie, tengamos conectados múltiples routers</u>.

![[Pasted image 20240617201905.png|400]]

---

Como el protocolo nació con el concepto de un mainframe que procesa y varias terminales bobas que no tenían ningún tipo de procesamiento. Su capacidad de computo estaba extremadamente reducida a lo poco que le pudiera dar la interfaz de red.

**Tipos de estaciones**: Las estaciones corresponden a hosts.

+ **Primaria**: <u>Es la encargada de controlar el funcionamiento del enlace. Generalmente son las estaciones que tienen el poder de computo. Son quienes **generan ordenes**</u>.
+ **Secundaria**: <u>Es controlada por una estación primaria. **Genera respuestas**</u>.
+ **Combinadas**: <u>Puede ser una estación primaria o secundaria</u>. Cumple cualquiera de los dos roles, dependiendo del momento en el que está operando.
  
  <u>Se dan cuando uno pone en vez de una terminal boba un router a trabajar con el protocolo HDLC o cuando pone una computadora que tiene gran poder de computo a trabajar con este protocolo. **Genera ordenes o respuestas**</u>.

---

**Configuraciones del Enlace**:

+ **No Balanceado**: <u>Está formado por una estación primaria y una o más secundarias</u>.
+ **Balanceado**: <u>Esta formado por dos estaciones combinadas</u>. 

Las dos trabajan en [[Modo de transmisión Half Duplex y Full Duplex|Half Duplex o Full Duplex]].

---

**Modos de Operaciones**:

+ **Modo de Respuesta Normal (NRM)**: Se utiliza en la configuración **no balanceada**. <u>La estación primaria emite órdenes y la o las secundarias envían respuestas</u>. Corresponde al modo original de trabajo en donde se encuentra la única primaria que comanda a multiples secundarias.
+ **Modo Balanceado Asincrónico (ABM)**: Se utiliza en la configuración **balanceada**. <u>Cualquiera de las estaciones combinadas puede iniciar la comunicación. En este caso, dos estaciones combinadas trabajan pasándose información. Una primero adopta el rol de primaria y luego de secundaria y viceversa</u>.
+ **Modo de Respuesta Asincrónico (ARM)**: Se utiliza en la configuración **no balanceada**. <u>La estación secundaria puede iniciar la comunicación, pero la primaria sigue siendo la responsable de la comunicación</u>.

EI modo ABM es el más utilizado en enlace punto a punto full duplex.

### Trama HDLC

**El protocolo HDLC tiene 3 formas de operación**:

+ <u>Puede estar enviando tramas de información</u>
+ <u>Puede estar enviando tramas de supervisión</u>
+ <u>Puede estar enviando tramas no numeradas</u>

Cada uno de estos campos es la **cantidad de bits** que ocupa.

![[Pasted image 20240618095820.png|500]]

Vamos a tener los siguientes campos:

+ Campo FLAG que tiene 8 bits.
+ Campo de DIRECCIÓN de 8 bits.
+ Campo de CONTROL puede ser entre 8 y 16 bits, aunque más grande también: <u>Indica qué tipo de trama estamos usando</u>.
+ Campo de INFORMACIÓN: Es de longitud variable. No hay límite. El único requerimiento es que los datos que vayan ahí sean múltiplos de 8 bits (bytes completos).
+ Campo de CRC de 16 bits.
+ Campo de FLAG nuevamente de 8 bits.

Este protocolo es sincrónico orientado al bit. <u>HDLC utiliza un código banda base no retorno a cero invertido. Esto significa que cuando hay un 0, invierte la polaridad, y cuando hay un 1 también</u>.

Otra característica que tiene HDLC es que, normalmente, cuando enviamos una secuencia de bits, el menos significativa es el que se manda primero y así sucesivamente. <u>En este caso es al revés, se empieza por el más significativo</u>.

<u>El encapsulado que le hace CISCO es que le agrega un campo de protocolo. Ahí va **qué protocolo tiene en la capa de red (capa 3)**</u>.

![[Pasted image 20240618100728.png|550]]

---
#### HDLC - Campo FLAG

+ Los campos FLAG son los delimitadores de la trama y tienen la forma $01111110$ ($7E$)
+ Utiliza el mecanismo de inserción de ceros, para garantizar la transparencia del protocolo.
+ <u>EI objetivo es que no existan en el campo de datos una combinación de bits igual al FLAG</u>.
+ En caso que aparezcan 5 unos seguidos, el transmisor a continuación inserta un cero.

Ejemplo de inserción de ceros:

+ Bits originales: 
	$01101100111101111101111110$
+ Bits con inserción de ceros: 
	$011011001111011111 \textcolor{#cd9324}{0} 011111 \textcolor{#cd9324}{0} 10$

<u>El campo FLAG es el que se utiliza para hacer el sincronismo de tramas</u>. Así como teníamos en Ethernet 8 bytes y que estaban conformados por AA los 7 primeros y el último era AB para indicar que ahí terminaba el FLAG.

En este caso el FLAG es un solo byte y lo que tiene es, especificado en binario, el número $7E$ ($1111110_{2}$). <u>Es la trama que se utiliza como delimitador para decir que estoy iniciando o terminando</u>.
##### Mecanismo de inserción de ceros

Esto no tiene que ver con el campo, tiene que ver con el protocolo. <u>Si yo tengo una cadena muy larga de 1, tenemos que buscar la forma para poder seguir manteniendo el sincronismo</u>.

Recordar que, las propiedades que tenía que tener un código de banda base era tratar de reducir la componente de continua, buscar el sincronismo y la detección de la línea. Entonces, si tengo una cadena muy larga de 1, podría perder alguna de estas cuestiones.

<u>Entonces este protocolo si detecta 5 unos seguidos, inserta un cero para que haya un cambio de estado</u>.

<u>Esto lo hace el protocolo cuando inserta los datos en la red</u>. Ya sabe qué datos tiene que poner, los tiene en memoria y a medida que los va insertando bit a bit, si detecta 5 unos seguidos, inserta un cero. Cuando detecta el quinto, no importa lo que siga, inserta un cero, después sigue con lo que tiene.

<u>Del lado del receptor hacer exactamente lo mismo</u>. Cuenta cuantos 1 seguidos tiene. Si detecto los 5 unos seguidos y encuentra un 0 al siguiente, ese lo quita. Si el bit que sigue no es un cero, sino que es un uno, lo que va a hacer es fijarse. <u>Si hay un séptimo que es cero, es un delimitador ($7E=1111110_{2}$) y termina la trama. Si el séptimo no es un cero, ósea es un uno, hay un error en el protocolo y la trama se descarta</u>.

![[Pasted image 20240618102110.png|500]]

#### HDLC - Campo de dirección

EI campo Dirección normalmente tiene 8 bits, pero puede ser ampliado a varios bloques múltiplos de 7 bits.

<u>EI bit menos significativo de cada octeto indica si es el último octeto de la dirección</u>.

+ 0 más octetos.
+ 1 último octeto.

<u>Es utilizado para identificar las estaciones secundarias en un enlace punto a multipunto</u>. Este campo no se utiliza en enlaces punto a punto.

Lo único que especifica es la dirección de la máquina secundaria. Si estamos en una conexión punto a punto el campo de dirección no se utiliza, porque yo le mando a una maquina y la otra me envía a mi.

Pero en un campo punto a multipunto, la primaria, la cual siempre se sabe que dirección es, el tema es como identifico a las secundarias. 

Entonces en este campo lo único que tengo es la dirección lógica que va a tener cada una de las máquinas secundarias.

Es una dirección lógica que se le pone a cada máquina (no es una MAC).

#### HDLC - Campo de control

EI campo Control tiene formato variable (puede ser de uno o dos bytes) y <u>se implementan todos los mecanismos de control de flujo y enlace</u>.

**Existen 3 tipos de tramas**:

+ <u>Información o datos de usuarios</u>
+ <u>Supervisión</u>
+ <u>Gestión o No numeradas</u>

Este mismo campo es un campo multifunción. Dependiendo de uno o dos bits vamos a determinar que tipo tiene. 

Este campo de control sirve para 3 tipos de tramas.

##### Trama de información o datos de usuario

Se utiliza para:

+ Enviar datos de usuarios (capa superior a HDLC)
+ Aceptación de tramas
+ Información de tramas enviadas

![[Pasted image 20240618104151.png|300]]

El primer bit es un cero.

**$\text{N(s)}$**: Número asociado a las tramas enviadas.

**$\text{P/F}$**: Poll / Fin

**Poll** significa que la estación primaria está enviando información. Si la estación secundaria prende este bit significa que está enviando una finalización (**Fin**) de la información que está enviando.

**$\text{N(r)}$**: Número de secuencia de la próxima trama que se espera recibir.

<u>Si el campo de control empieza en cero, es una trama de información. El protocolo HDLC es un protocolo confiable. Aquellos que son confiables garantizan que las tramas que se envían llegan a destino</u>.

HDLC hace un juego parecido a lo que hace TCP. En TCP teníamos el número de secuencia y el ACK. Acá hace lo mismo pero, en vez de hacer con cantidad de bytes, lo hace con tramas enviadas.

<u>Este protocolo lo que hace es que, cuando envía las 7 tramas ($2^{3}$), vuelve al cero de nuevo</u>. Entonces, de la misma forma en que TCP podía mandar multiples tramas y recibir un solo ACK por todas ellas, este protocolo puede hacer lo mismo. La única salvedad es que el máximo de tramas que puede enviar y recibir un ACK por todo junto es 7.

##### Trama de supervisión

**Se utilizan para tareas de supervisión**:

+ <u>Aceptación de tramas</u>
+ <u>Solicitud de transmisión de tramas</u>
+ <u>Suspensión temporal de la transmisión</u>

Algunos ejemplo de este tipo de tramas:

+ **RR**: Receptor Preparado ($00$)
	<u>Especifica que todas las tramas me llegaron bien hasta el número de trama indicado en el campo $\text{N(r)} - 1$</u>.
	
	Por ejemplo, si en el campo $\text{N(r)}$ me vino el número 5. Le voy a decir que tengo todas aceptadas hasta el número 4. Espero que mandes el número 5.
+ **RNR**: Receptor no Preparado ($10$)
	<u>Especifica que no puede recibir más tramas pero te reconozco que llegaron hasta la trama que venga en $\text{N(r)} - 1$</u>.
+ **REJ**: Rechazo Simple ($01$)
	<u>Significa que recibí hasta el número de trama que venga en el $\text{N(r)} - 1$. Todo lo que sea de ahí en adelante se tiene que retransmitir todo</u>.
+ **SREJ**: Rechazo Selectivo ($11$)
	<u>Especifica que la trama que estoy enviando en el $\text{N(r)} - 1$ no la recibí. Pude haber recibido las que siguen pero esa en particular no</u>.

![[Pasted image 20240618105026.png|300]]

**$\text{N(r)}$**: Número de secuencia de la próxima trama que se espera recibir.

**$\text{S}$**: Codifica el tipo de trama de supervisión. Especifica el comando que estoy enviando de la estación primaria a la secundaria o viceversa.

**$\text{P/F}$**: Poll / Fin

En este caso, nos fijamos en los 2 primeros bits. Si estos tienen un 10 es una trama de supervisión.

##### Tramas no numeradas

Son utilizadas para:

+ Tareas de gestión
+ Conexión / Desconexión del enlace
+ Control del enlace

Algunos ejemplos de comandos y respuestas de tramas no numeradas:

+ **SABM (C)**: Fija modo asincrónico balanceado.
	Coordinamos entre dos maquinas combinadas que vamos a usar el módulo asincrónico balanceado.
+ **UA (R)**: Es una confirmación.
+ **DISC (C)**: Desconectar.
+ **DM (R)**: Modo desconectado.
+ **FRMR (R)**: Rechazo de tramas.
+ **RSET (C)**: reiniciar conexión.

C: Comando
R: Respuesta

![[Pasted image 20240618121518.png|300]]

El primer y segundo bit es $11$.

**$\text{M}$**: Codifica ordenes y respuestas en este tipo de tramas. 5 bits (los dos del comienzo y los 3 del final) define 32 comandos y 32 respuestas.

**$\text{P/F}$**: Poll / Fin

Más que estado lo que hace es dar ordenes. 

<u>Tengo 5 bits para clasificar todos los posibles comandos y respuestas</u>.

Este es un modo orientado a la conexión y confiable. Esto significa que previo a hacer una comunicación tengo que conectarme, pedir permiso.

#### Campo de información

+ <u>Este campo solo está presente en las tramas de Información</u>. 
	Si estamos mandando una trama de supervisión o no numerada este campo no va, son 0 bytes.
+ La cantidad de bits es múltiplo de 8.
	Siempre se envían octetos.
+ Es un campo variable. 
	No hay limitación en este campo, uno puede mandar la cantidad de datos que quiera.

#### Campo FCS (Frame Check Sequence)

Frame Check Sequence:

+ Código para la detección de errores, se excluyen los delimitadores
+ Normalmente se utiliza CRC de 16 bits aunque puede negociarse 32 bits

#### HDLC - Formatos extendidos

Esto significa. <u>Cuando nació el protocolo en los 70s con los campos de 8 bits alcanzaba, pero luego comenzó a crecer la cantidad de maquinas y de cosas y fueron creciendo los campos de control</u>.

El campo de control quiere crecer porque si tengo un campo de control de por ejemplo 7 bits, solo tengo una ventana con 8 tramas que puedo enviar y quizás esto es un muy poco en redes donde debo tener más velocidad. Si bien esto en interfaces serie y lo máximo que puedo poner son 2Mb, pero no importa, si tengo más velocidad, 7 tramas es muy pequeño. Entonces se hicieron campos de control con mayor cantidad de bits tanto para tramas enviadas como para recibidas. Entonces tenemos campos de control con 16, 32 y 64 bits.

![[Pasted image 20240618122429.png|500]]

Normalmente se utiliza el campo de 8 bits, pero por ejemplo si estamos en una red en donde el HDLC se está comunicando por una comunicación vía satélite donde hay mucha latencia y ancho de banda reducido, conviene que la ventana sea más grande para enviar mayor cantidad de tramas sin confirmación y luego cuando baja la confirmación lo hace con todas juntas.

#### HDLC - Bit Poll/Fin

Depende de quien lo use tiene un significado.

+ Su función depende del contexto.
+ Si es la estación primaria, esta utiliza el bit Poll para solicitar una respuesta de estado a la estación secundaria.
+ La estación secundaria responde al bit Poll con una trama de información o supervisión y el bit Fin.
+ EI bit Fin indica final de la transmisión de la estación secundaria en NRM

---

Tema importante: Cuando hicimos el TP con las interfaces serie, para que estas funcionen tenían que utilizar un protocolo. Cuando levantamos una interfaz serie, CISCO activa en ellas el protocolo HDLC. 

Ósea que cuando hicimos las conexiones serie, lo que estaba por debajo en capa 2, era el protocolo HDLC.

Así es como se vería en el ROUTER. Si hacemos un `sh int se0` (show interface a la serial 0), se ve que la encapsulación HDLC.

![[Pasted image 20240618123431.png|450]]

Está no es la única encapsulación que hay.

### HDLC - Comunicación

Consiste en el intercambio de tramas entre 2 estaciones

Fases:

+ Establecimiento de la conexión
+ Transferencia de datos
+ Liberación de la conexión

Tenemos varias fases para poder intercambiar información entre una máquina y otra.

Antes de comenzar a ver esto. Nosotros tenemos en la trama el 7E como flag, luego vienen todos los campos y después el algoritmo de inserción de 0 cada 5. Pero, ¿Por qué cada 5 bits?

Por que, por ejemplo, en el campo de información, no está prohibido que se envíe el 7E. Por lo tanto, de alguna manera el protocolo tiene que cortar eso para que no llegue este flag de corte en cualquier lado.

#### Establecimiento y fin de conexión

SABM: Establecimiento de la conexión en modo asincrónico balanceado.

UA: Aceptación de la solicitud.

DISC: Pedido de desconexión.

![[Pasted image 20240618123842.png|300]]

El establecimiento de la conexión se hace indicándole que quiere iniciar con cierto modo y si el receptor puede conectarse contesta con un UA (aceptación de la solicitud) y para desconectarse es exactamente lo mismo. Se avisa que se quiere desconectar, recibe un UA y se desconecta.

#### Ejemplo de Datos

Cuando se habla de estación A y B, es host A y host B o router A y router B, o cualquier dispositivo que tiene un vinculo HDLC.

![[Captura de pantalla 2024-06-18 124556.png|500]]

La primer letra "I" es porque se trata de una trama de información.

Entonces la estación A le manda a B, que le está enviando su trama 0 y espera una respuesta de trama 0.

La estación B le manda a la A, a la trama de información, te estoy mandando mi trama 0 y espero recibir tu trama 1.

<u>En el punto donde B le dice que espera la trama 3 de A, ya quiere decir que aceptó la trama 1 y 2</u>.

Cuando la estación A no tiene más datos para enviar, envía un RR pero estoy dispuesto a seguir recibiendo y espero recibir la 4 porque la última recibida fue la 3.

---

Ahora la estación B envía la 3 y espera la 0 del otro lado. 

A envía RNR (Receptor No Ready) con la 4. Ósea no puede recibir más datos.

B vuelve a pregunta y le dice que se encuentra RR y espera la trama 0 y manda la "P" preguntando para que conteste el dato.

A vuelve a responder con RNR. Sigue sin poder recibir, esperando la próxima que va a ser la 4 y con un "F".

B vuelve a preguntar con "P".

A ahora responde con RR, ahora puede recibir. Pudo limpiar el buffer o lo que sea que haya pasado, espera el 4 y pone el "F" para saber que es el fin de la respuesta.

B luego envía el campo de información el 4.

![[Captura de pantalla 2024-06-18 125235.png|500]]

---

¿Cómo se recupera ante un rechazo?

A envía 3 tramas seguidas. Envía la 3, 4, y 5 y espera la 0 del B. La 4 no llega nunca.

![[Captura de pantalla 2024-06-18 125721.png|500]]

En este caso, B hace un rechazo completo. Quiere decir que acepto hasta la 3 y de ahí en adelante hace como que no recibió nada. Entonces dice REJ y espera el 4.

Luego A envía 4 y 5.

En este caso podría ser que haga un REJ selectivo para que solo le envíe la 4. ¿Cómo decide si es un REJ selectivo o completo? Dependiendo de las capas superiores. Dependiendo de lo que haya dicho la capa 3 y 4 con cada una de las tramas que va recibiendo es que va a hacer uno u otro.

---

Recuperación de Timeout.

Al igual que en TCP hay temporizadores. Estos no son tan complejos.

![[Captura de pantalla 2024-06-18 130226.png|500]]

Ambos equipos tienen un Timeout especificado. Este tiene que ver con una configuración preliminar.

Cuando este se vence, se detecta el Timeout y se opera para tratar de recuperarlo.

En este caso.

En el segundo envío de A, B nunca recibe la trama 3. Entonces llega un momento en que la estación B responde RR, estoy esperando tu 3. Pero como el 3 ya lo había enviado, y se ve que no llegó, al esperar el tiempo, A va a decir RR, espero 0 y hace el Pull para preguntar su estado. B responde nuevamente que RR y que espera el 3 (ya que nunca llegó) con el Fin. A envía la 3 y luego B espera la 4.

Esto es como se recupera ante una trama que no haya llegado nunca con confirmación.

Se envía una trama, pasa el tiempo y no me llega la confirmación, listo, tengo que volver a enviarla. A pregunta y se vuelve a enviar.

¿Por qué pregunta para después enviarla?, ¿Qué puede haber pasado?, Manda el 3, ý el 3 llegó pero más tarde. Ósea me perdí la respuesta de la estación B hacía la estación A. No es que me perdí el paquete que llegó sino la respuesta.

Entonces cuando pasa el Timeout vuelve a preguntar y cuando pregunto. Porque el que pregunta es el que tiene información para enviar. Cuando pregunto, dice ok, me llego hasta tal, envía la que sigue.

---
## Clase 11 - [[Frame Relay]]

Características:

+ <u>Técnica de conmutación de tramas</u>
	+ Tamaño variable (Modo Ráfaga)
+ <u>Se utiliza para la transmisión de voz, video y datos a alta velocidad</u>.
	Alta velocidad esta pensada en los años 90s en donde todo el mundo tenía una conexión de modem telefónico. No se transmitía más que 20 o 30Kbps.
	En Frame Relay estamos hablando de conexiones que tenían entre 32Kpbs a 2Mbps.
+ Encapsulación de multiprotocolo (IP, IPX, SNA, etc.).
	Frame Relay es un protocolo de capa 2. Entonces, lo que esté por encima de está capa se podría utilizar cualquier tipo de protocolo como los mencionados aquí.
+ Alternativa a los enlaces dedicados o punto a punto
+ <u>Orientado a la conexión NO confiable</u>.
	Cuando nos conectamos a Frame Relay, nosotros nos vamos a conectar a un Switch de Frame Relay y este Switch va a generar una conexión local, entre nuestro dispositivo y ese Switch.
	
	Esta conexión que nos asigna nuestro proveedor de servicios es exclusiva nuestra. Luego como el proveedor de servicios lo hace internamente en su red es problema de él, pero a nosotros nos entrega un identificador con el cual nos vamos a conectar y del otro extremo también tendrán un id para conectarnos al destino.
	
	Es no confiable. Esto es porque los paquetes se pueden perder (por varias razones).
+ Conexiones
	+ Permanentes (PVC)
	+ Conmutadas (SVC)
+ <u>No corrige errores y no tiene control de flujo</u>.
	Generalmente los protocolos de capa 2 tienen corrección de errores o algún método para retransmisiones o corrección de errores cuando son orientados a la conexión, pero FR no tiene nada.
	
	Lo único que hace es que, la trama que yo envío desde el origen, cuando llega a destino, si nuestro verificador dio bien, sigue.
	
	No hay control de flujo. Por ejemplo HDLC, que es orientado a la conexión y confiable, tenemos un control de flujo. Que es cuantas tramas mando, pero en este caso no hay nada.
	
	El FR nació para ser un protocolo en el cual yo puedo mandar paquetes en forma muy rápida.

<u>Es un protocolo de la capa de enlace</u>. De esta capa ya hemos vistos 3 protocolos distintos:

+ Ethernet (Dix v2 y el 802.3)
+ 802.11
+ HDLC

El protocolo de Frame Relay está hecho en una red que es conmutada porque lleva paquetes de un Switch a otro. Así como en una central telefónica, una vez que establecemos una comunicación, y llevamos la comunicación telefónica por un circuito armado, esto funciona de la misma manera. Lo que hace es conmutar tramas.

### Formato de trama

La trama es extremadamente corta.

![[Pasted image 20240618155204.png|500]]

**Campo Flag (1 byte)**: También es $7E$ al igual que en HDLC.

**Campo de Dirección (2, 3, o 4 bytes)**: Si bien es llamado de esta forma, tiene algunas cuestiones adicionales. En este campo va el <u>número que identifica la conexión entre mi terminal y el Switch al cual me estoy conectando</u>.

**Campo de Información (bytes variable)**: Campo variable.

**Campo FCS (2 bytes)**: Es el CRC.

**Otro campo de Flag (1 byte)**: Indica que termina toda la trama.

#### Campo de direcciones

Analizaremos dependiendo de cuantos octetos está compuesta.

##### Campo de 2 bytes

**Campo DLCI (Data Link Connection Identifier 6 bits)**: Es el identificador del link de conexión de datos. <u>Lo que identifica es, desde mi terminal hasta el Switch, que número tengo</u>.

<u>El campo de dirección esta dividido en dos partes</u>. Tenemos los 6 bits superiores y los 4 inferiores (10 bits para dirección).

![[Pasted image 20240618161249.png|400]]

**Campo C/R (1 bit)**: Corresponde al Comando/Respuesta. Tiene un funcionamiento similar al Pull/Fin de HDLC.

**Campo EA=0 (1 bit)**: Corresponde al Extension Address (extensión de la dirección). <u>Si está en cero quiere decir que la dirección continua en el campo de abajo. Si está en 1 quiere decir que el campo de dirección termino</u>.

**Campo FECN (1 bit)**: Su traducción es Notificación explicita de congestion hacía adelante. <u>Indica que, en la red, hay congestión en el sentido en que el terminal está mandando datos hacía el terminal distante</u>.

**Campo BECN (1 bit)**: Su traducción es Notificación explicita de congestion hacía atrás. <u>Indica que hay congestión desde el terminal distante hacía mi ubicación</u>.

**Campo DE (1 bit)**: Su traducción es Elegibilidad para el descarte. <u>Cuando está en 1 la red puede descartar el paquete, de lo contrario no lo hará</u>.

##### Campo de 3 bytes

En comparación con el campo de dirección compuesto por 2 bytes, este, <u>en la segunda fila, el campo de EA se encuentra en 0 y en la tercer fila está en 1</u>. Recordar que, si está en cero, la dirección DLCI sigue en el campo de abajo. Por lo tanto, el campo de DLCI pasa a ser una dirección de $2^{16}$ (pasamos de 10 bits a 16 bits). 

**Se agrega un Flag más llamado D/C (1 bit)**: Lo utiliza el core de la red, ósea Switches que están entre medio de la red.

<u>El último bit de la trama, el campo EA, se encuentra en 1 para indica que terminó el campo de dirección</u>.

![[Pasted image 20240618162335.png|400]]

##### Campo de 4 bytes

<u>Si tenemos un campo de dirección de 4 octetos cambia un poco más</u>. Se intercala un campo más en la tercera fila en donde agrando el número de DLCI. <u>Ahora tengo 23 bits para el campo de direcciones</u>.

![[Pasted image 20240618162822.png|400]]

#### Conceptos

##### DLCI (Data Link Connection Identifier)

+ Es un identificador lógico del circuito
+ Tiene significado local

Es la conexión que identifica lógicamente mi router hacía el Switch. En una misma interfaz física (cable) se pueden tener un DLCI o varios. Un router tiene una interfaz física contra el Switch de Frame Relay pero pueden tener una o varias subinterfaces lógicas, cada una con su DLCI distinto.

Cada DLCI nos va a comunicar con una terminal remota, con alguien del otro lado. Un DLCI no me comunica con varias. A eso hace referencia de que sea local.

##### DATOS

+ Longitud Variable, número enteros de bytes
+ Máximo tamaño del campo 8192 bytes
+ Normalmente se utilizan campos de 1600 bytes

##### CIR

<u>Committed Information Rate, es el caudal garantizado por la red en un tiempo Tc</u>. 

Es el tráfico contratado al proveedor y por el que se paga

Que tasa de información voy a pasar por unidad de tiempo, en el cual el proveedor me garantiza que no se va a descartar tráfico en la red.

Por ejemplo, puedo tener un enlace de 2 Mbits pero contrato con mi proveedor 64 Kbits de tasa de transferencia. Todo lo que este por debajo de esos 64 K, el proveedor no va a tocar ningún paquete y todos ellos irán de origen a destino sin ningún tipo de inconveniente.

Si me paso de esos 64K, el proveedor puede, si quiere, dejar pasar el tráfico o cortarlo. 

##### DIR

**DE (Discard Eligibility)**. Indica que la trama puede ser elegida para descarte en caso de congestión en la red.

Cuando enviamos la trama, este valor siempre está en 0 para que no sea descartada, pero si se cumplen ciertas condiciones, la red pondrá un 1 y si este se encuentra en ese valor y hay congestión, la red puede descartarlo.

<u>Quien pone el valor de 1 en este Flag es el Switch al que estemos conectados, porque es quien va contando la cantidad de bytes que nosotros estamos mandando y, si nos pasamos del CIR, este lo pone en 1</u>.

##### Bc

+ Committed Burst Size.
+ Volumen de información comprometida durante el tiempo Tc.
+  $Bc = CIR * Tc$

<u>Es el tamaño máximo de ráfaga comprometida. Es la cantidad máxima de datos que la red se compromete a aceptar en un intervalo de tiempo específico (Tc)</u>.

Está asociado al CIR. Generalmente el CIR se especifica en Kbps. Si el Bc mide una vez por segundo, va a ser lo mismo que el CIR. 

El concepto de este es que volumen de información puedo mandar en ráfaga. Por ejemplo, supongamos que tengo que enviar un archivo. Generalmente el archivo es un flujo de datos que se va "goteando" para que la información vaya pasando. Pero si yo tengo algo más al estilo video en el cual yo te transfiero un pedacito de información, ese pedacito se pone en caché y después voy pasando diferenciales, ese pequeño pedacito de información lo debo pasar en un corto tiempo sino pierde sentido esos diferenciales. Entonces, lo que trata de medir este Bc es que la ráfaga no sea demasiado rápida.

Lo que trata de hacer este Bc es que, si me comprometí a pasar esos 64 Kbps, esos 64 Kbps no los pase en la primera decima de segundo, si no que sean distribuidos de la mejor forma posible.

##### Be

+ Excess Burst Size
+ Tráfico marcado al ingresar al nodo FR

<u>Es el tamaño máximo de ráfaga excedente. Es la cantidad adicional de datos que la red puede aceptar por encima de Bc si hay capacidad disponible</u>.

Es todo tráfico que se excede de lo que contrate y que llega al Switch de FR. Este lo marca y podrían ser descartados.

##### Switch

El reloj lo pone el Switch. Es el DCE (Data Circuit terminating Equipment).

##### Router

Funciona como DTE (Data Terminal Equipment - Dispositivo Terminal de Datos) porque es el terminal.

Por ejemplo, contrato a mi proveedor un enlace FR de 64Kbps, pero este no me conecta un clock de 64K, sino que conecta uno de 128K. Esto significa que yo puedo mandar entre 0 y los 64K sin ningún tipo de marca y todo llegará a la otra punta. Si yo me paso de los 64K hasta los 128K, el proveedor los va a marcar y estos podrían ser descartados.

##### FECN (Forward Explicit Congestion Notification)

+ Mecanismo que utiliza la red para avisar en el sentido que viaja la trama que existe congestión

Este bit siempre esta en cero. 

La congestión es que cuando hay una tasa de mensajes o de paquetes que llega a uno de los Switches que está en la red, lo que hace que ese Switch esté sobrecargado, tanto en CPU, como en Memoria, como en Buffer, o lo que sea, y hace que los paquetes no se despachen en tiempo y forma. Cuando detecta esa condición, el Switch lo que hace es poner un 1 dependiendo en que dirección está yendo el paquete.

<u>Si este está yendo de nuestro terminal hacía uno remoto, al terminal remoto se lo pone en el BECN y para nosotros cuando nos llegue el paquete nos los va a poner en el FECN</u>.

##### BECN (Backward Explicit Congestion Notification)

+ Mecanismo que utiliza la red para avisar en el sentido contrario que viaja la trama que existe congestión.

### Ejemplo de FR

En este caso solo tiene 4 nodos, pero pueden ser muchos más en el medio.

![[Pasted image 20240619132722.png|600]]

Imaginemos que es una empresa que tiene 4 sitios. Buenos Aires, Bahía Blanca, Córdoba y Mendoza. Todas las sucursales necesitan estar conectadas entre si.

<u>Las redes FR es una conexión punto a punto. Se conecta un punto A con el punto B y se terminó</u>.

<u>El Backbone son un montón de nodos, de Switches de FR que están en la red y el proveedor lo que hace es, así como a nosotros nos asigna un DLCI para conectarnos al Switch de FR, entre los distintos Switches para la conexión asigna distintos DLCI de la misma forma</u>.

Por ejemplo, con nuestro proveedor nos dijo que, para conectar Buenos Aires le pongamos la interfaz física, que es única, pero que tiene una subinterfaz con DLCI 10. Ese DLCI 10 es para comunicarnos hacía Bahía Blanca. Entre el nodo donde esta conectado Buenos Aires y Bahía Blanca utilizo el DLCI 50 y entre el nodo de FR y Bahía Blanca uso el DLCI 28.

<u>**¿Deben ser todos los números DLCI distintos?** No, pueden ser todos iguales. El número solo tiene significado local entre, ya sea el DTE y el DCE o entre cualquiera de los nodos de Switches de FR. Lo que hace es una conexión punto a punto</u>.

El servicio genera todo el circuito interno.

¿Cómo hace Córdoba para comunicarse con Mendoza, o Mendoza con Bahía Blanca? La única forma que tienen para poder comunicarse es pasando por Buenos Aires. 

¿Se puede hacer un enlace directo? Si, se puede. Se contrata otro enlace de Córdoba a Mendoza y listo ya funciona. 

<u>Ahora tengo un problema, Buenos Aires se convierte en un cuello de botella. Recordemos que el enlace físico en este caso es 1 y los demás son lógicos</u>.

Si yo tengo que, por ejemplo, el enlace lógico es de 64K CIR y el proveedor me puso 128K de clock, si yo pongo 2 enlaces más de 64K, el proveedor deberá subir la velocidad porque no podrá cumplirlo.

<u>Estás redes tienen tarifa plana. Esto quiere decir que, yo contrate los 64K CIR a 1000 pesos por mes. Son 1000 pesos por mes siempre</u>.

### LMI (Interfaz de Administración Local)

Hay un protocolo más. Este es interno del proveedor. No es entre la comunicación DTE y DCE.

Este es un protocolo para la administración de interfaces.

![[Pasted image 20240619141458.png|500]]

![[Pasted image 20240619141522.png|600]]

Con respecto al gráfico del ejemplo de red FR. Este es muy sencillo porque son solo 4 Switches FR. Pero antes había centenares de estos. Entonces el proveedor, de alguna forma tenía que configurar todos ellos para que el camino se forme completo desde un DTE hasta el otro DTE de la otra punta.

Con este protocolo tenía dos tipos de controles:

+ <u>Se fijaba que el terminal este vivo</u>. Cada 10 segundos se enviaba un keep alive al terminal para saber que estaba vivo. 
  
  ¿Esto para qué? Supongamos, por ejemplo el caso de Buenos Aires Bahía Blanca, si el terminal de Bahía Blanca se cayó, directamente <u>lo que hace este protocolo es, todo paquete que salga de Buenos Aires hacía allí, directamente lo descarta porque el destino está apagado, para que congestionar la red</u>.
+ <u>También administra todos los Switches que están en el medio</u>. Supongamos que uno se cae. Estos por lo general tienen enlace redundantes entre otros Switches. Entonces, <u>lo que puede hacer este Switch internamente es generar nuevos DLCI entre los distintos Switches para que el tráfico que iba a pasar por el que se cayó, sea conmutado hacía otro Switch y este pueda manejar ese tráfico</u>.
  
	Esto generará algún corte en la comunicación pero rápidamente lo va a recuperar y hará que el tráfico siga funcionando.

### Ejercicio de Frame Relay

El tiempo Tc, que es el "policía", indica cada cuanto tiempo voy a verificar los bytes que pasaron. Voy a verificar cada cierto tiempo en forma periódica cuantos bytes pasaron. 

Cada paquete que llega al Switch de Frame Relay me dice "sumaste tantos bytes más" y va calculando cuantos bytes pasaron.

![[Captura de pantalla 2024-06-19 142240.png|600]]

AR: A que velocidad ajuste el clock. Más rápido que este no voy a mandar nada.

EIR es el tope máximo lógico en el cual el proveedor solo marca los paquetes. Todo lo que exceda el EIR va a ser descartado. Y ahí si lo descarta el primer Switch al cual estamos conectados.

Las flechas de colores indican con que tasa de envío de paquetes estoy atacando al Switch de FR.

Si por ejemplo estoy mandando 64K y 1s de tiempo. Si estoy mandando 64 paquetes de 1K cada uno, uno detrás del otro, tendré un crecimiento lineal hasta el CIR.

Pero, si por ejemplo, en vez de mandar 64 paquetes de 1K cada uno linealmente, mando 8 paquetes de 8K todos en el primer tiempo, ósea porque cada paquete lo mando de una forma bastante rápida porque tengo un AR muy alto. El crecimiento en vez de ser lineal al CIR, llegará al final del Tc, superándolo.

Generalmente el ISP pone el AR al mismo nivel que el EIR. ¿Para qué? El ISP te da un rango para que mandes mas información de la que tenes contratada pero no tanta como para saturar la red. Entonces por ejemplo, tengo un enlace de 128K, el clock (AR) lo fije en 128K y tenes un CIR contratado de 64K. Entonces, el nodo de FR no va a descartar nada pero si va a marcar todo paquete que exceda el CIR.

Esto si tengo una única interfaz. Si tengo múltiples DLCI el proveedor de servicios pondrá un AR que cumpla con todos los CIR que tengo contrastados, más un "changüí" que me da.

[[CyR II - TP - Frame Relay]]

---
## Clase 12 - Protocolo ATM

Es sería el último protocolo que vamos a ver de capa 2. Este es bastante antiguo. Se creó por la década del 60s.

Es bastante distinto a todos los demás. Todos los protocolos que estudiamos hasta ahora, cuando uno transporta datos, tenían como características que el campo de datos era un campo variable en el cual uno podía tener, dependiendo la tecnología 1500 bytes en Ethernet, 2000 y pico en la 802.11 o hasta 8K en FR o HDLC.

<u>En este caso ATM trabaja con longitud fija</u>. Todos los protocolos de capa 2 tenían su encabezado y cola, en este caso no tiene cola. Como sabemos que siempre va a ser de un tamaño fijo, no necesita cola.

![[Captura de pantalla 2024-06-20 185942.png|400]]

### ATM (Asynchronous Transfer Mode) - Modo de transferencia asincrónica

+ Efectúa la transferencia de datos en celdas de longitud fija
+ Multiplexación de varias conexiones lógicas a través de una única interfaz física.
+ Mínima capacidad de control de errores y de flujo: 
	Reduce el costo de procesamiento.
+ Las velocidades de transmisión especificadas en la capa física van desde 155 Mbps hasta 40 Gbps

De sincrónico no tiene nada.

<u>ATM tiene como característica que uno podría llegar a tener diferentes tasas de velocidad o diferentes anchos de banda de subida que de bajada</u>.

Basa su funcionamiento en una red de conmutación. Se basa en pequeños paquetes (celdas). El protocolo basa todo su funcionamiento en la conmutación de estas celdas, las cuales se multiplexan vía TDM. 

Este protocolo utiliza multiplexación por división de tiempo. Es un protocolo que nació en la telefonía. Es un protocolo de datos que nació en la telefonía.

<u>Nació con altas velocidades. Como dice ahí va desde 155Mbps hasta 40Gbps. Aunque en realidad, como es un producto que nació en la telefonía, todas las tasas de transferencia están relacionadas con los canales de las diferentes jerarquías de telefonía. Donde teníamos famosas tramas [[Normas E1 y T1|E1 y T1]] con diferentes velocidades</u>.

Todas las tasas de velocidades que tiene ATM están referidas a velocidades de este tipo de jerarquías.

Llegan a velocidades tan altas como esos 40Gbps todo porque se transporta por SDH que es la jerarquía digital sincrónica.

La multiplexación se hace por división de tiempos. En ATM vamos a tener una conexión, un enlace físico en el cual vamos a tener algún camino virtual y circuitos virtuales. Esto lo que hace es que, por el mismo enlace físico, de una forma similar a las VLAN's lo hace ATM.

### Pros y contras de la longitud fija o variable

<u>Cuando nosotros trabajamos con estructuras de datos de longitud fija, tiene la ventaja de que es muy fácil y rápido de procesar</u>. Físicamente dentro del hardware se encuentra en posiciones consecutivas, en cambio la longitud variable, al tener que determinarlo en tiempo de ejecución, los bloques de datos se tienen que apartar a medida que los vaya necesitando la aplicación.

<u>La contra de la longitud fija es que es rígido para hacer cambios</u>.

<u>La longitud variable es mucho más dinámica en ese aspecto, pero dificulta el procesamiento</u>.

### Modelo de referencia

El cubo es, cada una de las capas (así como las vemos en el modelo OSI), tienen algún tipo de dialogo entre ellos. Se comunican por servicios. 

![[Pasted image 20240620192439.png|500]]

Tenemos la **capa física**, la **capa propia ATM**, una capa de **adaptación a ATM - AAL**, una **capa de servicios y aplicaciones ATM** y **protocolos de más alto nivel**. Esto está en lo que se llama plano de usuario, que es lo que utilizamos nosotros para transferir información.

Después tenemos dos planos adicionales: 

+ **Plano de control**: <u>El plano de control, es quien nos permite establecer la conexión o el control de la llamada. Este es un protocolo orientado a la conexión</u>.
+ **plano de administración**: <u>El plano de administración es quien se encarga de hacer la administración de las capas. Hace que las funciones que brinda cada capa se manejen adecuadamente</u>.

Recordar que esto viene de la telefonía. Allí, todos los equipos que se conectan entre ellos, tienen todo un sistema de señalización que hace que puedan trabajar en conjunto. 

#### Características

**Protocolo orientado a la conexión**: Tenemos dos tipos de circuitos que podemos hacer cuando hacemos una conexión.

Existen dos tipos principales de conexiones virtuales que se pueden establecer entre dos puntos en la red:

+ **[[SVC y PVC#SVC (Switched Virtual Circuit)|SVC (Switched Virtual Circuit - Circuitos Virtuales Conmutados)]]**
	Este tipo de conexión es al mejor estilo de llamada telefónica.
	
	<u>Cuando hago la conexión con este SVC, va a ser la red la que va a tratar de reservar todos los recursos para completar la llamada extremo a extremo</u>.
+ **[[SVC y PVC#PVC (Permanent Virtual Circuit)|PVC (Permanent Virtual Circuit - Circuitos Virtuales Permanentes)]]**
	<u>En contraposición tenemos el PVC. Acá es el administrador quien genera de punta a punta la reserva de recursos</u>.
	
	El SVC lo hace de forma dinámica y en PVC el proveedor genera un camino virtual para satisfacer la conexión.

**Utiliza el par VPI/VCI para establecer las conexiones**: <u>Asimilemos que el par VPI/VCI son dos identificadores. Uno es el identificador del camino virtual y el otro del circuito virtual. Son identificadores similar al DLCI de FR. Tiene un sentido local</u>. 

+ Dentro de un VPI existen varios VCI

Cuando se establece la conexión se reservan los recursos para garantizar la calidad de servicio establecida.

### Relación con el modelo OSI

La capa física sigue siendo igual, pero los servicios que tiene que brindar la capa de enlace en el modelo OSI, se brindan casi en su mayoría con las dos capas. Una la de la red ATM y la otra la de adaptación a ATM. No en su mayoría porque en el modelo OSI tiene un par de funciones más.

![[Captura de pantalla 2024-06-20 193820.png|500]]

ATM nació como una red para hacer conexiones punto a punto. En algún momento se hizo para utilizarse a nivel de redes LAN. La red ATM es para usar en una red WAN, pero en un momento se utilizó para una red LAN.

<u>En ATM el broadcast no existe</u>.

<u>El otro gran problema es el costo. La red ATM es cara</u>. Es privativa para usar a nivel de LAN porque requiere de equipos especializados, capas especializadas. Eso hizo que no funcione a nivel LAN, aunque si a nivel WAN.

<u>Lo que tenía de bueno ATM es que su capa física tiene muchos tipos de conexiones</u>. Esta puede ser de coaxil, de UTP, con fibra, con enlace microondas, ya que está pensado para la telefonía. Su uso más grande se hizo para las redes WAN.

### Las distintas capas

Si empezamos por abajo. La capa física donde tenemos el clock y el medio físico.

+ Con coaxil en el medio físico llegábamos a los 155Mb.
+ Con par trenzado UTP desde 25Mb a 150Mb.
+ Con fibra de 150 Mb para arriba. 

![[Pasted image 20240620200521.png|500]]

Dentro de la capa física tenemos la sincronización de celdas. Nosotros vamos a enviar celdas y estás deben estar sincronizadas. No hay un reloj externo para garantizar esto. El sincronismo va en la propia celda. Transmitimos y con el código banda base que estamos mandando tenemos que sincronizar los clocks.

También la capa física hace la verificación del encabezado. Tenemos un código similar al CRC. En el cual si hay algún problema, la capa física descarta directamente.

Capa ATM hace un control de flujo, de conexiones, trabaja en la multiplexación de las celdas.

<u>La AAL lo que va a hacer es segmentación y reensamble (es lo que vimos como fragmentación)</u>. Como está arriba podemos tener cualquier protocolo de capa 3, supongamos que tenemos IP y viene un paquete de 1500 bytes. Lo va a tener que fragmentar en la cantidad de celdas que sean necesarias, las va a mandar y del otro lado la va a tener que desfragmentar.

Convergencia. Vamos a ver que esta capa AAL lo que nos permite es tener distintos tipos de servicios. Son 4.

Capas superiores. Capa 3, capa 4 de protocolo que elijamos. 

### Celdas ATM

+ Tamaño fijo de 53 bytes
+ 5 octetos de cabecera
+ Campo de información de 48 octetos
	Acá, nos dijo que esto venía del mundo de la telefonía. Y en este mundo teníamos dos grandes mundos, el europeo. Donde tenemos la tramas E1 y tenemos el Japón/EEUU y ahí están la T1.
	Los Europeos utilizan 8 bits, los americanos 7 bits.
	Cada canal de comunicaciones. En la telefonía Europea son 64K en la telefonía Yankee son 56K. Esa es la gran diferencia.
	Entonces los norteamericanos proponían un tamaño de 32 bytes para cada celda de datos y los Europeos proponían 64K de bytes de datos. Al no ponerse de acuerdo hicieron el promedio (64 + 32) / 2 = 48 
+ EI empleo de celdas pequeñas reduce el Jitter
	Jitter: Cuando nosotros transmitimos en cualquier red, dependiendo de la longitud que tenga el medio donde estamos transmitiendo vamos a tardar más o menos. A ese fenómeno se lo conoce como latencia. Es el tiempo que me lleva a mi un paquete, que salga de un origen y llegue a un destino. 
	
	<u>El Jitter se refiere a que, yo mando 1000 paquetes y estos no tardan exactamente lo mismo. Algunos más, otros menos. El Jitter es la diferencia entre el que más tarde y el que menos tarda</u>.
	
	<u>Si yo tengo todos los paquetes de la misma longitud, yo lo que hago es reducir este Jitter. Porque todos los paquetes primero van a seguir el mismo camino y segundo que los paquetes cuando son pequeños, tardan el mismo tiempo en la computación</u>.
	
	<u>Otra ventaja que tiene el tener celdas pequeñas es que los buffer que tienen que tener los equipos de comunicaciones son pequeños</u>. Primero el hardware se puede optimizar más y segundo, opero mucho más rápido que si fueran paquetes variables.
	
	<u>Pero el rendimiento del protocolo es horrible. De 53 transporto 48</u>.
+ Las celdas de tamaño fijo se pueden conmutar de forma más eficiente 
+ La implementación física de los mecanismos de conmutación es más fácil para celdas de tamaño fijo

Las celdas ATM tienen 53 bytes de tamaño fijo. Pensemos que Ethernet, la trama corta eran 64 bytes, la trama larga 1518. Acá todas las celdas tienen 53 bytes.

De estos 53, los primeros 5 son la cabecera. 

### Red ATM

<u>Una red ATM es muy parecido al FR. Tengo un nodo en el cual se va a conectar a un Switch ATM y ese Switch ATM se va a conectar con uno o múltiples Switch ATM en la red del ISP y vamos a terminar en otra terminal también conectada a un Switch ATM</u>.

![[Pasted image 20240620202625.png|500]]

Los Switches FR no tienen nada que ver con los ATM. Están pensados para distintos servicios. 

Acá se definen dos tipos de interfaces: 

+ **Interfaz UNI (User Network Interface - Interfaz de la red al usuario)**: Es la que va entre el terminal y el Switch ATM
+ **Interfaz NNI (Network Network Interface - Interfaz de red a red)**: Es la que vincula distintos Switches ATM.

En la interfaz UNI generalmente tenemos velocidades de [[Normas E1 y T1|E1 o T1]], sea un 1 mega y medio o 2 megas hasta 155Mb.

<u>Las interfaces NNI si están conectadas por fibra</u>. Desde el Switch ATM al usuario puede tener otros tipos de tecnologías pero entre los Switch ATM la mayoría de veces eran fibra. Entonces la velocidades iban entre 155Mbps y 40Gbps. 

### Switch ATM

El Switch ATM tiene dos metas.

+ Hacer la conmutación lo más rápido posible. Con la tasa de pérdida de celdas lo más baja posible. Eso trata de hacer el Switch ATM.
	Esto porque el protocolo va a tratar de enviar todo lo que pueda, excepto que haya una emergencia. No hay garantía de las celdas.
+ El Switch nunca va reordenar las celdas. Si llegan desordenadas, el Switch las pasa desordenadas. No hay control de ordenamiento.

---

![[Pasted image 20240620203712.png|500]]

Conceptualmente nosotros tenemos un enlace físico y dentro de este vamos a generar caminos virtuales. Ese camino virtual que está dentro del enlace físico.

El enlace físico es un gran caño en donde ponemos pequeños canales. Ese camino virtual lo que va a hacer es, si nosotros tenemos un camino virtual permanente, como sería el de arriba de todo (VP2 y VP3). 

Ese camino virtual, lo que va a generar es como si fuera nuestro "número de teléfono", esa indicación física o virtual del camino y después por dentro puedo enviar múltiples comunicaciones y esos se llaman circuitos y es por donde realmente voy a enviar las cosas.

Por eso es que existe un par VPI/VCI. Uno es el camino y el otro es el circuito que, ese par genera la identificación de la comunicación completa.

Si yo tengo un circuito permanente, el Switch ATM lo que va a hacer es agarrar el VPI y utilizarlo para rootear con ese número. El VPI indica la red y el VCI lo que índica es el Host, sería una cosa similar a eso (es una analogía).

Entendamos que el punto terminal es un router, no es una computadora. Podría ser una PC. Pero generalmente es un router y del lado de atrás del router voy a tener una red LAN con Ethernet o lo que sea y la voy a manejar.

### Capa ATM

Como ya nos dijo, son 53 bytes. Los primeros 5 son correspondientes al header.

**GFC (Generic Flow Control - Control de flujo genérico - 4 bits)**: Controlan la interfaz entre el terminal y el Switch de ATM. Informa entre el Switch y el terminal si hay algún tipo de congestión. Por problemas de convención, vienen en 0.

**VPI (8 bits)**: Es el identificador del camino virtual.

**VCI (16 bits)**: Identifica el circuito virtual.

<u>El par VPI/VCI es el que identifica con que terminal nos queremos comunicar</u>. Es un número que nos da el proveedor y vamos a tener que configurar en el equipo.

**Payload Type (3 bits)**: Está relacionado con la siguiente tabla.

![[Pasted image 20240620234805.png|400]]

Los 4 primeros son datos de usuario. Si experimenta o no congestión.

**CLP (Cell Loss Priority - Prioridad para la pérdida de celdas - 1 bit)**: Este sería parecido al bit de descarte en FR. Con la diferencia de que 0 quiere decir que no puede descartarse la celda y 1 quiere decir que podría llegar a descartarse.

**HEC (Header Error Correction - Corrección de Error de Cabecera - 8 bits)**: Es como un CRC mejorado. No solo permite verificar si hay errores sino que también nos permite detectar y corregir algún error simple, pero solo del encabezado.

**Datos (48 octetos)**.

![[Pasted image 20240620234737.png|400]]

No vamos a tener una trama en un parcial.

---
 
Entre los distintos Switches, la celda es apenas distinta.

En el formato de red a red, el campo de control de flujo no existe. Tenemos un VPI más grande. Esto porque normalmente los Switches ATM manejan entre 16 y 1024 canales para hacer la conmutación y la gran cantidad de canales y circuitos la voy a tener entre los distintos Switches, no entre Switch y cliente final.

Se descarta el GFC y extiendo el VPI a 12 bits. Lo demás queda igual.

![[Pasted image 20240620235825.png|400]]

---

La capa de ATM, la AAL mencionada anteriormente. Nació con 5 tipos de servicios distintos.

+ **CBR constante bit rate**
	Significa que, yo estoy transmitiendo a 64K por segundo y esos son siempre 64K.
+ **VBR-RT Real time variable bit rate**
	Típicamente transmito 64K, después nada, después a 1Mb, eso es variable.
+ **VBR - nRT No Real time variable bit rate**
	Después una combinación. Si es en tiempo real o sino lo es.
	Tengamos en cuenta que, las cosas en tiempo real están pensadas para eventos que están sucediendo en el momento y que no pueden tener dilación en el tiempo.
	Por ejemplo, las interrupciones del microprocesador con las interfaces I/O de las máquinas.
	Estas tienen mayor prioridad.
+ **ABR disponible Bit Rate**
	Yo puedo transmitir con lo que tengo disponible.
+ **UBR inespecífico Bit Rate**
	Si no clasifica en ninguna, entra aquí y es quien menos prioridad tiene.

![[Pasted image 20240621000129.png|500]]

La prioridad de la red, lo más importante es CBR y si nos ponemos a pensar, por como funciona o como fue pensado ATM en la red telefonía en donde siempre estoy mandando tramas en forma sincrónica.

El CBR es más fácil de administrar, más difícil es el bit rate variable. 

### Capa de adaptaciones al medio

Si empezamos de abajo vemos que AAL 1, 2, 5, 3/4. Al principio se hicieron 5, después dijeron que con 4 alcanzaba.

Tenemos dos tipos de conexión. Orientado a la conexión o sin conexión.

Bit rate constante o variable.

Sincronización entre fuente y destino, si es requerido o no y características.

![[Pasted image 20240621001239.png|500]]

AAL 1 - Características: 

+ Soporta bit rate constante
+ Es el primero que se utiliza
+ Es sincrónico
+ Orientado a la conexión
+ De alta prioridad y está garantizado
+ Se utiliza para telefonía. Audio y video va por este canal sin comprimir.

AAL 2 - Características:

+ Es el bit rate en tiempo real
+ Orientado al tráfico sincrónico también
+ Tiene un poco menos de prioridad que AAL 1
+ Generalmente se utiliza para video comprimido. Porque al mandarse comprimido, estoy mandando varios frames en la misma compresión. Al ser de bit rate variable. El video generalmente envío un Key Frame en donde tengo toda la imagen de esa pantalla y luego voy mandando pequeños diferenciales por como va cambiando esa imagen en la original. Cada x Frame mando una completa y luego todos diferenciales. Los diferenciales son chiquitos, pero la completa es grande, eso hace que tenga un Bit Rate Variable. 
  Para este tipo de video se utiliza la capa de adaptación 2. 
  Si el video es sin comprimir, ósea mando una imagen detrás de la otra siempre tengo que garantizar que todas las imágenes lleguen, sino el video se verá mal.

AAL 5 - Características:

+ Bit rate variable
+ Generalmente se utiliza para mandar TCP IP. Mandar datos.

AAL 3/4 - Características:

+ Bit rate variable
+ Se utiliza cuando yo por encima de ATM tengo un servicio orientado a la conexión y sincrónico, por ejemplo FR. Lo mando por esta capa 3/4 que no está orientada a la conexión para que sea lo mas liviano posible
+ No orientada a la conexión

---

Distintos tipos de servicios y cuan tolerante o que tipo voy a tener que poner a funcionar o sobre que capa.

![[Pasted image 20240621002133.png|600]]

---
## Material extra

En este apartado se encuentra material extra como diferentes parciales (tanto primero como segundo) de diferentes años.

### Ejemplos de primer parcial

#### 1er parcial - 1C. 2024 

1. Preguntó sobre los nodos expuestos y ocultos.
	+ [[Comunicación y Redes II#Nodo oculto|Nodo oculto]]
	+ [[Comunicación y Redes II#Nodo expuesto|Nodo expuesto]]
2. Hacer un esquema sobre el cableado estructurado.
	+ [[Comunicación y Redes II#Cableado estructurado|Cableado estructurado]]
3. Tipo y clase de trama. Privada, pública, etc.
4. Una trama Ethernet sin bytes de sincronismo no CRC
5. Una trama IP dónde pide muchas cosas.  
6. **Domino de colisión y dominio de broadcast. 1 switch con 3 Hosts. Otro switch con 1 host. Los dos switches conectados a un router.**
	+ Dominio de colisión: 4+2, ósea 6. 4 del primer Switch y 2 del otro Switch.
		+ Dominio de broadcast: 2 dominios de broadcast. Uno por cada Switch.
7. Ejercicio de subnetting

---

+ [[Comunicación y Redes II - 1er parcial - 1C 2019]]
+ [[Comunicación y Redes II - 1er parcial recuperatorio - 1C 2017]]

### Ejemplos de segundo parcial

+ [[Comunicación y Redes II - 2do parcial 2019]]

### Ejemplos de examen final

+ [[Comunicación y Redes II - Examen final - Julio 2018]]

## Adicional

+ [[Protocolos.excalidraw]]