---
title: Desarrollar aplicaciones de servicios de Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 2912568e967c8c6096842b1b4f24eac88318dffb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="developing-windows-service-applications"></a>Desarrollar aplicaciones de servicios de Windows
Mediante Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, puede crear fácilmente servicios mediante la creación de una aplicación que se instala como un servicio. Este tipo de aplicación se denomina un servicio de Windows. Características del marco de trabajo, puede crear servicios, instalarlos e iniciar, detener y controlar su comportamiento.  
  
> [!WARNING]
>  La plantilla de servicio de Windows de C++ no se incluyó en Visual Studio 2010. Para crear un servicio de Windows, puede crear un servicio en código administrado en Visual C# o Visual Basic, que puede interactuar con el código de C++ existente si es necesario, o puede crear un servicio de Windows en C++ nativo mediante el [Asistente para proyectos de ATL](/cpp/atl/reference/atl-project-wizard).  
  
## <a name="in-this-section"></a>En esta sección  
 [Introducción a las aplicaciones de servicio de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Proporciona información general de las aplicaciones de servicio de Windows, la duración de un servicio, y cómo las aplicaciones de servicio se diferencian de otros tipos de proyecto comunes.  
  
 [Tutorial: Crear una aplicación de servicio de Windows en el Diseñador de componentes](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Proporciona un ejemplo de creación de un servicio en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] y Visual C#.  
  
 [Arquitectura de programación de aplicaciones de servicio](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Explica los elementos de lenguaje que se utilizan en la programación de servicio.  
  
 [Cómo: crear servicios de Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Describe el proceso de creación y configuración de servicios de Windows mediante la plantilla de proyecto de servicio de Windows.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 <xref:System.ServiceProcess.ServiceBase>  
 Describe las características principales de la <xref:System.ServiceProcess.ServiceBase> (clase), que se utiliza para crear servicios.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Describe las características de la <xref:System.ServiceProcess.ServiceProcessInstaller> (clase), que se utiliza junto con la <xref:System.ServiceProcess.ServiceInstaller> clase para instalar y desinstalar servicios.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Describe las características de la <xref:System.ServiceProcess.ServiceInstaller> (clase), que se utiliza junto con la <xref:System.ServiceProcess.ServiceProcessInstaller> clase para instalar y desinstalar el servicio.  
  
 [NIB crear proyectos a partir de plantillas](http://msdn.microsoft.com/en-us/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Describe los proyectos de tipos utilizados en este capítulo y cómo elegir entre ellos.
