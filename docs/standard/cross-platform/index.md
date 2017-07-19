---
title: "Desarrollo de varias plataformas con .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Desarrollo de varias plataformas con .NET Framework
Con .NET Framework y Visual Studio se pueden desarrollar aplicaciones destinadas a plataformas de Microsoft y de terceros.  
  
## Opciones del desarrollo multiplataforma  
 Si va a desarrollar para varias plataformas, puede compartir código de origen o archivos binarios, y puede realizar llamadas entre código de .NET Framework y las API de Windows en tiempo de ejecución.  
  
|Si desea...|Use...|  
|-----------------|------------|  
|Compartir código de origen entre aplicaciones de Windows Phone 8.1 y Windows 8.1|**Proyectos compartidos** \(Plantilla Aplicaciones universales de Visual Studio 2013, Update 2\).<br /><br /> -   No compatible actualmente con Visual Basic.<br />-   Puede separar código específico de plataforma con instrucciones \#`if`.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Crear aplicaciones diseñadas para Windows y Windows Phone con Visual Studio](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) \(artículo de MSDN\)<br />-   [Uso de Visual Studio para crear aplicaciones XAML universales](http://blogs.msdn.com/b/visualstudio/archive/2014/04/14/using-visual-studio-to-build-universal-xaml-apps.aspx) \(entrada de blog\)<br />-   [Uso de Visual Studio para crear aplicaciones convergidas XAML](http://channel9.msdn.com/Events/Build/2014/3-591) \(vídeo\)|  
|Compartir archivos binarios entre aplicaciones destinadas a plataformas diferentes|**Proyectos de la Biblioteca de clases portable** para código independiente de la plataforma.<br /><br /> -   Este enfoque se usa normalmente para código que implementa lógica empresarial.<br />-   Se puede usar Visual Basic o C\#.<br />-   La compatibilidad con API varía según la plataforma.<br />-   Los proyectos de la Biblioteca de clases portable destinadas a Windows 8.1 y Windows Phone 8.1 admiten las API de Windows en tiempo de ejecución y XAML.  Estas características no están disponibles en versiones anteriores de la Biblioteca de clases portable.<br />-   En caso necesario, se puede abstraer el código específico de la plataforma mediante interfaces o clases abstractas.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) \(artículo de MSDN\)<br />-   [Cómo trabajar con bibliotecas de clases portables](http://blogs.msdn.com/b/dsplaisted/archive/2012/08/27/how-to-make-portable-class-libraries-work-for-you.aspx) \(entrada de blog\)<br />-   [Usar la Biblioteca de clases portable con MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md) \(artículo de MSDN\)<br />-   [Recursos de aplicación para bibliotecas destinadas a varias plataformas](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md) \(artículo de MSDN\)<br />-   [Analizador de portabilidad de .NET](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) \(extensión de Visual Studio\)|  
|Compartir código de origen entre aplicaciones de plataformas distintas de Windows Phone 8.1 y Windows 8.1|Característica **Agregar como vínculo**.<br /><br /> -   Este enfoque es adecuado para lógica de aplicación común a ambas aplicaciones, pero, por algún motivo, no portable.  Se puede usar esta característica para código de Visual Basic o C\#.<br />     Por ejemplo, Windows Phone 8 y Windows 8 comparten las API de Windows en tiempo de ejecución, pero las Bibliotecas de clases portables no admiten Windows en tiempo de ejecución con esas plataformas.  Puede usar `Add as link` para compartir código común de Windows en tiempo de ejecución entre una aplicación de Windows Phone 8 y una aplicación de la Tienda Windows diseñada para Windows 8.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Compartir código con Agregar como vínculo](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx) \(artículo de MSDN\)<br />-   [Cómo: Agregar elementos existentes a un proyecto](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx) \(artículo de MSDN\)|  
|Escribir aplicaciones de la Tienda Windows con .NET Framework o llamar a las API de Windows en tiempo de ejecución desde código de .NET Framework|**API de Windows en tiempo de ejecución** desde su código de Visual Basic o C\# de .NET Framework, y use .NET Framework para crear aplicaciones de la Tienda Windows.  Tenga en cuenta las diferencias de API entre las dos plataformas.  No obstante, hay clases que sirven para trabajar con esas diferencias.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) \(artículo de MSDN\)<br />-   [Pasar un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md) \(artículo de MSDN\)<br />-   <xref:System.IO.WindowsRuntimeStreamExtensions> \(página de referencia de API de MSDN\)<br />-   <xref:System.WindowsRuntimeSystemExtensions> \(página de referencia de API de MSDN\)|  
|Crear aplicaciones de .NET Framework para otras plataformas \(diferentes de Microsoft\)|**Ensamblados de referencia de la Biblioteca de clases portable** en .NET Framework y una extensión de Visual Studio o una herramienta de terceros como, por ejemplo, Xamarin.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Biblioteca de clases portable ahora disponible en todas las plataformas](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx) \(entrada de blog en inglés\).<br />-   [Xamarin](http://xamarin.com/visual-studio) \(sitio web de Xamarin\)|  
|Usar JavaScript y HTML para desarrollo multiplataforma|**Plantillas de aplicación universal** de Visual Studio 2013, Update 2 para desarrollar con las API de Windows en tiempo de ejecución para Windows 8.1 y Windows Phone 8.1.  Actualmente, no se puede usar JavaScript ni HTML con las API de .NET Framework para desarrollar aplicaciones multiplataforma.<br /><br /> Para obtener información detallada, vea:<br /><br /> -   [Plantillas de proyecto JavaScript](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)<br />-   [Cómo migrar una aplicación de Windows en tiempo de ejecución con JavaScript a Windows Phone](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)|