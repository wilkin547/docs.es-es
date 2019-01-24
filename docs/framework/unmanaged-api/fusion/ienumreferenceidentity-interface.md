---
title: IEnumReferenceIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f2ea9d0e20cb67cc36d0b5883e483ce98941b2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743223"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity (Interfaz)
Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Obtiene un puntero de interfaz a una nueva `IEnumReferenceIdentity` que contiene los mismos miembros que esto `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Next`|Obtiene el número especificado de `IReferenceIdentity` objetos, empezando en la posición actual.|  
|`IEnumReferenceIdentity::Reset`|Mueve el puntero de instrucción al principio de este `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Mueve el puntero de instrucción al día por el número especificado de elementos, empezando por la posición actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Isolation.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
