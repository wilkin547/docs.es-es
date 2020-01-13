---
title: Redactar flujos
ms.date: 01/21/2019
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
ms.openlocfilehash: 689cc9537cd7a5fe6a677d42e5790bbcf1b3aefa
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708153"
---
# <a name="compose-streams"></a><span data-ttu-id="d8f57-102">Redactar flujos</span><span class="sxs-lookup"><span data-stu-id="d8f57-102">Compose streams</span></span>
<span data-ttu-id="d8f57-103">Una *memoria auxiliar* es un medio de almacenamiento, como un disco o memoria.</span><span class="sxs-lookup"><span data-stu-id="d8f57-103">A *backing store* is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="d8f57-104">Cada memoria auxiliar distinta implementa su propia secuencia como una implementación de la clase <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="d8f57-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> 

<span data-ttu-id="d8f57-105">Cada tipo de secuencia lee y escribe los bytes desde y en su memoria auxiliar determinada.</span><span class="sxs-lookup"><span data-stu-id="d8f57-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="d8f57-106">Los flujos que se conectan a las memorias auxiliares reciben el nombre de *secuencias base*.</span><span class="sxs-lookup"><span data-stu-id="d8f57-106">Streams that connect to backing stores are called *base streams*.</span></span> <span data-ttu-id="d8f57-107">Las secuencias base tienen constructores con los parámetros necesarios para conectar el flujo a la memoria auxiliar.</span><span class="sxs-lookup"><span data-stu-id="d8f57-107">Base streams have constructors with the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="d8f57-108">Por ejemplo, <xref:System.IO.FileStream> tiene constructores que especifican un parámetro de ruta de acceso, que especifica cómo los procesos compartirán el archivo.</span><span class="sxs-lookup"><span data-stu-id="d8f57-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes.</span></span>  

<span data-ttu-id="d8f57-109">El diseño de las clases <xref:System.IO> proporciona la composición de flujos simplificada.</span><span class="sxs-lookup"><span data-stu-id="d8f57-109">The design of the <xref:System.IO> classes provides simplified stream composition.</span></span> <span data-ttu-id="d8f57-110">Puede asociar las secuencias base a uno o varios flujos de paso a través que proporcionan la funcionalidad que desee.</span><span class="sxs-lookup"><span data-stu-id="d8f57-110">You can attach base streams to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="d8f57-111">Puede asociar un lector o escritor al final de la cadena para que los tipos deseados se puedan leer o escribir con facilidad.</span><span class="sxs-lookup"><span data-stu-id="d8f57-111">You can attach a reader or writer to the end of the chain, so the preferred types can be read or written easily.</span></span>  

<span data-ttu-id="d8f57-112">En los ejemplos de código siguientes se crea una clase **FileStream** en torno al archivo *MyFile.txt* para almacenar *MyFile.txt* en el búfer.</span><span class="sxs-lookup"><span data-stu-id="d8f57-112">The following code examples create a **FileStream** around the existing *MyFile.txt* in order to buffer *MyFile.txt*.</span></span> <span data-ttu-id="d8f57-113">Tenga en cuenta que las clases **FileStreams** se almacenan en búfer de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d8f57-113">Note that **FileStreams** are buffered by default.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d8f57-114">En los ejemplos, se da por supuesto que un archivo llamado *MyFile.txt* ya existe en la misma carpeta que la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8f57-114">The examples assume that a file named *MyFile.txt* already exists in the same folder as the app.</span></span>  

## <a name="example-use-streamreader"></a><span data-ttu-id="d8f57-115">Ejemplo: Usar StreamReader</span><span class="sxs-lookup"><span data-stu-id="d8f57-115">Example: Use StreamReader</span></span>
<span data-ttu-id="d8f57-116">En el siguiente ejemplo se crea una clase <xref:System.IO.StreamReader> para leer los caracteres desde **FileStream**, que se pasa a **StreamReader** como argumento de su constructor.</span><span class="sxs-lookup"><span data-stu-id="d8f57-116">The following example creates a <xref:System.IO.StreamReader> to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="d8f57-117">A continuación, <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> lee hasta que <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> no encuentra más caracteres.</span><span class="sxs-lookup"><span data-stu-id="d8f57-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> then reads until <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> finds no more characters.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a><span data-ttu-id="d8f57-118">Ejemplo: Usar BinaryReader</span><span class="sxs-lookup"><span data-stu-id="d8f57-118">Example: Use BinaryReader</span></span>
<span data-ttu-id="d8f57-119">En el siguiente ejemplo se crea una clase <xref:System.IO.BinaryReader> para leer los bytes desde **FileStream**, que se pasa a **BinaryReader** como argumento de su constructor.</span><span class="sxs-lookup"><span data-stu-id="d8f57-119">The following example creates a <xref:System.IO.BinaryReader> to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="d8f57-120">A continuación, <xref:System.IO.BinaryReader.ReadByte%2A> lee hasta que <xref:System.IO.BinaryReader.PeekChar%2A> no encuentra más bytes.</span><span class="sxs-lookup"><span data-stu-id="d8f57-120"><xref:System.IO.BinaryReader.ReadByte%2A> then reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="d8f57-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8f57-121">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
