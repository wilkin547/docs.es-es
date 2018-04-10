---
title: Desarrollo de varias plataformas con .NET Framework
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9acceb04ea48ef7d9a99d8a82c63090ee344ea54
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="developing-for-multiple-platforms-with-the-net-framework"></a>Desarrollo de varias plataformas con .NET Framework
Con .NET Framework y Visual Studio se pueden desarrollar aplicaciones destinadas a plataformas de Microsoft y de terceros.  
  
## <a name="options-for-cross-platform-development"></a>Opciones del desarrollo multiplataforma  
 Si va a desarrollar para varias plataformas, puede compartir código de origen o archivos binarios, y puede realizar llamadas entre código de .NET Framework y las API de Windows en tiempo de ejecución.  
  
|Si desea...|Use...|  
|-----------------------|------------|  
|Compartir código de origen entre aplicaciones de Windows Phone 8.1 y Windows 8.1|**Los proyectos compartidos** (plantilla aplicaciones universales en Visual Studio 2013, Update 2).<br /><br /> -Actualmente no hay compatibilidad con Visual Basic.<br />-Se puede separar código específico de la plataforma mediante #`if` instrucciones.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Compilar aplicaciones que tienen como destino Windows y Windows Phone con Visual Studio](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) (artículo de MSDN)<br />-   [Usar Visual Studio para crear aplicaciones XAML universales](http://blogs.msdn.com/b/visualstudio/archive/2014/04/14/using-visual-studio-to-build-universal-xaml-apps.aspx) (entrada de blog)<br />-   [Con Visual Studio para crear aplicaciones Convergidas XAML](http://channel9.msdn.com/Events/Build/2014/3-591) (vídeo)|  
|Compartir archivos binarios entre aplicaciones destinadas a plataformas diferentes|**Proyectos de biblioteca de clases Portable** para el código que es independiente de la plataforma.<br /><br /> -Este enfoque se usa normalmente para el código que implementa la lógica de negocios.<br />-Se puede usar Visual Basic o C#.<br />-Compatibilidad con la API varía según la plataforma.<br />-Los proyectos de biblioteca de clases portables cuyo destino sea Windows 8.1 y Windows Phone 8.1 admiten Windows Runtime APIs y XAML. Estas características no están disponibles en versiones anteriores de la Biblioteca de clases portable.<br />-Si es necesario, se puede abstraer el código específico de la plataforma mediante interfaces o clases abstractas.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Biblioteca de clases Portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) (artículo de MSDN)<br />-   [Cómo realizar trabajo de bibliotecas de clase Portable automáticamente](http://blogs.msdn.com/b/dsplaisted/archive/2012/08/27/how-to-make-portable-class-libraries-work-for-you.aspx) (entrada de blog)<br />-   [Usar la biblioteca de clases Portable con MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md) (artículo de MSDN)<br />-   [Recursos de la aplicación para bibliotecas destinadas a varias plataformas](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md) (artículo de MSDN)<br />-   [Analizador de portabilidad de .NET](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) (extensión de Visual Studio)|  
|Compartir código de origen entre aplicaciones de plataformas distintas de Windows Phone 8.1 y Windows 8.1|**Agregar como vínculo** característica.<br /><br /> -Este enfoque es adecuado para la lógica de aplicación que es común a ambas aplicaciones, pero no portátil, por algún motivo. Se puede usar esta característica para código de Visual Basic o C#.<br />     Por ejemplo, Windows Phone 8 y Windows 8 comparten las API de Windows en tiempo de ejecución, pero las Bibliotecas de clases portables no admiten Windows en tiempo de ejecución con esas plataformas. Puede usar `Add as link` para compartir código común de Windows en tiempo de ejecución entre una aplicación de Windows Phone 8 y una aplicación de la Tienda Windows diseñada para Windows 8.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Compartir código con agregar como vínculo](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx) (artículo de MSDN)<br />-   [Cómo: agregar elementos existentes a un proyecto](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx) (artículo de MSDN)|  
|Escribir aplicaciones de la Tienda Windows con .NET Framework o llamar a las API de Windows en tiempo de ejecución desde código de .NET Framework|**Windows Runtime APIs** desde su código de Visual Basic o C# de .NET Framework y use .NET Framework para crear aplicaciones de la tienda de Windows. Tenga en cuenta las diferencias de API entre las dos plataformas. No obstante, hay clases que sirven para trabajar con esas diferencias.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Compatibilidad de .NET framework Windows almacén de aplicaciones y en tiempo de ejecución de Windows](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (artículo de MSDN)<br />-   [Pasar un identificador URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md) (artículo de MSDN)<br />-   <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>-->`System.IO.WindowsRuntimeStreamExtensions` (Página de referencia de API de MSDN)<br />-   <!--zz <xref:System.WindowsRuntimeSystemExtensions>-->`System.WindowsRuntimeSystemExtensions` (Página de referencia de API de MSDN)|  
|Crear aplicaciones de .NET Framework para otras plataformas (diferentes de Microsoft)|**Ensamblados de referencia de biblioteca de clases Portable** en .NET Framework y una herramienta de terceros o de extensiones de Visual Studio como Xamarin.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Biblioteca de clases Portable ahora disponible en todas las plataformas.](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx) (entrada de blog)<br />-   [Xamarin](http://xamarin.com/visual-studio) (sitio Web de Xamarin)|  
|Usar JavaScript y HTML para desarrollo multiplataforma|**Plantillas de aplicación universal** en Visual Studio 2013, Update 2 para desarrollar con Windows Runtime APIs para Windows 8.1 y Windows Phone 8.1. Actualmente, no se puede usar JavaScript ni HTML con las API de .NET Framework para desarrollar aplicaciones multiplataforma.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Plantillas de proyecto de JavaScript](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)<br />-   [Cómo migrar una aplicación de Windows Runtime con JavaScript para Windows Phone](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)|
