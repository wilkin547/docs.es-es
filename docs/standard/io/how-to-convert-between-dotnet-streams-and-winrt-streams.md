---
title: 'Cómo: Convertir flujos de .NET Framework en flujos de Windows Runtime, y viceversa'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f67f88cd7f690e56664fa45878d1c9ac1f8a6b6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33577566"
---
# <a name="how-to-convert-between-net-framework-streams-and-windows-runtime-streams"></a>Cómo: Convertir flujos de .NET Framework en flujos de Windows Runtime, y viceversa
.NET Framework para aplicaciones de la Tienda Windows es un subconjunto de la plataforma .NET Framework completa. Debido a los requisitos de seguridad y de otro tipo de las aplicaciones de la Tienda Windows, no se puede usar el conjunto completo de API de .NET Framework para abrir y leer archivos. Para más información, consulte [Información general de .NET para aplicaciones de la Tienda Windows](http://msdn.microsoft.com/library/windows/apps/br230302.aspx). Sin embargo, puede que desee usar las API de .NET Framework para otras operaciones de manipulación de secuencias. Para manipular estas secuencias, puede que sea necesario convertir entre un tipo de secuencia de .NET Framework como <xref:System.IO.MemoryStream> o <xref:System.IO.FileStream>, y una secuencia de Windows Runtime como [IInputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.iinputstream.aspx), [IOutputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ioutputstream.aspx)o [IRandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.aspx).  
  
 La clase <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` contiene métodos que facilitan estas conversiones. Sin embargo, hay diferencias subyacentes entre las secuencias de .NET Framework y de Windows en tiempo de ejecución que afectarán a los resultados del uso de estos métodos. Los detalles se describen en las secciones siguientes.  
  
<a name="BKMK_ConvertingfromaWindowsRuntimestreamtoaNETFrameworkstream"></a>   
## <a name="converting-from-a-windows-runtime-stream-to-a-net-framework-stream"></a>Convertir una secuencia de Windows en tiempo de ejecución en una secuencia de .NET Framework  
 Puede convertir una secuencia de Windows en tiempo de ejecución en una secuencia de .NET Framework usando uno de métodos siguientes de la clase <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` :  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStream`  
 Convierte una secuencia de acceso aleatorio de Windows en tiempo de ejecución en una secuencia administrada del subconjunto de .NET para aplicaciones de la Tienda Windows.  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite`
 Convierte un flujo de salida de Windows en tiempo de ejecución en una secuencia administrada del subconjunto de .NET para aplicaciones de la Tienda Windows.  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead`  
 Convierte un flujo de entrada de Windows en tiempo de ejecución en una secuencia administrada del subconjunto de .NET para aplicaciones de la Tienda Windows.  
  
 Windows en tiempo de ejecución ofrece tipos de secuencia que admiten solo lectura, solo escritura o lectura y escritura. Estas capacidades se mantienen al convertir una secuencia de Windows en tiempo de ejecución a una secuencia de .NET Framework. Además, en caso de convertir una secuencia de Windows en tiempo de ejecución en secuencia de .NET Framework y de nuevo al revés, obtendrá de nuevo la instancia original de Windows en tiempo de ejecución. Se recomienda usar el método de conversión correspondiente a las capacidades de la secuencia de Windows en tiempo de ejecución que desea convertir. Sin embargo, como [IRandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.aspx) es de lectura y escritura (implementa tanto [IOutputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ioutputstream.aspx) como [IInputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.iinputstream.aspx)), puede usar cualquiera de los métodos de conversión y las capacidades de la secuencia original se mantendrán. Por ejemplo, si usa <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead` para convertir un objeto [IRandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.aspx) , no se limitará la secuencia de .NET Framework convertida de forma que sea de solo lectura, sino que también se podrá modificar.  
  
#### <a name="to-convert-from-a-windows-runtime-random-access-stream-to-a-net-framework-stream"></a>Para convertir una secuencia de acceso aleatorio de Windows en tiempo de ejecución en una secuencia de .NET Framework  
  
-   Utilice el método <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStream` .  
  
     En el ejemplo de código siguiente se muestra cómo pedir al usuario que seleccione un archivo, abrirlo con las API de Windows en tiempo de ejecución y, a continuación, convertirlo en una secuencia de .NET Framework, que se lee y se escribe en un bloque de texto. En este escenario, normalmente se manipularía la secuencia con las API de .NET Framework antes de generar los resultados.  
  
     Para ejecutar este ejemplo, debe crear una aplicación XAML de la Tienda Windows que contenga un bloque de texto denominado `TextBlock1` y un botón denominado  `Button1`. El evento Click del botón debe asociarse al método `button1_Click` mostrado en el ejemplo.  
  
     [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
     [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]  
    [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#1)]
    [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#1)]  
  
<a name="BKMK_ConvertingfromaNETFrameworkstreamtoaWindowsRuntimestream"></a>   
## <a name="converting-from-a-net-framework-stream-to-a-windows-runtime-stream"></a>Convertir una secuencia de .NET Framework en una secuencia de Windows en tiempo de ejecución  
 Puede convertir una secuencia de .NET Framework en una secuencia de Windows en tiempo de ejecución usando uno de métodos siguientes de la clase <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` :  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsInputStream`  
 Convierte una secuencia administrada del subconjunto de .NET para aplicaciones de la Tienda Windows en un flujo de entrada de Windows en tiempo de ejecución.  
  
<!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsOutputStream%2A>  --> `System.IO.WindowsRuntimeStreamExtensions.AsOutputStream`
 Convierte una secuencia administrada del subconjunto de .NET para aplicaciones de la Tienda Windows en un flujo de salida de Windows en tiempo de ejecución.  
  
 [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md)  
 Convierte una secuencia administrada del subconjunto de .NET para aplicaciones de la Tienda Windows en una secuencia de acceso aleatorio que se puede utilizar para leer o escribir en Windows en tiempo de ejecución.  
  
 Al convertir una secuencia de .NET Framework en secuencia de Windows en tiempo de ejecución, las capacidades de la secuencia convertida dependerán de la secuencia original. Por ejemplo, si la secuencia original admite lectura y escritura y se llama a <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsInputStream` para convertir la secuencia, el tipo devuelto será `IRandomAccessStream`, que implementa  `IInputStream` e `IOutputStream`y admite tanto lectura como escritura  
  
 Las secuencias de .NET Framework no admiten la clonación, incluso después de la conversión. Esto significa que, si se convierte una secuencia de .NET Framework en secuencia de Windows Runtime y se llama a [GetInputStreamAt](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.inmemoryrandomaccessstream.getinputstreamat.aspx) o [GetOutputStreamAt](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.getoutputstreamat.aspx), que a su vez llaman a [CloneStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstreamoverstream.clonestream.aspx) o [CloneStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstreamoverstream.clonestream.aspx) directamente, se producirá una excepción.  
  
#### <a name="to-convert-from-a-net-framework-stream-to-a-windows-runtime-random-access-stream"></a>Para convertir una secuencia de .NET Framework en una secuencia de acceso aleatorio de Windows en tiempo de ejecución  
  
-   Use el método [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md) , como se muestra en el ejemplo siguiente.  
  
    > [!IMPORTANT]
    >  Asegúrese de que la secuencia de .NET Framework que está usando admite las búsquedas, o cópiela en una secuencia que las admita. Puede usar la propiedad <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType> para averiguarlo.  
  
     Para ejecutar este ejemplo, debe crear una aplicación XAML de la Tienda Windows destinada a .NET Framework 4.5.1 y que contenga un bloque de texto denominado `TextBlock2` y un botón denominado `Button2`. El evento Click del botón debe asociarse al método `button2_Click` mostrado en este ejemplo.  
  
     [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
     [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]  
    [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#2)]
    [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Tutorial rápido: leer y escribir en un archivo (Windows)](https://msdn.microsoft.com/library/windows/apps/hh464978.aspx)  
 [Información general de .NET para aplicaciones de la Tienda Windows](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [.NET para aplicaciones de la Tienda Windows: API admitidas](https://msdn.microsoft.com/library/windows/apps/br230232.aspx)
