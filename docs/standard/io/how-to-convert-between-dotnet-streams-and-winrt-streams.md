---
title: Filtrar Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa (solo Windows)
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc38e69a79af7c7220b8e3b55d4cb1f4ca3695f6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255203"
---
# <a name="how-to-convert-between-net-framework-and-windows-runtime-streams-windows-only"></a>Filtrar Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa (solo Windows)

.NET Framework para aplicaciones para UWP es un subconjunto de la plataforma .NET Framework completa. Debido a los requisitos de seguridad y de otro tipo de las aplicaciones para UWP, no se puede usar el conjunto completo de API de .NET Framework para abrir y leer archivos. Para obtener más información, consulte [Información general de .NET para aplicaciones para UWP](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Sin embargo, puede que desee usar las API de .NET Framework para otras operaciones de manipulación de secuencias. Para manipular estos flujos, puede convertir entre un tipo de flujo de .NET Framework como <xref:System.IO.MemoryStream> o <xref:System.IO.FileStream>, y un flujo de Windows Runtime como <xref:Windows.Storage.Streams.IInputStream>, <xref:Windows.Storage.Streams.IOutputStream> o <xref:Windows.Storage.Streams.IRandomAccessStream>.

La clase [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx) contiene métodos que facilitan estas conversiones. Sin embargo, las diferencias subyacentes entre los flujos de .NET Framework y de Windows Runtime afectan a los resultados del uso de estos métodos, tal como se describe en las secciones siguientes:

## <a name="convert-from-a-windows-runtime-to-a-net-framework-stream"></a>Convertir un flujo de Windows Runtime en un flujo de .NET Framework
Para convertir un flujo de Windows Runtime en un flujo de .NET Framework, use uno de los métodos siguientes de la clase [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx):

- [System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx) convierte un flujo de acceso aleatorio de Windows Runtime en un flujo administrado de .NET para aplicaciones para UWP.
  
- [System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforwrite.aspx) convierte un flujo de salida de Windows Runtime en un flujo administrado de .NET para aplicaciones para UWP.
  
- [System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx) convierte un flujo de salida de Windows Runtime en un flujo administrado de .NET para aplicaciones para UWP.

Windows Runtime ofrece tipos de flujo que admiten solo lectura, solo escritura o lectura y escritura. Estas funcionalidades se mantienen al convertir un flujo de Windows Runtime en un flujo de .NET Framework. Además, en caso de convertir una secuencia de Windows en tiempo de ejecución en secuencia de .NET Framework y de nuevo al revés, obtendrá de nuevo la instancia original de Windows en tiempo de ejecución. 

Se recomienda usar el método de conversión correspondiente a las funcionalidades del flujo de Windows Runtime que desea convertir. Pero como <xref:Windows.Storage.Streams.IRandomAccessStream> es de lectura y escritura (implementa tanto <xref:Windows.Storage.Streams.IOutputStream> como <xref:Windows.Storage.Streams.IInputStream>), los métodos de conversión mantienen las funcionalidades del flujo original. Por ejemplo, si usa [System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx) para convertir un objeto <xref:Windows.Storage.Streams.IRandomAccessStream>, no se limita el flujo de .NET Framework convertido de forma que sea de lectura. También es de escritura.

## <a name="example-convert-windows-runtime-random-access-to-net-framework-stream"></a>Ejemplo: Convertir un flujo de acceso aleatorio de Windows Runtime en un flujo de .NET Framework
Para convertir un flujo de acceso aleatorio de Windows Runtime en un flujo de .NET Framework, use el método [System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx).

En el ejemplo de código siguiente, se le pide que seleccione un archivo, lo abra con las API de Windows Runtime y, a continuación, lo convierta en un flujo de .NET Framework. Lee el flujo y lo genera en un bloque de texto. Normalmente se manipularía el flujo con las API de .NET Framework antes de generar los resultados.

Para ejecutar este ejemplo, cree una aplicación XAML para UWP que contenga un bloque de texto denominado `TextBlock1` y un botón denominado `Button1`. Asocie el evento Click del botón al método `button1_Click` mostrado en el ejemplo.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage1.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage1.xaml.vb)]

## <a name="convert-from-a-net-framework-to-a-windows-runtime-stream"></a>Convertir un flujo de .NET Framework en un flujo de Windows Runtime
Para convertir un flujo de .NET Framework en un flujo de Windows Runtime, use uno de los métodos siguientes de la clase [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx):

- [System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx) convierte un flujo administrado de .NET para aplicaciones para UWP en un flujo de entrada de Windows Runtime.
  
- [System.IO.WindowsRuntimeStreamExtensions.AsOutputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asoutputstream.aspx) convierte un flujo administrado de .NET para aplicaciones para UWP en un flujo de salida de Windows Runtime.
  
- [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md) convierte un flujo administrado de .NET para aplicaciones para UWP en un flujo de acceso aleatorio que Windows Runtime puede usar para leer o escribir.

Al convertir un flujo de .NET Framework en un flujo de Windows Runtime, las funcionalidades del flujo convertido dependen del flujo original. Por ejemplo, si el flujo original admite lectura y escritura y se llama a [System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx) para convertir el flujo, el tipo devuelto es `IRandomAccessStream`. `IRandomAccessStream` implementa `IInputStream` y `IOutputStream`, y admite la lectura y la escritura.

Los flujos de .NET Framework no admiten la clonación, incluso después de la conversión. Si se convierte un flujo de .NET Framework en un flujo de Windows Runtime y se llama a <xref:Windows.Storage.Streams.InMemoryRandomAccessStream.GetInputStreamAt%2A> o <xref:Windows.Storage.Streams.IRandomAccessStream.GetOutputStreamAt%2A>, que a su vez llaman a <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A>, o si llama a <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> directamente, se producirá una excepción.

## <a name="example-convert-net-framework-to-windows-runtime-random-access-stream"></a>Ejemplo: Convertir un flujo de .NET Framework en un flujo de acceso aleatorio de Windows Runtime

Para convertir un flujo de .NET Framework en un flujo de acceso aleatorio de Windows Runtime, use el método [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md), tal como se muestra en el ejemplo siguiente:

> [!IMPORTANT]
> Asegúrese de que el flujo de .NET Framework que está usando admite las búsquedas, o cópielo en un flujo que las admita. Puede usar la propiedad <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType> para averiguarlo.

Para ejecutar este ejemplo, cree una aplicación XAML para UWP destinada a .NET Framework 4.5.1 y que contenga un bloque de texto denominado `TextBlock2` y un botón denominado `Button2`. Asocie el evento Click del botón al método `button2_Click` mostrado en el ejemplo.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage2.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage2.xaml.vb)]

## <a name="see-also"></a>Vea también

- [Inicio rápido: Leer y escribir un archivo (Windows)](https://msdn.microsoft.com/library/windows/apps/hh464978.aspx)  
- [Información general de .NET para aplicaciones de la Tienda Windows](https://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
- [.NET para aplicaciones de la Tienda Windows: API admitidas](https://msdn.microsoft.com/library/windows/apps/br230232.aspx)  
