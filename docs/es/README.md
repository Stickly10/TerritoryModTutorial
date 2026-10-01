# Tutorial de creación de mods de Territory

Español | [中文（原文）](../../README.md)

Traducción al español del tutorial de creación de mods de **Territory: Farming and Warfare**. Las guías originales en chino se conservan sin cambios. Las notas adicionales de comprobación se identifican como tales.

## Aviso sobre los recursos del juego

Todos los elementos del juego incluidos en este repositorio pertenecen al autor del juego. Solo pueden utilizarse para crear mods; no se permite destinarlos a otros usos.

## Funciones disponibles

- **Código:** añadir DLL en `Assemblies` para modificar funciones del juego. [Guía](ModExample/Assemblies/README.md).
- **Planos de construcción:** guardar planos de distribución en `ModXXX/BuildBlueprint` para compartirlos mediante un mod. [Guía](ModExample/BuildBlueprint/README.md).
- **Mapas:** guardar mapas personalizados en `ModXXX/Map`. [Guía](ModExample/Map/README.md).
- **Datos:** guardar archivos de configuración en `ModXXX/Defs` para modificar los datos del juego. [Guía](ModExample/Defs/README.md).
- **Imágenes:** guardar imágenes en `ModXXX/Textures` para sustituir las existentes o añadir otras. [Guía](ModExample/Textures/README.md).
- **Sonido:** guardar archivos en `ModXXX/Sounds` para modificar o añadir efectos de sonido y música. [Guía](ModExample/Sounds/README.md).
- **Traducción:** guardar textos de localización en `ModXXX/Languages` para mejorar las traducciones. [Guía](ModExample/Languages/README.md).

## Cómo utilizar el ejemplo

`ModExample` es un mod de ejemplo. Cada carpeta contiene una breve explicación de su función. Consulta también la [estructura del ejemplo](ModExample/README.md) y la [carpeta About](ModExample/About/README.md).

## Crear un mod

### 0. Preparar el juego

Suscríbete al menos a un mod para activar la instalación del sistema de mods y reinicia el juego. Los mods necesitan ese sistema para funcionar.

### 1. Copiar el ejemplo

Copia la carpeta `ModExample` y cambia su nombre por el que tendrá tu mod. Utiliza letras del alfabeto inglés y guiones bajos en el nombre de la carpeta.

### 2. Editar los metadatos

Edita `ModExample/About/About.xml`:

| Campo | Contenido |
| --- | --- |
| `name` | Nombre del mod. |
| `authors` | Autor o autores. Puedes indicar varios si el mod es un trabajo conjunto. |
| `description` | Descripción breve. La descripción extensa puede escribirse en la página del mod en Steam. |
| `url` | Enlace con información del mod, como su repositorio de código o una página explicativa. |
| `packageId` | Identificador del paquete, normalmente con la estructura `Author.ModName`. |
| `supportedVersions` | El valor predeterminado es `1.0`. |
| `modVersion` | Número de versión del mod. Consulta la nota sobre su formato al final de esta guía. |

### 3. Preparar la imagen de vista previa

Sustituye `ModExample/About/Preview.png` por la imagen de tu mod. El tutorial indica un tamaño de **637 × 658 píxeles** y formato **PNG**.

### 4. Añadir el código, si hace falta

Coloca las DLL en `ModExample/Assemblies`. No todos los mods necesitan código: modificar configuraciones, imágenes o añadir contenido mediante los datos del juego puede hacerse sin generar una DLL.

### 5. Incluir los recursos utilizados

Las demás carpetas contienen imágenes, sonidos, configuraciones y otros recursos. Elimina del mod las carpetas que no utilices.

### 6. Conservar el identificador de Workshop

Al subir un mod nuevo se genera `ModExample/About/PublishedFileId.txt`, que contiene su identificador único en Steam.

**No modifiques ni elimines este archivo al actualizar el mismo mod.** Steam utiliza ese identificador para actualizar el elemento existente y distribuir la actualización a sus suscriptores. Si el archivo no existe, la subida se tratará como un mod nuevo.

### 7. Probar el mod durante el desarrollo

Para probar un solo mod, copia **el contenido de su carpeta**, sin incluir la carpeta contenedora, a:

```text
C:/TerritoryModTest
```

El juego lo cargará automáticamente al iniciarse.

Para probar varios mods, copia **las carpetas de los mods**, esta vez incluyendo cada carpeta contenedora, a:

```text
C:/TerritoryModTestBatch
```

El juego cargará los mods de esa ubicación al iniciarse. El sistema no comprueba si hay mods duplicados: evita cargar dos copias del mismo mod durante las pruebas.

## Nota adicional: error de formato de `modVersion` al subir un mod

Esta comprobación se añadió a la traducción tras reproducir el error en el juego **1.0.20260916.20**. El panel de subida exige **dos grupos numéricos separados por un punto**:

```xml
<modVersion>1.62</modVersion>
```

- Válidos: `1.0`, `1.4`, `1.62`.
- No válido: `1.6.2`, porque contiene tres grupos numéricos.

Con un valor no válido, el panel muestra: «modVersion debe tener formato x.y, por ejemplo 1.0».

Corrige el campo en `About/About.xml` de la carpeta que estás subiendo y vuelve a intentarlo. Las notas de actualización pueden seguir indicando una edición como `1.6.2`; el campo `modVersion` debe cumplir el formato que acepta el cargador. `1.62` es un ejemplo de identificador válido, no una conversión automática del juego.

Cuando el panel solicite la ruta, selecciona la **carpeta raíz del mod**, que contiene `About`, `Defs`, `Languages` y las demás carpetas que utilice. Si el paquete completo está preparado en `C:/TerritoryModTest`, esa es la ruta que debes seleccionar. Conserva `About/PublishedFileId.txt` para actualizar el elemento existente.
