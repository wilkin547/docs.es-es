---
title: "Introducción a .NET Framework | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, getting started
- getting started [.NET Framework]
ms.assetid: c693fd34-88fe-4d90-b332-19eeadf3b7e7
caps.latest.revision: 35
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: adb9c30b6dc52ea17410423fd76c938e258549eb
ms.openlocfilehash: 6c069db2e6138f73935a4bdd458fbe94ef57d968
ms.lasthandoff: 05/02/2017

---
# <a name="getting-started-with-the-net-framework"></a>Introducción a .NET Framework
.NET Framework es un entorno de ejecución runtime que administra aplicaciones cuyo destino es .NET Framework. Incorpora Common Language Runtime, que proporciona administración de la memoria y otros servicios del sistema, y una biblioteca de clases completa, que permite a los programadores aprovechar el código sólido y confiable de todas las áreas principales del desarrollo de aplicaciones.  
  
<a name="Introducing"></a>   
## <a name="what-is-the-net-framework"></a>¿Qué es .NET Framework?  
 .NET Framework es un entorno de ejecución administrado que proporciona diversos servicios a las aplicaciones en ejecución. Consta de dos componentes principales: Common Language Runtime (CLR), que es el motor de ejecución que controla las aplicaciones en ejecución, y la biblioteca de clases de .NET Framework, que proporciona una biblioteca de código probado y reutilizable al que pueden llamar los desarrolladores desde sus propias aplicaciones. Los servicios que ofrece .NET Framework a las aplicaciones en ejecución son los siguientes:  
  
-   Administración de la memoria. En muchos lenguajes de programación, los programadores son responsables de asignar y liberar memoria y de administrar la vida útil de los objetos. En las aplicaciones de .NET Framework, CLR proporciona estos servicios en nombre de la aplicación.  
  
-   Sistema de tipos comunes. En los lenguajes de programación tradicionales, el compilador define los tipos básicos, lo que complica la interoperabilidad entre lenguajes. En .NET Framework, los tipos básicos los define el sistema de tipos de .NET Framework y son comunes a todos los lenguajes que tienen como destino .NET Framework.  
  
-   Biblioteca de clases extensa. En lugar de tener que escribir cantidades extensas de código para controlar operaciones comunes de programación de bajo nivel, los programadores pueden usar una biblioteca de tipos accesible en todo momento y sus miembros desde la biblioteca de clases de .NET Framework.  
  
-   Marcos y tecnologías de desarrollo. .NET Framework incluye bibliotecas para determinadas áreas de desarrollo de aplicaciones, como ASP.NET para aplicaciones web, ADO.NET para el acceso a los datos y Windows Communication Foundation para las aplicaciones orientadas a servicios.  
  
-   Interoperabilidad de lenguajes. Los compiladores de lenguajes cuya plataforma de destino es .NET Framework emiten un código intermedio denominado Lenguaje intermedio común (CIL), que, a su vez, se compila en tiempo de ejecución a través de Common Language Runtime. Con esta característica, las rutinas escritas en un lenguaje están accesibles a otros lenguajes, y los programadores pueden centrarse en crear aplicaciones en su lenguaje o lenguajes preferidos.  
  
-   Compatibilidad de versiones. Con raras excepciones, las aplicaciones que se desarrollan con una versión determinada de .NET Framework se pueden ejecutar sin modificaciones en una versión posterior.  
  
-   Ejecución en paralelo. .NET Framework ayuda a resolver conflictos entre versiones y permite que varias versiones de Common Language Runtime coexistan en el mismo equipo. Esto significa que también pueden coexistir varias versiones de las aplicaciones, y que una aplicación se puede ejecutar en la versión de .NET Framework con la que se compiló.  
  
-   Compatibilidad con múltiples versiones (multi-targeting). Al usar la Biblioteca de clases portable de .NET Framework, los desarrolladores pueden crear ensamblados que funcionen en varias plataformas, como Windows 7, Windows 8, Windows 8.1, Windows 10, Windows Phone y Xbox 360. Para más información, consulte [Biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).  
  
<a name="ForUsers"></a>   
## <a name="the-net-framework-for-users"></a>.NET Framework para usuarios  
 Si no desarrollara aplicaciones de .NET Framework, pero las usa, no es necesario tener conocimientos específicos de .NET Framework o de su funcionamiento. En general, .NET Framework es completamente transparente para los usuarios.  
  
 Si usa el sistema operativo Windows, es posible que .NET Framework ya esté instalado en el equipo. Además, si instala una aplicación que requiera .NET Framework, el programa de instalación de la aplicación puede instalar una versión concreta de .NET Framework en el equipo. En algunos casos, puede aparecer un cuadro de diálogo en el que se le pida que instale .NET Framework. Si acababa de intentar ejecutar una aplicación cuando aparece este cuadro de diálogo y si el equipo tiene acceso a Internet, puede ir a una página web que le permita instalar la versión de .NET Framework que falta.  
  
 En general, no conviene desinstalar ninguna versión de .NET Framework instalada en el equipo. Hay dos motivos para ello:  
  
-   Si una aplicación que utiliza depende de una versión específica de .NET Framework, podría dañarse si esa versión se quita.  
  
-   Algunas versiones de .NET Framework son actualizaciones locales de versiones anteriores. Por ejemplo, [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] es una actualización local de la versión 2.0 y .NET Framework 4.6 lo es de las versiones 4, 4.5, 4.5.1 y 4.5.2. Para más información, consulte [Versiones y dependencias de .NET Framework](../../../docs/framework/migration-guide/versions-and-dependencies.md).  
  
 Si decide quitar .NET Framework, use siempre la opción **Programas y características** del Panel de control para desinstalarlo. No quite nunca una versión de .NET Framework manualmente.  
  
 Tenga en cuenta que se pueden cargar varias versiones de .NET Framework en un único equipo al mismo tiempo. Esto significa que no tiene que desinstalar las versiones anteriores para instalar una versión posterior.  
  
<a name="ForDevelopers"></a>   
## <a name="the-net-framework-for-developers"></a>.NET Framework para desarrolladores  
 Si es un desarrollador, puede elegir cualquier lenguaje de programación compatible con .NET Framework para crear la aplicación. Dado que .NET Framework proporciona independencia e interoperabilidad entre lenguajes, puede interactuar con otras aplicaciones y componentes de .NET Framework independientemente del lenguaje con el que se desarrollaron.  
  
 Para desarrollar aplicaciones o componentes de .NET Framework, haga lo siguiente:  
  
1.  Si no está preinstalado en el sistema operativo, instale la versión de .NET Framework que será el destino de su aplicación. La versión de producción más reciente es Framework. NET 4.7, que está preinstalada en Windows 10 Creators Update y puede descargarse en versiones anteriores del sistema operativo Windows. Para información sobre los requisitos de sistema de .NET Framework, consulte [Requisitos del sistema](../../../docs/framework/get-started/system-requirements.md). Para información sobre la instalación de otras versiones de .NET Framework, consulte [Guía de instalación](../../../docs/framework/install/guide-for-developers.md). Hay paquetes adicionales de .NET Framework que se publican fuera de banda. Para información sobre estos paquetes, consulte [.NET Framework y versiones fuera de banda](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md).  
  
2.  Seleccione el lenguaje o los lenguajes de .NET Framework que utilizará para desarrollar las aplicaciones. Hay varios lenguajes disponibles, incluido Visual Basic, C#, Visual F# y C++ en Microsoft. (Un lenguaje de programación que permita desarrollar aplicaciones de .NET Framework cumple las [especificaciones de Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkId=199862)).  
  
3.  Seleccione e instale el entorno de desarrollo que utilizará para crear aplicaciones y que admita el lenguaje o los lenguajes de programación elegidos. El entorno de desarrollo integrado de Microsoft para las aplicaciones de .NET Framework es [Visual Studio](http://go.microsoft.com/fwlink/?LinkId=325532). Está disponible en diversas ediciones comerciales y gratuitas.  
  
 Para más información sobre el desarrollo de aplicaciones destinadas a .NET Framework, consulte [Guía de desarrollo](../../../docs/framework/development-guide.md).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[Información general](../../../docs/framework/get-started/overview.md)|Proporciona información detallada para los desarrolladores que compilan aplicaciones cuyo destino es .NET Framework.|  
|[.NET Framework y versiones fuera de banda](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)|Describe las versiones fuera de banda de .NET Framework y cómo utilizarlas en la aplicación.|  
|[Requisitos del sistema](../../../docs/framework/get-started/system-requirements.md)|Muestra los requisitos de hardware y software para ejecutar .NET Framework.|  
|[.NET Core y código abierto](../../../docs/framework/get-started/net-core-and-open-source.md)|Describe qué es .NET Core con respecto a .NET Framework y cómo acceder a los proyectos de .NET Core de código abierto.|  
|[Documentación de .NET Core](https://docs.microsoft.com/dotnet/)|Documentación de referencia de API y conceptual de .NET Core.|  
|[Guía de instalación](../../../docs/framework/install/guide-for-developers.md)|Proporciona información sobre cómo instalar .NET Framework.|  
  
## <a name="see-also"></a>Vea también  
 [.NET Framework 4.5 y 4.6](../../../docs/framework/index.md)   
 [Novedades](../../../docs/framework/whats-new/index.md)   
 [Biblioteca de clases .NET Framework](http://go.microsoft.com/fwlink/?LinkId=227195)   
 [Guía de desarrollo](../../../docs/framework/development-guide.md)
