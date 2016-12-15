---
title: "C&#243;mo: Leer archivos de texto con varios formatos en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "E/S [Visual Basic], leer archivos de texto"
  - "My.Computer.FileSystem.WriteAllText (método), analizar archivos de texto estructurados"
  - "PeekChars (método), determinar el formato de texto"
  - "leer archivos de texto, varios formatos"
  - "archivos de texto, leer"
  - "TextFieldParser (objeto), leer un archivo"
  - "TextFieldType (enumeración)"
  - "WriteAllText (método), analizar archivos de texto estructurados"
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Leer archivos de texto con varios formatos en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El objeto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> proporciona una manera de analizar con facilidad y eficiencia archivos de texto estructurados, como por ejemplo los registros.  Puede procesar un archivo con varios formatos utilizando el método `PeekChars` para determinar el formato de cada línea a medida que se va analizando el archivo.  
  
### Para analizar un archivo de texto con varios formatos  
  
1.  Agregue un archivo de texto denominado testfile.txt al proyecto.  Agregue el contenido siguiente al archivo de texto.  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2.  Defina el formato esperado y el formato utilizado cuando se cree un informe un error.  La última entrada en cada matriz es \-1, por consiguiente se supone que el último campo es de ancho variable.  Esto se produce cuando la última entrada en la matriz es menor o igual que 0.  
  
     [!code-vb[VbFileIORead#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_1.vb)]  
  
3.  Cree un nuevo objeto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>, definiendo su ancho y su formato.  
  
     [!code-vb[VbFileIORead#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_2.vb)]  
  
4.  Recorra en iteración las filas, probando el formato antes de leerlas.  
  
     [!code-vb[VbFileIORead#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_3.vb)]  
  
5.  Escriba los errores en la consola.  
  
     [!code-vb[VbFileIORead#7](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_4.vb)]  
  
## Ejemplo  
 A continuación se proporciona el ejemplo completo que lee del archivo `testfile.txt`.  
  
 [!code-vb[VbFileIORead#8](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_5.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No se puede analizar una fila con el formato especificado \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  El mensaje de excepción especifica la línea que produce la excepción y la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se asigna al texto contenido en la línea.  
  
-   El archivo especificado no existe \(<xref:System.IO.FileNotFoundException>\).  
  
-   Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo.  \(<xref:System.Security.SecurityException>\).  
  
-   La ruta de acceso es demasiado larga \(<xref:System.IO.PathTooLongException>\).  
  
-   El usuario no tiene permisos suficientes para el acceso al archivo \(<xref:System.UnauthorizedAccessException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 [Cómo: Leer archivos de texto delimitado por comas](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [Cómo: Leer archivos de texto de ancho fijo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Analizar archivos de texto con el objeto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)