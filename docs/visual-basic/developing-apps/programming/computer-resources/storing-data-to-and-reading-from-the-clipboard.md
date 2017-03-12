---
title: "Almacenar y leer datos en el Portapapeles (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Portapapeles"
  - "Portapapeles, leer de (My.Computer.Clipboard)"
  - "Portapapeles, almacenar datos en (My.Computer.Clipboard)"
  - "datos [Visual Basic], Portapapeles"
  - "My.Computer.Clipboard (objeto), tareas"
  - "leer datos, del Portapapeles"
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Almacenar y leer datos en el Portapapeles (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El Portapapeles se puede utilizar para almacenar datos, como texto e imágenes.  Dado que todos los procesos activos comparten el Portapapeles, se puede utilizar para transferir datos entre ellos.  El objeto de `My.Computer.Clipboard` permite tener acceso fácilmente al portapapeles y que lo lea de y que escribir.  
  
## Leer el portapapeles  
 Utilice el método de <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> para leer el texto del portapapeles.  El siguiente código lee el texto y lo muestra en un cuadro de mensaje.  Debe haber texto almacenado en el Portapapeles para que el ejemplo se ejecute correctamente.  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_1.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms\> Portapapeles**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
 Utilice el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> para recuperar una imagen del Portapapeles.  Este ejemplo comprueba si existe una imagen en el Portapapeles antes de recuperarla y asignarla a  `PictureBox1`.  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_2.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms\> Portapapeles**.Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
 Los elementos incluidos en el Portapapeles se conservarán incluso después de salir de la aplicación.  
  
## Determinar el tipo de archivo almacenado en el portapapeles  
 Los datos del Portapapeles pueden tener formas diferentes, puede tratarse, por ejemplo, de un texto, un archivo de sonido o una imagen.  Para determinar qué tipo de archivo se encuentra en el Portapapeles, puede utilizar distintos métodos, como <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> y <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.  Puede utilizar el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> si tiene un formato personalizado que desea comprobar.  
  
 Utilice la función `ContainsImage` para determinar si los datos contenidos en el Portapapeles son una imagen.  El código siguiente comprueba si los datos son una imagen y crea un informe en consecuencia.  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_3.vb)]  
  
## borrar el portapapeles  
 El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> borra el Portapapeles.  Otros procesos comparten el Portapapeles, por lo que borrarlo puede tener un impacto en ellos.  
  
 En el código siguiente se muestra cómo puede utilizar el método `Clear`.  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_4.vb)]  
  
## Escribir en el portapapeles  
 Utilice el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> para escribir texto en el Portapapeles.  El código siguiente escribe la cadena "This is a test string" en el Portapapeles.  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_5.vb)]  
  
 El método de `SetText` puede aceptar un parámetro de formato que contenga un tipo de <xref:System.Windows.Forms.TextDataFormat>.  El código siguiente escribe la cadena "This is a test string" en el Portapapeles como texto RTF.  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_6.vb)]  
  
 Utilice el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> para escribir datos en el Portapapeles.  En este ejemplo se escribe `DataObject` `dataChunk` en el Portapapeles en el formato `specialFormat` personalizado.  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_7.vb)]  
  
 Utilice el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> para escribir datos de sonido en el Portapapeles.  En este ejemplo se crea la matriz de bytes `musicReader`, se lee en ella el archivo `cool.wav` y, a continuación, se escribe en el Portapapeles.  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_8.vb)]  
  
> [!IMPORTANT]
>  Como otros usuarios pueden tener acceso al Portapapeles, no se debe utilizar para almacenar información confidencial, como contraseñas o datos reservados.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>   
 [Cómo: Leer objetos de datos de un archivo XML](../Topic/How%20to:%20Read%20Object%20Data%20from%20an%20XML%20File%20\(C%23%20and%20Visual%20Basic\).md)   
 [Cómo: Escribir objetos de datos en un archivo XML](../Topic/How%20to:%20Write%20Object%20Data%20to%20an%20XML%20File%20\(C%23%20and%20Visual%20Basic\).md)