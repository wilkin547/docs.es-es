---
description: 'Más información acerca de: 402-StartSignpostEvent'
title: 402 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
ms.openlocfilehash: e77cac50be2a2e96fabe1301aaeab7ff74142e5a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99656688"
---
# <a name="402---startsignpostevent"></a>402 - StartSignpostEvent

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|402|  
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
