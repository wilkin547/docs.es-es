---
title: "3503 - DuplicateCorrelationQuery | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3503 - DuplicateCorrelationQuery
## Propiedades  
  
|||  
|-|-|  
|Id.|3503|  
|Palabras clave|WFServices|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 Indica que se encontró una CorrelationQuery duplicada.  La consulta duplicada no se usará al calcular la correlación.  
  
## Mensaje  
 Se encontró una consulta CorrelationQuery duplicada con Where\='%1'.  Esta consulta duplicada no se usará al calcular la correlación.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Where|xs:string|Proporción Where de la consulta de correlación.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|