---
title: Almacenamiento y lectura de datos en el Portapapeles
ms.date: 07/20/2015
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
ms.openlocfilehash: 243fb237f3f9ba53f8b29079df08531c102c78dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349732"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a>Almacenar y leer datos en el Portapapeles (Visual Basic)

El Portapapeles se puede usar para almacenar datos, como texto e imágenes. Dado que todos los procesos activos comparten el Portapapeles, se puede usar para transferir datos entre ellos. El objeto `My.Computer.Clipboard` permite acceder fácilmente al Portapapeles y leer y escribir en él.  
  
## <a name="reading-from-the-clipboard"></a>Leer desde el Portapapeles  

 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> para leer el texto en el Portapapeles. El código siguiente lee el texto y lo muestra en un cuadro de mensaje. Para que el ejemplo se ejecute correctamente debe haber texto almacenado en el Portapapeles.  
  
 [!code-vb[VbVbcnMyClipboard#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#4)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> para recuperar una imagen del Portapapeles. En este ejemplo se comprueba si hay una imagen en el Portapapeles antes de recuperarla y asignarla a `PictureBox1`.  
  
 [!code-vb[VbResourceTasks#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#16)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**. Para más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
 Los elementos colocados en el Portapapeles se conservan incluso después de que se cierre la aplicación.  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a>Determinar el tipo de archivo almacenado en el Portapapeles  

 Los datos del Portapapeles pueden adoptar varios formatos distintos, como texto, un archivo de audio o una imagen. Para determinar qué tipo de archivo está en el Portapapeles, puede usar métodos como <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> y <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>. El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> puede usarse si tiene un formato personalizado que desea comprobar.  
  
 Use la función `ContainsImage` para determinar si los datos incluidos en el Portapapeles son una imagen. El código siguiente comprueba si los datos son una imagen e informa en consecuencia.  
  
 [!code-vb[VbResourceTasks#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#13)]  
  
## <a name="clearing-the-clipboard"></a>Borrar el Portapapeles  

 El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> borra el Portapapeles. Dado que otros procesos comparten el Portapapeles, borrarlo puede afectar a esos procesos.  
  
 En el código siguiente se muestra cómo puede utilizar el método `Clear`.  
  
 [!code-vb[VbVbcnMyClipboard#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#3)]  
  
## <a name="writing-to-the-clipboard"></a>Escribir en el Portapapeles  

 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> para escribir texto en el Portapapeles. El código siguiente escribe la cadena "This is a test string" en el Portapapeles.  
  
 [!code-vb[VbVbcnMyClipboard#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#1)]  
  
 El método `SetText` puede aceptar un parámetro de formato que contenga un tipo de <xref:System.Windows.Forms.TextDataFormat>. El código siguiente escribe la cadena "This is a test string" en el Portapapeles como texto RTF.  
  
 [!code-vb[VbVbcnMyClipboard#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#2)]  
  
 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> para escribir datos en el Portapapeles. En este ejemplo se escribe el `DataObject` `dataChunk` en el Portapapeles con el formato personalizado `specialFormat`.  
  
 [!code-vb[VbVbcnMyClipboard#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#7)]  
  
 Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> para escribir datos de audio en el Portapapeles. Este ejemplo crea la matriz de bytes `musicReader`, lee el archivo `cool.wav` que hay dentro y lo escribe en el Portapapeles.  
  
 [!code-vb[VbResourceTasks#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#5)]  
  
> [!IMPORTANT]
> Dado que otros usuarios pueden acceder al Portapapeles, no lo use para almacenar información confidencial, como contraseñas o datos confidenciales.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>
- [Cómo: Leer datos de objetos en un archivo XML](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [Cómo: Escribir datos de objeto en un archivo XML](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
