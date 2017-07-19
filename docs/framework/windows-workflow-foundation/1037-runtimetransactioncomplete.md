---
title: "1037 - RuntimeTransactionComplete | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1037 - RuntimeTransactionComplete
## Propiedades  
  
|||  
|-|-|  
|Id.|1037|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que la transacción en tiempo de ejecución se ha completado.  
  
## Mensaje  
 La transacción en tiempo de ejecución se ha completado con el estado '%1'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Estado|xs:string|Estado de la transacción.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|