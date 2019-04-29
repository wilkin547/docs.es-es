---
title: IReferenceAppId (Interfaz)
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25733e459423500352595d6be0eee26ef75ca7e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789693"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId (Interfaz)
Representa una referencia al identificador único para la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Obtiene un puntero a una representación de cadena del identificador del código de la aplicación que hace referencia esta `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Establece el identificador de código de la aplicación que hace referencia esta `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Obtiene un puntero de interfaz a un `IEnumReferenceIdentity` instancia que contiene el `IReferenceIdentity` instancias que representan los miembros de este `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Obtiene un puntero a una representación de cadena del identificador del token para una suscripción a este `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Establece el identificador de token para una suscripción a este `IReferenceAppId` al valor de cadena especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Isolation.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IEnumReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [IReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
