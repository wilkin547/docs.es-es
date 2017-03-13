---
title: "C&#243;mo: Leer archivos de texto delimitado por comas en Visual Basic | Microsoft Docs"
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
  - "archivos, analizar"
  - "leer archivos de texto, delimitado por comas"
  - "archivos de texto, leer"
  - "archivos de texto, tareas"
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# C&#243;mo: Leer archivos de texto delimitado por comas en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El objeto `TextFieldParser` proporciona una manera de analizar con facilidad y eficiencia archivos de texto estructurados, como por ejemplo los registros.  La propiedad `TextFieldType` define si se trata de un archivo delimitado o uno con campos de ancho fijo de texto.  
  
### Para analizar un archivo de texto delimitado por comas  
  
1.  Cree un nuevo objeto `TextFieldParser`.  El código siguiente crea el objeto `TextFieldParser` denominado `MyReader` y abre el archivo `test.txt`.  
  
     [!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]  
  
2.  Defina el tipo de `TextField` y el delimitador.  El código siguiente define la propiedad `TextFieldType` como `Delimited` y el delimitador como ",".  
  
     [!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]  
  
3.  Recorra los campos del archivo.  Si alguna línea está dañada, cree un informe de error y continúe el análisis.  El código siguiente recorre el archivo para mostrar cada campo a la vez e indica los campos con formato incorrecto.  
  
     [!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]  
  
4.  Cierre los bloques `While` y `Using` con `End While` y `End Using`.  
  
     [!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]  
  
## Ejemplo  
 En este ejemplo se lee el archivo `test.txt`.  
  
 [!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No se puede analizar una fila con el formato especificado \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  El mensaje de excepción especifica la línea que produce la excepción y se asigna a la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> el texto contenido en la línea.  
  
-   El archivo especificado no existe \(<xref:System.IO.FileNotFoundException>\).  
  
-   Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo.  \(<xref:System.Security.SecurityException>\).  
  
-   La ruta de acceso es demasiado larga \(<xref:System.IO.PathTooLongException>\).  
  
-   El usuario no tiene permisos suficientes para el acceso al archivo \(<xref:System.UnauthorizedAccessException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [Cómo: Leer archivos de texto de ancho fijo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Analizar archivos de texto con el objeto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Tutorial: Manipular archivos y directorios en Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Solución de problemas: Leer y escribir en archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Solución de problemas de excepciones: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)