---
title: "No se pueden leer los campos delimitados porque una comilla doble no es un delimitador v&#225;lido cuando EscapeQuotes se establece en True. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrTextFieldParser_IllegalDelimiter"
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# No se pueden leer los campos delimitados porque una comilla doble no es un delimitador v&#225;lido cuando EscapeQuotes se establece en True.
El `TextFieldParser` no se puede leer desde el archivo porque se han proporcionado comillas \("\) como delimitador y `EscapeQuotes` está establecido en `True`.  
  
### Para corregir este error  
  
-   Establezca `EscapeQuotes` en `False`.  
  
## Vea también  
 [Método TextFieldParser.SetDelimiters](http://msdn.microsoft.com/es-es/21fa40ec-5866-4d0e-9fd9-c708a190dcc9)   
 [Propiedad TextFieldParser.Delimiters](http://msdn.microsoft.com/es-es/4eb18f4d-3011-40a9-b668-be93eed0444f)   
 [Cómo: Leer archivos de texto delimitado por comas](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [TextFieldParser \(Objeto\)](../../visual-basic/language-reference/objects/textfieldparser-object.md)