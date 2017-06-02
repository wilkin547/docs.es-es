---
title: "System.ServiceModel.Channels.TcpConnectError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 22d93797-072e-405d-a3e0-5c519ddf290b
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# System.ServiceModel.Channels.TcpConnectError
Error en la operación de conexión TCP.  
  
## Descripción  
 Este seguimiento de traza de nivel de advertencia indica un error en la conexión a un extremo TCP.Esto podría suceder si el extremo remoto no responde en una dirección IP y puerto determinados.Puede omitirse este seguimiento de traza si se realizan correctamente otros intentos posteriores de conexión con otras direcciones IP válidas \(como direcciones IPv4 o IPv6, u otras direcciones IP que representan un nombre de host concreto\).La excepción de este seguimiento de traza puede revelar información adicional acerca del error.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)