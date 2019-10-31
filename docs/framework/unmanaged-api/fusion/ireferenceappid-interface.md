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
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131658"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId (Interfaz)
Representa una referencia al identificador único de la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Obtiene un puntero a una representación de cadena del identificador de código para la aplicación a la que hace referencia este `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Establece el identificador de código de la aplicación a la que hace referencia este `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Obtiene un puntero de interfaz a una instancia de `IEnumReferenceIdentity` que contiene las instancias de `IReferenceIdentity` que representan a los miembros de este `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Obtiene un puntero a una representación de cadena del identificador de token de una suscripción a esta `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Establece el identificador de token de una suscripción a esta `IReferenceAppId` en el valor de cadena especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IEnumReferenceIdentity (interfaz)](ienumreferenceidentity-interface.md)
- [IReferenceIdentity (interfaz)](ireferenceidentity-interface.md)
