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
ms.openlocfilehash: 4ebc9fe36955bac8b93ec95e9a55fc8ac1197d9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429126"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity (Interfaz)
Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Obtiene un puntero de interfaz a una nueva `IEnumReferenceIdentity` que contiene los mismos miembros que esto `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Next`|Obtiene el número especificado de `IReferenceIdentity` módulos, comenzando en la posición actual.|  
|`IEnumReferenceIdentity::Reset`|Mueve el puntero de instrucción al principio de este `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Mueve el puntero de instrucción hacia delante el número especificado de elementos, empezando en la posición actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Isolation.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
