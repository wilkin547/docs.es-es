---
title: IDefinitionIdentity (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionIdentity
helpviewer_keywords: IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b074ae2a0a4e4e65f0402ff35888b557b00dd071
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity (Interfaz)
Representa la firma única del código que define la aplicación en el ámbito actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Obtiene un puntero de interfaz a una nueva `IDefinitionIdentity` objeto que es idéntico a `IDefinitionIdentity`, excepto para los cambios de atributo especificado.|  
|`IDefinitionIdentity::EnumAttributes`|Obtiene un puntero de interfaz a una [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) objeto que contiene los atributos asociados a este `IDefinitionIdentity`.|  
|`IDefinitionIdentity::GetAttribute`|Obtiene el valor del atributo con el nombre especificado en el espacio de nombres especificado.|  
|`IDefinitionIdentity::SetAttribute`|Establece el atributo que tiene el nombre especificado en el espacio de nombres especificado en el valor especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Isolation.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
