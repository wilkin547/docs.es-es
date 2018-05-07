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
ms.openlocfilehash: 2484fa61c03b95e7cbdb452b92a68a2049701374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId (Interfaz)
Representa una referencia al identificador único para la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Obtiene un puntero a una representación de cadena del identificador del código de la aplicación que hace referencia esta `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Establece el identificador de código de la aplicación que hace referencia esta `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Obtiene un puntero de interfaz a una `IEnumReferenceIdentity` instancia que contiene el `IReferenceIdentity` instancias que representan los miembros de este `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Obtiene un puntero a una representación de cadena del identificador del token para una suscripción a este `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Establece el identificador del token para una suscripción a este `IReferenceAppId` en el valor de cadena especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Isolation.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [IReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
