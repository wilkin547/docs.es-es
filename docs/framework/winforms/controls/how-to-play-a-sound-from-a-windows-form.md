---
title: "C&#243;mo: Reproducir un sonido desde Windows Forms | Microsoft Docs"
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
  - "reproducir sonidos, formularios Windows Forms"
  - "sonidos, reproducción"
  - "SoundPlayer (clase)"
  - "sonidos"
  - "My.Computer.Audio (objeto), reproducir sonidos"
  - "ejemplos [Windows Forms], sonidos"
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Reproducir un sonido desde Windows Forms
En este ejemplo se reproduce un sonido en una ruta determinada en tiempo de ejecución.  
  
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
  
-   Que reemplace el nombre de archivo `"c:\Windows\Media\chimes.wav"` por un nombre de archivo válido.  
  
-   (C#) Una referencia a la <xref:System.Media?displayProperty=fullName> espacio de nombres.  
  
## <a name="robust-programming"></a>Programación sólida  
 Operaciones de archivo se deberían agregar dentro de bloques de control de excepciones estructurado adecuado.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la ruta de acceso es incorrecto. Por ejemplo, contiene caracteres no válidos o es de sólo espacios en blanco (<xref:System.ArgumentException> clase).  
  
-   La ruta de acceso es de sólo lectura (<xref:System.IO.IOException> clase).  
  
-   El nombre de ruta de acceso es `null` (<xref:System.ArgumentNullException> clase).  
  
-   El nombre de ruta de acceso es demasiado largo (<xref:System.IO.PathTooLongException> clase).  
  
-   La ruta de acceso no es válido (<xref:System.IO.DirectoryNotFoundException> clase).  
  
-   La ruta de acceso es sólo un signo de dos puntos ":" (<xref:System.NotSupportedException> clase).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo `Form1.vb` no sea un archivo de código fuente de Visual Basic. Compruebe todas las entradas antes de utilizar los datos en la aplicación.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Media.SoundPlayer>   
 [Cómo: cargar un sonido de forma asincrónica en un formulario Windows Forms](../../../../docs/framework/winforms/controls/how-to-load-a-sound-asynchronously-within-a-windows-form.md)   
 