---
title: Crear secuencias
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e52b827f337892c33ec61b9affa1cc646a759c5
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46577027"
---
# <a name="composing-streams"></a>Crear secuencias
Una memoria auxiliar es un medio de almacenamiento, como un disco o memoria. Cada memoria auxiliar distinta implementa su propia secuencia como una implementación de la clase <xref:System.IO.Stream>. Cada tipo de secuencia lee y escribe los bytes desde y en su memoria auxiliar determinada. Las secuencias que se conectan a las memorias auxiliares reciben el nombre de secuencias base. Las secuencias base tienen constructores que disponen de los parámetros necesarios para conectar la secuencia a la memoria auxiliar. Por ejemplo, <xref:System.IO.FileStream> tiene constructores que especifican un parámetro de ruta de acceso, que especifica cómo los procesos compartirán el archivo, etc.  
  
 El diseño de las clases <xref:System.IO> proporciona la composición de secuencias simplificada. Las secuencias base pueden adjuntarse a una o varias secuencias de paso a través que proporcionan la funcionalidad que desee. Un lector o escritor puede adjuntarse al final de la cadena para que los tipos deseados se puedan leer o escribir con facilidad.  
  
 En el ejemplo de código siguiente se crea una clase **FileStream** en torno al archivo `MyFile.txt` para almacenar `MyFile.txt` en el búfer. (Tenga en cuenta que las clases **FileStreams** se almacenan en búfer de forma predeterminada). Después, se crea una clase <xref:System.IO.StreamReader> para leer los caracteres desde **FileStream**, que se pasa a **StreamReader** como argumento de su constructor. <xref:System.IO.StreamReader.ReadLine%2A> lee hasta que <xref:System.IO.StreamReader.Peek%2A> no encuentra más caracteres.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 En el ejemplo de código siguiente se crea una clase **FileStream** en torno al archivo `MyFile.txt` para almacenar `MyFile.txt` en el búfer. (Tenga en cuenta que las clases **FileStreams** se almacenan en búfer de forma predeterminada). Después, se crea una clase **BinaryReader** para leer los bytes desde **FileStream**, que se pasa a **BinaryReader** como argumento de su constructor. <xref:System.IO.BinaryReader.ReadByte%2A> lee hasta que <xref:System.IO.BinaryReader.PeekChar%2A> no encuentra más bytes.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamReader>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
