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
# <a name="asynchronous-file-io"></a>E/S de archivos asincrónica

Las operaciones asincrónicas permiten realizar operaciones de E/S que hacen un uso intensivo de recursos sin bloquear el subproceso principal. Esta consideración de rendimiento es especialmente importante en una aplicación de la Tienda Windows 8.x o una aplicación de escritorio en que una operación de streaming prolongada puede bloquear el subproceso de interfaz de usuario y hacer que parezca que una aplicación ha dejado de responder.

A partir de .NET Framework 4.5, los tipos de E/S incluyen métodos asincrónicos para simplificar las operaciones asincrónicas. Un método asincrónico contiene `Async` en su nombre, como <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>y <xref:System.IO.TextReader.ReadToEndAsync%2A>. Estos métodos asincrónicos se implementan en clases de secuencias, como <xref:System.IO.Stream>, <xref:System.IO.FileStream>y <xref:System.IO.MemoryStream>, y en las clases de las que se usan para leer o escribir en secuencias, como <xref:System.IO.TextReader> y <xref:System.IO.TextWriter>.

En .NET Framework 4 y versiones anteriores, es necesario usar métodos como <xref:System.IO.Stream.BeginRead%2A> y <xref:System.IO.Stream.EndRead%2A> para implementar operaciones de E/S asincrónicas. Estos métodos siguen disponibles en las versiones actuales de .NET para admitir código heredado, pero los métodos asincrónicos facilitan la implementación de operaciones de E/S asincrónicas con más facilidad.

C# y Visual Basic tienen dos palabras clave para la programación asincrónica:

- El modificador`Async` (Visual Basic) o `async` (C#), que se utiliza para marcar un método que contiene una operación asincrónica.

- El operador`Await` (Visual Basic) o `await` (C#), que se aplica al resultado de un método asincrónico.

Para implementar operaciones de E/S asincrónicas, use estas palabras clave junto con los métodos asincrónicos, como se muestra en los ejemplos siguientes. Para obtener más información, vea [Programación asincrónica con Async y Await (C#)](../../csharp/programming-guide/concepts/async/index.md) y [Programación asincrónica con Async y Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).

En el ejemplo siguiente se muestra cómo usar dos objetos <xref:System.IO.FileStream> para copiar archivos de forma asincrónica de un directorio en otro. Observe que el controlador de eventos <xref:System.Web.UI.WebControls.Button.Click> para el control <xref:System.Windows.Controls.Button> está marcado con el modificador `async` porque llama a un método asincrónico.

[!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
[!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]

El ejemplo siguiente es similar al anterior, pero utiliza objetos <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter> para leer y escribir el contenido de un archivo de texto de forma asincrónica.

[!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
[!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]

En el ejemplo siguiente se muestra el archivo de código subyacente y el archivo XAML que se usan para abrir un archivo como <xref:System.IO.Stream> en una aplicación de la Tienda Windows 8.x y leer su contenido mediante una instancia de la clase <xref:System.IO.StreamReader>. Utiliza métodos asincrónicos para abrir el archivo como secuencia y leer su contenido.

[!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
[!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]

[!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]

## <a name="see-also"></a>Vea también

- <xref:System.IO.Stream>
- [E/S de archivos y secuencias](index.md)
- [Programación asincrónica con async y await (C#)](../../csharp/programming-guide/concepts/async/index.md)
- [Programación asincrónica con Async y Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md)
