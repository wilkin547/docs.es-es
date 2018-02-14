---
title: "Cómo: Leer y escribir en un archivo de datos recién creado"
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
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 04ded71a23ba4cabab0a22e0d66c1084a726d8c8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="b1376-102">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="b1376-102">How to: Read and Write to a Newly Created Data File</span></span>
<span data-ttu-id="b1376-103">Las clases <xref:System.IO.BinaryWriter> y <xref:System.IO.BinaryReader?displayProperty=nameWithType> se usan para escribir y leer datos, en lugar de cadenas de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b1376-103">The <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data rather than character strings.</span></span> <span data-ttu-id="b1376-104">En el ejemplo de código siguiente se muestra cómo se escriben y se leen datos de una nueva secuencia de archivos vacía denominada `Test.data`.</span><span class="sxs-lookup"><span data-stu-id="b1376-104">The following example demonstrates how to write data to, and read data from, a new, empty file stream called `Test.data`.</span></span> <span data-ttu-id="b1376-105">Después de crear el archivo de datos en el directorio actual, se crean los objetos <xref:System.IO.BinaryWriter> y <xref:System.IO.BinaryReader> asociados, y se usa el objeto <xref:System.IO.BinaryWriter> para escribir los enteros de 0 a 10 en `Test.data`, que deja el puntero de archivo al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="b1376-105">After creating the data file in the current directory, the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects are created, and the <xref:System.IO.BinaryWriter> object is used to write the integers 0 through 10 to `Test.data`, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="b1376-106">Después de volver a establecer el puntero de archivo en el origen, el objeto <xref:System.IO.BinaryReader> lee el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="b1376-106">After setting the file pointer back to the origin, the <xref:System.IO.BinaryReader> object reads out the specified content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1376-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1376-107">Example</span></span>  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b1376-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b1376-108">Robust Programming</span></span>  
 <span data-ttu-id="b1376-109">Si `Test.data` ya existe en el directorio actual, se genera una excepción <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="b1376-109">If `Test.data` already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="b1376-110">Use la opción de modo de archivo <xref:System.IO.FileMode.Create?displayProperty=nameWithType> al inicializar la secuencia de archivo para crear siempre un archivo nuevo sin generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="b1376-110">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> when you initialize the file stream to always create a new file without throwing an  exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1376-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1376-111">See Also</span></span>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryWriter>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
 <xref:System.IO.SeekOrigin>  
 [<span data-ttu-id="b1376-112">Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="b1376-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="b1376-113">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="b1376-113">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="b1376-114">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="b1376-114">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="b1376-115">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="b1376-115">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="b1376-116">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="b1376-116">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="b1376-117">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="b1376-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="b1376-118">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="b1376-118">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
