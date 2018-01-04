---
title: IAssemblyName (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName
helpviewer_keywords: IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 902ad9f67d06306e79666f0e10d85bdb9c65c377
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyname-interface"></a>IAssemblyName (Interfaz)
Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|Crea una copia superficial de este `IAssemblyName` objeto.|  
|[Finalize (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|Esto permite `IAssemblyName` objeto para liberar recursos y realizar otras operaciones de limpieza antes de llama a su destructor.|  
|[GetDisplayName (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|Obtiene el nombre legible del ensamblado que hace referencia esta `IAssemblyName` objeto.|  
|[GetName (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|Obtiene el nombre sencillo y sin cifrar del ensamblado que hace referencia esta `IAssemblyName` objeto.|  
|[GetProperty (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|Obtiene un puntero a la propiedad al que hace referencia especificado `PropertyId`.|  
|[GetVersion (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|Obtiene la información de versión del ensamblado que hace referencia esta `IAssemblyName` objeto.|  
|[IsEqual (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|Determina si un determinado `IAssemblyName` es igual a este objeto `IAssemblyName`, en función de las marcas de comparación especificada.|  
|[SetProperty (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|Establece el valor de la propiedad al que hace referencia especificado `PropertyId`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IAssemblyEnum (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
