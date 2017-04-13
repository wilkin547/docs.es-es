---
title: "Contadores de rendimiento de los servicios | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Contadores de rendimiento de los servicios
Los contadores de rendimiento del servicio miden el conjunto del comportamiento del servicio y se utilizan para diagnosticar el rendimiento de todo el servicio.Se pueden encontrar bajo el objeto de rendimiento `ServiceModelService 4.0.0.0` al visualizarlo mediante el monitor de rendimiento \(Perfmon.exe\).Los nombres de las instancias se establecen utilizando el siguiente modelo:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.Cuando un nombre de instancia de contador [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] supera la longitud máxima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] reemplaza una parte del nombre de instancia con un valor hash.  
  
## Vea también  
 [Contadores de rendimiento](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)