---
title: Procedimiento Escribir caracteres en una cadena
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
ms.openlocfilehash: 21661a858cff9fc8bc84d497b4af8bedb1393f0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734535"
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="0d507-102">Procedimiento Escribir caracteres en una cadena</span><span class="sxs-lookup"><span data-stu-id="0d507-102">How to: Write characters to a string</span></span>

<span data-ttu-id="0d507-103">Los siguientes ejemplos de código escriben caracteres de forma sincrónica y asincrónica desde una matriz de caracteres en una cadena.</span><span class="sxs-lookup"><span data-stu-id="0d507-103">The following code examples write characters synchronously or asynchronously from a character array into a string.</span></span>  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a><span data-ttu-id="0d507-104">Ejemplo: Escribir caracteres de forma sincrónica en una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="0d507-104">Example: Write characters synchronously in a console app</span></span>  

 <span data-ttu-id="0d507-105">En el siguiente ejemplo se usa un <xref:System.IO.StringWriter> para escribir cinco caracteres de forma sincrónica en un objeto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="0d507-105">The following example uses a <xref:System.IO.StringWriter> to write five characters synchronously to a <xref:System.Text.StringBuilder> object.</span></span>
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a><span data-ttu-id="0d507-106">Ejemplo: Escribir caracteres de forma asincrónica en una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="0d507-106">Example: Write characters asynchronously in a WPF app</span></span>

 <span data-ttu-id="0d507-107">El ejemplo siguiente es el código subyacente en una aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="0d507-107">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="0d507-108">En la carga de la ventana, el ejemplo lee todos los caracteres de forma asincrónica desde un control <xref:System.Windows.Controls.TextBox> y los almacena en una matriz.</span><span class="sxs-lookup"><span data-stu-id="0d507-108">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="0d507-109">Luego escribe de forma asincrónica cada carácter de letra o espacio en blanco en una línea independiente de un control <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="0d507-109">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0d507-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d507-110">See also</span></span>

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [<span data-ttu-id="0d507-111">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="0d507-111">File and stream I/O</span></span>](index.md)  
- [<span data-ttu-id="0d507-112">E/S de archivos asincrónica</span><span class="sxs-lookup"><span data-stu-id="0d507-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)  
- [<span data-ttu-id="0d507-113">Cómo: Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="0d507-113">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="0d507-114">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="0d507-114">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="0d507-115">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="0d507-115">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="0d507-116">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="0d507-116">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="0d507-117">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="0d507-117">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="0d507-118">Cómo: Leer caracteres de una cadena</span><span class="sxs-lookup"><span data-stu-id="0d507-118">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)
