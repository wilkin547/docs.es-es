---
title: 402 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
ms.openlocfilehash: ff32c900f4e357b7f1eca669a0ea60f80ea24b19
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258327"
---
# <a name="402---startsignpostevent"></a>402 - StartSignpostEvent

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|402|  
|Palabras clave|Solución de problemas|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Este evento marca el inicio de una actividad de un extremo a otro. Contiene el nombre de la actividad.  
  
## <a name="message"></a>Message  

 Límite de la actividad.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Extended Data|`xs:string`|El nombre de la actividad.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
