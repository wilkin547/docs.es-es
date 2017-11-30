---
title: "Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d037e17ef48ebfdd5cfd860efbacf195e7b6a76d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a>Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido (Guía de programación de C#)
En el siguiente ejemplo de código de C# se muestra cómo se usan los servicios de invocación de plataforma para reproducir un archivo de sonido en el sistema operativo Windows.  
  
## <a name="example"></a>Ejemplo  
 En este código de ejemplo se usa `DllImport` para importar el punto de entrada del método `winmm.dll` de `PlaySound` como `Form1 PlaySound()`. El ejemplo tiene un formulario Windows Forms simple con un botón. Al hacer clic en el botón, se abre un cuadro de diálogo <xref:System.Windows.Forms.OpenFileDialog> estándar de Windows para que pueda abrir un archivo y reproducirlo. Cuando se selecciona un archivo de sonido, este se reproduce mediante el método `PlaySound()` del método de ensamblado winmm.DLL. Para obtener más información sobre el método `PlaySound` de winmm.dll, vea [Using the PlaySound function with Waveform-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553) (Usar la función PlaySound con archivos para forma de onda de sonido). Busque y seleccione un archivo que tenga una extensión .wav y, después, haga clic en **Abrir** para reproducirlo mediante la invocación de plataforma. Un cuadro de texto muestra la ruta de acceso completa del archivo seleccionado.  
  
 El cuadro de diálogo **Abrir archivos** se puede filtrar con los siguientes valores para que muestre solo los archivos que tengan la extensión .wav:  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
### <a name="to-compile-the-code"></a>Para compilar el código  
  
1.  Cree un nuevo proyecto de aplicación para Windows C# en Visual Studio y asígnele el nombre **WinSound**.  
  
2.  Copie el código anterior y péguelo sobre el contenido del archivo `Form1.cs`.  
  
3.  Copie el código siguiente y péguelo en el archivo `Form1.Designer.cs`, en el método `InitializeComponent()`, después de cualquier código existente.  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Compile y ejecute el código.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para obtener más información, vea [Seguridad de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Información general sobre interoperabilidad](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [Información general sobre interoperabilidad](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [Invocación de un vistazo más cerca de la plataforma](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [Serialización de datos con invocación de plataforma](../../../framework/interop/marshaling-data-with-platform-invoke.md)
