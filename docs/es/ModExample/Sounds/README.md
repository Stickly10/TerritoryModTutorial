# Nota

Esta carpeta contiene los archivos de sonido que utiliza el mod. El sistema carga automáticamente los sonidos que se encuentran aquí y el mod puede reproducirlos mediante la interfaz correspondiente.

# Tutorial

Coloca los archivos de sonido en formato `wav` o los archivos de música de fondo en formato `mp3` dentro de `ModExample\Sounds`.

Cuando el mod esté activado, puedes reproducir música de fondo mediante:

```csharp
SoundManager.Ins.PlayBgMusic(string bg_name, bool loop = true)
```

Puedes reproducir un efecto de sonido mediante:

```csharp
SoundManager.Ins.PlaySound(string sound_name, AudioSource audio_source = null, bool loop = false, float delay = 0)
```

Si un sonido del mod tiene el mismo nombre que un sonido original del juego, sustituirá automáticamente al sonido original.

La mayoría de los sonidos se configuran mediante su nombre en las tablas de datos de `Defs`; el juego los reproduce automáticamente cuando los necesita.

[Volver al índice en español](../../README.md) · [Ver el original en chino](../../../../ModExample/Sounds/README.md)
