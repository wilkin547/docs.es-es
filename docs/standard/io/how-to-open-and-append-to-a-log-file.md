---
title: Procedimiento Abrir y anexar a un archivo de registro
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
ms.openlocfilehash: a549aba3a763bcfc5a3889efd65e2495eca7622c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155716"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="d04be-102">Procedimiento Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="d04be-102">How to: Open and append to a log file</span></span>
<span data-ttu-id="d04be-103"><xref:System.IO.StreamWriter> y <xref:System.IO.StreamReader> escriben y leen caracteres de secuencias.</span><span class="sxs-lookup"><span data-stu-id="d04be-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="d04be-104">En el siguiente ejemplo de código se abre el archivo *log.txt* para realizar entradas o se crea el archivo en caso de que no exista y se adjunta información de registro al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="d04be-104">The following code example opens the *log.txt* file for input, or creates it if it doesn't exist, and appends log information to the end of the file.</span></span> <span data-ttu-id="d04be-105">El ejemplo, a continuación, escribe el contenido del archivo en la salida estándar para su presentación.</span><span class="sxs-lookup"><span data-stu-id="d04be-105">The example then writes the contents of the file to standard output for display.</span></span>

<span data-ttu-id="d04be-106">Como alternativa a este ejemplo, podría almacenar la información como una sola cadena o como una matriz de cadenas, y usar el método <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> o <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> para lograr la misma funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="d04be-106">As an alternative to this example, you could store the information as a single string or string array, and use the <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> or <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> method to achieve the same functionality.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d04be-107">Los usuarios de Visual Basic tienen la opción de utilizar los métodos y las propiedades proporcionados por las clases <xref:Microsoft.VisualBasic.Logging.Log> o <xref:Microsoft.VisualBasic.FileIO.FileSystem> para crear archivos de registro o escribir en ellos.</span><span class="sxs-lookup"><span data-stu-id="d04be-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d04be-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d04be-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d04be-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d04be-109">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="d04be-110">Cómo: Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="d04be-110">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="d04be-111">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="d04be-111">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="d04be-112">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="d04be-112">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="d04be-113">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="d04be-113">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="d04be-114">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="d04be-114">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="d04be-115">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="d04be-115">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="d04be-116">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="d04be-116">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
