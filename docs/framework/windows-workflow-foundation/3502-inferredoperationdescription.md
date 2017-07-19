---
title: "3502 - InferredOperationDescription | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3502 - InferredOperationDescription
## Propiedades  
  
|||  
|-|-|  
|Id.|3502|  
|Palabras clave|WFServices|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 Indica que un OperationDescription se ha inferido de WorkflowService.  
  
## Mensaje  
 OperationDescription con Name\='%1' en el contrato '%2' se ha inferido de WorkflowService.  IsOneWay\=%3.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|OperationName|xs:string|Nombre de la operación.|  
|ContractName|xs:string|El nombre del contrato.|  
|IsOneWay|xs:string|True o false para indicar si el contrato es unidireccional.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|