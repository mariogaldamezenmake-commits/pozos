\## 📋 Descripción del Proyecto



En este proyecto de topografía se realiza un levantamiento de pozos y arquetas para posteriormente procesar la información en gabinete. El proceso se divide en \*\*dos pasadas en campo\*\* y un \*\*trabajo de gabinete\*\*.



---



\## 📍 Primera Pasada: Levantamiento Planialétrico y Altimétrico



\### Objetivo



Dotar de coordenadas planialtéricas (X, Y, Z) a las tapas de los pozos.



\### Procedimiento



1\. \*\*Ubicación\*\*: Se identifica cada pozo en campo

2\. \*\*Medición\*\*: Se toma un único punto en el \*\*centro de la tapa\*\* del pozo

3\. \*\*Registro\*\*: Se obtienen coordenadas X, Y, Z (cota de la tapa)

4\. \*\*Numeración\*\*: Se asigna un identificador único a cada pozo



\### Equipo utilizado



\- Estación total o GPS RTK

\- Prisma o antena GPS

\- Libreta de campo



\### Datos obtenidos



\- \*\*Pozo ID\*\*: Identificador único

\- \*\*X, Y\*\*: Coordenadas planialtéricas

\- \*\*Z (cota de tapa)\*\*: Altura de la tapa del pozo



---



\## 🔍 Segunda Pasada: Caracterización del Pozo



\### Objetivo



Obtener información detallada sobre las características físicas y conexiones de cada pozo.



\### Procedimiento



\### 1. Medición de la tapa



\- \*\*Diámetro de la trapa\*\* (para pozos circulares)

\- \*\*Dimensiones\*\* (para arquetas cuadradas) → esto tengo que preguntarlo porque no estoy seguro



\### 2. Apertura del pozo



\- Se abre la tapa para inspección interna



\### 3. Categorización del tipo de agua



Se clasifica según el tipo de agua que transporta:



\- 💧 \*\*Pluvial\*\*: Aguas de lluvia

\- 🚽 \*\*Fecal / Saneamiento\*\*: Aguas residuales

\- 💧 \*\*Potable\*\*: Agua de consumo

\- 🌾 \*\*Acequia\*\*: Riego agrícola

\- 📶 \*\*Telecomunicaciones\*\*: Cableado

\- ⚡ \*\*Electricidad\*\*: Red eléctrica

\- ❓ \*\*No se sabe\*\*: Casos dudosos



\### 4. Medición de profundidad de los tubos



\- Se mide la distancia vertical desde la \*\*tapa hasta la parte baja del agujero del tubo\*\*

\- Esta medida permite calcular la \*\*cota del tubo\*\*: `cota\_fondo = cota\_tapa - profundidad`



\### 5. Conteo y medición de tubos



Para cada tubo conectado al pozo:



\- \*\*Cantidad\*\*: Número total de tubos

\- \*\*Diámetro\*\*: De cada tubo individual

\- Profundidad: distancia a la parte mas lejana de la tapa al tubo

\- \*\*Dirección\*\*: Se anota hacia dónde se dirige en un croquis

\- \*\*Tipo de tubo\*\*:

&nbsp;   - 🔹 \*\*Colector principal\*\*: Entrada y salida (flujo principal) → Puede no saberse al abrir el tubo que agujero es la entrada y cual es la salida. Puede darse el caso de que solo haya un agujero de salida y no entrada en cuyo caso se trata de un pozo de arranque.

&nbsp;   - 🔸 \*\*Acometidas\*\*: Conexiones secundarias (puede haber varias)



\### 6. Registro en plano de situación



El equipo trabaja con un \*\*plano en papel\*\* donde:



\- Anota el \*\*número del pozo\*\*

\- Marca la \*\*profundidad del pozo para saber la cota del arenero → duda preguntar\*\*

\- Anota el número de tubos del pozo

\- Anota los diámetros de los tubos

\- Anota las profundidades de los tubos

\- Dibuja \*\*líneas\*\* representando los tubos con su dirección aproximada

\- Relaciona pozos: \*"el pozo 24 conecta con el pozo 25"\*



---



\## 📊 Tipos de Pozos



\### Por forma de la tapa



\- 🔵 \*\*Pozos\*\*: Tapa circular

\- 🟪 \*\*Arquetas\*\*: Tapa cuadrada/rectangular



\### Por tipo de conexión



\- 🔴 \*\*Pozo de arranque\*\*: Solo tiene UNA salida de colector principal (sin entrada). Define el punto inicial de la red y el sentido de flujo.

\- 🟪 \*\*Pozo intermedio\*\*: Tiene entrada y salida de colector

\- 🟡 \*\*Pozo con acometidas\*\*: Tiene conexiones secundarias además del colector



---



\## 📝 Conceptos Importantes



\### Colector Principal



\- Solo puede haber \*\*UN colector principal\*\* en cada pozo

\- Tiene una \*\*entrada\*\* y una \*\*salida\*\*

\- Si solo hay flujo en una dirección sin entrada → \*\*Pozo de arranque\*\*

\- Si no fluye agua, es difícil determinar cuál es entrada y cuál salida



\### Acometidas



\- Puede haber \*\*múltiples acometidas\*\* en un pozo

\- Son conexiones que desembocan en el colector

\- No forman parte del flujo principal



\### Sentido de flujo



\- Se determina observando el flujo de agua en el pozo

\- Los \*\*pozos de arranque\*\* ayudan a establecer el sentido de la red

\- Importante para validación de diseño y normativas



---



\## 🛠️ Desafíos en Campo



\### 🎯 Dirección de tubos



\*\*Problema\*\*: Es complicado determinar con precisión hacia dónde se dirige cada tubo.



\*\*Solución actual\*\*:



\- El técnico se mete físicamente en el pozo

\- Observa visualmente la dirección aproximada

\- Anota en el plano la conexión estimada con otros pozos



---



\## 💼 Trabajo de Gabinete



Una vez recopilada toda la información de campo, se procede a:



1\. \*\*Digitalización\*\* en AutoCAD:

&nbsp;   - Creación de polilíneas 3D para tubos

&nbsp;   - Ajuste de cotas Z en extremos

&nbsp;   - Inserción de bloques POZO con atributos

2\. \*\*Validación\*\*:

&nbsp;   - Verificar conexiones entre pozos

&nbsp;   - Comprobar coherencia de cotas

&nbsp;   - Detectar errores en direcciones

3\. \*\*Generación de entregables\*\*:

&nbsp;   - Planos de planta

&nbsp;   - Planos de perfil longitudinal

&nbsp;   - Fichas técnicas por pozo

&nbsp;   - Listados y tablas



\### 🤖 Herramientas de Automatización: Comando P1



Para agilizar el trabajo de gabinete se ha desarrollado el comando \*\*P1\*\* en AutoLISP para AutoCAD 2026.



\#### P1.lsp (Versión 1.0)



\*\*Propósito\*\*: Inserción de UN SOLO pozo a la vez



\*\*Flujo de trabajo\*\*:

1\. \*\*Solicita datos del pozo\*\*:

&nbsp;   - Cota de la tapa (Z de la superficie)

&nbsp;   - Profundidad del tubo (medida desde tapa hasta parte baja del agujero)

&nbsp;   - Diámetro del tubo

&nbsp;   - Número de tubos conectados



2\. \*\*Calcula automáticamente\*\*:

&nbsp;   - \`resultado = cota\_tapa - profundidad\`

&nbsp;   - Este "resultado" es la \*\*cota Z del fondo del tubo\*\*



3\. \*\*Ajusta la geometría 3D\*\*:

&nbsp;   - Permite seleccionar una polilínea 3D (que representa el tubo)

&nbsp;   - Permite hacer clic cerca del extremo deseado

&nbsp;   - \*\*Modifica la coordenada Z de ese extremo\*\* al valor "resultado"

&nbsp;   - Esto garantiza que la polilínea 3D termina exactamente en la cota del fondo del tubo



4\. \*\*Inserta el bloque POZO\*\*:

&nbsp;   - Inserta un bloque llamado "POZO" en el punto especificado

&nbsp;   - Rellena automáticamente los atributos:

&nbsp;     - \`RESULTADO\`: Cota Z del fondo del tubo

&nbsp;     - \`DIAMETRODETUBO\`: Diámetro del tubo

&nbsp;     - \`NUMERODETUBOS\`: Cantidad de tubos conectados

&nbsp;   - \*\*Orienta el bloque\*\* según la tangente de la polilínea en ese extremo



\*\*Ventaja\*\*: Reduce errores al calcular cotas y asigna atributos de forma automática



\#### P1\_v1.2.lsp (Versión 1.2 - ACTUAL)



\*\*Propósito\*\*: Inserción de \*\*MÚLTIPLES pozos en una sola ejecución\*\*



\*\*Mejoras respecto a v1.0\*\*:



1\. \*\*Proceso en dos fases\*\*:

&nbsp;   - \*\*FASE 1 - Recopilación de datos\*\*: Se solicitan los datos de TODOS los pozos consecutivamente (cota, profundidad, diámetro, tubos)

&nbsp;   - \*\*FASE 2 - Inserción gráfica\*\*: Se insertan los bloques uno por uno, seleccionando polilíneas y extremos



2\. \*\*Validaciones integradas\*\*:

&nbsp;   - Verifica que la profundidad sea positiva

&nbsp;   - Verifica que el diámetro sea positivo

&nbsp;   - Verifica que haya al menos 1 tubo

&nbsp;   - Emite advertencias si los valores son incorrectos



3\. \*\*Mejor manejo de errores\*\*:

&nbsp;   - Si falla la inserción de un pozo, permite continuar con los siguientes

&nbsp;   - Mensajes informativos sobre el progreso (ej: "POZO 3 de 5")

&nbsp;   - Opción de cancelar o saltar pozos individuales



4\. \*\*Experiencia de usuario mejorada\*\*:

&nbsp;   - Muestra resumen de datos antes de cada inserción

&nbsp;   - Indica progreso durante el proceso

&nbsp;   - Mensaje final con el total de pozos procesados



\*\*Ventaja principal\*\*: Permite trabajar en \*\*lote\*\*, ideal cuando se tienen muchos pozos del mismo levantamiento. Se pueden introducir todos los datos numéricos de una vez (mirando la libreta de campo) y luego hacer todas las inserciones gráficas seguidas.



\*\*Uso recomendado\*\*: Cuando tienes 5+ pozos para digitalizar, usar v1.2 ahorra mucho tiempo al no tener que repetir el comando para cada pozo.



\#### P1\_v2.0.lsp (Versión 2.0 - CARGA AUTOMÁTICA DESDE CSV)



\*\*Propósito\*\*: Automatización completa mediante \*\*lectura de datos desde archivos CSV\*\* (PRIMERA\_PASADA.txt y SEGUNDA\_PASADA.txt)



\*\*Revolución en el flujo de trabajo\*\*:



1\. \*\*Entrada de datos\*\*: Ya NO se escriben datos manualmente en gabinete

&nbsp;   - Los datos ya están capturados en los archivos CSV de campo

&nbsp;   - El usuario solo selecciona el archivo SEGUNDA\_PASADA.txt

&nbsp;   - El sistema busca automáticamente PRIMERA\_PASADA.txt en la misma carpeta



2\. \*\*Procesamiento automático\*\*:

&nbsp;   - Lee y combina ambos archivos CSV

&nbsp;   - Para cada tubo, calcula automáticamente: \`cota\_tubo = cota\_tapa - prof\_tubo\`

&nbsp;   - Muestra resumen: "5 pozos cargados, 12 tubos totales"



3\. \*\*Flujo iterativo por tubo\*\*:

&nbsp;   - Para CADA tubo en SEGUNDA\_PASADA.txt:

&nbsp;     - Muestra información: "POZO P003 - Tubo 2/3 - Colector salida Ø30cm"

&nbsp;     - Muestra cálculo: "Cota tapa: 107.78m | Prof: 2.30m → Cota tubo: 105.48m"

&nbsp;     - Solicita: Seleccionar polilínea 3D

&nbsp;     - Solicita: Click en extremo de la polilínea

&nbsp;     - Ajusta automáticamente Z del vértice a la cota calculada

&nbsp;     - Solicita: Punto de inserción del bloque POZO

&nbsp;     - Inserta bloque con atributos ya rellenos

&nbsp;     - Continúa con el siguiente tubo



4\. \*\*Datos extraídos de los CSV\*\*:

&nbsp;   - De PRIMERA\_PASADA.txt: ID\_POZO, X, Y, Z (cota\_tapa)

&nbsp;   - De SEGUNDA\_PASADA.txt: tipo\_agua, forma\_tapa, dim\_tapa, prof\_arenero, num\_tubo, total\_tubos, tipo\_tubo, diam\_tubo, prof\_tubo

&nbsp;   - Calculados: cota\_tubo (para ajustar Z del vértice)



5\. \*\*Atributos del bloque POZO\*\* (igual que en v1.2):

&nbsp;   - \`RESULTADO\`: Cota del tubo (cota\_tapa - prof\_tubo)

&nbsp;   - \`DIAMETRODETUBO\`: Diámetro del tubo en cm

&nbsp;   - \`NUMERODETUBOS\`: Total de tubos del pozo



\*\*Ventajas clave de v2.0\*\*:

\- ✅ \*\*Cero escritura manual\*\*: Los datos ya están en los CSV de campo

\- ✅ \*\*Cero errores de transcripción\*\*: No hay riesgo de equivocarse al teclear números

\- ✅ \*\*Procesamiento tubo por tubo\*\*: El usuario solo hace clicks en posiciones correctas

\- ✅ \*\*Trazabilidad completa\*\*: Toda la información viene directamente de campo

\- ✅ \*\*Escalabilidad\*\*: Funciona igual con 5 tubos o 500 tubos



\*\*Uso recomendado\*\*: \*\*SIEMPRE\*\* que tengas los archivos CSV de campo. Esta es la versión definitiva para producción. Solo requiere que el técnico de campo haya registrado correctamente los datos en PRIMERA\_PASADA.txt y SEGUNDA\_PASADA.txt.



\*\*Requisitos\*\*:

\- Archivos PRIMERA\_PASADA.txt y SEGUNDA\_PASADA.txt en la misma carpeta

\- Formato CSV con separador de coma (,)

\- Bloque "POZO" con atributos RESULTADO, DIAMETRODETUBO, NUMERODETUBOS



---

