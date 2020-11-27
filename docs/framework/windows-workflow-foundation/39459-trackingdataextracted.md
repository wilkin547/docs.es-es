---
title: 39459 - TrackingDataExtracted
ms.date: 03/30/2017
ms.assetid: fcf7be96-8a7b-4ae1-bf38-b77ea9ebfb6b
ms.openlocfilehash: c830bba55d3cde8a922ee021df1351d94fbcb8d2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275884"
---
# <a name="39459---trackingdataextracted"></a>39459 - TrackingDataExtracted

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|39459|  
|Palabras clave|WFRuntime|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que los datos de seguimiento se han extraído en una actividad.  
  
## <a name="message"></a>Message  

 Datos de seguimiento %1 extraídos en la actividad %2.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|data|xs:string|Nombre de los datos extraídos.|  
|Actividad|xs:string|El nombre de la actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
