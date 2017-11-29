---
title: 39457 - TrackingRecordRaised
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a2731d1-c731-4b79-bb69-016cb69ef481
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3d2e142db5834a6c867970a28ec74e9fceebee16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39457---trackingrecordraised"></a>39457 - TrackingRecordRaised
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|39457|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que un TrackingRecord se ha iniciado en un TrackingParticipant.  
  
## <a name="message"></a>Mensaje  
 Registro de seguimiento %1 desencadenado para %2.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|Número del registro de seguimiento.|  
|ParticipantId|xs:string|Participante de seguimiento.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
