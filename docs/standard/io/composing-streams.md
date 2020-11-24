---
title: Redactar flujos
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
ms.openlocfilehash: c50a372ee3434fcd7f72ad707ca82c5c9ad8a5c8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823386"
---
# <a name="compose-streams"></a>Redactar flujos
Una *memoria auxiliar* es un medio de almacenamiento, como un disco o memoria. Cada memoria auxiliar distinta implementa su propia secuencia como una implementación de la clase <xref:System.IO.Stream>.

Cada tipo de secuencia lee y escribe los bytes desde y en su memoria auxiliar determinada. Los flujos que se conectan a las memorias auxiliares reciben el nombre de *secuencias base*. Las secuencias base tienen constructores con los parámetros necesarios para conectar el flujo a la memoria auxiliar. Por ejemplo, <xref:System.IO.FileStream> tiene constructores que especifican un parámetro de ruta de acceso, que especifica cómo los procesos compartirán el archivo.  

El diseño de las clases <xref:System.IO> proporciona la composición de flujos simplificada. Puede asociar las secuencias base a uno o varios flujos de paso a través que proporcionan la funcionalidad que desee. Puede asociar un lector o escritor al final de la cadena para que los tipos deseados se puedan leer o escribir con facilidad.  

En los ejemplos de código siguientes se crea una clase **FileStream** en torno al archivo *MyFile.txt* para almacenar *MyFile.txt* en el búfer. Tenga en cuenta que las clases **FileStreams** se almacenan en búfer de forma predeterminada.

>[!IMPORTANT]
>En los ejemplos, se da por supuesto que un archivo llamado *MyFile.txt* ya existe en la misma carpeta que la aplicación.  

## <a name="example-use-streamreader"></a>Ejemplo: Usar StreamReader
En el siguiente ejemplo se crea una clase <xref:System.IO.StreamReader> para leer los caracteres desde **FileStream**, que se pasa a **StreamReader** como argumento de su constructor. A continuación, <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> lee hasta que <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> no encuentra más caracteres.  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a>Ejemplo: Usar BinaryReader
En el siguiente ejemplo se crea una clase <xref:System.IO.BinaryReader> para leer los bytes desde **FileStream**, que se pasa a **BinaryReader** como argumento de su constructor. A continuación, <xref:System.IO.BinaryReader.ReadByte%2A> lee hasta que <xref:System.IO.BinaryReader.PeekChar%2A> no encuentra más bytes.  
  
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
