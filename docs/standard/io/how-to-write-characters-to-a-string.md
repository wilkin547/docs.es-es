---
title: "Cómo: Escribir caracteres en una cadena"
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
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d409b9f9cada319c64c4b5a1315b8a5abbd731e9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="68adf-102">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="68adf-102">How to: Write Characters to a String</span></span>
<span data-ttu-id="68adf-103">Los siguientes ejemplos de código escriben caracteres de forma sincrónica y asincrónica desde una matriz de caracteres en una cadena.</span><span class="sxs-lookup"><span data-stu-id="68adf-103">The following code examples write characters synchronously and asynchronously from a character array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68adf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68adf-104">Example</span></span>  
 <span data-ttu-id="68adf-105">En el ejemplo siguiente se escriben cinco caracteres de forma sincrónica desde una matriz en una cadena.</span><span class="sxs-lookup"><span data-stu-id="68adf-105">The following example writes 5 characters synchronously from an array to a string.</span></span>  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="68adf-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68adf-106">Example</span></span>  
 <span data-ttu-id="68adf-107">En el ejemplo siguiente se leen todos los caracteres e forma asincrónica desde un control <xref:System.Windows.Controls.TextBox> y se almacenan en una matriz.</span><span class="sxs-lookup"><span data-stu-id="68adf-107">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="68adf-108">Luego escribe de forma asincrónica cada carácter de letra o espacio en blanco en una línea independiente seguida de un salto de línea en un control <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="68adf-108">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="68adf-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="68adf-109">See Also</span></span>  
 <xref:System.IO.StringWriter>  
 <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="68adf-110">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="68adf-110">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)  
 <span data-ttu-id="68adf-111">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)</span><span class="sxs-lookup"><span data-stu-id="68adf-111">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)</span></span>  
 [<span data-ttu-id="68adf-112">Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="68adf-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="68adf-113">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="68adf-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="68adf-114">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="68adf-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="68adf-115">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="68adf-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="68adf-116">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="68adf-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="68adf-117">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="68adf-117">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
