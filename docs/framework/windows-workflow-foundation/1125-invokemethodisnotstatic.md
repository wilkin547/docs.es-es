---
description: 'Más información acerca de: 1125-InvokeMethodIsNotStatic'
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: cd63b7b75121a70f7d7bad6a799827971aa4eae9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667374"
---
# <a name="1125---invokemethodisnotstatic"></a>1125 - InvokeMethodIsNotStatic

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1125|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Durante el paso CacheMetadata, la actividad InvokeMethod indica que el método que se va a invocar no es estático.  
  
## <a name="message"></a>Message  

 InvokeMethod '%1': el método no es estático.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Identificación y nombre para mostrar de la actividad InvokeMethod.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
