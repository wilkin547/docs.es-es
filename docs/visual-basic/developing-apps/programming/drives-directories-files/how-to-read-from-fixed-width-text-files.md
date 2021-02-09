---
description: 'Más información acerca de: Cómo: Leer archivos de texto de ancho fijo en Visual Basic'
title: Procedimiento para leer archivos de texto de ancho fijo
ms.date: 07/20/2015
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
ms.openlocfilehash: 4f5868fa68009851cc65eeaf5ff6431ac22840d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797463"
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a>Cómo: Leer archivos de texto de ancho fijo en Visual Basic

El objeto `TextFieldParser` proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros.  
  
 La propiedad `TextFieldType` define si el archivo analizado se trata de un archivo delimitado o uno que tiene campos de texto de ancho fijo. En un archivo de texto de ancho fijo, el campo puede tener un ancho variable al final. Para especificar que el campo tiene un ancho variable al final, debe definirlo para que tenga un ancho menor o igual que cero.  
  
### <a name="to-parse-a-fixed-width-text-file"></a>Para analizar un archivo de texto de ancho fijo  
  
1. Cree un nuevo `TextFieldParser`. El código siguiente crea el `TextFieldParser` denominado `Reader` y abre el archivo `test.log`.  
  
     [!code-vb[VbFileIORead#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#9)]  
  
2. Defina la propiedad `TextFieldType` como `FixedWidth` definiendo el ancho y el formato. El código siguiente define las columnas de texto; la primera tiene un ancho de 5 caracteres, la segunda de 10, la tercera de 11 y la cuarta es de ancho variable.  
  
     [!code-vb[VbFileIORead#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#10)]  
  
3. Recorra en bucle los campos del archivo. Si alguna línea está dañada, cree un informe de error y continúe el análisis.  
  
     [!code-vb[VbFileIORead#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#11)]  
  
4. Cierre los bloques `While` y `Using` con `End While` y `End Using`.  
  
     [!code-vb[VbFileIORead#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#12)]  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se lee el archivo `test.log`.  
  
 [!code-vb[VbFileIORead#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#13)]  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar una excepción:  
  
- No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). El mensaje de excepción especifica la línea que produce la excepción y la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se asigna al texto contenido en la línea.  
  
- El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).  
  
- Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo. (<xref:System.Security.SecurityException>).  
  
- La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).  
  
- El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [Procedimiento para leer archivos de texto delimitado por comas](how-to-read-from-comma-delimited-text-files.md)
- [Procedimiento para leer archivos de texto con varios formatos](how-to-read-from-text-files-with-multiple-formats.md)
- [Analizar archivos de texto con el objeto TextFieldParser](parsing-text-files-with-the-textfieldparser-object.md)
- [Tutorial: Manipulación de archivos y directorios en Visual Basic](walkthrough-manipulating-files-and-directories.md)
- [Solución del problema: leer y escribir en archivos de texto](troubleshooting-reading-from-and-writing-to-text-files.md)
