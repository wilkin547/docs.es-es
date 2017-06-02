---
title: "C&#243;mo: Escribir caracteres en una cadena | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "secuencias de datos, escribir caracteres en una cadena"
  - "escribir caracteres en cadenas"
  - "secuencias, escribir caracteres en una cadena"
  - "E/S [.NET Framework], escribir caracteres en cadenas"
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Escribir caracteres en una cadena
Los siguientes ejemplos de código escriben caracteres sincrónica y asincrónicamente desde una matriz de caracteres a una cadena.  
  
## Ejemplo  
 El siguiente ejemplo escribe 5 caracteres sincrónicamente desde una matriz a una cadena.  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## Ejemplo  
 El siguiente ejemplo lee de forma asincrónica todos los caracteres de un control <xref:System.Windows.Controls.TextBox>, y los almacena en una matriz.  Luego escribe de forma asincrónica cada carácter de la letra o espacio en blanco en una línea independiente seguida de un salto de línea en un control <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## Vea también  
 <xref:System.IO.StringWriter>   
 <xref:System.IO.StringWriter.Write%2A?displayProperty=fullName>   
 <xref:System.Text.StringBuilder>   
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)   
 [E\/S de archivos asincrónica](../../../docs/standard/io/e-s-de-archivos-asincrónica.md)   
 [Cómo: Enumerar directorios y archivos](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Cómo: Leer caracteres de una cadena](../../../docs/standard/io/how-to-read-characters-from-a-string.md)