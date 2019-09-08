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
ms.openlocfilehash: 522ed80f161f114af25e1fa7ad041c8238073d6f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796370"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId (Interfaz)
Representa una referencia al identificador único de la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Obtiene un puntero a una representación de cadena del identificador de código para la aplicación a la que hace `IReferenceAppId`referencia este.|  
|`IReferenceAppId::put_CodeBase`|Establece el identificador de código de la aplicación a la que hace `IReferenceAppId`referencia este.|  
|`IReferenceAppId::EnumAppPath`|Obtiene un puntero de interfaz a `IEnumReferenceIdentity` una instancia de `IReferenceIdentity` que contiene las instancias de que `IReferenceAppId`representan a los miembros de este objeto.|  
|`IReferenceAppId::get_SubscriptionId`|Obtiene un puntero a una representación de cadena del identificador de token de una suscripción a este `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Establece el identificador de token de una suscripción en `IReferenceAppId` el valor de cadena especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IEnumReferenceIdentity (interfaz)](ienumreferenceidentity-interface.md)
- [IReferenceIdentity (interfaz)](ireferenceidentity-interface.md)
