# 📊 Datos Brutos - Levantamiento Topográfico

Este directorio contiene los **archivos CSV de campo** obtenidos durante el levantamiento de pozos y arquetas. Estos archivos son la entrada para las versiones automáticas del comando P1 (v2.0 y v2.1).

---

## 📂 Archivos en este Directorio

### 📍 PRIMERA_PASADA.txt

**Propósito:** Levantamiento planialétrico y altimétrico
**Estructura:** Una fila por pozo
**Separador:** Coma (,)
**Codificación:** UTF-8

#### Columnas

| # | Columna | Tipo | Descripción | Ejemplo |
|---|---------|------|-------------|---------|
| 1 | `ID_POZO` | String | Identificador único del pozo | P001 |
| 2 | `X` | Float | Coordenada X (centro de tapa) | 450123.45 |
| 3 | `Y` | Float | Coordenada Y (centro de tapa) | 4321567.89 |
| 4 | `Z` | Float | Cota de la tapa (metros) | 108.23 |
| 5 | `FECHA` | String | Fecha del levantamiento (YYYYMMDD) | 20241015 |
| 6 | `OPERADOR` | String | Iniciales del técnico de campo | JMS |

#### Ejemplo
```csv
ID_POZO,X,Y,Z,FECHA,OPERADOR
P001,450120.45,4321560.12,108.23,20241015,JMS
P002,450125.78,4321562.89,107.95,20241015,JMS
```

---

### 🔍 SEGUNDA_PASADA.txt

**Propósito:** Caracterización detallada de pozos y tubos
**Estructura:** Una fila por tubo (datos del pozo se repiten en cada fila)
**Separador:** Coma (,)
**Codificación:** UTF-8

#### Columnas

| # | Columna | Tipo | Descripción | Valores Posibles |
|---|---------|------|-------------|------------------|
| 1 | `ID_POZO` | String | Referencia al pozo | P001, P002, ... |
| 2 | `TIPO_AGUA` | String | Tipo de servicio | pluvial, fecal, potable, acequia, telecom, electrica, no_se_sabe |
| 3 | `FORMA_TAPA` | String | Forma de la tapa | circular, cuadrada |
| 4 | `DIM_TAPA` | Float | Dimensión (diámetro si circular, lado si cuadrada) en cm | 60, 80, 100 |
| 5 | `PROF_ARENERO` | Float | Profundidad total hasta arenero (metros) | 2.50, 3.20 |
| 6 | `NUM_TUBO` | Integer | Número de orden del tubo | 1, 2, 3, ... |
| 7 | `TOTAL_TUBOS` | Integer | Cantidad total de tubos en el pozo | 1, 2, 3, 4 |
| 8 | `TIPO_TUBO` | String | Tipo de tubo | colector_entrada, colector_salida, acometida, desconocido |
| 9 | `DIAM_TUBO` | Float | Diámetro del tubo en cm | 20, 30, 40 |
| 10 | `PROF_TUBO` | Float | Profundidad desde tapa hasta parte baja del agujero (metros) | 2.00, 2.50 |
| 11 | `FECHA` | String | Fecha de caracterización (YYYYMMDD) | 20241022 |
| 12 | `OPERADOR` | String | Iniciales del técnico | JMS |

#### Ejemplo
```csv
ID_POZO,TIPO_AGUA,FORMA_TAPA,DIM_TAPA,PROF_ARENERO,NUM_TUBO,TOTAL_TUBOS,TIPO_TUBO,DIAM_TUBO,PROF_TUBO,FECHA,OPERADOR
P001,fecal,circular,60,2.50,1,1,colector_salida,30,2.20,20241022,JMS
P002,fecal,circular,60,2.70,1,2,colector_entrada,30,2.40,20241022,JMS
P002,fecal,circular,60,2.70,2,2,colector_salida,30,2.30,20241022,JMS
```

---

### 📐 CROQUIS_AUTOCAD.txt

**Propósito:** Información adicional para verificación visual
**Formato:** Texto libre con anotaciones del técnico
**Uso:** Referencia manual durante la digitalización

Contiene:
- Conexiones entre pozos ("P001 conecta con P002")
- Direcciones aproximadas de tubos
- Observaciones de campo
- Croquis ASCII art (opcional)

---

## 🎯 Datos de Ejemplo Incluidos

### Red de Saneamiento (Fecal)

Esta carpeta incluye datos de ejemplo de una **red de 5 pozos** interconectados:

| Pozo | Tipo | Tubos | Descripción |
|------|------|-------|-------------|
| **P001** | 🔴 Arranque | 1 | Solo salida (punto inicial de la red) |
| **P002** | 🟪 Intermedio | 2 | Entrada + salida |
| **P003** | 🟡 Con acometida | 3 | Entrada + salida + 1 acometida |
| **P004** | 🟪 Intermedio | 2 | Entrada + salida |
| **P005** | 🟢 Final | 4 | Entrada + salida + 2 acometidas |

**Total:** 5 pozos, 12 tubos

### Características del Ejemplo

- **Tipo de red:** Saneamiento (fecal)
- **Pendiente:** Descendente siguiendo gravedad
- **Coordenadas:** Sistema UTM (ficticio)
- **Profundidades:** 2.00m - 3.50m
- **Diámetros:** 20cm - 40cm
- **Operador:** JMS (Juan Martínez Sánchez)
- **Fechas:**
  - Primera pasada: 15/10/2024
  - Segunda pasada: 22/10/2024

---

## 🚀 Cómo Usar estos Archivos

### Con P1_v2.0 o P1_v2.1

1. **Preparar archivos:**
   - Asegúrate de tener `PRIMERA_PASADA.txt` y `SEGUNDA_PASADA.txt` en la misma carpeta

2. **En AutoCAD:**
   - Dibuja polilíneas 3D aproximadas para cada tubo
   - Ejecuta comando `P1`
   - Selecciona `SEGUNDA_PASADA.txt`

3. **Sistema procesará automáticamente:**
   - Lee ambos archivos CSV
   - Combina datos por ID_POZO
   - Calcula `cota_tubo = Z - PROF_TUBO` para cada tubo
   - Solicita clicks para ajustar polilíneas e insertar bloques

### Crear tus Propios Archivos

#### Opción 1: Aplicación Móvil (Recomendada)
- Usa app de campo que exporte directamente a CSV
- Valida formato antes de usar

#### Opción 2: Excel/LibreOffice
1. Crea una hoja con las columnas especificadas
2. Rellena los datos de campo
3. Exporta como CSV con:
   - Separador: coma (,)
   - Codificación: UTF-8
   - Sin comillas en números

#### Opción 3: Edición Manual
- Usa un editor de texto (VS Code, Notepad++, Sublime)
- Respeta exactamente el formato CSV
- Verifica que no haya espacios extra

---

## ✅ Validación de Datos

### Antes de usar en AutoCAD

#### Checklist PRIMERA_PASADA.txt
- [ ] Cada pozo tiene una única fila
- [ ] ID_POZO es único
- [ ] Coordenadas X, Y son numéricas (sin letras)
- [ ] Cota Z es numérica y razonable
- [ ] Formato de fecha es YYYYMMDD
- [ ] No hay líneas vacías entre datos

#### Checklist SEGUNDA_PASADA.txt
- [ ] Cada tubo tiene su propia fila
- [ ] ID_POZO coincide con PRIMERA_PASADA
- [ ] TIPO_AGUA es uno de los valores válidos
- [ ] FORMA_TAPA es "circular" o "cuadrada"
- [ ] DIM_TAPA > 0
- [ ] NUM_TUBO va de 1 a TOTAL_TUBOS
- [ ] TOTAL_TUBOS coincide con el número de filas del pozo
- [ ] PROF_TUBO < PROF_ARENERO (tubo no puede estar más profundo que el arenero)
- [ ] DIAM_TUBO > 0

### Errores Comunes

| Error | Causa | Solución |
|-------|-------|----------|
| "No se encuentra PRIMERA_PASADA.txt" | Archivos en carpetas diferentes | Ambos CSV en misma carpeta |
| "ID_POZO no encontrado" | ID no coincide entre archivos | Verifica nombres exactos (P001 vs P01) |
| "Cota calculada negativa" | PROF_TUBO > Z | Revisa profundidades y cotas |
| "Formato CSV incorrecto" | Excel añadió comillas o separadores | Exporta como CSV UTF-8 simple |

---

## 🔗 Ver También

- **[../Versiones/P1_v2.0.lsp](../Versiones/P1_v2.0.lsp)** - Script que lee estos CSV (con selección manual)
- **[../Versiones/P1_v2.1.lsp](../Versiones/P1_v2.1.lsp)** - Script mejorado con detección automática
- **[../CLAUDE.md](../CLAUDE.md)** - Documentación completa del proyecto
- **[README.txt](./README.txt)** - Versión texto plano de esta documentación

---

## 📝 Notas Técnicas

### Formato CSV
- **Separador:** Coma (,)
- **Codificación:** UTF-8
- **Línea de cabecera:** Sí (nombres de columnas)
- **Comillas:** Solo si el valor contiene comas
- **Decimales:** Punto (.) no coma (,)

### Convenciones de Nombres
- **Pozos:** P001, P002, P003... (con ceros a la izquierda)
- **Tipo de agua:** Minúsculas, sin espacios, con guión bajo
- **Tipo de tubo:** snake_case (colector_entrada, no "Colector Entrada")

### Coordenadas
- **Sistema:** UTM o local (especificar en proyecto)
- **Unidades:** Metros
- **Precisión:** Mínimo 2 decimales para X, Y
- **Cota Z:** Referida a nivel de tapa del pozo

---

**💡 Tip:** Valida tus CSV abriendo con Excel o LibreOffice antes de usar en AutoCAD. Verifica que todas las columnas estén correctamente separadas.

**⚠️ Importante:** Si modificas estos archivos manualmente, NO uses Excel para guardar (puede cambiar el formato). Usa un editor de texto plano.
