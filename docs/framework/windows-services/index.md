---
title: Desarrollar aplicaciones de servicios de Windows
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: af6e4bf7697b3139f6809295737fdd0d90b7f013
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512273"
---
# <a name="developing-windows-service-applications"></a>Desarrollar aplicaciones de servicios de Windows
Con Microsoft Visual Studio o el SDK de Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], puede crear fácilmente servicios mediante la creación de una aplicación que se instale como un servicio. Este tipo de aplicación se denomina servicio Windows. Con las características de la plataforma, puede crear servicios, instalarlos e iniciar, detener y controlar su comportamiento.  
  
> [!WARNING]
>  La plantilla de servicio de Windows para C++ no se ha incluido en Visual Studio 2010. Para crear un servicio de Windows, puede crear un servicio en código administrado en Visual C# o Visual Basic, que podría interoperar con el código C++ existente si es necesario, o bien puede crear un servicio de Windows en C++ nativo mediante el [Asistente para proyectos ATL](/cpp/atl/reference/atl-project-wizard).  
  
## <a name="in-this-section"></a>En esta sección  
 [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Proporciona información general de las aplicaciones de servicio de Windows, la duración de un servicio y las diferencias entre las aplicaciones de servicio y otros tipos de proyectos comunes.  
  
 [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Proporciona un ejemplo de cómo crear un servicio en Visual Basic y Visual C#.  
  
 [Arquitectura de programación de aplicaciones de servicio](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Explica los elementos del lenguaje utilizados en la programación de servicios.  
  
 [Creación de servicios de Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Describe el proceso de creación y configuración de servicios de Windows mediante la plantilla de proyecto de servicio de Windows.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 <xref:System.ServiceProcess.ServiceBase>  
 Describe las características principales de la clase <xref:System.ServiceProcess.ServiceBase>, que se utiliza para crear servicios.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Describe las características de la clase <xref:System.ServiceProcess.ServiceProcessInstaller>, que se utiliza junto con la clase <xref:System.ServiceProcess.ServiceInstaller> para instalar y desinstalar servicios.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Describe las características de la clase <xref:System.ServiceProcess.ServiceInstaller>, que se utiliza junto con la clase <xref:System.ServiceProcess.ServiceProcessInstaller> para instalar y desinstalar su servicio.  
  
 [NIB: Crear proyectos a partir de plantillas](http://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Describe los tipos de proyectos utilizados en este capítulo y cómo elegir entre ellos.
