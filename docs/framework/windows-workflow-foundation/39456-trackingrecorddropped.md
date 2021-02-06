---
description: 'Más información acerca de: 39456-TrackingRecordDropped'
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: 0f6920ef85327318f4ea8662ae36f26c7494bcb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631299"
---
# <a name="39456---trackingrecorddropped"></a>39456 - TrackingRecordDropped

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|39456|  
|Palabras clave|WFTracking|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que se ha quitado un registro de seguimiento porque su tamaño supera el máximo permitido por el proveedor de sesión ETW.  
  
## <a name="message"></a>Message  

 El tamaño del registro de seguimiento %1 excede el máximo permitido por la sesión de ETW para el proveedor %2  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Excepción|xs:string|Detalles de la excepción para la excepción|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
