---
title: 'Cómo: Leer texto de un archivo'
ms.date: 03/30/2017
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
ms.openlocfilehash: 0bb37c5beaaa529ea09fa23f31b55a0d6bc6d510
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574535"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="8c168-102">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="8c168-102">How to: Read Text from a File</span></span>
<span data-ttu-id="8c168-103">En los ejemplos siguientes se muestra cómo leer texto desde un archivo de texto de forma sincrónica y asincrónica mediante .NET para aplicaciones de escritorio.</span><span class="sxs-lookup"><span data-stu-id="8c168-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="8c168-104">En ambos ejemplos, cuando se crea la instancia de la clase <xref:System.IO.StreamReader>, se proporciona la ruta de acceso relativa o absoluta del archivo.</span><span class="sxs-lookup"><span data-stu-id="8c168-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> <span data-ttu-id="8c168-105">En los ejemplos siguientes se supone que el archivo denominado TestFile.txt está en la misma carpeta que la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8c168-105">The following examples assume that the file named TestFile.txt is in the same folder as the application.</span></span>  
  
 <span data-ttu-id="8c168-106">Estos ejemplos de código no se pueden aplicar al desarrollo de aplicaciones de la Tienda Windows porque Windows Runtime ofrece diferentes tipos de secuencias al leer archivos o escribir en ellos.</span><span class="sxs-lookup"><span data-stu-id="8c168-106">These code examples do not apply developing for Windows Store Apps because the Windows Runtime provides different streams types reading and writing to files.</span></span> <span data-ttu-id="8c168-107">Para obtener un ejemplo acerca de cómo leer el texto de un archivo en el contexto de una aplicación de la Tienda Windows, vea [Inicio rápido: lectura y escritura de un archivo](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c168-107">For an example that shows how to read text from a file within the context of a Windows Store app, see [Quickstart: Reading and writing files](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).</span></span> <span data-ttu-id="8c168-108">Para obtener ejemplos que muestren cómo convertir entre secuencias de .NET Framework y secuencias de Windows Runtime, consulte [Cómo: Convertir entre secuencias .NET Framework y secuencias de Windows Runtime](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="8c168-108">For examples that show how to convert between .NET Framework streams and Windows runtime streams see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c168-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c168-109">Example</span></span>  
 <span data-ttu-id="8c168-110">El primer ejemplo muestra una operación de lectura sincrónica dentro de una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="8c168-110">The first example shows a synchronous read operation within a console application.</span></span> <span data-ttu-id="8c168-111">En este ejemplo, el archivo de texto se abre con un lector de secuencias, el contenido se copia en una cadena y la cadena se envía a la consola.</span><span class="sxs-lookup"><span data-stu-id="8c168-111">In this example, the text file is opened using a stream reader, the contents are copied to a string and string is output to the console.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="8c168-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c168-112">Example</span></span>  
 <span data-ttu-id="8c168-113">El segundo ejemplo muestra una operación de lectura asincrónica dentro de una aplicación de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="8c168-113">The second example shows an asynchronous read operation within a Windows Presentation Foundation (WPF) application.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8c168-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c168-114">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <span data-ttu-id="8c168-115">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)</span><span class="sxs-lookup"><span data-stu-id="8c168-115">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)</span></span>  
 [<span data-ttu-id="8c168-116">Cómo: Crear una lista de directorios</span><span class="sxs-lookup"><span data-stu-id="8c168-116">NIB: How to: Create a Directory Listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="8c168-117">Inicio rápido: lectura y escritura de un archivo</span><span class="sxs-lookup"><span data-stu-id="8c168-117">Quickstart: Reading and writing files</span></span>](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [<span data-ttu-id="8c168-118">Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa</span><span class="sxs-lookup"><span data-stu-id="8c168-118">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [<span data-ttu-id="8c168-119">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="8c168-119">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="8c168-120">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="8c168-120">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="8c168-121">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="8c168-121">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="8c168-122">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="8c168-122">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="8c168-123">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="8c168-123">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="8c168-124">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="8c168-124">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
