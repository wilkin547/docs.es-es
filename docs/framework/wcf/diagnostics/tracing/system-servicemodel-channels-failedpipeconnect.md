---
title: "System.ServiceModel.Channels.FailedPipeConnect | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.FailedPipeConnect
Se produjo un error al intentar conectar al extremo de la canalización con nombre.Se realiza otro intento dentro del período de tiempo de espera especificado.  
  
## Descripción  
 Este seguimiento de traza de información indica un error en la conexión con un extremo de canalización con nombre.Esto podría ocurrir si el extremo de canalización con nombre no se encuentra o está ocupado.Se realizan intentos adicionales, cada uno separado por un espacio de tiempo, hasta que uno se realiza correctamente o finaliza OpenTimeout.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)