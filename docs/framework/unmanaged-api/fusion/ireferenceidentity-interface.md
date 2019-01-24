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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb8686342b20bd6afe0a4c4803d64428ed95c98b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665778"
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity (Interfaz)
Representa una referencia a la firma única de un objeto de código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Obtiene un puntero de interfaz a una nueva `IReferenceIdentity` que es idéntica a esta instancia de `IReferenceIdentity`, excepto los cambios de atributo especificado.|  
|`IReferenceIdentity::EnumAttributes`|Obtiene un puntero de interfaz a un `IEnumIDENTITY_ATTRIBUTE` instancia que contiene los atributos asociados con este `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Obtiene el valor del atributo en el espacio de nombres especificado, con el nombre especificado.|  
|`IReferenceIdentity::SetAttribute`|Establece el atributo que tiene el espacio de nombres especificado y el nombre especificado en el valor especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Isolation.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IEnumIDENTITY_ATTRIBUTE (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
