# Guion de exposición — Brüningk et al. (2019)

Preparado para las 20 diapositivas visibles de `slides.md`. Las frases están escritas para decirse en voz alta; las indicaciones entre corchetes son acciones, no se leen. Puedes usarlo como texto de lectura durante el ensayo y después como apoyo para explicar con tus palabras.

El tiempo objetivo es **18:30**, con **1:30 de margen hasta 20 minutos**. Los **5 minutos de preguntas** van aparte. Los tiempos incluyen pausas, señalar figuras y avanzar las animaciones; deben confirmarse en un ensayo. No leas los pies de fuente ni todos los números de las tablas.

El contenido se basa en el artículo original y en la presentación actual. La introducción desarrolla el contexto necesario para este modelo; una explicación más extensa de apoptosis o de biología del cáncer requiere las fuentes adicionales señaladas en `revision-articulo.md`.

## Puntos de control del tiempo

| Al terminar | Tiempo acumulado objetivo |
|---|---:|
| Esferoides: final de la introducción (10) | 7:00 |
| Combinación: final del modelo (14) | 12:20 |
| Resultados combinados (18) | 17:00 |
| Referencias (20) | 18:30 |

## 1. Portada

**Duración: 0:20 · Reloj: 0:00–0:20**

Buenos días. Soy Tlacaelel Jaime Flores-Villaseñor y voy a presentar el trabajo de Brüningk y colaboradores sobre un modelo de autómatas celulares para estudiar la respuesta de esferoides tumorales a radiación e hipertermia. La pregunta que nos va a acompañar es cómo conectar lo que le ocurre a una célula con el crecimiento de todo el esferoide.

## 2. Contenido

**Duración: 0:20 · Reloj: 0:20–0:40**

Primero voy a introducir los conceptos biológicos necesarios para entender el problema. Después explicaré cómo se traducen esos conceptos en reglas del modelo. Finalmente, revisaremos cómo se ajustó y qué tan bien reprodujo los resultados experimentales, para cerrar con sus principales alcances y limitaciones.

## 3. Resumen

**Duración: 0:50 · Reloj: 0:40–1:30**

La idea central es que medir cuántas células conservan la capacidad de reproducirse después de un tratamiento no basta para describir lo que ocurrirá con el tamaño del esferoide.

[Primer avance: subrayado rojo.]

Dos tratamientos pueden producir una supervivencia clonogénica comparable y, aun así, dar lugar a distintas curvas de crecimiento. Una posible explicación está en el momento y la forma en que mueren las células.

[Segundo avance: subrayado azul.]

Por eso, los autores distinguen la muerte ligada al intento de división tras la radiación de la muerte independiente de la proliferación tras el calentamiento. Su propuesta es incorporar esa diferencia en un modelo espacial y comparar sus predicciones con experimentos. Para entenderlo, primero necesitamos revisar qué características celulares conserva el modelo.

## 4. La célula

**Duración: 0:40 · Reloj: 1:30–2:10**

Para esta presentación podemos pensar en cada célula como una unidad que cambia de estado y responde a su entorno. No necesitamos representar todos sus componentes internos: necesitamos saber si está proliferando, si está en reposo o si ha muerto.

También debemos conocer cuánto oxígeno tiene disponible y si hay espacio para que pueda dividirse. Finalmente, después del tratamiento, necesitamos distinguir si conservará su capacidad reproductiva y cuánto tiempo pasará antes de que muera si resulta dañada.

Estas son las propiedades que los autores convierten en reglas para cada célula. Veamos primero cómo representan la división.

## 5. Ciclo celular

**Duración: 0:55 · Reloj: 2:10–3:05**

El ciclo celular describe la secuencia por la que pasa una célula antes de dividirse. Aquí vemos G1, la fase S, en la que se duplica el ADN, G2 y la fase M, correspondiente a la división.

[Recorrer el esquema con el puntero.]

En la simulación, cada célula tiene su propio reloj y puede comenzar en una fase distinta. Eso evita que todas se dividan al mismo tiempo. Si al intentar dividirse no encuentra espacio, entra en un estado de reposo reversible llamado G0. Si después aparece espacio, puede reactivarse.

Esta distinción será fundamental: una célula en reposo sigue viva, y en el modelo el daño por radiación no provoca necesariamente su eliminación inmediata. La muerte se ejecuta cuando vuelve a intentar dividirse.

## 6. Apoptosis y muerte celular

**Duración: 0:40 · Reloj: 3:05–3:45**

Aquí conviene separar las distintas formas de representar la muerte. La apoptosis aparece como parte del contexto biológico, pero el autómata no reproduce sus vías moleculares.

Lo que implementa son reglas: después de la radiación, la muerte depende de un intento de división; después del calor, ocurre tras un retraso que no depende de que la célula esté proliferando. Además, una exposición prolongada a bajo oxígeno puede producir muerte y contribuir al núcleo necrótico.

Por tanto, no vamos a llamar apoptosis a toda muerte celular. Lo relevante para este modelo es cuándo ocurre y qué cambia en el entorno cuando la célula desaparece.

## 7. Cáncer: el problema que se quiere representar

**Duración: 0:40 · Reloj: 3:45–4:25**

El sistema experimental de este trabajo utiliza HCT116, una línea celular de carcinoma colorrectal humano. El interés de reunir estas células en tres dimensiones es que ya no todas están expuestas a las mismas condiciones.

Las células de la periferia y las del centro pueden tener distinta disponibilidad de oxígeno y distinto acceso a espacio para proliferar. Esa heterogeneidad hace que la respuesta del conjunto no se pueda deducir solamente de una célula aislada.

Lo que queremos representar es precisamente esa interacción entre las propiedades de cada célula, su posición y su microambiente.

## 8. Hipoxia y necrosis

**Duración: 1:00 · Reloj: 4:25–5:25**

Esta figura muestra cómo cambia el interior del esferoide con el tiempo. El azul marca los núcleos celulares; el rojo identifica proliferación y el verde señala hipoxia, es decir, bajo oxígeno.

[Señalar primero el día 4 y después los días 11 y 25.]

En el día cuatro no se observa hipoxia significativa. Conforme el agregado crece, aparece una región hipóxica central, rodeada por una periferia con numerosas células proliferantes.

Es importante distinguir hipoxia de necrosis. La señal verde indica bajo oxígeno, no demuestra por sí sola que las células estén muertas. En el día veinticinco, la menor densidad celular central puede indicar necrosis.

Hay además un detalle que retomaremos al final: los tratamientos se aplicaron al día cuatro. Por tanto, estos experimentos no permiten validar de manera suficiente cómo cambia la respuesta a radiación cuando ya existe un centro claramente hipóxico.

## 9. Radioterapia e hipertermia

**Duración: 0:55 · Reloj: 5:25–6:20**

Los dos tratamientos que estudian son radioterapia, que utiliza radiación ionizante, e hipertermia, que eleva la temperatura.

La dosis de radiación se expresa en gray. Para el calentamiento se utiliza CEM43: minutos equivalentes acumulados a cuarenta y tres grados. Esta medida permite comparar exposiciones que combinan distinta temperatura y duración. En estos experimentos, el calentamiento real fue a cuarenta y siete grados; por ejemplo, cinco minutos corresponden a ochenta CEM43.

Lo esencial para el modelo es que las dos modalidades producen dinámicas diferentes de muerte. La radiación se representa mediante muerte ligada a la división, mientras que el calor puede eliminar células que también estaban en reposo. Esto cambia dónde se libera espacio y cómo se reorganiza el esferoide.

## 10. Esferoides tumorales

**Duración: 0:40 · Reloj: 6:20–7:00**

Un esferoide tumoral es un agregado tridimensional de células, sin vasos sanguíneos. Permite estudiar gradientes de oxígeno y contactos celulares que no aparecen de la misma manera en un cultivo plano.

Los autores sembraron trescientas células HCT116, dejaron que formaran el agregado y aplicaron el tratamiento al día cuatro. Después siguieron su evolución durante tres semanas, midiendo su diámetro.

Ese diámetro a lo largo del tiempo es el resultado que el modelo busca reproducir: cuánto se reduce el esferoide, cuánto tarda en volver a crecer y si el recrecimiento aparece dentro del periodo observado. Ahora podemos pasar de esta descripción biológica a su representación matemática.

## 11. Modelo: un autómata celular 3D

**Duración: 1:20 · Reloj: 7:00–8:20**

El modelo utiliza una malla tridimensional de pequeños cubos llamados vóxeles. Cada vóxel puede estar vacío o contener una célula, y cada célula conserva información sobre su estado, su reloj y su destino después del tratamiento.

El lado de cada vóxel es de doce micrómetros y una malla típica tiene doscientas posiciones en cada dirección. Eso corresponde a ocho millones de posiciones posibles, aunque no todas están ocupadas.

Para dividirse, la célula busca un sitio libre en un vecindario cercano. Los autores alternan vecindarios de Moore y de von Neumann, hasta segundo orden, y favorecen posiciones que mantienen un agregado compacto.

[Señalar las reglas locales.]

Conceptualmente, en cada paso se actualiza el oxígeno, se avanza el ciclo celular y se comprueba si puede haber división. También se aplican las reglas de muerte y eliminación. Si aparecen huecos, se reacomodan las células para conservar la estructura del agregado.

Ese reacomodo no es una simulación explícita de migración celular. Es una simplificación geométrica. La idea del autómata es que muchas reglas locales produzcan una dinámica global que podamos comparar con el experimento.

## 12. Oxígeno: difusión y consumo

**Duración: 1:25 · Reloj: 8:20–9:45**

Además de las células discretas, el modelo necesita un campo de oxígeno. Esa combinación es la que hace que podamos describirlo como un modelo híbrido.

[Señalar cada término de la ecuación, sin leer todos los símbolos.]

A la izquierda tenemos cómo cambia la presión parcial de oxígeno con el tiempo. El primer término de la derecha describe la difusión: el oxígeno se distribuye espacialmente. El segundo representa el consumo celular. En un vóxel vacío no hay consumo; donde hay una célula, sí lo hay.

En el exterior se fija una presión de cien milímetros de mercurio. Las células se consideran hipóxicas por debajo del umbral de once milímetros de mercurio utilizado en este modelo.

La difusión ocurre en una escala de segundos, mientras que el ciclo celular toma horas. Por eso, dentro de cada iteración del ciclo, los autores calculan el oxígeno hasta alcanzar prácticamente el equilibrio.

Esta distribución se conecta de vuelta con las reglas celulares: una célula que permanece bajo hipoxia puede morir y contribuir al núcleo necrótico. Así, el crecimiento modifica el oxígeno y el oxígeno modifica la evolución del esferoide.

## 13. Dos tratamientos, dos dinámicas de muerte

**Duración: 1:30 · Reloj: 9:45–11:15**

Para la radiación, la fracción que conserva supervivencia clonogénica se calcula con un modelo lineal-cuadrático. No necesitamos desarrollar toda la ecuación; lo relevante es que depende de la dosis, de parámetros de la línea celular, de la fase del ciclo y de la oxigenación.

Después se asigna aleatoriamente a cada célula un destino de supervivencia o de muerte. Pero estar marcada para morir no significa desaparecer en ese instante. La célula intenta dividirse y tiene una probabilidad de morir en ese intento. Incluso puede dividirse y transmitir la marca a sus hijas. Las células en G0 pueden permanecer dañadas hasta reactivarse.

En cambio, para el calor se emplea un modelo de supervivencia AlphaR ajustado a las observaciones en tres dimensiones. A las células destinadas a morir se les asigna un retraso, independiente de la proliferación. Cuando este termina, se eliminan de la malla.

[Contrastar las dos columnas.]

La diferencia espacial es importante: con calor también pueden liberarse espacios en regiones quiescentes. Eso favorece reoxigenación y reactivación de células supervivientes. Con radiación, la reducción sigue más estrechamente la zona donde se intenta proliferar. Esta es la explicación que el modelo pone a prueba.

## 14. Combinación RT + HT

**Duración: 1:05 · Reloj: 11:15–12:20**

Para combinar ambos tratamientos, los autores conectan las dos cascadas de respuesta. Primero se asigna una fracción a la vía de muerte por radiación. Dentro de la población restante, algunas células siguen la vía de muerte por calor y las demás sobreviven.

[Seguir las ramas del diagrama.]

La supervivencia total se expresa como el producto que vemos arriba. Sin embargo, esto no significa que sean dos efectos independientes. La radiosensibilización por calor ya está incorporada en los parámetros alfa y beta del componente radiativo, que dependen de la dosis térmica.

También debemos cuidar la interpretación del diagrama: sus últimas dos ramas son fracciones de la población que quedó tras la primera asignación. La pregunta experimental será si, una vez ajustadas las reglas de radiación y calor, este esquema permite reproducir la combinación sin volver a ajustar los parámetros.

## 15. Calibración y validación

**Duración: 0:55 · Reloj: 12:20–13:15**

Para evaluar esa pregunta hay que distinguir calibrar de validar. Calibrar es usar datos para elegir parámetros; validar es comprobar el modelo con condiciones que no se utilizaron para ese ajuste.

En radiación, ajustaron la curva de diez gray y después simularon dos y cinco gray sin cambiar esos parámetros. En hipertermia, ajustaron doscientos cuarenta CEM43 y comprobaron cuarenta y ochenta. Para la combinación no hicieron nuevos ajustes.

El oxígeno se comparó con un modelo analítico y con observaciones histológicas. El crecimiento sin tratamiento también se calibró. La concordancia entre curvas se resumió mediante R cuadrada. Por tanto, debemos interpretar cada resultado según si corresponde a un ajuste o a una comprobación posterior.

## 16. Resultados: crecimiento sin tratamiento

**Duración: 1:00 · Reloj: 13:15–14:15**

Primero veamos si el modelo reproduce el sistema antes de tratarlo. En la gráfica de la izquierda, los puntos son las mediciones del diámetro y la línea roja es la simulación. La curva calibrada alcanza una R cuadrada de cero punto noventa y nueve, con un tiempo de duplicación ajustado de veintiocho horas.

[Señalar las imágenes experimentales y luego los cortes simulados.]

La comparación espacial también muestra una coincidencia cualitativa de la región central muerta. En el análisis del oxígeno, las diferencias respecto al modelo analítico llegan hasta un quince por ciento. Ese porcentaje corresponde al campo de oxígeno, no al error del diámetro.

Esto da una base para estudiar el tratamiento, aunque recordemos que la curva de crecimiento sin tratar formó parte de la calibración.

## 17. Resultados: RT y HT por separado

**Duración: 1:30 · Reloj: 14:15–15:45**

En estas gráficas, el eje vertical es el diámetro del esferoide y el horizontal corresponde a los días desde la siembra. Los puntos son los experimentos y las líneas rojas son las simulaciones. La fila superior corresponde a radiación y la inferior a hipertermia.

[Señalar la primera columna.]

Aquí están las dos condiciones utilizadas para ajustar: diez gray y doscientos cuarenta CEM43. Las otras columnas muestran las condiciones posteriores de validación.

Después de diez gray observamos reducción sin recrecimiento durante la ventana estudiada. Después de la dosis térmica alta aparece una reducción marcada, seguida de recrecimiento. Estas dos curvas ilustran dinámicas distintas; no las estoy presentando como una pareja de dosis cuya equivalencia clonogénica se haya demostrado en esta figura.

En general, las R cuadradas están entre cero punto noventa y cuatro y cero punto noventa y ocho. Pero también hay un desacuerdo visible: para cuarenta y ochenta CEM43, el modelo subestima el diámetro en los primeros días. Los autores plantean que podría intervenir un aflojamiento de la estructura o cambios en la matriz que no se modelaron. La concordancia es buena, pero no perfecta.

## 18. Resultados: tratamiento combinado

**Duración: 1:15 · Reloj: 15:45–17:00**

Ahora vemos la combinación de dos gray con tres dosis térmicas. De izquierda a derecha, esas dosis son ciento sesenta, ochenta y cuarenta CEM43.

[Recorrer las tres curvas.]

Con la mayor dosis térmica, el diámetro disminuye durante gran parte del seguimiento. En las otras condiciones aparece recrecimiento, con distintos retrasos. Las simulaciones reproducen esas tendencias con R cuadradas de cero punto ochenta y seis, cero punto ochenta y ocho y cero punto noventa y seis, respectivamente.

El resultado que más me interesa destacar es que estas curvas se obtuvieron sin un nuevo ajuste de parámetros para la combinación. Eso apoya la utilidad de conectar las reglas calibradas para cada modalidad.

El alcance sigue siendo el sistema experimental estudiado: no demuestra todavía que el modelo pueda seleccionar tratamientos para un paciente, pero sí muestra que puede describir respuestas multimodales en estos esferoides.

## 19. Conclusiones

**Duración: 1:10 · Reloj: 17:00–18:10**

Podemos responder ahora la pregunta inicial: conocer la supervivencia clonogénica no basta para describir cómo cambia el tamaño del esferoide. También importa cuándo mueren las células, dónde están y qué cambios producen en su entorno.

El aporte del trabajo es mostrar que un autómata relativamente sencillo, acoplado a difusión de oxígeno y a distintas reglas de muerte, puede reproducir las curvas estudiadas. Además, los parámetros ajustados por separado permiten describir tratamientos combinados sin reajustes.

Pero hay límites claros: se estudió una sola línea celular, con geometría simplificada, sin vasculatura ni respuesta inmune y sin describir explícitamente pH o glucosa. También falta validar mejor el efecto de la hipoxia sobre la respuesta a radiación.

Por eso lo interpretaría como un primer paso para conectar mecanismos celulares y respuesta colectiva, que requiere ampliación y nueva validación antes de trasladarse a tumores in vivo.

## 20. Referencias y preguntas

**Duración: 0:20 · Reloj: 18:10–18:30**

Esta es la referencia del artículo original, de donde se tomaron los datos y las figuras presentadas. Con esto termino la exposición. Muchas gracias por su atención; podemos pasar a las preguntas.

## Si el ensayo se acerca a los 20 minutos

Conserva la pregunta principal, la diferencia RT/HT, la separación entre calibración y validación y las conclusiones. Para recuperar tiempo:

- En el autómata, omite los nombres de los vecindarios y explica solo la búsqueda de espacio cercano.
- En oxígeno, explica difusión y consumo sin detenerte en ambos valores de presión.
- En las gráficas individuales, compara las tendencias y menciona un intervalo de R²; no leas cada dosis y cada coeficiente.
- En combinación, destaca la ausencia de reajuste y describe las curvas sin recitar los tres R².

Puedes usar esta transición para acelerar: «Los detalles numéricos están en la diapositiva; el resultado que quiero destacar es que el modelo reproduce las tendencias sin reajustar la combinación».

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

«Indica buena concordancia entre las curvas comparadas según esa medida. Hay que distinguir si se trata de una curva de calibración o de validación. No demuestra por sí sola que los mecanismos propuestos sean los únicos posibles ni que exista validación clínica».

### ¿Por qué es importante que la combinación no se reajuste?

«Porque comprueba si las reglas y los parámetros obtenidos en las modalidades individuales conservan capacidad de describir otra condición experimental, en lugar de adaptar nuevos valores a cada curva».

### ¿Esto se puede aplicar directamente a pacientes?

«El artículo no demuestra eso. Es un modelo in vitro de una línea celular y omite aspectos como vasculatura, respuesta inmune y tejidos circundantes. Su extensión in vivo es una dirección futura».

### ¿Cómo se podría mejorar el trabajo?

«Una ampliación sería evaluar esferoides hipóxicos al momento del tratamiento. Otras serían representar cambios de densidad y mecánica, incorporar otros factores del microambiente y validar con más sistemas experimentales. Son propuestas de continuación, no resultados obtenidos aquí».

### Si preguntan algo que el artículo no resuelve

«Ese aspecto no se evaluó en este trabajo. Lo que sí muestran los resultados es…». Retoma después la evidencia pertinente. Es preferible delimitar el alcance a atribuirle al artículo un resultado que no presenta.

## Fuente para repasar antes de exponer

Brüningk, S. C. et al. (2019). *A cellular automaton model for spheroid response to radiation and hyperthermia treatments*. Scientific Reports, 9, 17674. https://doi.org/10.1038/s41598-019-54117-x.

Para el modelo: pp. 2–5. Para ajuste y validación: pp. 5–6. Para las figuras y resultados: pp. 6–8. Para límites y conclusiones: pp. 9–10. Las respuestas anteriores se basan en ese contenido; las propuestas de mejora están identificadas como continuación.
