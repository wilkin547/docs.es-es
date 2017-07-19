---
title: "Cómo: Leer archivos de texto delimitados por comas en Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, parsing
- text files, tasks
- reading text files, comma-delimited
- text files, reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 011e92f1d3c4aa7fae5a1022815dfe83b313685f
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a>Cómo: Leer archivos de texto delimitados por comas en Visual Basic
El objeto `TextFieldParser` proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros. La propiedad `TextFieldType` define si se trata de un archivo delimitado o de uno con campos de texto de ancho fijo.  
  
### <a name="to-parse-a-comma-delimited-text-file"></a>Para analizar un archivo de texto delimitado por comas  
  
1.  Cree un nuevo objeto `TextFieldParser`. El código siguiente crea el `TextFieldParser` denominado `MyReader` y abre el archivo `test.txt`.  
  
     [!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]  
  
2.  Defina el tipo `TextField` y el delimitador. El código siguiente define la propiedad `TextFieldType` como `Delimited` y el delimitador como ",".  
  
     [!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]  
  
3.  Recorra en bucle los campos del archivo. Si hay alguna línea dañada, informe del error y siga analizando. El siguiente código recorre en bucle el archivo y muestra los campos por turnos e indica aquellos que tienen un formato incorrecto.  
  
     [!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]  
  
4.  Cierre los bloques `While` y `Using` con `End While` y `End Using`.  
  
     [!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se lee el archivo `test.txt`.  
  
 [!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). El mensaje de excepción especifica la línea que inicia la excepción, mientras que a la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se le asigna el texto incluido en la línea.  
  
-   El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).  
  
-   Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo. (<xref:System.Security.SecurityException>).  
  
-   La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).  
  
-   El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [Cómo: Leer archivos de texto de ancho fijo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Analizar archivos de texto con el objeto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Tutorial: Manipular archivos y directorios en Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Solución de problemas: Leer y escribir en archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
