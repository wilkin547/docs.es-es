---
title: "39457 - TrackingRecordRaised | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a2731d1-c731-4b79-bb69-016cb69ef481
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 39457 - TrackingRecordRaised
## Propiedades  
  
|||  
|-|-|  
|Id.|39457|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que un TrackingRecord se ha iniciado en un TrackingParticipant.  
  
## Mensaje  
 Registro de seguimiento %1 desencadenado para %2.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|RecordNumber|xs:string|Número del registro de seguimiento.|  
|ParticipantId|xs:string|Participante de seguimiento.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|