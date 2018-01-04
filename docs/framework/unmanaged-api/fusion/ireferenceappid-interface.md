---
title: IReferenceAppId (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceAppId
helpviewer_keywords: IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22ac2d75632b3c670d7c185cbbf5081732dcaffc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [IReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
