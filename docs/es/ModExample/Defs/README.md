# Nota

Esta carpeta contiene las definiciones de configuración. El juego lee estos datos automáticamente y sus valores modifican la configuración del juego.

# Tutorial

`excel_data` contiene las tablas de datos originales. La primera fila es la descripción; la segunda contiene los nombres de los campos y sus tipos de datos.

`json_data` contiene los datos que utiliza el juego durante la ejecución; se obtienen a partir de `excel_data`.

## ¿Cómo modifica un mod estos datos?

Copia un conjunto de datos de `json_data`, conserva una sola entrada y elimina las demás.

Modifica esa entrada y guárdala en la carpeta `Defs` del mod. Cuando el mod esté activado, podrá modificar los datos que el juego usa durante la ejecución.

Si modificas el `Id` de una entrada, se generará una entrada nueva.

## Ejemplos

Por ejemplo, puedes asignar un `id` nuevo en `stuff.json` para añadir un elemento nuevo al juego.

Puedes añadir una receta nueva mediante `blueprint.json`.

Puedes añadir un edificio mediante `build.json`. Sin embargo, para que el edificio funcione hay que escribir el código correspondiente.

# Cómo modificar los parámetros de configuración globales

Consulta el código `ModExample\Defs\Config\C.cs`.

Usa los nombres de las variables que aparecen allí para escribir el archivo de configuración. Por ejemplo, `npc_move_speed` tiene un valor predeterminado de `0.75`.

Escribe la siguiente información de configuración y guárdala en `ModExample\Defs\config.json`. Cuando el mod esté activado, la velocidad de movimiento básica de los residentes cambiará a `0.85`.

Puedes modificar varias entradas a la vez; sepáralas con comas dentro de la lista JSON.

```json
[
  {
    "key": "npc_move_speed",
    "value": "0.85",
    "name": "Velocidad de movimiento de los NPC",
    "remark": "Aumenta la velocidad"
  }
]
```

[Volver al índice en español](../../README.md) · [Ver el original en chino](../../../../ModExample/Defs/README.md)
