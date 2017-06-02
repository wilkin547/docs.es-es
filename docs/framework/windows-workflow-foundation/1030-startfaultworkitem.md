---
title: "1030 - StartFaultWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1030 - StartFaultWorkItem
## Propiedades  
  
|||  
|-|-|  
|Id.|1030|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que un FaultWorkItem está iniciando la ejecución.  
  
## Mensaje  
 Iniciando la ejecución de un FaultWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'. La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|FaultActivity|xs:string|Nombre de tipo de la actividad que generó el error.|  
|FaultActivityDisplayName|xs:string|Nombre para mostrar de la actividad que generó el error.|  
|FaultActivityInstanceId|xs:string|Identificador de la actividad que generó el error.|  
|ExceptionActivity|xs:string|El nombre de tipo para mostrar de la actividad que produjo la excepción.|  
|ExceptionActivityDisplayName|xs:string|El nombre para mostrar de la actividad que produjo la excepción.|  
|ExceptionActivityInstanceId|xs:string|Identificador de instancia de la actividad que generó la excepción.|  
|Excepción|xs:string|Detalles de la excepción para la excepción|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|