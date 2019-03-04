---
title: 'Cómo: Leer archivos de texto delimitados por comas en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- reading text files [Visual Basic], comma-delimited
- text files [Visual Basic], reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
ms.openlocfilehash: 9035bf2639033915c686d336d7d4805a7205f0ae
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968024"
---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a>Cómo: Leer archivos de texto delimitados por comas en Visual Basic
El objeto `TextFieldParser` proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros. La propiedad `TextFieldType` define si se trata de un archivo delimitado o de uno con campos de texto de ancho fijo.  
  
### <a name="to-parse-a-comma-delimited-text-file"></a>Para analizar un archivo de texto delimitado por comas  
  
1.  Cree un nuevo objeto `TextFieldParser`. El código siguiente crea el `TextFieldParser` denominado `MyReader` y abre el archivo `test.txt`.  
  
     [!code-vb[VbFileIORead#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#15)]  
  
2.  Defina el tipo `TextField` y el delimitador. El código siguiente define la propiedad `TextFieldType` como `Delimited` y el delimitador como ",".  
  
     [!code-vb[VbFileIORead#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#16)]  
  
3.  Recorra en bucle los campos del archivo. Si hay alguna línea dañada, informe del error y siga analizando. El siguiente código recorre en bucle el archivo y muestra los campos por turnos e indica aquellos que tienen un formato incorrecto.  
  
     [!code-vb[VbFileIORead#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#17)]  
  
4.  Cierre los bloques `While` y `Using` con `End While` y `End Using`.  
  
     [!code-vb[VbFileIORead#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#18)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se lee el archivo `test.txt`.  
  
 [!code-vb[VbFileIORead#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). El mensaje de excepción especifica la línea que inicia la excepción, mientras que a la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se le asigna el texto incluido en la línea.  
  
-   El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).  
  
-   Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo. (<xref:System.Security.SecurityException>).  
  
-   La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).  
  
-   El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [Cómo: Leer archivos de texto de ancho fijo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [Análisis de archivos de texto con el objeto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [Tutorial: Manipulación de archivos y directorios en Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [Solución de problemas: Leer y escribir en archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
