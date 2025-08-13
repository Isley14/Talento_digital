Uso del sistema
Agregar libros

Opci�n 1: Agregar libro f�sico (t�tulo, autor, a�o)
Opci�n 2: Agregar libro digital (t�tulo, autor, a�o, formato)

Gestionar pr�stamos

Opci�n 7: Marcar un libro como prestado
Opci�n 8: Devolver un libro prestado

Consultar informaci�n

Opci�n 4: Ver todos los libros (disponibles y prestados)
Opci�n 5: Ver solo libros disponibles
Opci�n 6: Buscar un libro espec�fico por t�tulo
Opci�n 9: Ver estad�sticas generales

Mantenimiento

Opci�n 3: Eliminar un libro del sistema
Opci�n 10: Salir y guardar cambios

Persistencia de datos
Archivo biblioteca.txt

Se crea autom�ticamente al ejecutar el programa
Guarda toda la informaci�n de los libros
Se actualiza autom�ticamente al salir del programa
Formato interno: titulo|autor|a�o|estado|tipo|formato

Ejemplo de contenido del archivo:
El Quijote|Miguel de Cervantes|1605|disponible|libro
Cien a�os de soledad|Gabriel Garc�a M�rquez|1967|prestado|libro
Python Programming|John Smith|2020|disponible|digital|PDF
Manejo de errores
El sistema maneja los siguientes errores:

? Intentar agregar un libro que ya existe
? Buscar/eliminar un libro inexistente
? Marcar como prestado un libro ya prestado
? Devolver un libro que no estaba prestado
? Errores de formato en los datos de entrada
? Problemas de acceso al archivo

Diagrama de clases
???????????????????????
?      Libro          ?
???????????????????????
? - _titulo: str      ?
? - _autor: str       ?
? - _a�o: int         ?
? - _estado: str      ?
???????????????????????
? + get/set_titulo()  ?
? + get/set_autor()   ?
? + get/set_a�o()     ?
? + get/set_estado()  ?
? + marcar_prestado() ?
? + devolver()        ?
? + __str__()         ?
? + to_file_format()  ?
???????????????????????
           ?
           ? (herencia)
           ?
???????????????????????
?   LibroDigital      ?
???????????????????????
? - _formato: str     ?
???????????????????????
? + get/set_formato() ?
? + __str__()         ? (polimorfismo)
? + to_file_format()  ?
???????????????????????

???????????????????????
?    Biblioteca       ?
???????????????????????
? - _libros: list     ?
? - _archivo: str     ?
???????????????????????
? + cargar_libros()   ?
? + guardar_libros()  ?
? + agregar_libro()   ?
? + eliminar_libro()  ?
? + buscar_libro()    ?
? + marcar_prestado() ?
? + devolver_libro()  ?
? + listar_libros()   ?
???????????????????????
           ?
           ? (composici�n)
           ?
      [1..*] Libro
Ejemplos de uso
Agregar un libro digital:
Opci�n: 2
T�tulo: Python para principiantes
Autor: Juan P�rez
A�o: 2023
Formato: PDF
Buscar un libro:
Opci�n: 6
T�tulo: Python para principiantes
Resultado: T�tulo: Python para principiantes, Autor: Juan P�rez, A�o: 2023, Estado: disponible, Formato: PDF
Ver estad�sticas:
=== ESTAD�STICAS DE LA BIBLIOTECA ===
Total de libros: 15
Libros disponibles: 12
Libros prestados: 3
Libros digitales: 8
Estructura de archivos del proyecto
proyecto_biblioteca/
?
??? gestor_biblioteca.py    # C�digo principal del sistema
??? biblioteca.txt          # Archivo de datos (se crea autom�ticamente)
??? README.md              # Este archivo de documentaci�n
??? diagrama_clases.png    # Diagrama de clases (opcional)
Caracter�sticas t�cnicas

Lenguaje: Python 3.6+
Paradigma: Programaci�n Orientada a Objetos
Persistencia: Archivos de texto plano
Codificaci�n: UTF-8 para soporte de caracteres especiales
Manejo de errores: Try/except en operaciones cr�ticas

Contacto y soporte
Para reportar errores o sugerir mejoras, puedes:

Revisar el c�digo fuente en gestor_biblioteca.py
Verificar que el archivo biblioteca.txt tenga permisos de lectura/escritura
Asegurarte de tener Python 3.6 o superior instalado


?? Notas de desarrollo
Este proyecto fue desarrollado como ejercicio acad�mico para demostrar:

Conceptos fundamentales de POO
Manejo de archivos en Python
Dise�o de interfaces de usuario en consola
Gesti�n de errores y excepciones
Persistencia de datos simple pero efectiva