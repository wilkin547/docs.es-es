---
title: "C&#243;mo: Repetir la reproducci&#243;n de un sonido en Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "reproducir sonidos, en bucle"
  - "bucles de sonido"
  - "SoundPlayer (clase), reproducir en bucle"
  - "sonidos, en bucle"
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Repetir la reproducci&#243;n de un sonido en Windows Forms
En el ejemplo de código siguiente, se reproduce repetidamente un sonido.  Cuando se ejecuta el código en el controlador de eventos `stopPlayingButton_Click`, todos los sonidos que se estén reproduciendo se detienen.  Si no se está reproduciendo ningún sonido, no ocurre nada.  
  
## Ejemplo  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
-   Que reemplace el nombre de archivo `"c:\Windows\Media\chimes.wav"` por un nombre de archivo válido.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Programación eficaz  
 Las operaciones de archivo se deberían agregar dentro de los bloques de control de excepciones adecuados.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la ruta de acceso es incorrecto.  Por ejemplo, contiene caracteres que no son válidos o es solo espacios en blanco \(clase <xref:System.ArgumentException>\).  
  
-   La ruta de acceso es de solo lectura \(clase <xref:System.IO.IOException>\).  
  
-   El nombre de la ruta de acceso es `Nothing` \(clase <xref:System.ArgumentNullException>\).  
  
-   El nombre de la ruta de acceso es demasiado largo \(clase <xref:System.IO.PathTooLongException>\).  
  
-   La ruta de acceso no es válida \(clase <xref:System.IO.DirectoryNotFoundException>\).  
  
-   La ruta de acceso es solo dos puntos ":" \(clase <xref:System.NotSupportedException>\).  
  
## Seguridad de .NET Framework  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.  Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.  Compruebe todas las entradas antes de utilizar los datos en la aplicación.  
  
## Vea también  
 <xref:System.Media.SoundPlayer.PlayLooping%2A>   
 [Cómo: Reproducir un sonido desde Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)   
 [Información general sobre la clase SoundPlayer](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)