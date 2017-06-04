---
title: "E/S de archivos asincr&#243;nica | Microsoft Docs"
ms.custom: ""
ms.date: "03/03/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "secuencias, secuencias sincrónicas"
  - "E/S asincrónica"
  - "E/S sincrónica"
  - "secuencias, secuencias asincrónicas"
  - "E/S [.NET Framework], operaciones de E/S asincrónicas"
  - "Clase de secuencia, operaciones de E/S sincrónicas"
  - "secuencias de datos, secuencias asincrónicas"
  - "Clase de secuencia, operaciones de E/S asincrónicas"
  - "solicitudes de E/S múltiples"
  - "secuencias de datos, secuencias sincrónicas"
ms.assetid: dbdd55e7-d6b9-4f9e-8abb-ab0edd4457f7
caps.latest.revision: 23
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
---
# E/S de archivos asincr&#243;nica
Las operaciones asincrónicas permiten realizar operaciones de E\/S que hacen un uso intensivo de recursos sin bloquear el subproceso principal. Esta consideración de rendimiento es especialmente importante en una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] o una aplicación de [!INCLUDE[desktop_appname](../../../includes/desktop-appname-md.md)] en que una operación de streaming prolongada puede bloquear el subproceso de interfaz de usuario y hacer que parezca que una aplicación ha dejado de responder.  
  
 A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], los tipos de E\/S incluyen métodos asincrónicos para simplificar las operaciones asincrónicas. Un método asincrónico contiene `Async` en su nombre, como <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A> y <xref:System.IO.TextReader.ReadToEndAsync%2A>. Estos métodos asincrónicos se implementan en clases de secuencias, como <xref:System.IO.Stream>, <xref:System.IO.FileStream> y <xref:System.IO.MemoryStream>, y en las clases de las que se usan para leer o escribir en secuencias, como <xref:System.IO.TextReader> y <xref:System.IO.TextWriter>.  
  
 En .NET Framework 4 y versiones anteriores, es necesario usar métodos como <xref:System.IO.Stream.BeginRead%2A> y <xref:System.IO.Stream.EndRead%2A> para implementar operaciones de E\/S asincrónicas. Estos métodos siguen estando disponibles en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] por compatibilidad con el código heredado; sin embargo, los métodos asincrónicos implementan las operaciones de E\/S asincrónicas de una manera más sencilla.  
  
 A partir de [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], Visual Studio proporciona dos palabras clave para la programación asincrónica:  
  
-   El modificador `Async` \(Visual Basic\) o `async` \(C\#\), que se utiliza para marcar un método que contiene una operación asincrónica.  
  
-   El operador `Await` \(Visual Basic\) o `await` \(C\#\), que se aplica al resultado de un método asincrónico.  
  
 Para implementar operaciones de E\/S asincrónicas, use estas palabras clave junto con los métodos asincrónicos, como se muestra en los ejemplos siguientes. Para obtener más información, consulta [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 En el ejemplo siguiente se muestra cómo usar dos objetos <xref:System.IO.FileStream> para copiar archivos de forma asincrónica de un directorio en otro. Observe que el controlador de eventos <xref:System.Web.UI.WebControls.Button.Click> para el control <xref:System.Windows.Controls.Button> está marcado con el modificador `async` porque llama a un método asincrónico.  
  
 [!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
 [!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]  
  
 El ejemplo siguiente es similar al anterior, pero utiliza objetos <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter> para leer y escribir el contenido de un archivo de texto de forma asincrónica.  
  
 [!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
 [!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]  
  
 En el ejemplo siguiente se muestra el archivo de código subyacente y el archivo XAML que se usan para abrir un archivo como <xref:System.IO.Stream> en una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] y leer su contenido mediante una instancia de la clase <xref:System.IO.StreamReader>. Utiliza métodos asincrónicos para abrir el archivo como secuencia y leer su contenido.  
  
 [!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
 [!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]  
  
 [!code-xml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]  
  
## Vea también  
 <xref:System.IO.Stream>   
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)   
 [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)