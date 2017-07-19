---
title: "3501 - InferredContractDescription | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 21a70849-4fc0-41d2-b9a4-db5aa2acdf1a
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3501 - InferredContractDescription
## Propiedades  
  
|||  
|-|-|  
|Id.|3501|  
|Palabras clave|WFServices|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 Indica que un ContractDescription se ha inferido de WorkflowService.  
  
## Mensaje  
 ContractDescription con Name\='%1' y Namespace\='%2' se ha inferido de WorkflowService.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Name|xs:string|Nombre de ContractDescription.|  
|Espacio de nombres|xs:string|Espacio de nombres ContractDescription.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|