---
description: 'Más información acerca de: 451-MessageLogInfo'
title: 451 - MessageLogInfo
ms.date: 03/30/2017
ms.assetid: 485b4b29-dc21-4a35-93f8-5f4726d6aa5a
ms.openlocfilehash: 9df1911eaee3300b770175f2af26e6dafd3de90c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760282"
---
# <a name="451---messageloginfo"></a>451 - MessageLogInfo

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|451|  
|Palabras clave|Solución de problemas, WCFMessageLogging|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Se emite este evento cuando se envía la información del registro de mensajes.  
  
## <a name="message"></a>Message  

 %1  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|data1|`xs:string`||  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
