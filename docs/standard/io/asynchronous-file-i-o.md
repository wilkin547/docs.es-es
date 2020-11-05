---
title: E/S de archivos asincrónica
description: Obtenga información sobre la E/S de archivos asincrónica en .NET. Obtenga información sobre métodos asincrónicos para simplificar operaciones asincrónicas, como ReadAsync, WriteAsync, etc.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, synchronous streams
- asynchronous I/O
- synchronous I/O
- streams, asynchronous streams
- I/O [.NET], asynchronous I/O
- Stream class, synchronous I/O
- data streams, asynchronous streams
- Stream class, asynchronous I/O
- multiple I/O requests
- data streams, synchronous streams
ms.assetid: dbdd55e7-d6b9-4f9e-8abb-ab0edd4457f7
ms.openlocfilehash: a148e6e13ec0ee4ee469a0630f150199c5a3af13
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188606"
---
# <a name="asynchronous-file-io"></a><span data-ttu-id="2e6cb-104">E/S de archivos asincrónica</span><span class="sxs-lookup"><span data-stu-id="2e6cb-104">Asynchronous File I/O</span></span>

<span data-ttu-id="2e6cb-105">Las operaciones asincrónicas permiten realizar operaciones de E/S que hacen un uso intensivo de recursos sin bloquear el subproceso principal.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-105">Asynchronous operations enable you to perform resource-intensive I/O operations without blocking the main thread.</span></span> <span data-ttu-id="2e6cb-106">Esta consideración de rendimiento es especialmente importante en una aplicación de la Tienda Windows 8.x o una aplicación de escritorio en que una operación de streaming prolongada puede bloquear el subproceso de interfaz de usuario y hacer que parezca que una aplicación ha dejado de responder.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-106">This performance consideration is particularly important in a Windows 8.x Store app or desktop app where a time-consuming stream operation can block the UI thread and make your app appear as if it is not working.</span></span>

<span data-ttu-id="2e6cb-107">A partir de .NET Framework 4.5, los tipos de E/S incluyen métodos asincrónicos para simplificar las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-107">Starting with .NET Framework 4.5, the I/O types include async methods to simplify asynchronous operations.</span></span> <span data-ttu-id="2e6cb-108">Un método asincrónico contiene `Async` en su nombre, como <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>y <xref:System.IO.TextReader.ReadToEndAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-108">An async method contains `Async` in its name, such as <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>, and <xref:System.IO.TextReader.ReadToEndAsync%2A>.</span></span> <span data-ttu-id="2e6cb-109">Estos métodos asincrónicos se implementan en clases de secuencias, como <xref:System.IO.Stream>, <xref:System.IO.FileStream>y <xref:System.IO.MemoryStream>, y en las clases de las que se usan para leer o escribir en secuencias, como <xref:System.IO.TextReader> y <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-109">These async methods are implemented on stream classes, such as <xref:System.IO.Stream>, <xref:System.IO.FileStream>, and <xref:System.IO.MemoryStream>, and on classes that are used for reading from or writing to streams, such <xref:System.IO.TextReader> and <xref:System.IO.TextWriter>.</span></span>

<span data-ttu-id="2e6cb-110">En .NET Framework 4 y versiones anteriores, es necesario usar métodos como <xref:System.IO.Stream.BeginRead%2A> y <xref:System.IO.Stream.EndRead%2A> para implementar operaciones de E/S asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-110">In .NET Framework 4 and earlier versions, you have to use methods such as <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> to implement asynchronous I/O operations.</span></span> <span data-ttu-id="2e6cb-111">Estos métodos siguen disponibles en las versiones actuales de .NET para admitir código heredado, pero los métodos asincrónicos facilitan la implementación de operaciones de E/S asincrónicas con más facilidad.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-111">These methods are still available in current .NET versions to support legacy code; however, the async methods help you implement asynchronous I/O operations more easily.</span></span>

<span data-ttu-id="2e6cb-112">C# y Visual Basic tienen dos palabras clave para la programación asincrónica:</span><span class="sxs-lookup"><span data-stu-id="2e6cb-112">C# and Visual Basic each have two keywords for asynchronous programming:</span></span>

- <span data-ttu-id="2e6cb-113">El modificador`Async` (Visual Basic) o `async` (C#), que se utiliza para marcar un método que contiene una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-113">`Async` (Visual Basic) or `async` (C#) modifier, which is used to mark a method that contains an asynchronous operation.</span></span>

- <span data-ttu-id="2e6cb-114">El operador`Await` (Visual Basic) o `await` (C#), que se aplica al resultado de un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-114">`Await` (Visual Basic) or `await` (C#) operator, which is applied to the result of an async method.</span></span>

<span data-ttu-id="2e6cb-115">Para implementar operaciones de E/S asincrónicas, use estas palabras clave junto con los métodos asincrónicos, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-115">To implement asynchronous I/O operations, use these keywords in conjunction with the async methods, as shown in the following examples.</span></span> <span data-ttu-id="2e6cb-116">Para obtener más información, vea [Programación asincrónica con Async y Await (C#)](../../csharp/programming-guide/concepts/async/index.md) y [Programación asincrónica con Async y Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="2e6cb-116">For more information, see [Asynchronous programming with async and await (C#)](../../csharp/programming-guide/concepts/async/index.md) or [Asynchronous Programming with Async and Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="2e6cb-117">En el ejemplo siguiente se muestra cómo usar dos objetos <xref:System.IO.FileStream> para copiar archivos de forma asincrónica de un directorio en otro.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-117">The following example demonstrates how to use two <xref:System.IO.FileStream> objects to copy files asynchronously from one directory to another.</span></span> <span data-ttu-id="2e6cb-118">Observe que el controlador de eventos <xref:System.Web.UI.WebControls.Button.Click> para el control <xref:System.Windows.Controls.Button> está marcado con el modificador `async` porque llama a un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-118">Notice that the <xref:System.Web.UI.WebControls.Button.Click> event handler for the <xref:System.Windows.Controls.Button> control is marked with the `async` modifier because it calls an asynchronous method.</span></span>

[!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
[!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]

<span data-ttu-id="2e6cb-119">El ejemplo siguiente es similar al anterior, pero utiliza objetos <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter> para leer y escribir el contenido de un archivo de texto de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-119">The next example is similar to the previous one but uses <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> objects to read and write the contents of a text file asynchronously.</span></span>

[!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
[!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]

<span data-ttu-id="2e6cb-120">En el ejemplo siguiente se muestra el archivo de código subyacente y el archivo XAML que se usan para abrir un archivo como <xref:System.IO.Stream> en una aplicación de la Tienda Windows 8.x y leer su contenido mediante una instancia de la clase <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-120">The next example shows the code-behind file and the XAML file that are used to open a file as a <xref:System.IO.Stream> in a Windows 8.x Store app, and read its contents by using an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="2e6cb-121">Utiliza métodos asincrónicos para abrir el archivo como secuencia y leer su contenido.</span><span class="sxs-lookup"><span data-stu-id="2e6cb-121">It uses asynchronous methods to open the file as a stream and to read its contents.</span></span>

[!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
[!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]

[!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]

## <a name="see-also"></a><span data-ttu-id="2e6cb-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e6cb-122">See also</span></span>

- <xref:System.IO.Stream>
- [<span data-ttu-id="2e6cb-123">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="2e6cb-123">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="2e6cb-124">Programación asincrónica con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="2e6cb-124">Asynchronous programming with async and await (C#)</span></span>](../../csharp/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="2e6cb-125">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e6cb-125">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
