---
title: ".NET Core y c&#243;digo abierto | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# .NET Core y c&#243;digo abierto
.NET Core es una versión modular de .NET Framework diseñada para que sea portátil entre plataformas, a fin de permitir la reutilización del código al máximo y su uso compartido. Además, .NET Core será de código abierto y aceptará las contribuciones de la comunidad. Este tema responde a algunas preguntas comunes sobre .NET Core y sobre cómo tener acceso y contribuir a los paquetes de código abierto.  
  
<a name="BKMK_WhatisNETCore"></a>   
## ¿Qué es .NET Core?  
 Como ya indicó, .NET Core es una versión modular de .NET Framework diseñada para que sea portátil entre plataformas.  
  
 .NET Core es portátil entre plataformas porque, aunque se trata de un subconjunto de la versión completa de .NET Framework, proporciona una funcionalidad clave para implementar las características de la aplicación que necesita y reutilizar este código independientemente del destino de la plataforma. Antes, las distintas versiones de .NET para diferentes plataformas carecían de funcionalidad compartida para las tareas clave, como la lectura de archivos locales. Las plataformas de Microsoft que podrá establecer como destino con .NET Core incluyen Windows de escritorio tradicional, así como dispositivos y teléfonos de Windows. Cuando se usan herramientas de terceros como Xamarin, .NET Core debe ser portátil para dispositivos IOS y Android. Además, .NET Core pronto estará disponible para los sistemas operativos Mac y Linux para permitir que las aplicaciones web se ejecuten en estos sistemas.  
  
 .NET Core es modular, ya que se publica a través de NuGet en paquetes de ensamblado más reducidos. En lugar de un ensamblado grande que contiene la mayor parte de la funcionalidad básica, .NET Core está disponible como paquetes más pequeños centrados en las características. Esto nos permite un modelo de desarrollo más ágil y a usted le ofrece la posibilidad de elegir las funcionalidades que necesita para sus aplicaciones y bibliotecas. Para obtener más información sobre los paquetes de .NET que se lanzan en NuGet, vea [.NET Framework y versiones fuera de banda](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md).  
  
 A continuación se incluyen algunas preguntas frecuentes sobre .NET Core.  
  
### ¿Cómo puedo aprovechar mejor .NET Core?  
 Para las aplicaciones existentes, la mejor manera de aprovechar .NET Core y maximizar la reutilización del código consiste en usar Bibliotecas de clases portables \(PCL\), usar proyectos de aplicaciones universales y separar la lógica de negocios del código específico de la plataforma. Para las aplicaciones, los patrones Model\-View\-Controller \(MVC\) y Model\-View\-ViewMode son una buena elección para que sus aplicaciones sean fáciles de migrar a .NET Core.  
  
### ¿Cómo afecta .NET Core a la compatibilidad y la implementación?  
 Hay varios escenarios diferentes de implementación, pero aun así la implementación debería ser sencilla. .NET Framework se distribuirá con Windows y se actualizará a través de Microsoft Update, como en la actualidad. En algunos casos, la aplicación se basará en esta implementación en disco de .NET Framework y, en otros casos, se basará en ensamblados .NET que se implementan con el paquete de aplicación. Además, la compatibilidad entre versiones sigue siendo prioritaria para .NET Framework, por lo que si la aplicación se ejecuta en una versión de ensamblado más reciente que aquella con la que se compiló, su comportamiento debería ser el mismo.  
  
|Escenario|Implementación|  
|---------------|--------------------|  
|Aplicaciones de escritorio de Windows y ASP.NET que se ejecutan en equipos con Windows|La implementación es idéntica a la actual. Una aplicación se basa en la instalación de .NET Framework en el servidor o el equipo del usuario. Si .NET Framework no está instalado, se le pedirá al usuario que lo instale. También se puede encadenar una instalación de .NET con la aplicación. Al usar ensamblados de .NET Core que no están incluidos en .NET Framework, dichos ensamblados se incluyen en el paquete de aplicación. Además, si la misma aplicación hace referencia a dos versiones del mismo ensamblado, la aplicación se redirigirá al ensamblado más reciente. Para obtener más información, vea [Redirección de las versiones de ensamblado en el nivel de aplicación](../../../docs/framework/configure-apps/redirect-assembly-versions.md#BKMK_Redirectingassemblyversionsattheapplevel) y [Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).<br /><br /> Para obtener más información sobre la implementación de .NET, vea [Guía de implementación para desarrolladores](../../../docs/framework/deployment/deployment-guide-for-developers.md).|  
|Aplicaciones de Windows y Windows Phone disponibles a través de las tiendas de Windows y Windows Phone|La implementación es idéntica a la actual y las aplicaciones usan los ensamblados de .NET Framework que se incluyen con el sistema operativo. Si la aplicación usa una funcionalidad publicada en un ensamblado .NET Core que no está incluido en .NET Framework, el ensamblado se incluirá en el paquete de la aplicación. Si la aplicación hace referencia a varias versiones del mismo ensamblado, estas aplicaciones usan automáticamente la versión más reciente del ensamblado.|  
|Aplicaciones ASP.NET Core 5.0|Los ensamblados .NET Core son locales de la aplicación, lo que significa que los ensamblados necesarios se implementan con el paquete de la aplicación. Para obtener más información sobre ASP.NET Core 5.0, vea [Introducción a ASP.NET 5](http://www.asp.net/vnext/overview/aspnet-vnext/aspnet-5-overview).|  
|Aplicaciones compiladas con herramientas de Xamarin que se ejecutan en otras plataformas|Actualmente, estas aplicaciones se implementan con un conjunto simplificado de ensamblados Mono que se suministran con el paquete de aplicación. Esto podría cambiar, ya que hay más ensamblados .NET Core de código abierto.|  
  
<a name="BKMK_NETCoreOpenSourcePackages"></a>   
## Paquetes de código abierto de .NET Core  
 Además el diseño modular de .NET Framework, Microsoft está empezando a código abierto en los paquetes .NET Core en [GitHub](https://github.com/), en la licencia de [MIT](https://github.com/dotnet/corefx/blob/master/LICENSE). Esto significa que puede clonar el repositorio Git, leer y compilar el código y enviar solicitudes de extracción, igual que cualquier otro paquete de código abierto que encontrará en GitHub. Debido a nuestro compromiso con la calidad y la compatibilidad, cada solicitud de extracción se evaluará cuidadosamente antes de aceptarse. A continuación se incluyen algunas preguntas frecuentes.  
  
### ¿Cómo puedo obtener el código y compilarlo?  
 Los paquetes de origen de .NET Core se almacenan en `GitHub`, que usa `Git` como sistema de control de código fuente. Para obtener acceso al código y compilarlo debe es necesario conocer los aspectos básicos de [Git](http://git-scm.com/), [GitHub](https://github.com/dotnet/corefx) y [Visual Studio](http://msdn.microsoft.com/vstudio/aa718325.aspx), pero los pasos a continuación proporcionan información y vínculos para comenzar.  
  
 Para configurar Git y GitHub, consulte [Configurar Git](https://help.github.com/articles/set-up-git/) en el sitio de GitHub.  
  
 Para acceder al código de .NET Framework, tendrá que bifurcar el repositorio Git que lo contiene y clonarlo en el equipo de desarrollo. Para bifurcar el código, vaya al repositorio y haga clic en **Bifurcar** en la esquina superior derecha del explorador. Puede clonar la bifurcación mediante la aplicación de GitHub o en la línea de comandos en el shell de GitHub. Para clonar el repositorio en el shell de GitHub, ejecute este comando:  
  
```  
git clone https://github.com/dotnet/corefx  
```  
  
 Para compilar el código debe tener instalado Visual Studio 2013. Puede abrir y compilar las soluciones con Visual Studio 2013 y presionando F5, o bien compilarlas en la línea de comandos mediante el símbolo del sistema para desarrolladores. Para compilar con el símbolo del sistema, abra un símbolo del sistema para desarrolladores y navegue hasta la carpeta donde clonó el código fuente. A continuación, escriba:  
  
```  
build.cmd  
  
```  
  
 Para obtener más información sobre cómo acceder al símbolo del sistema para desarrolladores, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
### ¿Cuáles son las instrucciones para el envío de código?  
 Antes de incorporar el trabajo en la bifurcación principal, debe firmar un [Contrato de licencia de colaborador \(CLA\)](https://cla.dotnetfoundation.org/).  
  
 Se aceptan las contribuciones de la comunidad que usan el modelo de extracción y bifurcación. Debe bifurcar y clonar el código y enviar una solicitud de extracción a la bifurcación principal de .NET Framework. Para obtener más información sobre las solicitudes de extracción, consulte [Usar solicitudes de extracción](https://help.github.com/articles/using-pull-requests/). Para obtener instrucciones detalladas sobre cómo enviar una solicitud de extracción, consulte la [Guía de colaboración de .NET Core](https://github.com/dotnet/corefx/wiki/Contributing).  
  
### ¿Por qué no se aceptó mi solicitud de extracción?  
 Si rechazamos su solicitud le explicaremos por qué lo hacemos, pero debe tener en cuenta que Microsoft está muy comprometido con la calidad del código y la compatibilidad. Si no se aceptó su solicitud de extracción, se debe a que probablemente no complió nuestras instrucciones de codificación, no realizó las pruebas adecuadas para el envío del código o interrumpió la compatibilidad con la API. Además, los cambios de código deben seguir nuestra guía básica de .NET Framework. Para obtener instrucciones y obtener más información sobre codificación, consulte [Guía de contribución de .NET Core](https://github.com/dotnet/corefx/wiki/Contributing).  
  
## Vea también  
 [.NET es código abierto](http://blogs.msdn.com/b/dotnet/archive/2014/11/12/net-core-is-open-source.aspx)   
 [Código abierto de .NET en Curah](https://curah.microsoft.com/254870/net-core-open-source)   
 [Introducción a ASP.NET 5](http://www.asp.net/vnext/overview/aspnet-vnext/aspnet-5-overview)