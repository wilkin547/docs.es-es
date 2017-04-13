---
title: "1035 - RuntimeTransactionSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1035 - RuntimeTransactionSet
## Propiedades  
  
|||  
|-|-|  
|Id.|1035|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que una actividad ha establecido la transacción en tiempo ejecución.  
  
## Mensaje  
 La transacción en tiempo de ejecución ha sido establecida por la actividad '%1', DisplayName: '%2', InstanceId: '%3'. Ejecución aislada para la actividad '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|IsolatedActivity|xs:string|El nombre de tipo para mostrar de la actividad en la que la transacción está aislada.|  
|IsolatedActivityDisplayName|xs:string|El nombre para mostrar de la actividad en la que la transacción está aislada.|  
|IsolatedActivityInstanceId|xs:string|El identificador de la instancia de la actividad en la que la transacción está aislada.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|