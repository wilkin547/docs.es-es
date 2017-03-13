---
title: "C&#243;mo: Utilizar la invocaci&#243;n de plataforma para reproducir un archivo de sonido (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ".wav (archivos)"
  - "interoperabilidad [C#], reproducir archivos WAV mediante pinvoke"
  - "invocación de plataforma, archivos de sonido"
  - "wav (archivos)"
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# C&#243;mo: Utilizar la invocaci&#243;n de plataforma para reproducir un archivo de sonido (Gu&#237;a de programaci&#243;n de C#)
En el siguiente ejemplo de código de C\# se muestra cómo se utilizan los servicios de invocación de plataforma para reproducir un archivo de sonido en el sistema operativo Windows.  
  
## Ejemplo  
 En este código de ejemplo se utiliza `DllImport` para importar el punto de entrada del método `PlaySound` de `winmm.dll` como `Form1 PlaySound()`.  El ejemplo tiene un Windows Form simple con un botón.  Al hacer clic en el botón, se abre un cuadro de diálogo <xref:System.Windows.Forms.OpenFileDialog> estándar de Windows para que pueda abrir un archivo y reproducirlo.  Cuando se selecciona un archivo de sonido, éste se reproduce mediante el método `PlaySound()` del ensamblado winmm.DLL.  Para obtener más información sobre el método `PlaySound` de winmm.dll, vea [Using the PlaySound function with Waveform\-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553).  Busque y seleccione un archivo que tenga una extensión .wav y, a continuación, haga clic en **Abrir** para reproducirlo mediante la invocación de plataforma.  Un cuadro de texto muestra la ruta de acceso completa del archivo seleccionado.  
  
 El cuadro de diálogo **Abrir archivos** se puede filtrar con los siguientes valores para que muestre sólo los archivos que tengan la extensión .wav:  
  
 [!code-cs[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-cs[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## Compilar el código  
  
### Para compilar el código  
  
1.  Cree un nuevo proyecto de aplicación para Windows C\# en Visual Studio y asígnele el nombre WinSound.  
  
2.  Copie el código anterior y péguelo sobre el contenido del archivo `Form1.cs`.  
  
3.  Copie el código siguiente y péguelo en el archivo `Form1.Designer.cs`, en el método `InitializeComponent()`, después de cualquier código existente.  
  
     [!code-cs[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Compile y ejecute el código.  
  
## Seguridad de .NET Framework  
 Para obtener más información, vea [Seguridad de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Información general sobre interoperabilidad](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [Información general sobre interoperabilidad](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [A Closer Look at Platform Invoke](http://msdn.microsoft.com/es-es/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [Marshaling Data with Platform Invoke](../Topic/Marshaling%20Data%20with%20Platform%20Invoke.md)