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
ms.openlocfilehash: 8f6a117d1e2fe76c271b0b014e6079370c8b4fe4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127059"
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity (Interfaz)
Representa una referencia a la firma única de un objeto de código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Obtiene un puntero de interfaz a una nueva instancia de `IReferenceIdentity` que es idéntica a esta `IReferenceIdentity`, excepto por los cambios de atributo especificados.|  
|`IReferenceIdentity::EnumAttributes`|Obtiene un puntero de interfaz a una instancia de `IEnumIDENTITY_ATTRIBUTE` que contiene los atributos asociados a este `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Obtiene el valor del atributo en el espacio de nombres especificado, con el nombre especificado.|  
|`IReferenceIdentity::SetAttribute`|Establece el atributo que tiene el espacio de nombres especificado y el nombre especificado en el valor especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IEnumIDENTITY_ATTRIBUTE (interfaz)](ienumidentity-attribute-interface.md)
