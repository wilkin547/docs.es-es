---
title: IReferenceIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
ms.openlocfilehash: 867c09caa3bd3aed50de21c2ef91a02782830be2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704557"
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity (Interfaz)

Representa una referencia a la firma única de un objeto de código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Obtiene un puntero de interfaz a una nueva `IReferenceIdentity` instancia de que es idéntica a esta `IReferenceIdentity` , salvo por los cambios de atributo especificados.|  
|`IReferenceIdentity::EnumAttributes`|Obtiene un puntero de interfaz a una `IEnumIDENTITY_ATTRIBUTE` instancia de que contiene los atributos asociados a este `IReferenceIdentity` .|  
|`IReferenceIdentity::GetAttribute`|Obtiene el valor del atributo en el espacio de nombres especificado, con el nombre especificado.|  
|`IReferenceIdentity::SetAttribute`|Establece el atributo que tiene el espacio de nombres especificado y el nombre especificado en el valor especificado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IEnumIDENTITY_ATTRIBUTE (Interfaz)](ienumidentity-attribute-interface.md)
