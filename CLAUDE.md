# Proyecto: Automatización de Levantamiento Topográfico de Pozos

## Contexto del Proyecto
Empresa de topografía que realiza levantamientos de pozos y arquetas.

## Proceso Actual de Campo (2 pasadas)

### Primera Pasada
- Levantamiento de pozos para obtener coordenadas planimétricas y altimétricas
- Se toma un único punto en el centro de la tapa del pozo

### Segunda Pasada
- Medición del diámetro de la trapa
- Apertura del pozo para categorización:
  - Fecal
  - Pluvial
  - Potable
  - Acequia
  - Telecomunicaciones
  - No se sabe
- Averiguar cantidad de tubos que conectan con otros pozos

### Trabajo de Campo Manual
- Equipo trabaja con plano de situación (papel y boli)
- Anotan: número de pozo, profundidad, número de tubos con diámetros
- Dibujan líneas en el plano indicando dirección de tubos
- Se meten físicamente en el pozo para ver hacia dónde van los tubos
- Ejemplo: "pozo 24 conecta con pozo 25", "al pozo 25 mueren 3 acometidas..."

### Trabajo de Gabinete (AutoCAD)
- Se digitaliza toda la información recopilada en campo
- Se plasma todo para el cliente

## Objetivo del Proyecto
Automatizar procesos mediante mini-proyectos:
1. Scripts LISP para AutoCAD (como P1.lsp)
2. Base de datos en Notion para almacenar y relacionar pozos
3. Sistema de versionado (v1, v2, v2.1...)
4. Eventualmente: aplicación unificada que integre todo

## Requisitos Técnicos
- AutoCAD 2026
- Bloque llamado "POZO" con atributos:
  - RESULTADO (cota - profundidad)
  - DIAMETRODETUBO
  - NUMERODETUBOS
- Polilíneas 3D para representar conexiones entre pozos

## Estado Actual
- Existe P1.lsp (versión 1) que:
  - Ajusta Z de extremo de polilínea 3D
  - Inserta bloque POZO alineado en planta
  - Solicita: cota tapa, profundidad, diámetro, número tubos