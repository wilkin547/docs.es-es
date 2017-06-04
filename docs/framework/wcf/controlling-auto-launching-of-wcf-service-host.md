---
title: "Controlar inicio autom&#225;tico del host de servicio de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WcfOptions"
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Controlar inicio autom&#225;tico del host de servicio de WCF
Puede controlar la capacidad de inicio automático del host de servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] \(WcfSvcHost.exe\) para un proyecto de biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] al depurar otro proyecto de la misma solución de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] que contiene varios proyectos.  
  
 Para ello, haga clic con el botón secundario en el proyecto de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en el **Explorador de soluciones**, elija **Propiedades** y haga clic en la pestaña **Opciones de WCF**.La casilla **Iniciar el host de servicio de WCF al depurar otro proyecto de la misma solución** está activada de forma predeterminada.Puede desactivarla para que no se inicie el host de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para este proyecto concreto cuando se depure otro proyecto en la misma solución.  
  
 Este comportamiento no afecta a la depuración de F5 o a las funcionalidades de Agregar referencia de servicio para este proyecto.  
  
 Esta opción está disponible para los proyectos siguientes:  
  
-   Proyecto de biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Proyecto de biblioteca de servicio de flujo de trabajo secuencial.  
  
-   Proyecto de biblioteca de servicio de flujo de trabajo de equipo de estado.  
  
-   Proyecto de biblioteca de servicio de distribución.  
  
## Vea también  
 [Host de servicio WCF \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)