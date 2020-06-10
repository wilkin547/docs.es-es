---
title: Procedimiento Escribir texto en un archivo
description: Conozca las formas de escribir o anexar texto a un archivo para una aplicación de .NET. Use métodos de las clases StreamWriter o File para escribir texto de forma sincrónica o asincrónica.
ms.date: 01/04/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
ms.openlocfilehash: 52d3d07f4ffdbdc6510425a65fc173d36e674d06
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447217"
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="15ba2-104">Procedimiento Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="15ba2-104">How to: Write text to a file</span></span>
<span data-ttu-id="15ba2-105">En este tema se muestran diferentes maneras de escribir texto en un archivo para una aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="15ba2-105">This topic shows different ways to write text to a file for a .NET app.</span></span>

<span data-ttu-id="15ba2-106">Las clases y los métodos siguientes normalmente se usan para escribir texto en un archivo:</span><span class="sxs-lookup"><span data-stu-id="15ba2-106">The following classes and methods are typically used to write text to a file:</span></span>  
  
- <span data-ttu-id="15ba2-107"><xref:System.IO.StreamWriter> contiene métodos para escribir en un archivo de forma sincrónica (<xref:System.IO.StreamWriter.Write%2A> y <xref:System.IO.TextWriter.WriteLine%2A>) o asincrónica (<xref:System.IO.StreamWriter.WriteAsync%2A> y <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span><span class="sxs-lookup"><span data-stu-id="15ba2-107"><xref:System.IO.StreamWriter> contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> and <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
- <span data-ttu-id="15ba2-108"><xref:System.IO.File> proporciona métodos estáticos para escribir texto en un archivo (por ejemplo, <xref:System.IO.File.WriteAllLines%2A> y <xref:System.IO.File.WriteAllText%2A>), o bien para anexar texto a un archivo (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> y <xref:System.IO.File.AppendText%2A>).</span><span class="sxs-lookup"><span data-stu-id="15ba2-108"><xref:System.IO.File> provides static methods to write text to a file, such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file, such as <xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A>, and <xref:System.IO.File.AppendText%2A>.</span></span>  
  
- <span data-ttu-id="15ba2-109"><xref:System.IO.Path> es para cadenas que contienen información de la ruta de acceso al archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="15ba2-109"><xref:System.IO.Path> is for strings that have file or directory path information.</span></span> <span data-ttu-id="15ba2-110">Contiene el método <xref:System.IO.Path.Combine%2A> y, en .NET Core 2.1 y versiones posteriores, los métodos <xref:System.IO.Path.Join%2A> y <xref:System.IO.Path.TryJoin%2A>, que permiten la concatenación de cadenas para crear una ruta de acceso de archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="15ba2-110">It contains the <xref:System.IO.Path.Combine%2A> method and, in .NET Core 2.1 and later, the <xref:System.IO.Path.Join%2A> and <xref:System.IO.Path.TryJoin%2A> methods, which allow concatenation of strings to build a file or directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="15ba2-111">En los ejemplos siguientes solo se muestra la cantidad mínima de código necesario.</span><span class="sxs-lookup"><span data-stu-id="15ba2-111">The following examples show only the minimum amount of code needed.</span></span> <span data-ttu-id="15ba2-112">Normalmente, una aplicación real ofrece una comprobación de errores y un control de excepciones más exhaustivos.</span><span class="sxs-lookup"><span data-stu-id="15ba2-112">A real-world app usually provides more robust error checking and exception handling.</span></span>  
  
## <a name="example-synchronously-write-text-with-streamwriter"></a><span data-ttu-id="15ba2-113">Ejemplo: Escritura de texto con StreamWriter de forma sincrónica</span><span class="sxs-lookup"><span data-stu-id="15ba2-113">Example: Synchronously write text with StreamWriter</span></span>

<span data-ttu-id="15ba2-114">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.IO.StreamWriter> para escribir texto en un archivo nuevo de forma sincrónica, una línea a la vez.</span><span class="sxs-lookup"><span data-stu-id="15ba2-114">The following example shows how to use the <xref:System.IO.StreamWriter> class to synchronously write text to a new file one line at a time.</span></span> <span data-ttu-id="15ba2-115">Como en la instrucción <xref:System.IO.StreamWriter> se declara el objeto `using` y se crea una instancia de este, se invoca el método <xref:System.IO.StreamWriter.Dispose%2A>, que automáticamente vacía y cierra el flujo.</span><span class="sxs-lookup"><span data-stu-id="15ba2-115">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked, which automatically flushes and closes the stream.</span></span>  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/write.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/write.vb)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="example-synchronously-append-text-with-streamwriter"></a><span data-ttu-id="15ba2-116">Ejemplo: Anexión de texto con StreamWriter de forma sincrónica</span><span class="sxs-lookup"><span data-stu-id="15ba2-116">Example: Synchronously append text with StreamWriter</span></span>

<span data-ttu-id="15ba2-117">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.IO.StreamWriter> para anexar de forma sincrónica texto al archivo de texto creado en el primer ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15ba2-117">The following example shows how to use the <xref:System.IO.StreamWriter> class to synchronously append text to the text file created in the first example.</span></span>

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/append.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/append.vb)]  

## <a name="example-asynchronously-write-text-with-streamwriter"></a><span data-ttu-id="15ba2-118">Ejemplo: Escritura de texto con StreamWriter de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="15ba2-118">Example: Asynchronously write text with StreamWriter</span></span>

<span data-ttu-id="15ba2-119">En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo de forma asincrónica mediante la clase <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="15ba2-119">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="15ba2-120">Para invocar el método <xref:System.IO.StreamWriter.WriteAsync%2A>, la llamada al método debe estar dentro de un método `async`.</span><span class="sxs-lookup"><span data-stu-id="15ba2-120">To invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call must be within an `async` method.</span></span> <span data-ttu-id="15ba2-121">En el ejemplo de C# se requiere C# 7.1 o una versión posterior, lo que agrega compatibilidad para el modificador `async` en el punto de entrada del programa.</span><span class="sxs-lookup"><span data-stu-id="15ba2-121">The C# example requires C# 7.1 or later, which adds support for the `async` modifier on the program entry point.</span></span>

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/async.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/async.vb)]  

## <a name="example-write-and-append-text-with-the-file-class"></a><span data-ttu-id="15ba2-122">Ejemplo: Escritura y anexión de texto a la clase File</span><span class="sxs-lookup"><span data-stu-id="15ba2-122">Example: Write and append text with the File class</span></span>

<span data-ttu-id="15ba2-123">En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo y anexar nuevas líneas de texto en el mismo archivo con la clase <xref:System.IO.File> .</span><span class="sxs-lookup"><span data-stu-id="15ba2-123">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="15ba2-124">Los métodos <xref:System.IO.File.WriteAllText%2A> y <xref:System.IO.File.AppendAllLines%2A> abren y cierran el archivo automáticamente.</span><span class="sxs-lookup"><span data-stu-id="15ba2-124">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="15ba2-125">Si ya existe la ruta de acceso que se proporciona al método <xref:System.IO.File.WriteAllText%2A>, se sobrescribe el archivo.</span><span class="sxs-lookup"><span data-stu-id="15ba2-125">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file is overwritten.</span></span>  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/file.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/file.vb)]  

## <a name="see-also"></a><span data-ttu-id="15ba2-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="15ba2-126">See also</span></span>

- <xref:System.IO.StreamWriter>
- <xref:System.IO.Path>
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="15ba2-127">Cómo: Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="15ba2-127">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)
- [<span data-ttu-id="15ba2-128">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="15ba2-128">How to: Read and write to a newly-created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)
- [<span data-ttu-id="15ba2-129">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="15ba2-129">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)
- [<span data-ttu-id="15ba2-130">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="15ba2-130">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)
- [<span data-ttu-id="15ba2-131">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="15ba2-131">File and stream I/O</span></span>](index.md)
