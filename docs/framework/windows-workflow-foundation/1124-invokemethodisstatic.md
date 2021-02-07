---
description: 'Más información acerca de: 1124-InvokeMethodIsStatic'
title: 1124 - InvokeMethodIsStatic
ms.date: 03/30/2017
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
ms.openlocfilehash: 86febd9c94c2e4c533eb5ab4349855f6d048a5ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667387"
---
# <a name="1124---invokemethodisstatic"></a>1124 - InvokeMethodIsStatic

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1124|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Durante el paso CacheMetadata, la actividad InvokeMethod indica que el método que se va a invocar es estático.  
  
## <a name="message"></a>Message  

 InvokeMethod '%1': el método es estático.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Identificación y nombre para mostrar de la actividad InvokeMethod.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
