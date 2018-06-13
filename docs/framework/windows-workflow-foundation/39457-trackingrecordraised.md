---
title: 39457 - TrackingRecordRaised
ms.date: 03/30/2017
ms.assetid: 5a2731d1-c731-4b79-bb69-016cb69ef481
ms.openlocfilehash: 104d3fb4b544172001051be7bccc3721cf8d6d1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512371"
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
