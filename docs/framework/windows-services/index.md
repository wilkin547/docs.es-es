---
title: "Developing Windows Service Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ServiceInstaller class, Windows Service applications"
  - "Service class, Windows Service applications"
  - "Windows Service applications"
  - "Windows NT services"
  - "ServiceProcessInstaller class, Windows Service applications"
  - "services"
  - ".NET applications, Windows applications"
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: 18
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 18
---
# Developing Windows Service Applications
Si usa Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o el SDK de Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], puede crear fácilmente servicios mediante la creación de una aplicación que se instale como servicio.  Este tipo de aplicación se denomina Servicio de Windows.  Con las características del marco de trabajo, es posible crear servicios, instalarlos, iniciarlos, detenerlos y controlar su comportamiento.  
  
> [!WARNING]
>  La plantilla de servicio de Windows para C\+\+ no incluida en Visual Studio 2010.  Para crear un servicio de Windows, puede crear un servicio en código administrado en Visual c\# o Visual Basic, que puede interoperar con el código existente de C\+\+ si es necesario, o puede crear un servicio de Windows en C\+\+ nativo mediante [Asistente para proyectos ATL](../Topic/ATL%20Project%20Wizard.md).  
  
## En esta sección  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Proporciona información general sobre las aplicaciones de servicios de Windows, la duración de un servicio, y cómo las aplicaciones de servicios difieren de otros tipos de proyecto comunes.  
  
 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Proporciona un ejemplo de cómo crear un servicio en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] y Visual C\#.  
  
 [Service Application Programming Architecture](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Explica los elementos del lenguaje que se utilizan en la programación de servicios.  
  
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Describe el proceso de crear y configurar servicios de Windows mediante la plantilla de proyecto servicio de Windows.  
  
## Secciones relacionadas  
 <xref:System.ServiceProcess.ServiceBase>  
 Describe las características principales de la clase <xref:System.ServiceProcess.ServiceBase>, utilizada para crear servicios.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Describe las características de la clase <xref:System.ServiceProcess.ServiceProcessInstaller>, que se utiliza junto con la clase <xref:System.ServiceProcess.ServiceInstaller> para instalar y desinstalar servicios.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Describe las características de la clase <xref:System.ServiceProcess.ServiceInstaller>, que se utiliza junto con la clase <xref:System.ServiceProcess.ServiceProcessInstaller> para instalar y desinstalar el servicio.  
  
 [Crear proyectos a partir de plantillas](http://msdn.microsoft.com/es-es/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Describe los tipos de proyectos utilizados en este capítulo y cómo se pueden elegir.