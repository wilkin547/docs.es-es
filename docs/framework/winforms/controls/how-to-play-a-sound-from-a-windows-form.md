---
title: Procedimiento para reproducir un sonido desde un formulario Windows Forms
description: Obtenga información acerca de cómo reproducir un sonido desde Windows Forms en una ruta de acceso determinada en tiempo de ejecución. Además, obtenga información sobre cómo compilar el código y el marco de seguridad de .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: beb17d994e224f41b2b590ecb1401988cdad314d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613753"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a>Procedimiento para reproducir un sonido desde un formulario Windows Forms
En este ejemplo se reproduce un sonido en una ruta de acceso determinada en tiempo de ejecución.

## <a name="example"></a>Ejemplo

```vb
Sub PlaySimpleSound()
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")
End Sub
```

```csharp
private void playSimpleSound()
{
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");
    simpleSound.Play();
}
```

## <a name="compiling-the-code"></a>Compilar el código
 Para este ejemplo se necesita:

- Que reemplace el nombre de archivo `"c:\Windows\Media\chimes.wav"` por un nombre de archivo válido.

- C# Referencia al espacio de <xref:System.Media?displayProperty=nameWithType> nombres.

## <a name="robust-programming"></a>Programación sólida
 Las operaciones de archivo se deberían agregar dentro de los bloques de control de excepciones estructurado adecuados.

 Las condiciones siguientes pueden provocar una excepción:

- El nombre de la ruta de acceso es incorrecto. Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (clase <xref:System.ArgumentException>).

- La ruta de acceso es de solo lectura (clase <xref:System.IO.IOException>).

- El nombre de la ruta de acceso es `null` (clase <xref:System.ArgumentNullException>).

- El nombre de la ruta de acceso es demasiado largo (clase <xref:System.IO.PathTooLongException>).

- La ruta de acceso no es válida (clase <xref:System.IO.DirectoryNotFoundException>).

- La ruta de acceso es solo un signo de dos puntos, ":" ( <xref:System.NotSupportedException> clase).

## <a name="net-framework-security"></a>Seguridad de .NET Framework
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo `Form1.vb` no sea un archivo de código fuente de Visual Basic. Compruebe todas las entradas antes de utilizar los datos en la aplicación.

## <a name="see-also"></a>Vea también

- <xref:System.Media.SoundPlayer>
- [Procedimiento para cargar un sonido de forma asincrónica en un formulario Windows Forms](how-to-load-a-sound-asynchronously-within-a-windows-form.md)
