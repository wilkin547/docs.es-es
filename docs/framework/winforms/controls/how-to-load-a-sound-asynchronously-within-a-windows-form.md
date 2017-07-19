---
title: "C&#243;mo: Cargar un sonido de forma asincr&#243;nica en Windows Forms | Microsoft Docs"
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
  - "SoundPlayer (clase), cargar sonidos de forma asincrónica"
  - "sonidos, cargar en subprocesos separados"
  - "subprocesamiento [Windows Forms], suena"
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Cargar un sonido de forma asincr&#243;nica en Windows Forms
En el ejemplo de código siguiente, se carga un sonido de forma asincrónica desde una dirección URL y, a continuación, se reproduce en un nuevo subproceso.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
-   Que reemplace el nombre de archivo `"http://www.tailspintoys.com/sounds/stop.wav"` por un nombre de archivo válido.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Command-Line Building With csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: compilar y ejecutar un completo Windows Forms código de ejemplo en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="robust-programming"></a>Programación sólida  
 Las operaciones de archivo se deberían agregar dentro de los bloques de control de excepciones adecuados.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la ruta de acceso es incorrecto. Por ejemplo, contiene caracteres que no son válidos o es de sólo espacios en blanco (<xref:System.ArgumentException> clase).  
  
-   La ruta de acceso es de sólo lectura (<xref:System.IO.IOException> clase).  
  
-   El nombre de ruta de acceso es `Nothing` (<xref:System.ArgumentNullException> clase).  
  
-   El nombre de ruta de acceso es demasiado largo (<xref:System.IO.PathTooLongException> clase).  
  
-   La ruta de acceso no es válido (<xref:System.IO.DirectoryNotFoundException> clase).  
  
-   La ruta de acceso es sólo dos puntos ":" (<xref:System.NotSupportedException> clase).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo `Form1.vb` no sea un archivo de código fuente de Visual Basic. Compruebe todas las entradas antes de utilizar los datos en la aplicación.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>   
 <xref:System.Media.SoundPlayer.LoadCompleted>   
 <xref:System.Media.SoundPlayer.Play%2A>   
 [Cómo: reproducir un sonido desde un formulario Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)