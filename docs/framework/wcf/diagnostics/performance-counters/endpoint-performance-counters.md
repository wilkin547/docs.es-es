---
title: "Contadores de rendimiento del extremo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Contadores de rendimiento del extremo
Los contadores de rendimiento del extremo capturan datos que revelan cómo un extremo está aceptando los mensajes.Se pueden encontrar en el objeto de rendimiento `ServiceModelEndpoint 4.0.0.0` al verlo con el Monitor de rendimiento.Las instancias se denominan utilizando este modelo:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Los datos son similares a los datos reunidos para las operaciones individuales, pero solo se agregan a lo largo del extremo.  
  
> [!CAUTION]
>  Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.Cuando un nombre de instancia de contador [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] supera la longitud máxima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] reemplaza una parte del nombre de instancia con un valor hash.  
  
## Vea también  
 [Contadores de rendimiento](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)