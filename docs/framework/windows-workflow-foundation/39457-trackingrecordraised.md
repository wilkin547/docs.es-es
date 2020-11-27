---
title: 39457 - TrackingRecordRaised
ms.date: 03/30/2017
ms.assetid: 5a2731d1-c731-4b79-bb69-016cb69ef481
ms.openlocfilehash: 5bf343f29528bdb3941e253b2fd5b39799d94c2a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275910"
---
# <a name="39457---trackingrecordraised"></a>39457 - TrackingRecordRaised

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|39457|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que un TrackingRecord se ha iniciado en un TrackingParticipant.  
  
## <a name="message"></a>Message  

 Registro de seguimiento %1 desencadenado para %2.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|Número del registro de seguimiento.|  
|ParticipantId|xs:string|Participante de seguimiento.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
