---
description: 'Más información acerca de: 4209-TimeoutOpeningSqlConnection'
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9c7540e328530fdc01b9f065dfb75b92c467bd43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787999"
---
# <a name="4209---timeoutopeningsqlconnection"></a>4209 - TimeoutOpeningSqlConnection

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|4209|  
|Palabras clave|WFInstanceStore|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que se ha alcanzado el tiempo de espera al intentar abrir una conexión SQL.  
  
## <a name="message"></a>Message  

 Se agotó el tiempo de espera al intentar abrir una conexión SQL. La operación no se completó dentro del tiempo de espera asignado de %1. El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Tiempo de espera|xs:string|Valor de tiempo de espera para abrir la conexión SQL.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
