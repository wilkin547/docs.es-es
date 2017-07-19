---
title: "C&#243;mo: Leer texto de un archivo | Microsoft Docs"
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
  - "secuencias de datos, leer texto de archivos"
  - "E/S [.NET Framework], leer texto de archivos"
  - "leer datos, archivos de texto"
  - "leer archivos de texto"
  - "secuencias, leer texto de archivos"
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
caps.latest.revision: 23
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 23
---
# C&#243;mo: Leer texto de un archivo
En los ejemplos siguientes se muestra cómo leer texto desde un archivo de texto de forma sincrónica y asincrónica mediante .NET para aplicaciones de escritorio.  En ambos ejemplos, cuando se crea la instancia de la clase <xref:System.IO.StreamReader>, se proporciona la ruta de acceso relativa o absoluta del archivo.  En los ejemplos siguientes se supone que el archivo denominado TestFile.txt está en la misma carpeta que la aplicación.  
  
 Estos ejemplos de código no se pueden aplicar al desarrollo de aplicaciones de la Tienda Windows porque Windows en tiempo de ejecución ofrece diferentes tipos de secuencias al leer archivos o escribir en ellos.  Si desea ver un ejemplo en el que se muestre cómo leer el texto de un archivo en el contexto de una aplicación de la Tienda Windows, consulte [Inicio rápido: lectura y escritura de un archivo](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).  Para obtener ejemplos que muestren cómo convertir entre secuencias de .NET Framework y secuencias de Windows en tiempo de ejecución, consulte [Cómo: Convertir flujos de .NET Framework en flujos de Windows en tiempo de ejecución, y viceversa](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## Ejemplo  
 El primer ejemplo muestra una operación de lectura sincrónica dentro de una aplicación de consola.  En este ejemplo, el archivo de texto se abre con un lector de secuencias, el contenido se copia en una cadena y la cadena se envía a la consola.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## Ejemplo  
 El segundo ejemplo muestra una operación de lectura asincrónica dentro de una aplicación de Windows Presentation Foundation \(WPF\).  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## Vea también  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.File.OpenText%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 [E\/S de archivos asincrónica](../../../docs/standard/io/e-s-de-archivos-asincrónica.md)   
 [NIB: How to: Create a Directory Listing](http://msdn.microsoft.com/es-es/4d2772b1-b991-4532-a8a6-6ef733277e69)   
 [Inicio rápido: lectura y escritura de un archivo](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)   
 [Cómo: Convertir flujos de .NET Framework en flujos de Windows en tiempo de ejecución, y viceversa](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)   
 [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Cómo: Leer caracteres de una cadena](../../../docs/standard/io/how-to-read-characters-from-a-string.md)   
 [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)