---
title: "Troubleshooting: Debugging Windows Services | Microsoft Docs"
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
  - "debugging Windows Service applications"
  - "debugging [Visual Studio], Windows services"
  - "troubleshooting service applications"
  - "services, troubleshooting"
  - "troubleshooting debugging, Windows Services"
  - "Windows Service applications, debugging"
  - "services, debugging"
  - "Windows Service applications, troubleshooting"
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 8
---
# Troubleshooting: Debugging Windows Services
Al depurar una aplicación de servicios de Windows, interactúan el servicio y el **Administrador de servicios de Windows**.  El **Administrador de servicios** inicia el servicio mediante una llamada al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y, a continuación, espera 30 segundos el retorno del método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.  Si el método no retorna en este tiempo, el administrador mostrará un mensaje de error que indica que no es posible iniciar el servicio.  
  
 Al depurar el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>de la forma descrita en [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), debe tener en cuenta este período de 30 segundos.  Si se coloca un punto de interrupción en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y no avanza antes de 30 segundos, el administrador no iniciará el servicio.  
  
## Vea también  
 [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)   
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)