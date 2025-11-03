[![GitHub stars](https://img.shields.io/github/stars/TuUsuario/Automatas-JFLAP-Lab1.svg?style=social&label=Star)](https://github.com/TuUsuario/Automatas-JFLAP-Lab1)
[![GitHub forks](https://img.shields.io/github/forks/TuUsuario/Automatas-JFLAP-Lab1.svg?style=social&label=Fork)](https://github.com/TuUsuario/Automatas-JFLAP-Lab1/fork)
[![GitHub watchers](https://img.shields.io/github/watchers/TuUsuario/Automatas-JFLAP-Lab1.svg?style=social&label=Watch)](https://github.com/TuUsuario/Automatas-JFLAP-Lab1)

# 🤖 Autómatas Finitos y Lenguajes Regulares con JFLAP

[![JFLAP](https://img.shields.io/badge/JFLAP-7.1-blue.svg)](https://www.jflap.org/)
[![Java](https://img.shields.io/badge/Java-SE%20Runtime-orange.svg)](https://www.java.com/)
[![License](https://img.shields.io/badge/License-Academic-green.svg)]()
[![Status](https://img.shields.io/badge/Status-Completed-success.svg)]()

> Laboratorio académico sobre teoría de autómatas, expresiones regulares y gramáticas formales utilizando JFLAP como herramienta de simulación y análisis.

---

## 📋 Tabla de Contenidos

- [Descripción](#-descripción)
- [Objetivos](#-objetivos)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación](#-instalación)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Desarrollo](#-desarrollo)
  - [Autómata Finito Determinista](#1-autómata-finito-determinista)
  - [Expresión Regular](#2-expresión-regular)
  - [Gramática Formal](#3-gramática-formal)
  - [Descripción del Lenguaje](#4-descripción-del-lenguaje)
- [Resultados](#-resultados)
- [Capturas de Pantalla](#-capturas-de-pantalla)
- [Documentación](#-documentación)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Autor](#-autor)
- [Agradecimientos](#-agradecimientos)
- [Licencia](#-licencia)

---

## 🎯 Descripción

Este proyecto corresponde al **Laboratorio #1** de la asignatura de **Fundamentos de la Computación**, donde se explora la relación entre diferentes formalismos para describir lenguajes regulares:

- **Autómatas Finitos Deterministas (AFD)**
- **Expresiones Regulares**
- **Gramáticas Regulares (Tipo 3)**

A través de la herramienta educativa **JFLAP (Java Formal Languages and Automata Package)**, se construye, analiza y valida un autómata finito que reconoce un lenguaje específico sobre el alfabeto **Σ = {a, b, c}**.

---

## 🎓 Objetivos

### Objetivo General
Comprender y aplicar los conceptos de autómatas finitos, expresiones regulares y gramáticas formales mediante el uso de herramientas de simulación.

### Objetivos Específicos
- ✅ Construir un autómata finito determinista (AFD) en JFLAP
- ✅ Derivar la expresión regular equivalente al autómata
- ✅ Obtener la gramática regular que genera el mismo lenguaje
- ✅ Validar cadenas de entrada (aceptadas y rechazadas)
- ✅ Describir informalmente el lenguaje reconocido

---

## 📦 Requisitos Previos

Antes de comenzar, asegúrate de tener instalado:

- **Java Runtime Environment (JRE)** versión 8 o superior
  - Descarga: [https://www.java.com/es/download/](https://www.java.com/es/download/)
  
- **JFLAP 7.1**
  - Descarga: [https://www.jflap.org/jflaptmp/](https://www.jflap.org/jflaptmp/)

---

## 🔧 Instalación

### 1. Instalar Java
```bash
# En Windows: Descargar el instalador desde java.com
# En Linux (Ubuntu/Debian):
sudo apt update
sudo apt install default-jre

# Verificar instalación
java -version
```

### 2. Descargar JFLAP
```bash
# Descargar JFLAP7.1.jar desde el sitio oficial
wget http://www.jflap.org/jflaptmp/july27-18/JFLAP7.1.jar

# O descargarlo manualmente desde: https://www.jflap.org/jflaptmp/
```

### 3. Ejecutar JFLAP
```bash
# Método 1: Doble clic en JFLAP7.1.jar (Windows/Mac)

# Método 2: Desde terminal
java -jar JFLAP7.1.jar
```

### 4. Clonar este Repositorio
```bash
git clone https://github.com/TuUsuario/Automatas-JFLAP-Lab1.git
cd Automatas-JFLAP-Lab1
```

### 5. Abrir el Archivo del Autómata

1. Ejecutar JFLAP
2. File → Open → Seleccionar `Autómatas finitos y lenguajes regulares con JFLAP.jff`

---

## 📁 Estructura del Proyecto
```
Automatas-JFLAP-Lab1/
│
├── 📄 README.md                                          # Este archivo
├── 📄 Autómatas finitos y lenguajes regulares con JFLAP.jff   # Archivo JFLAP
├── 📄 Autómatas finitos y lenguajes regulares con JFLAP + Alejandro De Mendoza.pdf
│                                                         # Documentación completa
├── 📂 imagenes/                                          # Capturas de pantalla
│   ├── automata_original.png
│   ├── automata_jflap.png
│   ├── expresion_regular.png
│   ├── gramatica.png
│   ├── pruebas_multiple_run.png
│   └── ...
│
└── 📂 docs/                                              # Documentación adicional
    ├── metodologia.md
    ├── resultados.md
    └── bibliografia.md
```

---

## 🚀 Desarrollo

### 1. Autómata Finito Determinista

#### Especificaciones

- **Estados:** `q0, q1, q2, q3, q4, q5` (6 estados)
- **Estado inicial:** `q0`
- **Estados finales:** `q0, q1, q3, q4` (representados con doble círculo)
- **Alfabeto:** `Σ = {a, b, c}`

#### Tabla de Transiciones

| Origen | Destino | Símbolo(s) |
|--------|---------|------------|
| q0     | q1      | a          |
| q0     | q3      | b, c       |
| q1     | q1      | b          |
| q1     | q2      | c          |
| q1     | q4      | a          |
| q2     | q2      | a, b, c    |
| q2     | q5      | b          |
| q3     | q3      | b, c       |
| q3     | q4      | a          |
| q4     | q4      | a          |
| q4     | q3      | c          |
| q4     | q5      | b          |
| q5     | q3      | a          |
| q5     | q4      | b, c       |

#### Diagrama

![Autómata Finito](imagenes/automata_jflap.png)

---

### 2. Expresión Regular

Mediante el proceso de eliminación de estados en JFLAP, se obtuvo la siguiente expresión regular:
```
λ + a + a(a + ba)(a + ba)* (b + c + ab(b + c) + a(a + ba)(a + ba)* (c + b(b + c))) (b + c + a(a + ba)* (c + b(b + c)))* (λ + a(a + ba)*)
```

**Notación:**
- `λ` : cadena vacía (épsilon)
- `+` : unión (OR)
- `*` : clausura de Kleene (cero o más repeticiones)
- Concatenación: yuxtaposición directa

**Análisis:**
La expresión acepta:
- λ (cadena vacía)
- `a` (cadena simple)
- Cadenas complejas que comienzan con `a` seguidas de patrones específicos

---

### 3. Gramática Formal

#### Especificación

- **Alfabeto de terminales:** `Σ = {a, b, c}`
- **Conjunto de no terminales:** `V = {S, A, B, C, D, E}`
- **Símbolo inicial:** `S`

#### Producciones
```
S → λ | aA | cC | bC
A → λ | aD | cB | bE
B → aB | bB | cB
C → λ | bC | cC | aD
D → λ | aD | cC | bE
E → bC | cC | aD | bE
```

**Tipo:** Gramática Regular Tipo 3 (Lineal por la Derecha)

**Características:**
- Estados finales derivan en `λ` (S, A, C, D)
- Formato: `A → λ` o `A → xB`
- Equivalente al autómata original

---

### 4. Descripción del Lenguaje

#### El lenguaje **ACEPTA**:

✅ **Cadena vacía (ε)**
- El estado inicial `q0` es también final

✅ **Cadenas de solo 'b' y/o 'c'**
- Ejemplos: `b`, `c`, `bc`, `bbb`, `cc`, `cbc`
- Transita de `q0` a `q3` y permanece allí indefinidamente

✅ **Cadenas de solo 'a's**
- Ejemplos: `a`, `aa`, `aaa`, `aaaa`
- Transita de `q0 → q1 → q4` (ambos finales)

✅ **Patrones específicos con 'a' + 'b'/'c'**
- Ejemplos: `abc`, `abbb`, `aabc`
- Después de una o más `a`, continúa con patrones que llegan a estados finales

#### El lenguaje **NO ACEPTA**:

❌ **Cadenas con patrón "ac"**
- Ejemplos: `ac`, `aca`, `acb`, `acbb`
- Lleva al estado trampa `q2` (no final)

❌ **Cadenas "ab"**
- El patrón `a` seguido de `b` puede llevar a estados no finales

❌ **Cualquier cadena que termine en q2 o q5**
- Estos estados no son finales

#### Resumen Formal
```
L = {ε} ∪ {b,c}* ∪ {a}* ∪ {a+ seguido de patrones válidos con b,c}
```

**Restricción principal:** No se acepta el patrón `ac` cerca del inicio.

---

## 📊 Resultados

### Cadenas Aceptadas (5 ejemplos)

| # | Cadena | Ruta de Ejecución | Estado Final |
|---|--------|-------------------|--------------|
| 1 | ε      | q0                | q0 (final) ✅ |
| 2 | b      | q0 → q3           | q3 (final) ✅ |
| 3 | c      | q0 → q3           | q3 (final) ✅ |
| 4 | bc     | q0 → q3 → q3      | q3 (final) ✅ |
| 5 | aaa    | q0 → q1 → q4 → q4 | q4 (final) ✅ |

### Cadenas Rechazadas (5 ejemplos)

| # | Cadena | Ruta de Ejecución | Estado Final |
|---|--------|-------------------|--------------|
| 1 | ab     | q0 → q1 → q1      | Indefinido ❌ |
| 2 | ac     | q0 → q1 → q2      | q2 (no final) ❌ |
| 3 | aca    | q0 → q1 → q2 → q2 | q2 (no final) ❌ |
| 4 | acb    | q0 → q1 → q2 → q5 | q5 (no final) ❌ |
| 5 | acbb   | q0 → q1 → q2 → q5 | q5 (no final) ❌ |

---

## 📸 Capturas de Pantalla

### Construcción del Autómata
![Autómata en JFLAP](imagenes/automata_jflap.png)

### Pruebas Multiple Run
![Pruebas](imagenes/pruebas_multiple_run.png)

### Expresión Regular
![Expresión Regular](imagenes/expresion_regular.png)

### Gramática
![Gramática](imagenes/gramatica.png)

---

## 📚 Documentación

La documentación completa del laboratorio se encuentra en:

- **[PDF Completo](Autómatas%20finitos%20y%20lenguajes%20regulares%20con%20JFLAP%20+%20Alejandro%20De%20Mendoza.pdf)** - Documento académico con análisis detallado
- **[Metodología](docs/metodologia.md)** - Proceso paso a paso
- **[Resultados](docs/resultados.md)** - Análisis de resultados
- **[Bibliografía](docs/bibliografia.md)** - Referencias académicas

---

## 🛠️ Tecnologías Utilizadas

| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| ![JFLAP](https://img.shields.io/badge/JFLAP-7.1-blue) | 7.1 | Simulación de autómatas |
| ![Java](https://img.shields.io/badge/Java-SE-orange) | 8+ | Entorno de ejecución |
| ![Markdown](https://img.shields.io/badge/Markdown-Documentation-lightgrey) | - | Documentación |

---

## 👨‍💻 Autor

**Alejandro De Mendoza Tovar**
- 🎓 Ingeniería Informática
- 🏛️ Fundación Universitaria Internacional de La Rioja (UNIR)
- 📍 Bogotá D.C., Colombia
---

## 🙏 Agradecimientos

Agradecimiento especial al **Ing. Rogerio Orlando Beltrán Castro**, profesor de la asignatura, por su guía y enseñanzas en el desarrollo de este laboratorio.

También a la comunidad de desarrolladores de **JFLAP** por proporcionar una herramienta educativa de alta calidad para el estudio de autómatas y lenguajes formales.

---

## 📖 Referencias Bibliográficas

- Hopcroft, J. E., Motwani, R., & Ullman, J. D. (2006). *Introduction to Automata Theory, Languages, and Computation* (3.ª ed.). Pearson Education.

- Sipser, M. (2013). *Introduction to the Theory of Computation* (3.ª ed.). Cengage Learning.

- Linz, P. (2011). *An Introduction to Formal Languages and Automata* (5.ª ed.). Jones & Bartlett Learning.

- Rodger, S. H., & Finley, T. W. (2006). *JFLAP: An Interactive Formal Languages and Automata Package*. Jones & Bartlett Publishers.

- JFLAP Official Website: [https://www.jflap.org/](https://www.jflap.org/)

---

## 📄 Licencia

Este proyecto es de carácter **académico** y fue desarrollado con fines educativos para la asignatura de Fundamentos de la Computación.
```
Copyright © 2025 Alejandro De Mendoza Tovar
Uso exclusivo para fines académicos y educativos.
```

---

## 📞 Contacto

Si tienes preguntas, sugerencias o comentarios sobre este proyecto, no dudes en contactarme:

- 📧 Email: [tu-email@ejemplo.com]
- 💬 Issues: [Abrir un Issue](https://github.com/TuUsuario/Automatas-JFLAP-Lab1/issues)
- 🐛 Bugs: [Reportar Bug](https://github.com/TuUsuario/Automatas-JFLAP-Lab1/issues/new)

---

<div align="center">

### ⭐ Si este proyecto te fue útil, no olvides darle una estrella ⭐

**Desarrollado con 💙 por Alejandro De Mendoza**

**Fundación Universitaria Internacional de La Rioja - 2025**

</div>

---

## 🔄 Actualizaciones

### Versión 1.0.0 (Noviembre 2025)
- ✅ Construcción del autómata finito determinista
- ✅ Conversión a expresión regular
- ✅ Conversión a gramática formal
- ✅ Validación de cadenas
- ✅ Documentación completa

---

<div align="center">

[![Made with Love](https://img.shields.io/badge/Made%20with-❤️-red.svg)](https://github.com/TuUsuario)
[![UNIR](https://img.shields.io/badge/UNIR-Colombia-yellow.svg)](https://www.unir.net/)

</div>
