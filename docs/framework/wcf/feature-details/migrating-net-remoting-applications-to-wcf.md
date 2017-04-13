---
title: "Migraci&#243;n de aplicaciones de .NET Remoting a WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ", NET remoting [WCF]"
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Migraci&#243;n de aplicaciones de .NET Remoting a WCF
**Este tema es específico de una tecnología heredada que se mantiene para la compatibilidad con versiones anteriores con aplicaciones existentes y no se recomienda para nuevo desarrollo.Las aplicaciones distribuidas se deben desarrollar ahora usando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**  
  
 Hay dos maneras de sacar provecho de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con aplicaciones .NET Remoting existentes: la integración y la migración.La integración le permite tener .Net Remoting 2.0 e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ejecutándose lado a lado, permitiéndole exponer los mismos objetos de negocio sobre ambas tecnologías de manera simultánea sin tener que modificar su código existente de .NET Remoting 2.0.La integración requiere que trabaje con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o posterior.Si desea aprovecharse de las características de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y no necesita la compatibilidad de la conexión con sistemas de comunicación remota 2.0, puede migrar su servicio a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].La migración de .NET Remoting 2.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere la realización de cambios en la interfaz del objeto remoto y su configuración.Ambos temas se cubren en [De la comunicación remota a Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).  
  
## Vea también  
 [Información conceptual](../../../../docs/framework/wcf/conceptual-overview.md)