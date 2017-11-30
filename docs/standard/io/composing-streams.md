---
title: Crear secuencias
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75800210a52620c5b08a01c5f8fa888bf40843fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="composing-streams"></a>Crear secuencias
Una memoria auxiliar es un medio de almacenamiento, como un disco o memoria. Cada almacén de respaldo distinto implementa su propia secuencia como una implementación de la <xref:System.IO.Stream> clase. Cada tipo de secuencia lee y escribe los bytes desde y hacia su memoria auxiliar determinado. Secuencias que se conectan a almacenes de respaldo se denominan secuencias base. Secuencias base tienen constructores con los parámetros necesarios para conectar la secuencia a la memoria auxiliar. Por ejemplo, <xref:System.IO.FileStream> tiene constructores que especifican un parámetro de ruta de acceso, que especifica cómo compartirán el archivo los procesos y así sucesivamente.  
  
 El diseño de la <xref:System.IO> clases proporciona la composición de secuencias simplificada. Secuencias base se pueden asociar a uno o varios flujos de paso a través que proporcionan la funcionalidad que desee. Un lector o escritor puede adjuntarse al final de la cadena para que los tipos deseados se pueden leer o escritos con facilidad.  
  
 En el ejemplo de código siguiente se crea un **FileStream** alrededor existente `MyFile.txt` en orden al búfer `MyFile.txt`. (Tenga en cuenta que **secuencias** se almacenan en búfer de forma predeterminada.) Después, un <xref:System.IO.StreamReader> se crea para leer los caracteres desde la **FileStream**, que se pasa a la **StreamReader** como argumento de su constructor. <xref:System.IO.StreamReader.ReadLine%2A>lee hasta que <xref:System.IO.StreamReader.Peek%2A> no encuentra más caracteres.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 En el ejemplo de código siguiente se crea un **FileStream** alrededor existente `MyFile.txt` en orden al búfer `MyFile.txt`. (Tenga en cuenta que **secuencias** se almacenan en búfer de forma predeterminada.) Después, un **BinaryReader** se crea para leer los bytes de la **FileStream**, que se pasa a la **BinaryReader** como argumento de su constructor. <xref:System.IO.BinaryReader.ReadByte%2A>lee hasta que <xref:System.IO.BinaryReader.PeekChar%2A> no encuentra más bytes.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
