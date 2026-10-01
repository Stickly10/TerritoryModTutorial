# Nota

Esta carpeta contiene las imágenes que utiliza el mod. El sistema carga automáticamente las imágenes que se encuentran aquí y el mod puede utilizarlas mediante una interfaz común. El documento original señala que esta función está en desarrollo.

# Tutorial

Las imágenes que el juego utiliza actualmente se guardan en la carpeta `ModExample\Textures\Images being used in the game`.

Para modificar una imagen, guárdala en la carpeta `Textures` del mod y configura después sus datos en `textures.xml`.

La estructura de los datos es la siguiente:

```xml
<Image
  file="kingdom_treasure_box_0.png"
  action="replace"
  anchor="0,0"
  />
```

`file` es el nombre del archivo de imagen.

`action` indica la acción: usa `replace` para sustituir una imagen original del juego y `add` para añadir una imagen nueva.

`anchor` es el punto de anclaje para alinear la imagen. Por lo general, el anclaje de las imágenes de edificios es `"0,0"` y el de las demás imágenes es `"0.5,0.5"`. Si la imagen queda desalineada, puedes probar a modificar este valor.

En la mayoría de las imágenes basta con configurar el nombre en la tabla de datos correspondiente dentro de `ModExample\Defs` para que surtan efecto.

Si necesitas llamar a una imagen o modificarla desde el código, los métodos habituales son:

Para un elemento `Image` de la interfaz, representado por la variable `img`:

```csharp
img.sprite = SpriteManager.Get(sprite_name);
```

O para un elemento `MySpriteRenderer` de la escena, representado por `sp_body`:

```csharp
sp_body.sprite_id = SpriteManager.Ins.TryGetSpriteId(sprite_name);
```

[Volver al índice en español](../../README.md) · [Ver el original en chino](../../../../ModExample/Textures/README.md)
