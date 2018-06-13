---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513170"
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
  
## <a name="message"></a>Mensaje  
 Se agotó el tiempo de espera al intentar abrir una conexión SQL. La operación no se completó dentro del tiempo de espera asignado de %1. El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Timeout|xs:string|Valor de tiempo de espera para abrir la conexión SQL.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
