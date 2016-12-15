---
title: "C&#243;mo: Leer archivos de texto de ancho fijo en Visual Basic | Microsoft Docs"
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
  - "archivos, analizar"
  - "archivo de texto de ancho fijo"
  - "leer archivos de texto, ancho fijo"
  - "archivos de texto, leer"
  - "archivos de texto, tareas"
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Leer archivos de texto de ancho fijo en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El objeto `TextFieldParser` proporciona una manera de analizar con facilidad y eficiencia archivos de texto estructurados, como por ejemplo los registros.  
  
 La propiedad `TextFieldType` define si el archivo analizado se trata de un archivo delimitado o uno que tiene campos de texto de ancho fijo.  En un archivo de texto de ancho fijo, el campo puede tener un ancho variable al final.  Para especificar que el campo tiene un ancho variable al final, debe definirlo para que tenga un ancho menor o igual que cero.  
  
### Para analizar un archivo de texto de ancho fijo  
  
1.  Cree un nuevo objeto `TextFieldParser`.  El código siguiente crea el objeto `TextFieldParser` denominado `Reader` y abre el archivo `test.log`.  
  
     [!code-vb[VbFileIORead#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_1.vb)]  
  
2.  Defina la propiedad `TextFieldType` como `FixedWidth`, definiendo el ancho y el formato.  El código siguiente define las columnas de texto; la primera tiene un ancho de 5 caracteres, la segunda de 10, la tercera de 11 y la cuarta es de ancho variable.  
  
     [!code-vb[VbFileIORead#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_2.vb)]  
  
3.  Recorra los campos del archivo.  Si alguna línea está dañada, cree un informe de error y continúe el análisis.  
  
     [!code-vb[VbFileIORead#11](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_3.vb)]  
  
4.  Cierre los bloques `While` y `Using` con `End While` y `End Using`.  
  
     [!code-vb[VbFileIORead#12](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_4.vb)]  
  
## Ejemplo  
 En este ejemplo se lee el archivo `test.log`.  
  
 [!code-vb[VbFileIORead#13](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_5.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No se puede analizar una fila con el formato especificado \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  El mensaje de excepción especifica la línea que produce la excepción y la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se asigna al texto contenido en la línea.  
  
-   El archivo especificado no existe \(<xref:System.IO.FileNotFoundException>\).  
  
-   Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo.  \(<xref:System.Security.SecurityException>\).  
  
-   La ruta de acceso es demasiado larga \(<xref:System.IO.PathTooLongException>\).  
  
-   El usuario no tiene permisos suficientes para el acceso al archivo \(<xref:System.UnauthorizedAccessException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [Cómo: Leer archivos de texto delimitado por comas](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Analizar archivos de texto con el objeto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Tutorial: Manipular archivos y directorios en Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Solución de problemas: Leer y escribir en archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Solución de problemas de excepciones: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)