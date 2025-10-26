============================================
DATOS BRUTOS - LEVANTAMIENTO TOPOGRÁFICO
============================================

Este directorio contiene los datos en bruto obtenidos en campo durante el levantamiento de pozos.

-------------------------------------------
PRIMERA_PASADA.txt
-------------------------------------------
Levantamiento planialétrico y altimétrico
Una fila por pozo

Columnas:
1. ID_POZO          - Identificador único del pozo
2. X                - Coordenada X (centro de tapa)
3. Y                - Coordenada Y (centro de tapa)
4. Z                - Cota de la tapa (m)
5. FECHA            - Fecha levantamiento (YYYYMMDD)
6. OPERADOR         - Iniciales del técnico

-------------------------------------------
SEGUNDA_PASADA.txt
-------------------------------------------
Caracterización detallada de pozos y tubos
Una fila por tubo (los datos del pozo se repiten)

Columnas:
1. ID_POZO          - Referencia al pozo
2. TIPO_AGUA        - Tipo de servicio (pluvial/fecal/potable/acequia/telecom/electrica/no_se_sabe)
3. FORMA_TAPA       - Forma de la tapa (circular/cuadrada)
4. DIM_TAPA         - Dimensión de tapa: diámetro si circular, lado si cuadrada (cm)
5. PROF_ARENERO     - Profundidad total del pozo hasta arenero (m)
6. NUM_TUBO         - Número de orden del tubo (1, 2, 3...)
7. TOTAL_TUBOS      - Cantidad total de tubos en este pozo
8. TIPO_TUBO        - Tipo de tubo (colector_entrada/colector_salida/acometida/desconocido)
9. DIAM_TUBO        - Diámetro del tubo (cm)
10. PROF_TUBO       - Profundidad desde tapa hasta parte baja del agujero del tubo (m)
11. FECHA           - Fecha de caracterización (YYYYMMDD)
12. OPERADOR        - Iniciales del técnico

-------------------------------------------
NOTAS SOBRE LOS DATOS
-------------------------------------------

Red generada: 5 pozos de saneamiento (fecal) interconectados

P001 - Pozo de arranque: 1 tubo (solo salida)
P002 - Pozo intermedio: 2 tubos (entrada + salida)
P003 - Pozo con acometida: 3 tubos (entrada + salida + 1 acometida)
P004 - Pozo intermedio: 2 tubos (entrada + salida)
P005 - Pozo final: 4 tubos (entrada + salida + 2 acometidas)

La profundidad del arenero y de los tubos aumenta progresivamente 
siguiendo la pendiente natural del terreno para permitir el flujo por gravedad.

Coordenadas: Sistema UTM (ficticio para ejemplo)
Operador: JMS (Juan Martínez Sánchez)
Fechas: Primera pasada 15/10/2024, Segunda pasada 22/10/2024
