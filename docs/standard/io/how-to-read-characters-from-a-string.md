---
title: 'Cómo: Leer caracteres de una cadena'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 13a57f8ea7db91e5357ecfb20c4e907f2706f78d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44194973"
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="3b7cd-102">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="3b7cd-102">How to: Read Characters from a String</span></span>
<span data-ttu-id="3b7cd-103">En los ejemplos de código siguientes se muestra cómo leer caracteres desde una cadena de forma sincrónica y asincrónica.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-103">The following code examples show how to read characters synchronously and asynchronously from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b7cd-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b7cd-104">Example</span></span>  
 <span data-ttu-id="3b7cd-105">Este ejemplo lee trece caracteres de forma sincrónica de una cadena, los almacena en un matriz y muestra dichos caracteres.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays those characters.</span></span> <span data-ttu-id="3b7cd-106">A continuación, lee los caracteres restantes de la cadena, los almacena en la matriz a partir del sexto elemento y muestra el contenido de la matriz.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-106">It then reads the remaining characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="3b7cd-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b7cd-107">Example</span></span>  
 <span data-ttu-id="3b7cd-108">En el ejemplo siguiente se leen todos los caracteres e forma asincrónica desde un control <xref:System.Windows.Controls.TextBox> y se almacenan en una matriz.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-108">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="3b7cd-109">Luego escribe de forma asincrónica cada carácter de letra o espacio en blanco en una línea independiente seguida de un salto de línea en un control <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="3b7cd-109">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3b7cd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b7cd-110">See also</span></span>

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- <span data-ttu-id="3b7cd-111">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)</span><span class="sxs-lookup"><span data-stu-id="3b7cd-111">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)</span></span>  
- [<span data-ttu-id="3b7cd-112">Cómo: Crear una lista de directorios</span><span class="sxs-lookup"><span data-stu-id="3b7cd-112">NIB: How to: Create a Directory Listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
- [<span data-ttu-id="3b7cd-113">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="3b7cd-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="3b7cd-114">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="3b7cd-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="3b7cd-115">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="3b7cd-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="3b7cd-116">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="3b7cd-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="3b7cd-117">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="3b7cd-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="3b7cd-118">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="3b7cd-118">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
