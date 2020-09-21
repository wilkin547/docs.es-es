---
title: Procedimiento Leer caracteres de una cadena
description: Aprenda a leer caracteres de una cadena en .NET. Vea ejemplos de lectura sincrónica y asincrónica de caracteres.
ms.date: 01/21/2019
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
ms.openlocfilehash: fa03d13036e9e245b8ca3f8c3218ae80a2762a12
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553953"
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="97aba-104">Procedimiento Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="97aba-104">How to: Read characters from a string</span></span>
<span data-ttu-id="97aba-105">En los ejemplos de código siguientes se muestra cómo leer caracteres desde una cadena de forma sincrónica o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="97aba-105">The following code examples show how to read characters synchronously or asynchronously from a string.</span></span>  
  
## <a name="example-read-characters-synchronously"></a><span data-ttu-id="97aba-106">Ejemplo: Leer caracteres de forma sincrónica</span><span class="sxs-lookup"><span data-stu-id="97aba-106">Example: Read characters synchronously</span></span>
 <span data-ttu-id="97aba-107">Este ejemplo lee trece caracteres de forma sincrónica de una cadena, los almacena en una matriz y los muestra.</span><span class="sxs-lookup"><span data-stu-id="97aba-107">This example reads 13 characters synchronously from a string, stores them in an array, and displays them.</span></span> <span data-ttu-id="97aba-108">A continuación, el ejemplo lee el resto de los caracteres de la cadena, los almacena en la matriz a partir del sexto elemento y muestra el contenido de la matriz.</span><span class="sxs-lookup"><span data-stu-id="97aba-108">The example then reads the rest of the characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a><span data-ttu-id="97aba-109">Ejemplo: Leer caracteres de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="97aba-109">Example: Read characters asynchronously</span></span>  
 <span data-ttu-id="97aba-110">El ejemplo siguiente es el código subyacente en una aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="97aba-110">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="97aba-111">En la carga de la ventana, el ejemplo lee todos los caracteres de forma asincrónica desde un control <xref:System.Windows.Controls.TextBox> y los almacena en una matriz.</span><span class="sxs-lookup"><span data-stu-id="97aba-111">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="97aba-112">Luego escribe de forma asincrónica cada carácter de letra o espacio en blanco en una línea independiente de un control <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="97aba-112">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="97aba-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="97aba-113">See also</span></span>

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="97aba-114">E/S de archivos asincrónica</span><span class="sxs-lookup"><span data-stu-id="97aba-114">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)  
- <span data-ttu-id="97aba-115">[Cómo: Crear una lista de directorios](/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="97aba-115">[How to: Create a directory listing](/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="97aba-116">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="97aba-116">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="97aba-117">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="97aba-117">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="97aba-118">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="97aba-118">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="97aba-119">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="97aba-119">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="97aba-120">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="97aba-120">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="97aba-121">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="97aba-121">File and stream I/O</span></span>](index.md)
