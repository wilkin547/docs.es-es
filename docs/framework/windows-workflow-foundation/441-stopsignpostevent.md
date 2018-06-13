---
title: 441- StopSignpostEvent1
ms.date: 03/30/2017
ms.assetid: fc9850a5-0dc3-4b84-a09a-744301c7c18e
ms.openlocfilehash: 69430372a472b19caaa9f1de9c0f06886001353e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511301"
---
# <a name="441--stopsignpostevent1"></a>441- StopSignpostEvent1
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|441|  
|Palabras clave|Solución de problemas|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 En el seguimiento de la actividad, indica que un mensaje ha terminado de cruzar el límite de la actividad para enviar o recibir.  
  
## <a name="message"></a>Mensaje  
 Límite de la actividad.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Extended Data|`xs:string`|El nombre de la actividad.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
