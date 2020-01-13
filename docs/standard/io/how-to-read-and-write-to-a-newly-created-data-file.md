---
title: Procedimiento Leer y escribir en un archivo de datos recién creado
ms.date: 01/21/2019
ms.technology: dotnet-standard
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
ms.openlocfilehash: 0bb06f42542d6acb3214fd4a1a3ca5c54f7caab2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706704"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="f4126-102">Procedimiento Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="f4126-102">How to: Read and write to a newly created data file</span></span>
<span data-ttu-id="f4126-103">Las clases <xref:System.IO.BinaryWriter?displayProperty=nameWithType> y <xref:System.IO.BinaryReader?displayProperty=nameWithType> se usan para escribir y leer datos distintos de cadenas de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f4126-103">The <xref:System.IO.BinaryWriter?displayProperty=nameWithType> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data other than character strings.</span></span> <span data-ttu-id="f4126-104">En el ejemplo siguiente se muestra cómo se crea un flujo de archivos vacío y cómo se escriben y se leen datos de este.</span><span class="sxs-lookup"><span data-stu-id="f4126-104">The following example shows how to create an empty file stream, write data to it, and read data from it.</span></span> 

<span data-ttu-id="f4126-105">El ejemplo crea un archivo de datos llamado *Test.data* en el directorio actual, crea los objetos <xref:System.IO.BinaryWriter> y <xref:System.IO.BinaryReader> asociados y usa el objeto <xref:System.IO.BinaryWriter> para escribir los enteros de 0 a 10 en *Test.data*, que deja el puntero de archivo al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="f4126-105">The example creates a data file called *Test.data* in the current directory, creates the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects, and uses the <xref:System.IO.BinaryWriter> object to write the integers 0 through 10 to *Test.data*, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="f4126-106">A continuación, el objeto <xref:System.IO.BinaryReader> vuelve a establecer el puntero de archivo en el origen y lee el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="f4126-106">The <xref:System.IO.BinaryReader> object then sets the file pointer back to the origin and reads out the specified content.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4126-107">Si *Test.data* ya existe en el directorio actual, se genera una excepción <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="f4126-107">If *Test.data* already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="f4126-108">Use la opción de modo de archivo <xref:System.IO.FileMode.Create?displayProperty=nameWithType> en lugar de <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> para crear siempre un archivo nuevo sin generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="f4126-108">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> rather than <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> to always create a new file without throwing an exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4126-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4126-109">Example</span></span>  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="f4126-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4126-110">See also</span></span>

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [<span data-ttu-id="f4126-111">Cómo: Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="f4126-111">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="f4126-112">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="f4126-112">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="f4126-113">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="f4126-113">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="f4126-114">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="f4126-114">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="f4126-115">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="f4126-115">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="f4126-116">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="f4126-116">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="f4126-117">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="f4126-117">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
