# __Gestores de arranque__

Un gestor de arranque es aquel software cuya función es ayudar al hardware y al firmware a cargar un sistema operativo, incluyendo la elección del mismo si hubieran varios.

### __Grub2__

Grub2 es el gestor de arranque de la mayoria de distribuciones de Linux ya que es un gestor de arranque famoso por su flexibilidad y compatibilidad.

Esta flexibilidad permite al usuario realizar configuraciones avanzadas como hacer un dual boot o restaurar sistemas si el kernel no carga correctamente entre otras cosas.

### __MBR y GPT__

* __MBR:__ es más antiguo, limitado a discos de hasta 2 TB y a un máximo de 4 particiones primarias.
* __GPT:__ es más moderno, soporta discos grandes, muchas particiones, mayor fiabilidad y está diseñado para trabajar con sistemas UEFI.