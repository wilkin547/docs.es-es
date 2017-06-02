---
title: "Env&#237;o y control de errores | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Env&#237;o y control de errores
En este ejemplo se muestra cómo utilizar las actividades de mensajería <xref:System.ServiceModel.Activities.ReceiveReply> y <xref:System.ServiceModel.Activities.SendReply> para enviar y recibir errores esperados e inesperados.En este escenario, la primera solicitud de cliente genera un error esperado que se ha incluido en su colección <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>.Las siguientes solicitudes de cliente producen la recepción de errores inesperados, antes de que la solicitud final se realice correctamente.  
  
## Para utilizar este ejemplo  
  
1.  Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic con el botón secundario en el icono [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y seleccionando **Ejecutar como administrador**.  
  
2.  Abra el archivo de solución Faults.sln.  
  
3.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
4.  Ejecute el proyecto de servicio.  
  
    1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el proyecto `FaultService` y seleccione **Establecer como proyecto de inicio**.  
  
    2.  Presione CTRL\+F5.  
  
5.  Abra otra copia de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic con el botón secundario en el icono [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y seleccionando **Ejecutar como administrador**.  
  
6.  Abra el archivo de solución Faults.sln.  
  
7.  Ejecute el proyecto de cliente.  
  
    1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el proyecto `FaultClient` y seleccione **Establecer como proyecto de inicio**.  
  
    2.  Presione CTRL\+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Services\Faults`  
  
## Vea también