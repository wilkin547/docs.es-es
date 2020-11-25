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
ms.openlocfilehash: 9aa7173d81d84d9080d90b0890769ffeaee6a738
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728620"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId (Interfaz)

Representa una referencia al identificador único de la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Obtiene un puntero a una representación de cadena del identificador de código para la aplicación a la que hace referencia este `IReferenceAppId` .|  
|`IReferenceAppId::put_CodeBase`|Establece el identificador de código de la aplicación a la que hace referencia este `IReferenceAppId` .|  
|`IReferenceAppId::EnumAppPath`|Obtiene un puntero de interfaz a una `IEnumReferenceIdentity` instancia de que contiene las `IReferenceIdentity` instancias de que representan a los miembros de este objeto `IReferenceAppId` .|  
|`IReferenceAppId::get_SubscriptionId`|Obtiene un puntero a una representación de cadena del identificador de token de una suscripción a este `IReferenceAppId` .|  
|`IReferenceAppId::put_SubscriptionId`|Establece el identificador de token de una suscripción en `IReferenceAppId` el valor de cadena especificado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IEnumReferenceIdentity (Interfaz)](ienumreferenceidentity-interface.md)
- [IReferenceIdentity (Interfaz)](ireferenceidentity-interface.md)
