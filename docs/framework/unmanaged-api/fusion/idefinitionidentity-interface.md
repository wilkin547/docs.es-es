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
ms.openlocfilehash: 84c595bfdcca84ee43a53e2ea913cc978ae0953e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796529"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity (Interfaz)
Representa la firma única del código que define la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Obtiene un puntero de interfaz a un `IDefinitionIdentity` nuevo objeto que es idéntico a `IDefinitionIdentity`este, excepto por los cambios de atributo especificados.|  
|`IDefinitionIdentity::EnumAttributes`|Obtiene un puntero de interfaz a un objeto [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) que contiene los atributos asociados a `IDefinitionIdentity`este.|  
|`IDefinitionIdentity::GetAttribute`|Obtiene el valor del atributo con el nombre especificado en el espacio de nombres especificado.|  
|`IDefinitionIdentity::SetAttribute`|Establece el atributo que tiene el nombre especificado en el espacio de nombres especificado en el valor especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
