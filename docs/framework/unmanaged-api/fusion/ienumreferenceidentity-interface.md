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
ms.openlocfilehash: 766b17bae0c58d9872ff9c118f330ebc3220257e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697256"
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
