---
title: "Servicio: Errores en llamadas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Servicio: Errores en llamadas
Nombre de contador: Llamadas con errores.  
  
## Descripción  
 Número de llamadas a este servicio que han devuelto errores.En las aplicaciones [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], los métodos de servicio comunican la información sobre errores de procesamiento mediante mensajes de error SOAP.Los errores SOAP son tipos de mensaje que se incluyen en los metadatos de una operación del servicio y, por consiguiente, crean un contrato de error que los clientes pueden utilizar para que su ejecución sea más sólida o interactiva.Dado que los errores SOAP se muestran a los clientes en formato XML, son sumamente interoperativos.  
  
## Vea también  
 [Especificación y administración de errores en contratos y servicios](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)