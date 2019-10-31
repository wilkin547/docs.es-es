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
ms.openlocfilehash: 5114f74e80da925c7a153b9e481c54067152eaec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108199"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId (Interfaz)
Representa un identificador único para el código que define la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Obtiene una cadena con formato que representa el código de este objeto `IDefinitionAppId`.|  
|`IDefinitionAppId::put_Codebase`|Establece el código de este objeto `IDefinitionAppId` en el valor de cadena con formato especificado.|  
|`IDefinitionAppId::EnumAppPath`|Obtiene un puntero de interfaz a un objeto [IEnumDefinitionIdentity (](ienumdefinitionidentity-interface.md) que contiene los ensamblados de la ruta de acceso de la aplicación actual.|  
|`IDefinitionAppId::SetAppPath`|Establece la ruta de acceso de la aplicación para el ensamblado en el ámbito actual en el valor al que hace referencia el objeto [IDefinitionIdentity](idefinitionidentity-interface.md) especificado.|  
|`IDefinitionAppId::get_SubscriptionId`|Obtiene un puntero a una representación de cadena del identificador de token de una suscripción a este objeto `IDefinitionAppId`.|  
|`IDefinitionAppId::put_SubscriptionId`|Establece el identificador de token de una suscripción a este objeto `IDefinitionAppId` en el valor de cadena especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
