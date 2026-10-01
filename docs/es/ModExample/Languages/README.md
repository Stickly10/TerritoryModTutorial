# Traducciones: Languages

[Índice del tutorial en español](../../README.md) | [Original en chino](../../../../ModExample/Languages/README.md)

Esta carpeta contiene textos de localización para sustituir o complementar las traducciones del juego. El documento original señala que esta función está en desarrollo.

## Mejorar una traducción existente

El ejemplo original utiliza el francés. Supongamos que juegas en ese idioma y quieres corregir una traducción mediante un mod.

1. Busca el archivo de referencia:

   ```text
   ModExample\Languages\Text being used in the game\localization_mod\localization_str_English.txt
   ```

2. Localiza el texto correspondiente. Por ejemplo:

   ```text
   <@ID=window_txt-1-txt_@>
   The translation of this game is provided or improved by enthusiasts. Thank you all.
   Russian: <color=#4CB34C>Zerlin</color>, <color=#4CB34C>Tristis Oris</color>
   ```

3. Traduce el texto y guarda la entrada en un archivo llamado `localization_str_French.txt`, dentro de la carpeta `Languages` de tu mod. Conserva el identificador de la entrada.

4. Para añadir o modificar apellidos y nombres de personajes, utiliza estos archivos dentro de `Languages`:

   ```text
   character_name/family_name_French.txt
   character_name/male_name_French.txt
   character_name/female_name_French.txt
   ```

**Importante:**

- `<@ID=window_txt-1-txt_@>` es el identificador del texto y no debe modificarse.
- `<color=#4CB34C>` y `</color>` son etiquetas de color; cada etiqueta de apertura debe tener su correspondiente cierre.

## Añadir un idioma

El tutorial original utiliza el vietnamita como ejemplo. Sus identificadores y valores se reproducen a continuación para conservar el ejemplo original.

### 1. Definir el idioma

Crea `language.json` en la carpeta `Defs` del mod con este contenido:

```json
[
    {
        "language_id": 12,
        "language_name_cn": "越南语",
        "enable": 1,
        "language_name": "Tiếng Việt",
        "language_name_en": "Vietnamese",
        "language_code": "vi",
        "unity_language_code": "Vietnamese",
        "steam_language_code": "vietnamese",
        "is_surname_come_first": true
    }
]
```

### 2. Traducir los textos

Copia `localization_str_English.txt` a la carpeta `Languages` del mod, cambia su nombre a `localization_str_Vietnamese.txt` y traduce su contenido.

### 3. Preparar los nombres de personajes

Copia los archivos `family_name_English.txt`, `male_name_English.txt` y `female_name_English.txt` de `ModExample/Languages/Text being used in the game/localization_mod/character_name/` a `Languages/character_name/` de tu mod.

Cambia sus nombres a:

```text
family_name_Vietnamese.txt
male_name_Vietnamese.txt
female_name_Vietnamese.txt
```

Borra el contenido de las copias y añade, respectivamente, apellidos, nombres masculinos y nombres femeninos del idioma nuevo.

> **Nota adicional sobre la ruta:** el original abrevia la carpeta de origen como `Language/character_name`. Aquí se indica la ruta completa comprobada en el repositorio. La carpeta de destino del mod es `Languages/character_name/`.

> **Nota de actualización:** el juego 1.0.20260916.20 ya incluye vietnamita. Para mejorar un idioma existente, utiliza la primera sección de esta guía; el ejemplo de alta de idiomas se conserva como referencia del tutorial original.
