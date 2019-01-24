---
title: IDefinitionIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb97c545d2d57ef589b5a7a5b3618eaa2b6f364f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687003"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity (Interfaz)
Representa la firma única del código que define la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Obtiene un puntero de interfaz a una nueva `IDefinitionIdentity` objeto que es idéntica a esta `IDefinitionIdentity`, excepto los cambios de atributo especificado.|  
|`IDefinitionIdentity::EnumAttributes`|Obtiene un puntero de interfaz a un [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) objeto que contiene los atributos asociados con este `IDefinitionIdentity`.|  
|`IDefinitionIdentity::GetAttribute`|Obtiene el valor del atributo con el nombre especificado en el espacio de nombres especificado.|  
|`IDefinitionIdentity::SetAttribute`|Establece el atributo que tiene el nombre especificado en el espacio de nombres especificado en el valor especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Isolation.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
