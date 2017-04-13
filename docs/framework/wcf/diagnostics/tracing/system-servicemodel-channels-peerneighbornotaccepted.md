---
title: "System.ServiceModel.Channels.PeerNeighborNotAccepted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 77309bf5-37ba-4b90-b31f-c00ef044db0d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# System.ServiceModel.Channels.PeerNeighborNotAccepted
Un vecino del mismo nivel no se ha aceptado.  
  
## Descripción  
 Este seguimiento se produce al procesar una conexión a un vecino.Entre las posibles razones, se pueden citar la no coincidencia de la configuración de seguridad, que se supere el tiempo de espera, un vecino que no puede aceptar una conexión o problemas transitorios en la red.  
  
## Solución de problemas  
 Compruebe que no exista una configuración de seguridad no coincidente, que no se haya agotado el tiempo de espera, que no exista una incapacidad del vecino para aceptar una conexión o problemas de red temporales.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)