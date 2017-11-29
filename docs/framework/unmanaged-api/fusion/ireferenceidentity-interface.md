---
title: IReferenceIdentity (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceIdentity
helpviewer_keywords: IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35c6152836adf02d541bacd149ed9ac053765ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity (Interfaz)
Representa una referencia a la firma única de un objeto de código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Obtiene un puntero de interfaz a una nueva `IReferenceIdentity` instancia que es idéntico a `IReferenceIdentity`, excepto para los cambios de atributo especificado.|  
|`IReferenceIdentity::EnumAttributes`|Obtiene un puntero de interfaz a una `IEnumIDENTITY_ATTRIBUTE` instancia que contiene los atributos asociados a este `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Obtiene el valor del atributo en el espacio de nombres especificado, con el nombre especificado.|  
|`IReferenceIdentity::SetAttribute`|Establece el atributo que tiene el espacio de nombres especificado y el nombre especificado en el valor especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Isolation.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumIDENTITY_ATTRIBUTE (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
