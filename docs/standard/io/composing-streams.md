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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d49661e93675b80bcd579a6cd341b3dc88a688c2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="composing-streams"></a><span data-ttu-id="6d014-102">Crear secuencias</span><span class="sxs-lookup"><span data-stu-id="6d014-102">Composing Streams</span></span>
<span data-ttu-id="6d014-103">Una memoria auxiliar es un medio de almacenamiento, como un disco o memoria.</span><span class="sxs-lookup"><span data-stu-id="6d014-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="6d014-104">Cada memoria auxiliar distinta implementa su propia secuencia como una implementación de la clase <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="6d014-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="6d014-105">Cada tipo de secuencia lee y escribe los bytes desde y en su memoria auxiliar determinada.</span><span class="sxs-lookup"><span data-stu-id="6d014-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="6d014-106">Las secuencias que se conectan a las memorias auxiliares reciben el nombre de secuencias base.</span><span class="sxs-lookup"><span data-stu-id="6d014-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="6d014-107">Las secuencias base tienen constructores que disponen de los parámetros necesarios para conectar la secuencia a la memoria auxiliar.</span><span class="sxs-lookup"><span data-stu-id="6d014-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="6d014-108">Por ejemplo, <xref:System.IO.FileStream> tiene constructores que especifican un parámetro de ruta de acceso, que especifica cómo los procesos compartirán el archivo, etc.</span><span class="sxs-lookup"><span data-stu-id="6d014-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="6d014-109">El diseño de las clases <xref:System.IO> proporciona la composición de secuencias simplificada.</span><span class="sxs-lookup"><span data-stu-id="6d014-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="6d014-110">Las secuencias base pueden adjuntarse a una o varias secuencias de paso a través que proporcionan la funcionalidad que desee.</span><span class="sxs-lookup"><span data-stu-id="6d014-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="6d014-111">Un lector o escritor puede adjuntarse al final de la cadena para que los tipos deseados se puedan leer o escribir con facilidad.</span><span class="sxs-lookup"><span data-stu-id="6d014-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="6d014-112">En el ejemplo de código siguiente se crea una clase **FileStream** en torno al archivo `MyFile.txt` para almacenar `MyFile.txt` en el búfer.</span><span class="sxs-lookup"><span data-stu-id="6d014-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="6d014-113">(Tenga en cuenta que las clases **FileStreams** se almacenan en búfer de forma predeterminada). Después, se crea una clase <xref:System.IO.StreamReader> para leer los caracteres desde **FileStream**, que se pasa a **StreamReader** como argumento de su constructor.</span><span class="sxs-lookup"><span data-stu-id="6d014-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="6d014-114"><xref:System.IO.StreamReader.ReadLine%2A> lee hasta que <xref:System.IO.StreamReader.Peek%2A> no encuentra más caracteres.</span><span class="sxs-lookup"><span data-stu-id="6d014-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="6d014-115">En el ejemplo de código siguiente se crea una clase **FileStream** en torno al archivo `MyFile.txt` para almacenar `MyFile.txt` en el búfer.</span><span class="sxs-lookup"><span data-stu-id="6d014-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="6d014-116">(Tenga en cuenta que las clases **FileStreams** se almacenan en búfer de forma predeterminada). Después, se crea una clase **BinaryReader** para leer los bytes desde **FileStream**, que se pasa a **BinaryReader** como argumento de su constructor.</span><span class="sxs-lookup"><span data-stu-id="6d014-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="6d014-117"><xref:System.IO.BinaryReader.ReadByte%2A> lee hasta que <xref:System.IO.BinaryReader.PeekChar%2A> no encuentra más bytes.</span><span class="sxs-lookup"><span data-stu-id="6d014-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="6d014-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d014-118">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
