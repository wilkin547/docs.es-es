---
title: Procedimiento Abrir y anexar a un archivo de registro
description: Abra y anexe a un archivo de registro con las clases StreamWriter y StreamReader en .NET, que escriben y leen caracteres en las secuencias.
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
ms.openlocfilehash: f92dd34b15ca79f229b365c7c2db4ace411d9353
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830758"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="c5380-103">Procedimiento Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="c5380-103">How to: Open and append to a log file</span></span>

<span data-ttu-id="c5380-104"><xref:System.IO.StreamWriter> y <xref:System.IO.StreamReader> escriben y leen caracteres de secuencias.</span><span class="sxs-lookup"><span data-stu-id="c5380-104"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="c5380-105">En el siguiente ejemplo de código se abre el archivo *log.txt* para realizar entradas o se crea el archivo en caso de que no exista y se adjunta información de registro al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="c5380-105">The following code example opens the *log.txt* file for input, or creates it if it doesn't exist, and appends log information to the end of the file.</span></span> <span data-ttu-id="c5380-106">El ejemplo, a continuación, escribe el contenido del archivo en la salida estándar para su presentación.</span><span class="sxs-lookup"><span data-stu-id="c5380-106">The example then writes the contents of the file to standard output for display.</span></span>

<span data-ttu-id="c5380-107">Como alternativa a este ejemplo, podría almacenar la información como una sola cadena o como una matriz de cadenas, y usar el método <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> o <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> para lograr la misma funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="c5380-107">As an alternative to this example, you could store the information as a single string or string array, and use the <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> or <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> method to achieve the same functionality.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5380-108">Los usuarios de Visual Basic tienen la opción de utilizar los métodos y las propiedades proporcionados por las clases <xref:Microsoft.VisualBasic.Logging.Log> o <xref:Microsoft.VisualBasic.FileIO.FileSystem> para crear archivos de registro o escribir en ellos.</span><span class="sxs-lookup"><span data-stu-id="c5380-108">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5380-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5380-109">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c5380-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5380-110">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="c5380-111">Cómo: Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="c5380-111">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="c5380-112">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="c5380-112">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="c5380-113">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="c5380-113">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="c5380-114">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="c5380-114">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="c5380-115">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="c5380-115">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="c5380-116">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="c5380-116">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="c5380-117">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="c5380-117">File and stream I/O</span></span>](index.md)
