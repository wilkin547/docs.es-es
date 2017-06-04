---
title: "Instancias | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Instancias
Nombre del contador: instancias.  
  
## Descripción  
 Número de contextos de instancias que el servicio contiene actualmente.  
  
 La mayoría del tiempo, el número de contextos de instancias es idéntico al número de instancias.  Sin embargo, los escenarios siguientes son la excepción a esta regla.  
  
-   Un método del servicio llama el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> explícitamente.  
  
-   Un <xref:System.ServiceModel.ReleaseInstanceMode> se aplica a una instancia <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## Vea también  
 <xref:System.ServiceModel.OperationBehaviorAttribute>