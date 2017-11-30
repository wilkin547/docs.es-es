---
title: "Cómo: Abrir y anexar a un archivo de registro"
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
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60c31339231405a1cbbb98dae37d36ad3c3709c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="ef492-102">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="ef492-102">How to: Open and Append to a Log File</span></span>
<span data-ttu-id="ef492-103"><xref:System.IO.StreamWriter>y <xref:System.IO.StreamReader> escriben y leen caracteres de secuencias.</span><span class="sxs-lookup"><span data-stu-id="ef492-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="ef492-104">El siguiente código en el ejemplo se abre la `log.txt` para la entrada de archivo, o crea el archivo si aún no existe y anexa información al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="ef492-104">The following code example opens the `log.txt` file for input, or creates the file if it does not already exist, and appends information to the end of the file.</span></span> <span data-ttu-id="ef492-105">El contenido del archivo, a continuación, se escribe en la salida estándar para su presentación.</span><span class="sxs-lookup"><span data-stu-id="ef492-105">The contents of the file are then written to standard output for display.</span></span> <span data-ttu-id="ef492-106">Como alternativa a este ejemplo, la información se puede almacenar como una sola cadena o una matriz de cadenas y el <xref:System.IO.File.WriteAllText%2A> o <xref:System.IO.File.WriteAllLines%2A> método podría utilizarse para lograr la misma funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="ef492-106">As an alternative to this example, the information could be stored as a single string or string array, and the <xref:System.IO.File.WriteAllText%2A> or <xref:System.IO.File.WriteAllLines%2A> method could be used to achieve the same functionality.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef492-107">Usuarios de Visual Basic pueden optar por usar los métodos y propiedades proporcionadas por el <xref:Microsoft.VisualBasic.Logging.Log> clase o <xref:Microsoft.VisualBasic.FileIO.FileSystem> clase para crear o escribir en archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="ef492-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef492-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef492-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ef492-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef492-109">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ef492-110">Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="ef492-110">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="ef492-111">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="ef492-111">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="ef492-112">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="ef492-112">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="ef492-113">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="ef492-113">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="ef492-114">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="ef492-114">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="ef492-115">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="ef492-115">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="ef492-116">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="ef492-116">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
