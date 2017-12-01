---
title: Almacenar y leer datos en el Portapapeles (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7bb4ad56f0a039aa7b23d7f0612aaab9366cb9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a>Almacenar y leer datos en el Portapapeles (Visual Basic)
El Portapapeles se puede usar para almacenar datos, como texto e imágenes. Dado que todos los procesos activos comparten el Portapapeles, se puede usar para transferir datos entre ellos. El objeto `My.Computer.Clipboard` permite acceder fácilmente al Portapapeles y leer y escribir en él.  
  
## <a name="reading-from-the-clipboard"></a>Leer desde el Portapapeles  
 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> para leer el texto en el Portapapeles. El código siguiente lee el texto y lo muestra en un cuadro de mensaje. Para que el ejemplo se ejecute correctamente debe haber texto almacenado en el Portapapeles.  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> para recuperar una imagen del Portapapeles. En este ejemplo se comprueba si hay una imagen en el Portapapeles antes de recuperarla y asignarla a `PictureBox1`.  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**. Para más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
 Los elementos colocados en el Portapapeles se conservan incluso después de que se cierre la aplicación.  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a>Determinar el tipo de archivo almacenado en el Portapapeles  
 Los datos del Portapapeles pueden adoptar varios formatos distintos, como texto, un archivo de audio o una imagen. Para determinar qué tipo de archivo está en el Portapapeles, puede usar métodos como <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> y <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>. El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> puede usarse si tiene un formato personalizado que desea comprobar.  
  
 Use la función `ContainsImage` para determinar si los datos incluidos en el Portapapeles son una imagen. El código siguiente comprueba si los datos son una imagen e informa en consecuencia.  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]  
  
## <a name="clearing-the-clipboard"></a>Borrar el Portapapeles  
 El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> borra el Portapapeles. Dado que otros procesos comparten el Portapapeles, borrarlo puede afectar a esos procesos.  
  
 En el código siguiente se muestra cómo puede utilizar el método `Clear`.  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]  
  
## <a name="writing-to-the-clipboard"></a>Escribir en el Portapapeles  
 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> para escribir texto en el Portapapeles. El código siguiente escribe la cadena "This is a test string" en el Portapapeles.  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]  
  
 El método `SetText` puede aceptar un parámetro de formato que contenga un tipo de <xref:System.Windows.Forms.TextDataFormat>. El código siguiente escribe la cadena "This is a test string" en el Portapapeles como texto RTF.  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]  
  
 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> para escribir datos en el Portapapeles. Este ejemplo escribe `DataObject``dataChunk` en el Portapapeles en el formato personalizado `specialFormat`.  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]  
  
 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> para escribir datos de audio en el Portapapeles. Este ejemplo crea la matriz de bytes `musicReader`, lee el archivo `cool.wav` que hay dentro y lo escribe en el Portapapeles.  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]  
  
> [!IMPORTANT]
>  Dado que otros usuarios pueden acceder al Portapapeles, no lo use para almacenar información confidencial, como contraseñas o datos confidenciales.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>  
 [Leer objetos de datos de un archivo XML](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)  
 [Escribir objetos de datos en un archivo XML](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
