---
title: Procedimiento para leer texto de un archivo
ms.date: 06/19/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f667b0a757a676788b693691504512dfc227a7e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646677"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="852d3-102">Procedimiento para leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="852d3-102">How to: Read Text from a File</span></span>
<span data-ttu-id="852d3-103">En los ejemplos siguientes se muestra cómo leer texto desde un archivo de texto de forma sincrónica y asincrónica mediante .NET para aplicaciones de escritorio.</span><span class="sxs-lookup"><span data-stu-id="852d3-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="852d3-104">En ambos ejemplos, cuando se crea la instancia de la clase <xref:System.IO.StreamReader>, se proporciona la ruta de acceso relativa o absoluta del archivo.</span><span class="sxs-lookup"><span data-stu-id="852d3-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> <span data-ttu-id="852d3-105">En los ejemplos siguientes se supone que el archivo denominado TestFile.txt está en la misma carpeta que la aplicación.</span><span class="sxs-lookup"><span data-stu-id="852d3-105">The following examples assume that the file named TestFile.txt is in the same folder as the application.</span></span>  
  
 <span data-ttu-id="852d3-106">Estos ejemplos de código no se pueden aplicar al desarrollo de aplicaciones de la Tienda Windows porque Windows Runtime ofrece diferentes tipos de secuencias para leer archivos o escribir en ellos.</span><span class="sxs-lookup"><span data-stu-id="852d3-106">These code examples do not apply to developing for Windows Store Apps because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="852d3-107">Para obtener un ejemplo en el que se muestra cómo leer el texto de un archivo en una aplicación de Microsoft Store, vea [Inicio rápido: lectura y escritura de un archivo](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="852d3-107">For an example that shows how to read text from a file in a Windows Store app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="852d3-108">Para obtener ejemplos en los que se muestra cómo convertir entre las secuencias de .NET Framework y las de tiempo de ejecución de Windows, vea [Cómo: Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="852d3-108">For examples that show how to convert between .NET Framework streams and Windows runtime streams, see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="852d3-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="852d3-109">Example</span></span>  
 <span data-ttu-id="852d3-110">En el siguiente ejemplo se muestra una operación de lectura sincrónica dentro de una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="852d3-110">The following example shows a synchronous read operation within a console application.</span></span> <span data-ttu-id="852d3-111">En este ejemplo, el archivo de texto se abre con un lector de secuencias, el contenido se copia en una cadena y la cadena se envía a la consola.</span><span class="sxs-lookup"><span data-stu-id="852d3-111">In this example, the text file is opened using a stream reader, the contents are copied to a string, and the string is output to the console.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="852d3-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="852d3-112">Example</span></span>  
 <span data-ttu-id="852d3-113">En el siguiente ejemplo se muestra una operación de lectura asincrónica en una aplicación de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="852d3-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="852d3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="852d3-114">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- [<span data-ttu-id="852d3-115">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="852d3-115">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
- [<span data-ttu-id="852d3-116">NIB: Procedimiento para crear una lista de directorios</span><span class="sxs-lookup"><span data-stu-id="852d3-116">NIB: How to: Create a Directory Listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)
- [<span data-ttu-id="852d3-117">Inicio rápido: lectura y escritura de archivos</span><span class="sxs-lookup"><span data-stu-id="852d3-117">Quickstart: Reading and writing files</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)
- [<span data-ttu-id="852d3-118">Cómo: Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa</span><span class="sxs-lookup"><span data-stu-id="852d3-118">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
- [<span data-ttu-id="852d3-119">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="852d3-119">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [<span data-ttu-id="852d3-120">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="852d3-120">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [<span data-ttu-id="852d3-121">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="852d3-121">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [<span data-ttu-id="852d3-122">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="852d3-122">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
- [<span data-ttu-id="852d3-123">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="852d3-123">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)
- [<span data-ttu-id="852d3-124">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="852d3-124">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
