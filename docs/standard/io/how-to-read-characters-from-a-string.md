---
title: "Cómo: Leer caracteres de una cadena"
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
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9116ec63bfc1d12daf7627186a52bd29d5918485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="c3f86-102">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="c3f86-102">How to: Read Characters from a String</span></span>
<span data-ttu-id="c3f86-103">Ejemplos de código siguientes muestran cómo leer caracteres de forma sincrónica y asincrónica de una cadena.</span><span class="sxs-lookup"><span data-stu-id="c3f86-103">The following code examples show how to read characters synchronously and asynchronously from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3f86-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3f86-104">Example</span></span>  
 <span data-ttu-id="c3f86-105">Este ejemplo lee 13 caracteres sincrónicamente desde una cadena, almacenarlos en una matriz y se muestran los caracteres.</span><span class="sxs-lookup"><span data-stu-id="c3f86-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays those characters.</span></span> <span data-ttu-id="c3f86-106">A continuación, lee los caracteres restantes de la cadena, almacena en la matriz empezando por el sexto elemento y muestra el contenido de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c3f86-106">It then reads the remaining characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="c3f86-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3f86-107">Example</span></span>  
 <span data-ttu-id="c3f86-108">En el ejemplo siguiente se lee todos los caracteres de forma asincrónica desde una <xref:System.Windows.Controls.TextBox> controlar y los almacena en una matriz.</span><span class="sxs-lookup"><span data-stu-id="c3f86-108">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="c3f86-109">, A continuación, escribe de forma asincrónica cada carácter de letra o un espacio en blanco en una línea independiente, seguida de un salto de línea para un <xref:System.Windows.Controls.TextBlock> control.</span><span class="sxs-lookup"><span data-stu-id="c3f86-109">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c3f86-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3f86-110">See Also</span></span>  
 <xref:System.IO.StringReader>  
 <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
 <span data-ttu-id="c3f86-111">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)</span><span class="sxs-lookup"><span data-stu-id="c3f86-111">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)</span></span>  
 [<span data-ttu-id="c3f86-112">NIB: Cómo: crear una lista de directorios</span><span class="sxs-lookup"><span data-stu-id="c3f86-112">NIB: How to: Create a Directory Listing</span></span>](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="c3f86-113">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="c3f86-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="c3f86-114">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="c3f86-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="c3f86-115">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="c3f86-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="c3f86-116">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="c3f86-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="c3f86-117">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="c3f86-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="c3f86-118">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="c3f86-118">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
