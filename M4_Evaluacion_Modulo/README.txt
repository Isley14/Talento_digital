Uso del sistema

Agregar libros

Opción 1: Agregar libro físico (título, autor, año)
Opción 2: Agregar libro digital (título, autor, año, formato)

Gestionar préstamos

Opción 7: Marcar un libro como prestado
Opción 8: Devolver un libro prestado

Consultar información

Opción 4: Ver todos los libros (disponibles y prestados)
Opción 5: Ver solo libros disponibles
Opción 6: Buscar un libro específico por título
Opción 9: Ver estadísticas generales

Mantenimiento

Opción 3: Eliminar un libro del sistema
Opción 10: Salir y guardar cambios

Persistencia de datos
Archivo biblioteca.txt

Se crea automáticamente al ejecutar el programa
Guarda toda la información de los libros
Se actualiza automáticamente al salir del programa
Formato interno: titulo|autor|año|estado|tipo|formato

Ejemplo de contenido del archivo:
El Quijote|Miguel de Cervantes|1605|disponible|libro
Cien años de soledad|Gabriel García Márquez|1967|prestado|libro
Python Programming|John Smith|2020|disponible|digital|PDF
Manejo de errores
El sistema maneja los siguientes errores:

✅ Intentar agregar un libro que ya existe
✅ Buscar/eliminar un libro inexistente
✅ Marcar como prestado un libro ya prestado
✅ Devolver un libro que no estaba prestado
✅ Errores de formato en los datos de entrada
✅ Problemas de acceso al archivo

Diagrama de clases
┌─────────────────────┐
│      Libro          │
├─────────────────────┤
│ - _titulo: str      │
│ - _autor: str       │
│ - _año: int         │
│ - _estado: str      │
├─────────────────────┤
│ + get/set_titulo()  │
│ + get/set_autor()   │
│ + get/set_año()     │
│ + get/set_estado()  │
│ + marcar_prestado() │
│ + devolver()        │
│ + __str__()         │
│ + to_file_format()  │
└─────────────────────┘
           △
           │ (herencia)
           │
┌─────────────────────┐
│   LibroDigital      │
├─────────────────────┤
│ - _formato: str     │
├─────────────────────┤
│ + get/set_formato() │
│ + __str__()         │ (polimorfismo)
│ + to_file_format()  │
└─────────────────────┘

┌─────────────────────┐
│    Biblioteca       │
├─────────────────────┤
│ - _libros: list     │
│ - _archivo: str     │
├─────────────────────┤
│ + cargar_libros()   │
│ + guardar_libros()  │
│ + agregar_libro()   │
│ + eliminar_libro()  │
│ + buscar_libro()    │
│ + marcar_prestado() │
│ + devolver_libro()  │
│ + listar_libros()   │
└─────────────────────┘
           │
           │ (composición)
           │
      [1..*] Libro

Ejemplos de uso

Agregar un libro digital:
Opción: 2
Título: Python para principiantes
Autor: Juan Pérez
Año: 2023
Formato: PDF
Buscar un libro:
Opción: 6
Título: Python para principiantes
Resultado: Título: Python para principiantes, Autor: Juan Pérez, Año: 2023, Estado: disponible, Formato: PDF
Ver estadísticas:
=== ESTADÍSTICAS DE LA BIBLIOTECA ===
Total de libros: 15
Libros disponibles: 12
Libros prestados: 3
Libros digitales: 8
Estructura de archivos del proyecto
proyecto_biblioteca/
│
├── gestor_biblioteca.py    # Código principal del sistema
├── biblioteca.txt          # Archivo de datos (se crea automáticamente)
├── README.md              # Este archivo de documentación
└── diagrama_clases.png    # Diagrama de clases (opcional)
Características técnicas

Lenguaje: Python 3.6+
Paradigma: Programación Orientada a Objetos
Persistencia: Archivos de texto plano
Codificación: UTF-8 para soporte de caracteres especiales
Manejo de errores: Try/except en operaciones críticas

Contacto y soporte
Para reportar errores o sugerir mejoras, puedes:

Revisar el código fuente en gestor_biblioteca.py
Verificar que el archivo biblioteca.txt tenga permisos de lectura/escritura
Asegurarte de tener Python 3.6 o superior instalado


📝 Notas de desarrollo
Este proyecto fue desarrollado como ejercicio académico para demostrar:

Conceptos fundamentales de POO
Manejo de archivos en Python
Diseño de interfaces de usuario en consola
Gestión de errores y excepciones
Persistencia de datos simple pero efectiva


