---
title: Procedimiento Leer caracteres de una cadena
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
ms.openlocfilehash: 6d32e9c5f89dba7590958bae6cc0489f104cd19a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291778"
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="d4b5e-102">Procedimiento Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="d4b5e-102">How to: Read characters from a string</span></span>
<span data-ttu-id="d4b5e-103">En los ejemplos de código siguientes se muestra cómo leer caracteres desde una cadena de forma sincrónica o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="d4b5e-103">The following code examples show how to read characters synchronously or asynchronously from a string.</span></span>  
  
## <a name="example-read-characters-synchronously"></a><span data-ttu-id="d4b5e-104">Ejemplo: Leer caracteres de forma sincrónica</span><span class="sxs-lookup"><span data-stu-id="d4b5e-104">Example: Read characters synchronously</span></span>
 <span data-ttu-id="d4b5e-105">Este ejemplo lee trece caracteres de forma sincrónica de una cadena, los almacena en una matriz y los muestra.</span><span class="sxs-lookup"><span data-stu-id="d4b5e-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays them.</span></span> <span data-ttu-id="d4b5e-106">A continuación, el ejemplo lee el resto de los caracteres de la cadena, los almacena en la matriz a partir del sexto elemento y muestra el contenido de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d4b5e-106">The example then reads the rest of the characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a><span data-ttu-id="d4b5e-107">Ejemplo: Leer caracteres de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="d4b5e-107">Example: Read characters asynchronously</span></span>  
 <span data-ttu-id="d4b5e-108">El ejemplo siguiente es el código subyacente en una aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="d4b5e-108">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="d4b5e-109">En la carga de la ventana, el ejemplo lee todos los caracteres de forma asincrónica desde un control <xref:System.Windows.Controls.TextBox> y los almacena en una matriz.</span><span class="sxs-lookup"><span data-stu-id="d4b5e-109">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="d4b5e-110">Luego escribe de forma asincrónica cada carácter de letra o espacio en blanco en una línea independiente de un control <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="d4b5e-110">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d4b5e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4b5e-111">See also</span></span>

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="d4b5e-112">E/S de archivos asincrónica</span><span class="sxs-lookup"><span data-stu-id="d4b5e-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)  
- <span data-ttu-id="d4b5e-113">[Cómo: Crear una lista de directorios](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d4b5e-113">[How to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="d4b5e-114">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="d4b5e-114">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="d4b5e-115">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="d4b5e-115">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="d4b5e-116">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="d4b5e-116">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="d4b5e-117">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="d4b5e-117">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="d4b5e-118">Cómo: Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="d4b5e-118">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="d4b5e-119">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="d4b5e-119">File and stream I/O</span></span>](index.md)
