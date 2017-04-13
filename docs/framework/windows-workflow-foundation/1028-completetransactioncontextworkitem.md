---
title: "1028 - CompleteTransactionContextWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1028 - CompleteTransactionContextWorkItem
## Propiedades  
  
|||  
|-|-|  
|Id.|1028|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que se ha completado un TransactionContextWorkItem.  
  
## Mensaje  
 Un TransactionContextWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|