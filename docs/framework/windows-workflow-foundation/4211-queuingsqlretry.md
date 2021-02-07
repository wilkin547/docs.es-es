---
description: 'Más información acerca de: 4211-QueuingSqlRetry'
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: 674914ee105bb0a48f8c32efbd573c685d22d9f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742711"
---
# <a name="4211---queuingsqlretry"></a>4211 - QueuingSqlRetry

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|4211|  
|Palabras clave|WFInstanceStore|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica poner en cola el intento de SQL.  
  
## <a name="message"></a>Message  

 Poniendo en cola el reintento SQL con %1 milisegundos de retraso.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Delay|xs:string|El retraso entre los reintentos.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
