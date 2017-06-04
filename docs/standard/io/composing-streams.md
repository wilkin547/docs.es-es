---
title: "Crear secuencias | Microsoft Docs"
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
  - "secuencias, secuencias base"
  - "E/S [.NET Framework], componer secuencias"
  - "clase Stream, componer secuencias"
  - "secuencias base"
  - "secuencias, memorias auxiliares"
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Crear secuencias
Una memoria auxiliar es un medio de almacenamiento, como un disco o la memoria.  Cada memoria auxiliar implementa su propia secuencia como una implementación de la clase <xref:System.IO.Stream>.  Cada tipo de secuencia lee y escribe bytes en y desde su memoria auxiliar determinada.  Las secuencias que se conectan a memorias auxiliares se denominan secuencias base.  Las secuencias base tienen constructores con los parámetros necesarios para conectar la secuencia a la memoria auxiliar.  Por ejemplo, <xref:System.IO.FileStream> tiene constructores que especifican un parámetro de ruta, que a su vez especifica cómo compartirán el archivo los procesos, etc.  
  
 El diseño de las clases <xref:System.IO> simplifica la composición de secuencias.  Las secuencias base se pueden asociar a una o varias secuencias de paso que proporcionan la funcionalidad deseada.  Se puede asociar a un lector o a un sistema de escritura al final de la cadena, para que los tipos preferidos se puedan leer o escribir con facilidad.  
  
 En el siguiente ejemplo de código se crea un objeto **FileStream** en torno al archivo `MyFile.txt` existente con el fin de almacenarlo en el búfer `MyFile.txt`. \(Tenga en cuenta que **FileStreams** se almacenan en el búfer de forma predeterminada.\) Después, se crea un <xref:System.IO.StreamReader> para leer los caracteres de **FileStream**, que se pasa a **StreamReader** como argumento de su constructor.  <xref:System.IO.StreamReader.ReadLine%2A> lee hasta que <xref:System.IO.StreamReader.Peek%2A> no encuentra más caracteres.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 En el siguiente ejemplo de código se crea un objeto **FileStream** en torno al archivo `MyFile.txt` existente con el fin de almacenarlo en el búfer `MyFile.txt`. \(Tenga en cuenta que **FileStreams** se almacenan en el búfer de forma predeterminada.\) A continuación, se crea **BinaryReader** para leer los bytes de **FileStream**, que se pasan a **BinaryReader** como argumento del constructor.  <xref:System.IO.BinaryReader.ReadByte%2A> lee hasta que <xref:System.IO.BinaryReader.PeekChar%2A> no encuentra más bytes.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## Vea también  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=fullName>   
 <xref:System.IO.FileStream>   
 <xref:System.IO.BinaryReader>   
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=fullName>   
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=fullName>