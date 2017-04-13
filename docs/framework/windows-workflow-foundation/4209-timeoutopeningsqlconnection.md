---
title: "4209 - TimeoutOpeningSqlConnection | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4209 - TimeoutOpeningSqlConnection
## Propiedades  
  
|||  
|-|-|  
|Id.|4209|  
|Palabras clave|WFInstanceStore|  
|Nivel|Error|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que se ha alcanzado el tiempo de espera al intentar abrir una conexión SQL.  
  
## Mensaje  
 Se agotó el tiempo de espera al intentar abrir una conexión SQL.  La operación no se completó dentro del tiempo de espera asignado de %1.  El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Timeout|xs:string|Valor de tiempo de espera para abrir la conexión SQL.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|