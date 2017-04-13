---
title: "Extremo: Errores en llamadas por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Extremo: Errores en llamadas por segundo
Nombre del contador: Errores de llamadas por segundo.  
  
## Descripción  
 Número de llamadas que han devuelto errores a este extremo en un segundo.  
  
 Este contador es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)  
  
 En las aplicaciones [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], los métodos de servicio comunican la información sobre errores de procesamiento mediante mensajes de error SOAP.Los errores SOAP son tipos de mensaje que se incluyen en los metadatos de una operación del servicio y, por consiguiente, crean un contrato de error que los clientes pueden utilizar para que su ejecución sea más sólida o interactiva.Dado que los errores SOAP se muestran a los clientes en formato XML, son sumamente interoperativos.  
  
## Vea también  
 [Especificación y administración de errores en contratos y servicios](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)