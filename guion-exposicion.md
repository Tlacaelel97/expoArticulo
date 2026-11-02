# Guion de exposición — Brüningk et al. (2019)

Actualizado para las **23 diapositivas visibles** de `slides.md`, incluidos los componentes y figuras actuales. Los números de cada apartado coinciden con los números visibles en la presentación. Las dos diapositivas de «La célula» y las dos de «Apoptosis y muerte celular» tienen explicaciones diferentes.

El texto sin corchetes está preparado para decirse en voz alta. Las indicaciones entre corchetes son acciones y no se leen. Los textos de este guion son una explicación oral; no necesitas leer todos los párrafos de las diapositivas, los pies de imagen ni las referencias bibliográficas completas.

**Objetivo actualizado: 19:50 de exposición, con 0:10 de margen hasta el límite de 20 minutos.** Las preguntas tienen 5 minutos aparte. Los tiempos son estimaciones de ensayo e incluyen pausas y señalar las figuras. La introducción tiene un objetivo de **7:20** y el bloque de modelo, de **6:40**, para explicar explícitamente las transiciones y las variables. El margen es estrecho: si el ensayo excede 20 minutos, usa los recortes indicados más abajo. Las notas de Slidev pueden conservar tiempos de versiones anteriores: para este ensayo usa los relojes de este documento.

Fuentes: **[1]** artículo de Brüningk et al.; **[2]** texto de histología en AccessMedicina; **[3]** Ross. Las referencias completas están al final de la presentación y de este guion. El contexto biológico y las reglas simplificadas del autómata se explican por separado. **Las ampliaciones técnicas de los apartados 13, 15, 16 y 17 y el apoyo de estudio se basan únicamente en el PDF original [1]; no se consultan ni completan con los trabajos que este cita.**

## Puntos de control del tiempo

| Al terminar | Tiempo acumulado objetivo |
|---|---:|
| Ciclo celular, incluido el aviso animado (6) | 3:20 |
| Esferoides: final de la introducción (12) | 7:20 |
| Combinación: final del modelo (17) | 14:00 |
| Resultados combinados (21) | 18:30 |
| Referencias (23) | 19:50 |

## 1. A cellular automaton model for spheroid response to radiation and hyperthermia treatments

**Duración: 0:20 · Reloj: 0:00–0:20**

Buenos días. Soy Tlacaelel Jaime Flores-Villaseñor y voy a presentar el trabajo de Brüningk y colaboradores sobre un autómata celular para estudiar la respuesta de esferoides tumorales a radiación e hipertermia. La pregunta principal es cómo conectar lo que le ocurre a una célula con el crecimiento de todo el esferoide.

## 2. Contenido

**Duración: 0:15 · Reloj: 0:20–0:35**

Primero revisaré el contexto biológico. Después explicaré cómo se convierte en reglas del modelo y cómo se comparan las simulaciones con los experimentos. Al final veremos los resultados y sus principales limitaciones.

## 3. Resumen

**Duración: 0:40 · Reloj: 0:35–1:15**

Las células hipóxicas son menos sensibles a la radiación. Esto motiva combinar radioterapia e hipertermia para aumentar la sensibilidad al tratamiento. El artículo estudia la respuesta en esferoides mediante células individuales y su microambiente: saber cuántas conservan capacidad de formar colonias no describe por completo la evolución del agregado.

[Primer avance: aparece el subrayado rojo.]

Radiación y calor pueden producir supervivencias comparables y distintas curvas de crecimiento.

[Segundo avance: aparece el subrayado azul.]

Para explicar esa diferencia, los autores distinguen la muerte ligada al intento de división tras radiación de la muerte independiente de la proliferación tras calentamiento. Esa será la idea conductora de la exposición.

## 4. La célula

**Duración: 0:30 · Reloj: 1:15–1:45**

[Definición y micrografía: referencia 2.]

Antes del modelo, partamos de la unidad que vamos a representar. La célula es la unidad morfológica y funcional de los seres vivos. La teoría celular establece que los organismos están formados por células y sus productos.

[Señalar la micrografía de la derecha.]

Esta imagen permite reconocer que una célula tiene una organización interna compleja. El modelo no reproduce cada orgánulo: selecciona propiedades que permiten describir su crecimiento y su respuesta al tratamiento. La definición y la micrografía de esta diapositiva corresponden a la referencia dos, el texto de histología disponible en AccessMedicina.

La siguiente pregunta es cuáles de esas propiedades necesitamos conservar.

## 5. La célula

**Duración: 0:25 · Reloj: 1:45–2:10**

[Representación simplificada de la célula: referencia 1.]

Para el modelo, cada célula tiene un estado: puede estar proliferando, en reposo o muerta. También tiene un entorno, definido aquí por el oxígeno disponible y por el espacio entre las células vecinas.

Después del tratamiento necesitamos conocer su destino y el tiempo hasta que muera, si ha resultado dañada. Cada célula del modelo representa una célula del esferoide.

El sistema es avascular: no se incluye una red de vasos sanguíneos. El oxígeno llega por difusión desde el exterior. Con estas simplificaciones podemos empezar a traducir la biología en reglas.

## 6. Ciclo celular

**Duración: 1:10 · Reloj: 2:10–3:20**

[Figura de Ross: referencia 3. El aviso se activa únicamente al cerrar esta explicación.]

El ciclo celular organiza los procesos necesarios para producir dos células hijas. En la interfase encontramos G1, la fase S y G2. Durante S se replica el ADN; después, la célula se prepara para la mitosis y la división.

[Recorrer el ciclo con el puntero, sin activar todavía el aviso.]

La figura también muestra puntos de control. Podemos entenderlos como mecanismos que revisan si existen condiciones para continuar; por ejemplo, si hay daño en el ADN o problemas en la segregación de los cromosomas.

[Señalar G0 y la salida hacia diferenciación terminal.]

Salir del ciclo no equivale automáticamente a morir. En el modelo del artículo, una célula que no encuentra espacio para dividirse puede entrar en G0 y reactivarse cuando aparece espacio.

[Avanzar UNA vez. El párrafo se superpone a toda la diapositiva. Hacer una pausa breve y leerlo como cierre.]

Una catástrofe mitótica causada por el mal funcionamiento de los puntos de control del ciclo celular puede conducir a la muerte celular y al desarrollo de células tumorales.

[Dejar el aviso visible. El siguiente avance lleva a la diapositiva 7.]

## 7. Apoptosis y muerte celular

**Duración: 0:45 · Reloj: 3:20–4:05**

[Comparación visual de necrosis y apoptosis: referencia 3.]

En esta imagen de Ross se comparan necrosis y apoptosis. Las dos columnas muestran cambios celulares diferentes.

[Recorrer de arriba abajo la columna izquierda.]

En la necrosis se observa daño de la membrana, edema o hinchazón celular y, finalmente, ruptura y desintegración. En esta diapositiva la relacionamos con una lesión celular aguda, por ejemplo, asociada a hipoxia o a otros agentes lesivos.

[Recorrer de arriba abajo la columna derecha.]

En la apoptosis, la imagen muestra fragmentación del ADN, reducción del volumen y formación de cuerpos apoptóticos. Puede ocurrir en condiciones fisiológicas normales.

Estos dos ejemplos no agotan todas las formas de muerte celular. Lo que necesitamos retener es que el destino de una célula puede seguir procesos distintos. Ahora veamos cuáles distingue el artículo en su modelo.

## 8. Apoptosis y muerte celular

**Duración: 0:30 · Reloj: 4:05–4:35**

[Reglas de muerte del modelo: referencia 1.]

Aquí pasamos de la imagen histológica a las reglas del autómata. La apoptosis forma parte del contexto, pero el modelo no resuelve sus vías moleculares.

Tras radiación, la muerte se representa como dependiente de un intento de división. Tras hipertermia, ocurre después de un retraso independiente de la proliferación. Además, la hipoxia prolongada puede producir muerte y contribuir al núcleo necrótico.

Por eso no llamaremos apoptosis a toda muerte del modelo: nos interesa cuándo sucede y cómo cambia el entorno al eliminarse una célula.

## 9. Cáncer: el problema que se quiere representar

**Duración: 0:30 · Reloj: 4:35–5:05**

El estudio utiliza HCT116, una línea celular de carcinoma colorrectal humano. Al reunir las células en tres dimensiones, aparecen condiciones diferentes entre la periferia y el centro.

Las células pueden tener distinto acceso a oxígeno y espacio para proliferar. Por eso, la respuesta del conjunto no se deduce solo de una célula aislada.

Este es el problema que se quiere representar: la interacción entre las propiedades celulares, la posición de cada célula y su microambiente. La siguiente imagen muestra cómo se desarrolla esa heterogeneidad.

## 10. Hipoxia y necrosis

**Duración: 0:50 · Reloj: 5:05–5:55**

En esta figura, el azul señala núcleos celulares, el rojo proliferación y el verde hipoxia, es decir, bajo oxígeno.

[Señalar el día 4 y después los días 11 y 25.]

En el día cuatro no hay hipoxia significativa. Conforme el esferoide crece, aparece una región hipóxica central, rodeada por una periferia con numerosas células proliferantes.

Hipoxia no significa necrosis: la señal verde no demuestra por sí sola que las células estén muertas. En el día veinticinco, la menor densidad celular central puede indicar necrosis.

Hay un detalle importante: los tratamientos se aplicaron al día cuatro. Esto limita lo que estos experimentos pueden demostrar sobre la respuesta a radiación cuando ya existe un centro claramente hipóxico.

## 11. Radioterapia e hipertermia

**Duración: 0:45 · Reloj: 5:55–6:40**

Los tratamientos son radioterapia, que utiliza radiación ionizante, e hipertermia, que eleva la temperatura. La dosis de radiación se expresa en gray.

La dosis térmica se expresa como CEM43: minutos equivalentes acumulados a cuarenta y tres grados. Combina el efecto de tiempo y temperatura. En los experimentos, la temperatura real fue de cuarenta y siete grados; cinco minutos corresponden a ochenta CEM43.

Para el modelo, la diferencia central es que la muerte por radiación está ligada a la división, mientras que el calor también puede eliminar células en reposo. Esto cambia dónde se libera espacio y cómo se reorganiza el esferoide.

## 12. Esferoides tumorales (*tumour spheroids*)

**Duración: 0:40 · Reloj: 6:40–7:20**

Un esferoide tumoral es un agregado tridimensional de células, sin vasos sanguíneos. Permite estudiar gradientes de oxígeno y contactos celulares que no aparecen de la misma manera en un cultivo plano.

Los autores sembraron trescientas células HCT116, dejaron que se formara el esferoide y lo trataron al día cuatro. Después siguieron su diámetro durante tres semanas.

Ese diámetro a lo largo del tiempo es lo que queremos reproducir: reducción, retraso del crecimiento y recrecimiento. Ya tenemos el contexto necesario para explicar cómo se representa todo esto en la simulación.

## 13. Modelo: un autómata celular 3D

**Duración: 1:40 · Reloj: 7:20–9:00**

[Fuente exclusiva de esta explicación: artículo [1], «Computational model», p. 2; oxigenación, pp. 2–3.]

Cada posición de la malla está vacía o contiene una célula. La célula tiene una fase del ciclo, un reloj individual y, después del tratamiento, una marca de supervivencia o de muerte futura. Cada vóxel mide doce micrómetros de lado.

[Señalar el esquema matemático. C sub i es la célula que intenta dividirse; F sub i reúne los sitios vecinos libres. Es una notación explicativa de las reglas del artículo, no una ecuación adicional que este formule.]

La generación de células nuevas ocurre por división. Cada célula avanza por G1, S, G2 y M según su reloj, comenzando en una fase aleatoria. Cuando intenta dividirse, se busca espacio libre en sus vecindarios de Moore y de von Neumann, alternados hasta segundo orden. Se favorecen posiciones más centrales para mantener un agregado compacto.

Si la división se completa, una célula da lugar a dos hijas: el número de células aumenta en una y hace falta una posición adicional. Si no hay espacio, no se genera una célula nueva: la célula entra en G0.

Quiescente significa precisamente eso: una célula en reposo, que no se divide en ese momento. En este modelo, G0 es reversible: si se libera espacio vecino, puede reingresar al ciclo.

También hay reglas de pérdida de células: la hipoxia persistente puede causar muerte; las células necróticas se eliminan probabilísticamente. Muerte y eliminación no son el mismo evento. El conjunto se reacomoda hacia dentro para conservar su estructura, sin simular migración explícita.

Por tanto, el crecimiento no se impone como una curva: resulta de divisiones locales, limitación de espacio, muerte y eliminación.

## 14. Oxígeno: difusión y consumo

**Duración: 1:10 · Reloj: 9:00–10:10**

A las células discretas se añade un campo continuo de oxígeno. Por eso hablamos de un modelo híbrido.

[Señalar los términos de la ecuación.]

A la izquierda está el cambio temporal de la presión parcial de oxígeno. A la derecha, el primer término describe la difusión y el segundo el consumo celular. En una posición vacía no hay consumo; donde hay una célula, sí.

En el exterior se fijan cien milímetros de mercurio, y el modelo utiliza once milímetros de mercurio como umbral de hipoxia.

La difusión ocurre en segundos y el ciclo celular en horas. Por eso se calcula el oxígeno hasta alcanzar prácticamente el equilibrio dentro de cada iteración del ciclo.

Así se conectan las dos partes: el crecimiento modifica la distribución de oxígeno y la hipoxia puede modificar la supervivencia celular.

## 15. Dos tratamientos, dos dinámicas de muerte

**Duración: 1:20 · Reloj: 10:10–11:30**

[Fuente exclusiva: artículo [1], ecuaciones 2–5 y figura 1, pp. 3–4. La ecuación visible aquí es de radiación; las ecuaciones térmicas se muestran en la diapositiva siguiente.]

[Señalar la ecuación.]

La ecuación que vemos corresponde a radiación. S sub RT es la fracción de supervivencia clonogénica: la proporción que conserva capacidad reproductiva. La dosis de radiación es d, en gray. La presión parcial de oxígeno se representa como p sub O dos.

OER es el factor que corrige la dosis por la menor radiosensibilidad de las células hipóxicas. Al dividir d entre OER obtenemos d sub OER, la dosis aparente usada en la ecuación. Gamma pondera la sensibilidad según la fase del ciclo celular.

Alfa y beta son coeficientes propios de la línea celular: alfa multiplica la dosis y controla el término lineal; beta multiplica la dosis al cuadrado y controla el término cuadrático. Para una misma dosis y las demás condiciones fijas, valores mayores reducen la supervivencia calculada.

Con esa fracción se sortean células supervivientes y destinadas a morir. Estas últimas no desaparecen inmediatamente: mueren con cierta probabilidad al intentar dividirse; si llegan a dividirse, ambas hijas conservan la marca.

La columna del calor anticipa una regla distinta: la muerte no exige dividirse. Ahora voy a mostrar cómo se calcula esa supervivencia térmica.

## 16. Hipertermia: modelo de supervivencia

**Duración: 1:10 · Reloj: 11:30–12:40**

[Señalar la primera ecuación. Fuente exclusiva: artículo [1], ecuaciones 4–5, pp. 3–4.]

Ahora sí vemos el modelo de calor. S sub A identifica el cálculo AlphaR. El menos logaritmo de la supervivencia tiene un tramo cuadrático y después uno lineal. La dosis térmica es t sub cuarenta y tres, medida en CEM43. CEM43 significa minutos equivalentes acumulados a cuarenta y tres grados Celsius: combina temperatura y duración en una dosis térmica equivalente; no es necesariamente el tiempo real de calentamiento.

Beta sub HT controla el tramo cuadrático, alfa sub cero el lineal y gamma sub HT pondera la sensibilidad por fase. D sub T es la dosis térmica donde cambia el tramo, no una temperatura.

[Señalar la segunda ecuación.]

Para representar la mayor resistencia observada en esferoides, por encima de ciento sesenta CEM43 se usa una meseta de supervivencia. Ese corte es distinto de D sub T.

Con S sub HT se sortean destinos. Las células que morirán reciben un retraso aleatorio; cuando termina, se eliminan sin exigir división. Esto también puede liberar espacio en regiones quiescentes: células en G0 que no están proliferando.

## 17. Combinación RT + HT

**Duración: 1:20 · Reloj: 12:40–14:00**

[Fuente exclusiva: artículo [1], «Implementation of radiation and hyperthermia combinations» y figura 2, p. 5.]

Aquí es fundamental distinguir tres símbolos. S sub RT es la supervivencia por radiación sola. S sub HT describe la supervivencia por calor. S sub RTHT, aunque el nombre pueda confundir, es el componente de supervivencia radiativa modificado por el calentamiento; no es todavía la supervivencia total combinada.

Se calcula con la ecuación lineal-cuadrática anterior, pero ahora alfa y beta dependen de la dosis térmica. Siguen siendo los coeficientes de los términos lineal y cuadrático de radiación; su dependencia del calor introduce la radiosensibilización.

[Señalar las ramas.]

Una fracción uno menos S sub RTHT sigue la vía de muerte por radiación. De la fracción restante, una proporción uno menos S sub HT sigue la vía de muerte por calor.

La proporción final que sobrevive a ambas asignaciones es S sub RTHT por S sub HT. Ese producto sí es la supervivencia combinada total. No se están suponiendo simplemente dos efectos independientes: el calor ya modifica los coeficientes del componente radiativo.

## 18. Calibración y validación

**Duración: 1:30 · Reloj: 14:00–15:30**

Para entender cómo evaluaron el modelo, hay que distinguir calibración de validación. Calibrar es elegir parámetros usando ciertos datos. Validar es conservar esos parámetros y comprobar otras condiciones.

Primero ajustaron la distribución de oxígeno del autómata. La compararon con un modelo analítico ya publicado y adaptaron el coeficiente de difusión para reducir las diferencias. Después ajustaron el crecimiento sin tratamiento con curvas experimentales de esferoides sin tratar. Aquí intervienen la cantidad inicial de células, el tiempo de duplicación, la muerte por hipoxia y la eliminación de células necróticas.

Con esa base, calibraron la respuesta a los tratamientos. Para radiación usaron la curva de diez gray; para hipertermia, la de doscientos cuarenta CEM43. Esas dosis permiten ajustar la respuesta al tratamiento, no el modelo analítico de oxígeno ni el crecimiento sin tratar.

Después conservaron los parámetros y simularon dos y cinco gray, y cuarenta y ochenta CEM43. Finalmente, comprobaron la combinación de dos gray con distintas dosis térmicas, sin nuevos ajustes.

La histología aporta una comparación complementaria: son cortes experimentales que permiten observar hipoxia, proliferación y distribución celular. No es otro modelo matemático. Sirve para comprobar cualitativamente la organización espacial, mientras que las curvas de diámetro y sus valores de R cuadrada permiten evaluar la evolución temporal. Ahora veamos los resultados de estas comparaciones.

## 19. Resultados: crecimiento sin tratamiento

**Duración: 1:10 · Reloj: 15:30–16:40**

Primero veamos el crecimiento sin tratamiento. A la izquierda, los puntos son mediciones del diámetro y la línea roja es la simulación. R cuadrada es el coeficiente de determinación: resume qué tan bien reproduce la curva los datos. El valor de cero punto noventa y nueve indica un ajuste muy alto; no significa noventa y nueve por ciento de eficacia terapéutica. Esta curva se utilizó para calibrar el modelo.

[Señalar el panel B, arriba a la derecha, y recorrerlo de izquierda a derecha.]

Arriba vemos imágenes experimentales de los días cuatro, once, dieciocho y veinticinco. Combinan microscopía de contraste de fases con fluorescencia de yoduro de propidio, que marca células muertas en naranja. La señal central aumenta con el tiempo.

[Señalar el panel C, debajo.]

Abajo vemos cortes centrales de los esferoides simulados: naranja para células necróticas, gris claro para quiescentes y gris oscuro para proliferantes. Las imágenes experimentales y simuladas están a la misma escala. La comparación muestra una coincidencia cualitativa en la región central muerta.

El quince por ciento mencionado en la diapositiva corresponde a otra comparación: oxígeno simulado frente al modelo analítico, no al error del diámetro ni a estas imágenes.

## 20. Resultados: RT y HT por separado

**Duración: 1:00 · Reloj: 16:40–17:40**

El eje vertical representa el diámetro y el horizontal los días desde la siembra. Los puntos son los experimentos y las líneas rojas, las simulaciones. Arriba vemos radiación; abajo, hipertermia.

[Señalar la primera columna y después las demás.]

La primera columna corresponde a las condiciones de calibración. Las otras muestran condiciones de validación.

Tras diez gray aparece reducción sin recrecimiento durante la ventana observada. Tras la dosis térmica alta, hay una reducción marcada seguida de recrecimiento. Estas curvas ilustran distintas dinámicas, aunque esta figura no demuestra que esas dos dosis sean una pareja clonogénicamente equivalente.

La concordancia general es buena, con R cuadradas entre cero punto noventa y cuatro y cero punto noventa y ocho. También hay un desacuerdo: para cuarenta y ochenta CEM43, el modelo subestima el diámetro temprano. Los autores proponen que cambios estructurales o de la matriz no modelados podrían contribuir a esa diferencia.

## 21. Resultados: tratamiento combinado

**Duración: 0:50 · Reloj: 17:40–18:30**

Aquí vemos dos gray combinados, de izquierda a derecha, con ciento sesenta, ochenta y cuarenta CEM43.

[Recorrer las tres gráficas.]

Con la dosis térmica mayor, el diámetro disminuye durante gran parte del seguimiento. En las otras condiciones aparece recrecimiento, con distintos retrasos. Las R cuadradas son cero punto ochenta y seis, cero punto ochenta y ocho y cero punto noventa y seis.

Lo principal es que estas curvas se obtuvieron sin reajustar los parámetros para la combinación. Esto apoya la utilidad de conectar las reglas calibradas para cada modalidad.

El resultado corresponde a estos esferoides experimentales; todavía no demuestra que el modelo pueda seleccionar un tratamiento para pacientes.

## 22. Conclusiones

**Duración: 1:00 · Reloj: 18:30–19:30**

Podemos responder la pregunta inicial: conocer la supervivencia clonogénica no basta para describir el tamaño del esferoide en el tiempo. También importan el momento de la muerte, la posición celular y los cambios en el microambiente.

El trabajo muestra que un autómata acoplado a difusión de oxígeno y a distintas reglas de muerte reproduce las curvas estudiadas. Además, permite describir la combinación sin reajustar sus parámetros.

Los límites son claros: una sola línea celular, geometría simplificada y ausencia de vasculatura, respuesta inmune y modelado explícito de pH o glucosa. También falta validar mejor el efecto de la hipoxia sobre radiación.

Su contribución es conectar mecanismos celulares y respuesta colectiva en un sistema controlado. La extensión a tumores in vivo requiere nuevos desarrollos y validación.

## 23. Referencias

**Duración: 0:20 · Reloj: 19:30–19:50**

Estas son las tres fuentes de la presentación: el artículo original para el modelo y los resultados, AccessMedicina para la definición celular y Ross para el contexto y las figuras de ciclo y muerte celular. Muchas gracias por su atención; podemos pasar a las preguntas.

## Apoyo técnico para entender el modelo — no se lee completo durante la exposición

Este bloque es para estudiar y responder preguntas. **No forma parte del reloj de 19:50.** Se basa únicamente en el artículo [1], pp. 2–5; los parámetros ajustados se toman de p. 7.

### A. Reglas de transición y nacimiento de células

El artículo describe reglas acopladas a oxígeno y tratamiento, no una única función de transición cerrada. Esta tabla las organiza para explicarlas; no transcribe código ni fija un orden de actualización que el PDF no especifica.

| Situación | Regla descrita | Consecuencia |
|---|---|---|
| Célula en ciclo | Avanza por G1, S, G2 y M según su reloj individual, desde una fase inicial aleatoria. | Las células no empiezan todas en la misma fase. |
| División con espacio disponible | Se buscan posiciones libres alternando vecindarios 3D de Moore y von Neumann hasta segundo orden; se favorecen posiciones centrales. | Dos hijas por división: aumento neto de una célula y necesidad de espacio adicional. |
| No hay espacio | Entrada en G0 reversible. | No se completa una nueva división mientras falte espacio. |
| Se libera espacio vecino | La célula en G0 puede reactivarse. | Recupera la posibilidad de proliferar. |
| Hipoxia persistente | Por debajo del umbral de 11 mmHg, las células hipóxicas mueren con probabilidad $p_{\mathrm{hypoxiaDeath}}$ por paso si no vuelven a normoxia. | Puede formarse un núcleo necrótico. |
| Célula necrótica | Se elimina con probabilidad $p_{\mathrm{clearNecrotic}}$ por paso. | Morir no implica vaciar inmediatamente el vóxel. |
| Célula destinada a morir tras RT | En cada intento de división al final de M, muere con probabilidad $p_{\mathrm{mitoticDeath}}$; si divide, ambas hijas heredan la marca. | Puede existir crecimiento transitorio de células destinadas a morir. |
| Célula destinada a morir tras HT | Recibe un retraso aleatorio hasta muerte; al terminar, se elimina inmediatamente. | La eliminación no exige un intento de división. |

Resumen de una **división exitosa**, como explicación de la regla y no como ecuación adicional propuesta por los autores:

$$
1\ \text{célula}\longrightarrow 2\ \text{hijas},\qquad \Delta N=+1.
$$

El esferoide se inicializa como una esfera densa, con una célula por vóxel. La malla típica es $200^3$, con vóxeles de $0.012\ \mathrm{mm}=12\ \mu\mathrm{m}$ de lado. Se reacomodan células hacia dentro para conservar una estructura compacta, sin migración explícita.

**Quiescencia, hipoxia y muerte no son sinónimos:** G0 es reposo reversible; hipoxia describe el oxígeno local; una célula destinada a morir puede seguir físicamente presente. Sin tratamiento no se impone envejecimiento ni un límite intrínseco de divisiones, pero siguen existiendo muerte hipóxica y restricción por espacio. Fuente: pp. 2–3 y figura 1, p. 4.

**Detalles no especificados aquí:** el artículo remite a su referencia [30] para la implementación previa del ciclo. No se inventan duraciones de cada fase, reinicio exacto de los relojes de las hijas, duración del paso temporal ni una función determinista completa que el PDF de 2019 no proporcione.

### B. Radiación: ecuación visible y significado de cada símbolo

Ecuaciones 2 y 3, p. 3:

$$
S_{\mathrm{RT}}=\exp\!\left[-\gamma\left(\alpha d_{\mathrm{OER}}+\beta d_{\mathrm{OER}}^2\right)\right],\qquad
 d_{\mathrm{OER}}=\frac{d}{\mathrm{OER}(p_{O_2})}.
$$

| Símbolo | Significado en este modelo |
|---|---|
| $S_{\mathrm{RT}}$ | Fracción de supervivencia clonogénica tras RT, usada para sortear supervivencia o muerte futura. No es la fracción físicamente eliminada de inmediato. |
| $\exp$ | Función exponencial: notación matemática, no un parámetro biológico. |
| $d$ | Dosis de radiación administrada, en Gy. |
| $p_{O_2}$ | Presión parcial de oxígeno local, en mmHg. |
| $\mathrm{OER}$ | *Oxygen enhancement ratio*: ponderación de la menor radiosensibilidad bajo hipoxia. |
| $d_{\mathrm{OER}}$ | Dosis aparente corregida por oxígeno, en Gy; no es otra exposición. |
| $\gamma$ | Ponderación por fase del ciclo celular. |
| $\alpha$ | Coeficiente específico de la línea celular: multiplica la dosis y controla el término lineal. |
| $\beta$ | Coeficiente específico de la línea celular: multiplica la dosis al cuadrado y controla el término cuadrático. |

Por consistencia dimensional, $\alpha$ tiene unidades $\mathrm{Gy}^{-1}$ y $\beta$, $\mathrm{Gy}^{-2}$; las ponderaciones son adimensionales. Esta es una lectura matemática de la fórmula. No se atribuyen a alfa y beta mecanismos moleculares que el artículo de 2019 no desarrolla.

La función implementada es:

$$
\mathrm{OER}(p_{O_2})=
\begin{cases}
1,&p_{O_2}>11\ \mathrm{mmHg},\\
3-\dfrac{2p_{O_2}}{11\ \mathrm{mmHg}},&p_{O_2}\leq11\ \mathrm{mmHg}.
\end{cases}
$$

En el límite de oxígeno nulo, OER es 3 y la dosis aparente es $d/3$; en 11 mmHg el factor es 1. Son consecuencias matemáticas de la ecuación 3, no nuevos experimentos.

**Alfa y beta calculan supervivencia; no fijan el instante de muerte.** Esa dinámica se añade con $p_{\mathrm{mitoticDeath}}$: el ajuste usa 0.44 durante los primeros 3.5 días y 0.59 después. Si hay división exitosa, ambas hijas heredan la marca. Las supervivientes a RT continúan proliferando sin un retraso de ciclo añadido. Fuentes: pp. 3 y 7.

El efecto de la hipoxia sobre RT no pudo ajustarse aquí por falta de hipoxia significativa al día de tratamiento (discusión, p. 9). No presentar OER como validado mediante ese contraste experimental.

### C. Calor: ecuaciones visibles en la diapositiva 16

**La ecuación de la diapositiva 15 es de radiación; la diapositiva 16 muestra HT.** Para calor se utilizan las ecuaciones 4 y 5, p. 3.

Para distinguir el cálculo AlphaR de su modificación 3D, este guion lo etiqueta $S_{\mathrm{AlphaR}}$. Es una ayuda de lectura, no un modelo distinto:

$$
S_{\mathrm{HT}}(t_{43})=
\begin{cases}
S_{\mathrm{AlphaR}}(t_{43}),&t_{43}\leq160\ \mathrm{CEM43},\\
S_{\mathrm{HT,plateau}},&t_{43}>160\ \mathrm{CEM43}.
\end{cases}
$$

El cálculo AlphaR es:

$$
-\log S_{\mathrm{AlphaR}}(t_{43})=
\begin{cases}
\gamma_{\mathrm{HT}}\beta_{\mathrm{HT}}t_{43}^{2},&t_{43}\leq D_T,\\
\gamma_{\mathrm{HT}}\left(\alpha_0t_{43}-\dfrac{\alpha_0^2}{4\beta_{\mathrm{HT}}}\right),&t_{43}>D_T,
\end{cases}
\qquad D_T=\frac{\alpha_0}{2\beta_{\mathrm{HT}}}.
$$

| Símbolo | Significado |
|---|---|
| $S_{\mathrm{HT}}$ | Fracción de supervivencia clonogénica al calor, con el ajuste usado para esferoides. |
| $t_{43}$ | Dosis térmica en CEM43, tiempo equivalente a 43 °C; no necesariamente duración real de calentamiento. |
| $\beta_{\mathrm{HT}}$ | Parámetro del tramo cuadrático de $-\log S$ térmico. |
| $\alpha_0$ | Parámetro del tramo lineal de $-\log S$ térmico. |
| $D_T$ | Dosis térmica de transición entre tramos, $\alpha_0/(2\beta_{\mathrm{HT}})$; no es temperatura. |
| $\gamma_{\mathrm{HT}}$ | Ponderación por fase del ciclo; distingue células en ciclo y en G0. |
| $S_{\mathrm{HT,plateau}}$ | Meseta impuesta por encima de 160 CEM43 para representar la mayor resistencia térmica observada en 3D. |

No confundir los parámetros térmicos $\alpha_0,\beta_{\mathrm{HT}}$ con $\alpha,\beta$ de RT. Tampoco confundir $D_T$, cambio entre tramos AlphaR, con el corte de 160 CEM43 de la meseta 3D.

**Hay dos partes:** asignar supervivencia o muerte futura mediante $S_{\mathrm{HT}}$ y establecer cuándo se ejecuta la muerte. El retraso hasta morir sigue una distribución normal; una vez que ocurre la muerte, la eliminación es inmediata. Las supervivientes tienen un arresto temporal del ciclo tomado de una distribución uniforme (p. 4).

Parámetros ajustados: meseta 0.0005, retraso medio hasta muerte de 96 h y arresto medio del ciclo de supervivientes de 30 h (p. 7). «Independiente de la proliferación» **no significa instantánea** ni igual sensibilidad en todas las fases. Se pondera la sensibilidad por fase, pero no se exige división para morir. No se añade dependencia directa de la letalidad térmica con oxígeno ni pH (p. 4).

### D. Combinación: significado de $S_{\mathrm{RTHT}}$

La ecuación 2 se aplica con parámetros dependientes de la dosis térmica, como describe p. 5:

$$
S_{\mathrm{RTHT}}(d,t_{43})=
\exp\!\left[-\gamma\left(\alpha(t_{43})d_{\mathrm{OER}}+\beta(t_{43})d_{\mathrm{OER}}^2\right)\right].
$$

Es el **componente radiativo sensibilizado por calor**, no la supervivencia final combinada. Esta escritura hace explícita la dependencia que describe el texto. El artículo remite a su referencia [30] para la parametrización previa; no se inventan fórmulas para $\alpha(t_{43})$ ni $\beta(t_{43})$.

La supervivencia combinada es:

$$
S_{\mathrm{total}}(d,t_{43})=S_{\mathrm{RTHT}}(d,t_{43})S_{\mathrm{HT}}(t_{43}).
$$

$S_{\mathrm{total}}$ es una etiqueta explicativa del guion para el producto descrito por los autores. Las fracciones respecto de **toda la población inicial** son:

| Destino | Fracción total |
|---|---|
| Vía de muerte RT | $1-S_{\mathrm{RTHT}}$ |
| Vía de muerte HT | $S_{\mathrm{RTHT}}(1-S_{\mathrm{HT}})$ |
| Supervivencia final | $S_{\mathrm{RTHT}}S_{\mathrm{HT}}$ |

Las tres suman uno. El factor aislado $1-S_{\mathrm{HT}}$ es una proporción **condicionada a la población restante** tras la asignación RT, como muestra la figura 2. No es otra proporción de toda la población inicial.

La sinergia se introduce modificando $\alpha$ y $\beta$ con la dosis térmica. No se debe presentar el producto como la multiplicación sin más de dos supervivencias de modalidades independientes. Las supervivientes continúan proliferando después del retraso de ciclo contemplado en la cascada (p. 5).

## Si el ensayo se acerca a los 20 minutos

Los puntos de control son más útiles que acelerar toda la lectura. Si terminas la introducción después de 7:20, ya estás consumiendo el margen. Abrevia primero la lectura de resultados; conserva las reglas de división y las definiciones de variables que motivan esta actualización:

- **Diapositiva 13:** conserva división con espacio, bloqueo en G0 y reactivación; omite el recuento de posiciones y los detalles del reacomodo si hace falta.
- **Diapositiva 14:** conserva difusión, consumo y el acoplamiento con las células; omite los valores de presión al hablar.
- **Diapositiva 20:** compara las dos tendencias sin leer cada dosis ni todos los R².
- **Diapositiva 21:** destaca que no hubo reajuste y describe las curvas sin recitar los tres coeficientes.

En la introducción, evita explicar todos los orgánulos de la micrografía o todos los rótulos del ciclo. En la diapositiva 7 recorre las dos columnas, sin desarrollar «otras formas de muerte celular». El aviso de la diapositiva 6 es el cierre: no reinicies la explicación del ciclo después de mostrarlo.

Conserva la pregunta inicial, las transiciones celulares, el significado de las variables RT/HT, la distinción entre supervivencia radiativa modificada y supervivencia combinada, y la separación entre calibración y validación. El apoyo técnico es para estudiar y responder: leerlo completo excedería el límite de 20 minutos.

Frase para recuperar ritmo: «Los valores están en la diapositiva; lo que quiero destacar es que el modelo reproduce estas tendencias sin reajustar la combinación».

## Respuestas breves para los 5 minutos de preguntas

### ¿Por qué un autómata celular?

«Porque permite conservar información de cada célula y de su posición. Así se pueden aplicar reglas de división, reposo y muerte que dependen del espacio y del microambiente, y observar la respuesta colectiva».

### ¿Por qué no basta una curva de supervivencia clonogénica?

«Porque informa sobre la capacidad reproductiva que queda después del tratamiento, pero no determina cuándo se eliminarán las células dañadas. Esas diferencias temporales y espaciales cambian el diámetro, el oxígeno y las oportunidades de repoblación».

### ¿Una célula marcada para morir ya está muerta?

«No. Es una categoría del modelo: perderá su capacidad de proliferar indefinidamente, pero puede permanecer físicamente en el esferoide y, en la implementación de RT, incluso dividirse antes de morir».

### ¿El modelo demuestra que la apoptosis es la responsable?

«No. Implementa reglas de destino y eliminación celular, no vías moleculares de apoptosis. La distinción principal es si la muerte depende o no de un intento de división».

### ¿El producto de supervivencias supone que RT y HT son independientes?

«No en esta formulación. El componente radiativo incorpora parámetros dependientes de la dosis térmica, de modo que la radiosensibilización ya está incluida antes de multiplicar por el componente de supervivencia al calor».

### ¿La hipoxia quedó validada como causa de resistencia a RT en este estudio?

«El modelo incorpora esa dependencia mediante OER, pero no pudieron ajustarla aquí porque los esferoides no tenían hipoxia significativa al tratarse en el día cuatro. Harían falta experimentos adicionales con esferoides hipóxicos».

### ¿Qué significa CEM43 si calentaron a 47 °C?

«Es una dosis térmica equivalente referida a cuarenta y tres grados, no la temperatura real del experimento. Permite expresar conjuntamente tiempo y temperatura. En este artículo, cinco minutos a cuarenta y siete grados equivalen a ochenta CEM43».

### ¿Qué significa una R² alta?

«R² es el coeficiente de determinación: resume qué tan bien se ajustan las predicciones a los datos. Un valor próximo a uno indica un ajuste alto. No representa la proporción de células eliminadas ni un porcentaje de eficacia terapéutica. En el crecimiento sin tratamiento, 0.99 corresponde a una curva utilizada para calibrar. Una R² alta no demuestra por sí sola que el mecanismo sea único ni valida clínicamente el modelo».

### ¿Qué muestran las imágenes de la derecha de la diapositiva 19?

«El panel B muestra microscopía experimental de contraste de fases combinada con señal de yoduro de propidio, naranja, que marca células muertas. El panel C muestra cortes ecuatoriales simulados: naranja para células necróticas, gris claro para quiescentes y gris oscuro para proliferantes. Corresponden a los días 4, 11, 18 y 25 y se presentan a la misma escala. Se compara cualitativamente la distribución espacial de células muertas. No son mapas de oxígeno ni las tinciones de hipoxia de la otra figura» (artículo [1], figura 5, p. 7).

### ¿Por qué es importante que la combinación no se reajuste?

«Porque comprueba si las reglas y los parámetros obtenidos en las modalidades individuales conservan capacidad de describir otra condición experimental, en lugar de adaptar nuevos valores a cada curva».

### ¿Esto se puede aplicar directamente a pacientes?

«El artículo no demuestra eso. Es un modelo in vitro de una línea celular y omite aspectos como vasculatura, respuesta inmune y tejidos circundantes. Su extensión in vivo es una dirección futura».

### ¿Cómo se podría mejorar el trabajo?

«Una ampliación sería evaluar esferoides hipóxicos al momento del tratamiento. Otras serían representar cambios de densidad y mecánica, incorporar otros factores del microambiente y validar con más sistemas experimentales. Son propuestas de continuación, no resultados obtenidos aquí».

### Si preguntan algo que el artículo no resuelve

«Ese aspecto no se evaluó en este trabajo. Lo que sí muestran los resultados es…». Retoma después la evidencia pertinente. Es preferible delimitar el alcance a atribuirle al artículo un resultado que no presenta.

### ¿Cómo se genera una célula nueva y qué pasa si no hay sitio?

«Por división de una célula que recorre su ciclo. Si la división se completa con espacio disponible, produce dos hijas: hay una célula más. Sin espacio, entra en G0; cuando se libera espacio vecino puede reactivarse. El crecimiento se obtiene de estas reglas, no de insertar células para ajustar directamente una curva» (p. 2).

### ¿Qué significa quiescente?

«En este modelo es una célula en G0, en reposo reversible. No está proliferando, pero no equivale a estar muerta ni necesariamente hipóxica. Puede reingresar al ciclo cuando se libera espacio vecino» (pp. 2–4).

### ¿La ecuación de la diapositiva 15 también modela el calor?

«No. La ecuación de la diapositiva 15 es de radiación. La diapositiva 16 muestra el calor con las ecuaciones 4 y 5: supervivencia AlphaR ajustada a 3D mediante una meseta para dosis superiores a 160 CEM43. Después se añade el retraso temporal hasta la muerte y la eliminación» (pp. 3–4).

### ¿Qué son alfa y beta, y qué es S sub RTHT?

«Alfa y beta ponderan las contribuciones lineal y cuadrática de la dosis en la supervivencia radiativa. En combinación dependen de la dosis térmica. S sub RTHT es ese componente radiativo modificado por calor; la supervivencia final es su producto con S sub HT» (pp. 3 y 5).

### ¿Qué fuentes sustentan la introducción y cuáles el modelo?

«La definición de célula se apoya en AccessMedicina, referencia dos. El contexto visual de ciclo celular y muerte celular se atribuye a Ross, referencia tres. Las reglas del autómata, los datos y los resultados corresponden al artículo de Brüningk, referencia uno. Una ilustración de biología no implica que el modelo simule todos los procesos que muestra».

## Referencias para repasar antes de exponer

[1] S. C. Brüningk et al., «A cellular automaton model for spheroid response to radiation and hyperthermia treatments», *Scientific Reports*, vol. 9, art. 17674, 2019. [DOI](https://doi.org/10.1038/s41598-019-54117-x).

Para las reglas: pp. 2–5; calibración y validación: pp. 5–6; figuras y resultados: pp. 6–8; discusión, límites y conclusiones: pp. 9–10.

[2] J. Sepúlveda Saavedra y A. Soto Domínguez, «La célula», en *Texto atlas de histología. Biología celular y tisular*, 2.ª ed., cap. 2. McGraw-Hill, 2014. [AccessMedicina](https://accessmedicina.mhmedical.com/content.aspx?bookid=1506&sectionid=98182026). Consultado: 2 de noviembre de 2026.

[3] W. Pawlina y M. H. Ross, *Ross. Histología: texto y atlas. Correlación con biología molecular y celular*, 8.ª ed. Barcelona, España: Wolters Kluwer, 2020. [PDF proporcionado para la presentación](https://ia601603.us.archive.org/11/items/histologia-ross-8/Histologia%20Ross%208.pdf).

Las respuestas sobre el autómata se basan en [1]. Las propuestas de mejora son continuaciones posibles, no resultados ya obtenidos. El guion no incorpora páginas ni números de figura de Ross que no se hayan verificado.
