---
title: IDefinitionAppId (Interfaz)
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e8bb31967a6ad515761e6cd03657f2c834debe5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545561"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId (Interfaz)
Representa un identificador único para el código que define la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Obtiene una cadena con formato que representa el código de esta `IDefinitionAppId` objeto.|  
|`IDefinitionAppId::put_Codebase`|Establece el código de este `IDefinitionAppId` objeto especificado del valor de cadena con formato.|  
|`IDefinitionAppId::EnumAppPath`|Obtiene un puntero de interfaz a un [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) objeto que contiene los ensamblados en la ruta de acceso de la aplicación actual.|  
|`IDefinitionAppId::SetAppPath`|Establece la ruta de acceso de la aplicación para el ensamblado en el ámbito actual en el valor al que hace referencia especificado [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) objeto.|  
|`IDefinitionAppId::get_SubscriptionId`|Obtiene un puntero a una representación de cadena del identificador del token para una suscripción a este `IDefinitionAppId` objeto.|  
|`IDefinitionAppId::put_SubscriptionId`|Establece el identificador de token para una suscripción a este `IDefinitionAppId` objeto por el valor de cadena especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Isolation.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
