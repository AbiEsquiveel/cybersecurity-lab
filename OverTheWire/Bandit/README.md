# 🚩 OverTheWire: Bandit (Write-up Niveles 0 a 6)

Anotaciones personales, comandos utilizados y conceptos aprendidos durante la resolución de los primeros niveles de **Bandit**.

---

## 🟢 NIVEL 0
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
Aceptamos la conexión (yes) e ingresamos la contraseña por defecto bandit0

---
## NIVEL 1
ls
cat readme
Concepto: Lectura de archivos básicos de texto.

Contraseña hallada: 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR

---

## NIVEL 2
ls
cat ./-
Concepto: Rutas relativas y uso de símbolos especiales:

. (un punto): Representa el directorio actual en el que estoy parada.

.. (dos puntos): Representa el directorio padre (la carpeta de arriba).

/ (barra): Es el separador de carpetas.

Explicación: Si escribimos cat ./- le decimos al sistema: "Buscá un archivo llamado - dentro del directorio actual (./)", evitando que cat confunda el guion con un parámetro.

Contraseña hallada: PK8fYLZg2hnHSz83plBL1iEPKdD3QToB

---

## NIVEL 3
ssh bandit2@bandit.labs.overthewire.org -p 2220
ls
cat "./--spaces in this filename--"
Concepto: Nombres con espacios.

Explicación: Cuando tenemos un archivo cuyo nombre tiene espacios, debemos usar cat + comillas + ./ + nombre del archivo.

Contraseña hallada: 7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME

---

## NIVEL 4
ssh bandit3@bandit.labs.overthewire.org -p 2220
cd inhere
ls -a
cat "./...Hiding-From-You"
Concepto: Archivos ocultos.

Explicación: En ls -a, la -a significa all/todos, utilizado para mostrar archivos ocultos que empiezan con punto.

Contraseña hallada: xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq

---

## NIVEL 5
ssh bandit4@bandit.labs.overthewire.org -p 2220
cd inhere
ls
cat "./-file07"
Concepto: Inspección de múltiples archivos y limpieza de consola.

Tip: Si la pantalla se pone rara por leer archivos binarios, usamos el comando reset.

Contraseña hallada: 6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrg

---

## NIVEL 6
ssh bandit5@bandit.labs.overthewire.org -p 2220
cd inhere
find . -type f -size 1033c ! -executable
Concepto: Búsqueda avanzada con find:

. busca a partir del directorio actual.

-type f filtra solo archivos (descarta directorios/carpetas).

-size 1033c busca un tamaño exacto de 1033 bytes (la c significa bytes).

! -executable el signo ! invoca la negación (archivos no ejecutables).

Resultado encontrado: ./maybehere07/.file2

cat "./maybehere07/.file2"
Contraseña hallada: DXjZPULLO31P33PF2YGr23A4BE31j143
