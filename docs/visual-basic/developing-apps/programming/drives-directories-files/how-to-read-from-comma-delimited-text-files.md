---
description: 'Más información acerca de: Cómo: Leer archivos de texto delimitados por comas en Visual Basic'
title: Procedimiento para leer archivos de texto delimitado por comas
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- reading text files [Visual Basic], comma-delimited
- text files [Visual Basic], reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
ms.openlocfilehash: dc4d4d5a7639ab7b5aa342aa8646b02985e40797
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797489"
---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a>Cómo: Leer archivos de texto delimitados por comas en Visual Basic

El objeto `TextFieldParser` proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros. La propiedad `TextFieldType` define si se trata de un archivo delimitado o de uno con campos de texto de ancho fijo.  
  
### <a name="to-parse-a-comma-delimited-text-file"></a>Para analizar un archivo de texto delimitado por comas  
  
1. Cree un nuevo `TextFieldParser`. El código siguiente crea el `TextFieldParser` denominado `MyReader` y abre el archivo `test.txt`.  
  
     [!code-vb[VbFileIORead#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#15)]  
  
2. Defina el tipo `TextField` y el delimitador. El código siguiente define la propiedad `TextFieldType` como `Delimited` y el delimitador como ",".  
  
     [!code-vb[VbFileIORead#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#16)]  
  
3. Recorra en bucle los campos del archivo. Si hay alguna línea dañada, informe del error y siga analizando. El siguiente código recorre en bucle el archivo y muestra los campos por turnos e indica aquellos que tienen un formato incorrecto.  
  
     [!code-vb[VbFileIORead#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#17)]  
  
4. Cierre los bloques `While` y `Using` con `End While` y `End Using`.  
  
     [!code-vb[VbFileIORead#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#18)]  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se lee el archivo `test.txt`.  
  
 [!code-vb[VbFileIORead#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar una excepción:  
  
- No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). El mensaje de excepción especifica la línea que inicia la excepción, mientras que a la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se le asigna el texto incluido en la línea.  
  
- El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).  
  
- Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo. (<xref:System.Security.SecurityException>).  
  
- La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).  
  
- El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [Procedimiento para leer archivos de texto de ancho fijo](how-to-read-from-fixed-width-text-files.md)
- [Procedimiento para leer archivos de texto con varios formatos](how-to-read-from-text-files-with-multiple-formats.md)
- [Analizar archivos de texto con el objeto TextFieldParser](parsing-text-files-with-the-textfieldparser-object.md)
- [Tutorial: Manipulación de archivos y directorios en Visual Basic](walkthrough-manipulating-files-and-directories.md)
- [Solución del problema: leer y escribir en archivos de texto](troubleshooting-reading-from-and-writing-to-text-files.md)
