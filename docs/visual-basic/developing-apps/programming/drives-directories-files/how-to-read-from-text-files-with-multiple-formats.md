---
title: Procedimiento Lectura de archivos de texto con varios formatos
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, reading from a file
- TextFieldType enumeration
- My.Computer.FileSystem.WriteAllText method, parsing structured text files
- WriteAllText method [Visual Basic], parsing structured text files
- PeekChars method [Visual Basic], determining format of text
- reading text files [Visual Basic], multiple formats
- I/O [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
ms.openlocfilehash: b36c781d5f8333749d346bb8f19540f0d1bd1692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334572"
---
# <a name="how-to-read-from-fext-files-with-multiple-formats-in-visual-basic"></a>Procedimiento Lectura de archivos de texto con varios formatos en Visual Basic

El objeto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros. Puede procesar un archivo con varios formatos usando el método `PeekChars` para determinar el formato de cada línea a medida que va analizando el archivo.
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a>Para analizar un archivo de texto con varios formatos

1. Agregue un archivo de texto denominado *testfile.txt* al proyecto. Agregue el contenido siguiente al archivo de texto:

    ```text
    Err  1001 Cannot access resource.
    Err  2014 Resource not found.
    Acc  10/03/2009User1      Administrator.
    Err  0323 Warning: Invalid access attempt.
    Acc  10/03/2009User2      Standard user.
    Acc  10/04/2009User2      Standard user.
    ```

2. Defina el formato esperado y el formato usado cuando se cree un informe un error. La última entrada en cada matriz es -1, por consiguiente se presupone que el último campo es de ancho variable. Esto se produce cuando la última entrada en la matriz es menor o igual que 0.

     [!code-vb[VbFileIORead#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#4)]

3. Cree un objeto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> que defina el ancho y el formato.

     [!code-vb[VbFileIORead#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#5)]

4. Recorra en iteración las filas, probando el formato antes de leerlas.

     [!code-vb[VbFileIORead#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#6)]

5. Escriba los errores en la consola.

     [!code-vb[VbFileIORead#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#7)]

## <a name="example"></a>Ejemplo

A continuación se proporciona el ejemplo completo que lee del archivo `testfile.txt`:

 [!code-vb[VbFileIORead#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#8)]

## <a name="robust-programming"></a>Programación sólida

Las condiciones siguientes pueden provocar una excepción:  
  
- No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). El mensaje de excepción especifica la línea que produce la excepción y la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se asigna al texto contenido en la línea.
- El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).
- Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo. (<xref:System.Security.SecurityException>).
- La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).
- El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- [Cómo: Leer archivos de texto delimitado por comas](how-to-read-from-comma-delimited-text-files.md)
- [Cómo: Leer archivos de texto de ancho fijo](how-to-read-from-fixed-width-text-files.md)
- [Análisis de archivos de texto con el objeto TextFieldParser](parsing-text-files-with-the-textfieldparser-object.md)
