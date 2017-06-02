---
title: "C&#243;mo: Leer caracteres de una cadena | Microsoft Docs"
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
  - "leer caracteres de cadenas"
  - "secuencias de datos, leer caracteres de una cadena"
  - "E/S [.NET Framework], leer caracteres de cadenas"
  - "leer datos, cadenas"
  - "secuencias, leer caracteres de una cadena"
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Leer caracteres de una cadena
Los siguientes ejemplos de código muestran cómo leer sincrónica y asincrónicamente caracteres de una cadena.  
  
## Ejemplo  
 Este ejemplo lee sincrónicamente 13 caracteres de una cadena, los almacena en una matriz, y muestra los caracteres.  Después lee los caracteres restantes en la cadena, los almacena en la matriz comenzando por el sexto elemento, y muestra el contenido de la matriz.  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## Ejemplo  
 El siguiente ejemplo lee de forma asincrónica todos los caracteres de un control <xref:System.Windows.Controls.TextBox>, y los almacena en una matriz.  Luego escribe de forma asincrónica cada carácter de la letra o espacio en blanco en una línea independiente seguida de un salto de línea en un control <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## Vea también  
 <xref:System.IO.StringReader>   
 <xref:System.IO.StringReader.Read%2A?displayProperty=fullName>   
 [E\/S de archivos asincrónica](../../../docs/standard/io/e-s-de-archivos-asincrónica.md)   
 [NIB: How to: Create a Directory Listing](http://msdn.microsoft.com/es-es/4d2772b1-b991-4532-a8a6-6ef733277e69)   
 [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)