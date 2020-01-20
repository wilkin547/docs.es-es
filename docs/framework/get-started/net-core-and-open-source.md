---
title: .NET Core y código abierto
ms.date: 03/30/2017
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
ms.openlocfilehash: 4032ba771d917d25473c8de350cc752bd052f94d
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75752550"
---
# <a name="net-core-and-open-source"></a>.NET Core y código abierto

En este artículo se proporciona una breve descripción de .NET Core y se muestra cómo encontrar más información. Para encontrar la lista completa de documentación de .NET Core, visite la [Guía de .NET Core](../../core/index.md).
  
<a name="BKMK_WhatisNETCore"></a>   
## <a name="what-is-net-core"></a>¿Qué es .NET Core?  
 .NET Core es una implementación de .NET Standard para uso general, modular, multiplataforma y de código abierto. Contiene muchas de las API de .NET Framework (aunque .NET Core es un conjunto más pequeño), e incluye componentes de entorno en tiempo de ejecución, marco de trabajo, compilador y herramientas que admiten diversos sistemas operativos y destinos de chip. La implementación de .NET Core se debe principalmente a las cargas de trabajo de ASP.NET Core, pero también a la necesidad y la intención de tener una implementación más moderna. Se puede utilizar en escenarios de dispositivos, nube e incrustados/IoT.  
  
 Para empezar a trabajar con .NET Core, vea el tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro).  
  
Estas son las principales características de .NET Core:
  
- **Multiplataforma**: .NET Core proporciona una funcionalidad clave para implementar las características de la aplicación que necesita y reutilizar este código independientemente del destino de la plataforma. En la actualidad es compatible con los tres sistemas operativos (SO) principales: Windows, Linux y macOS. Puede escribir aplicaciones y bibliotecas que se ejecutan sin modificaciones en todos los sistemas operativos compatibles. Para ver una lista de todos los sistemas operativos compatibles, visite [.NET Core roadmap](https://github.com/dotnet/core/blob/master/roadmap.md) (Mapa de ruta de .NET Core).
  
- **Código abierto**: .NET Core es uno de los muchos proyectos que administra [.NET Foundation](https://www.dotnetfoundation.org/) y está disponible en [GitHub](https://github.com/).  Al tratarse de un proyecto de código abierto, .NET Core favorece que el proceso de desarrollo sea más transparente y que exista una comunidad activa y comprometida.  
  
- **Desarrollo flexible**: hay dos modos principalmente para desarrollar una aplicación, implementación basada en marco e implementación autocontenida. Con la implementación basada en marco, solo se instalan su aplicación y las dependencias de terceros, y la aplicación requiere la presencia de una versión de .NET Core en todo el sistema.  Con la implementación autocontenida, la versión de .NET Core que se utiliza para compilar su aplicación también se implementa junto con la aplicación y las dependencias de terceros, y se puede ejecutar paralelamente con otras versiones.    Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../../core/deploying/index.md).

- **Modular**: .NET Core es modular, ya que se publica a través de NuGet en paquetes de ensamblado más reducidos. En lugar de un ensamblado grande que contiene la mayor parte de la funcionalidad básica, .NET Core está disponible como paquetes más pequeños centrados en las características. Esta característica nos permite un modelo de desarrollo más ágil y le permite optimizar su aplicación para incluir solo los paquetes de NuGet que necesita. Entre las ventajas de una menor superficie de aplicación se incluyen una mayor seguridad, mantenimiento reducido, rendimiento mejorado y menores costes en un modelo de suscripción ajustado a sus necesidades.  
  
## <a name="the-net-core-platform"></a>Plataforma .NET Core
  
La plataforma .NET Core está formada por varios componentes, entre los que se incluyen los compiladores administrados, el entorno de ejecución, las bibliotecas de clases base y numerosos modelos de aplicaciones, como ASP.NET Core. Puede obtener más información sobre los diferentes componentes y colaborar visitando los siguientes repositorios de [GitHub](https://github.com/):  
  
- [Página principal de .NET Core](https://github.com/dotnet/core)  
  
- [Entorno de ejecución: entorno de ejecución y plataforma .NET Core](https://github.com/dotnet/runtime)  
  
- [CLI: Herramientas de la interfaz de la línea de comandos de .NET Core](https://github.com/dotnet/cli)  
  
- [Roslyn: SDK de .NET Compiler Platform](https://github.com/dotnet/roslyn)  
  
- [ASP.NET Core](https://github.com/dotnet/aspnetcore)  
  
## <a name="see-also"></a>Vea también

- [Tutorial de .NET: Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)
- [Guía de .NET Core](../../core/index.md)
- [Documentos sobre ASP.NET Core](/aspnet/core/)
