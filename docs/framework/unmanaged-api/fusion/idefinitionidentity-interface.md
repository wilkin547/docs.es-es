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
ms.openlocfilehash: 59578e1d3a66809c86f7daad1b208df2ae09568d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108040"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity (Interfaz)
Representa la firma única del código que define la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Obtiene un puntero de interfaz a un nuevo objeto `IDefinitionIdentity` que es idéntico a este `IDefinitionIdentity`, excepto por los cambios de atributo especificados.|  
|`IDefinitionIdentity::EnumAttributes`|Obtiene un puntero de interfaz a un objeto [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) que contiene los atributos asociados a este `IDefinitionIdentity`.|  
|`IDefinitionIdentity::GetAttribute`|Obtiene el valor del atributo con el nombre especificado en el espacio de nombres especificado.|  
|`IDefinitionIdentity::SetAttribute`|Establece el atributo que tiene el nombre especificado en el espacio de nombres especificado en el valor especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
