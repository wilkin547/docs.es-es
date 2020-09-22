---
title: 'Procedimiento Utilizar la invocación de plataforma para reproducir un archivo de sonido: Guía de programación de C#'
description: En el ejemplo de código de C# se muestra cómo se usan los servicios de invocación de plataforma para reproducir un archivo de sonido WAV en el sistema operativo Windows.
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 6f507fa348bf1ea1b3fc5c3a868a6fbab7f8ec56
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558360"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a>Procedimiento Utilizar la invocación de plataforma para reproducir un archivo de sonido (Guía de programación de C#)

En el siguiente ejemplo de código de C# se muestra cómo se usan los servicios de invocación de plataforma para reproducir un archivo de sonido WAV en el sistema operativo Windows.

## <a name="example"></a>Ejemplo

En este código de ejemplo se usa <xref:System.Runtime.InteropServices.DllImportAttribute> para importar el punto de entrada del método `winmm.dll` de `PlaySound` como `Form1 PlaySound()`. El ejemplo tiene un formulario Windows Forms simple con un botón. Al hacer clic en el botón, se abre un cuadro de diálogo <xref:System.Windows.Forms.OpenFileDialog> estándar de Windows para que pueda abrir un archivo y reproducirlo. Cuando se selecciona un archivo de sonido, se reproduce mediante el método `PlaySound()` de la biblioteca *winmm.dll*. Para obtener más información sobre este método, vea [Using the PlaySound function with Waveform-Audio Files](/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files) (Uso de la función PlaySound con archivos para forma de onda de sonido). Busque y seleccione un archivo que tenga una extensión .wav y, después, haga clic en **Abrir** para reproducirlo mediante la invocación de plataforma. Un cuadro de texto muestra la ruta de acceso completa del archivo seleccionado.

El cuadro de diálogo **Abrir archivos** se puede filtrar con los siguientes valores para que muestre solo los archivos que tengan la extensión .wav:

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a>Compilación del código

1. Cree un proyecto de aplicación Windows Forms para C# en Visual Studio y asígnele el nombre **WinSound**.

2. Copie el código anterior y péguelo sobre el contenido del archivo *Form1.cs*.

3. Copie el código siguiente y péguelo en el archivo *Form1.Designer.cs*, en el método `InitializeComponent()`, después de cualquier código existente.

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. Compile y ejecute el código.

## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Información general sobre interoperabilidad](interoperability-overview.md)
- [Aproximación a la invocación de plataforma](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Serialización de datos con invocación de plataforma](../../../framework/interop/marshaling-data-with-platform-invoke.md)
