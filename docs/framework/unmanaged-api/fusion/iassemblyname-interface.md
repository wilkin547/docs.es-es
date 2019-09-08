---
title: IAssemblyName (Interfaz)
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aee9b986c1e26c1b2e34dac7151a00172451bbad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796551"
---
# <a name="iassemblyname-interface"></a>IAssemblyName (Interfaz)
Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[Clone (método)](iassemblyname-clone-method.md)|Crea una copia superficial de este `IAssemblyName` objeto.|  
|[Finalize (método)](iassemblyname-finalize-method.md)|Permite a `IAssemblyName` este objeto liberar recursos y realizar otras operaciones de limpieza antes de que se llame a su destructor.|  
|[GetDisplayName (método)](iassemblyname-getdisplayname-method.md)|Obtiene el nombre legible del ensamblado al que hace referencia este `IAssemblyName` objeto.|  
|[GetName (método)](iassemblyname-getname-method.md)|Obtiene el nombre simple y sin cifrar del ensamblado al que hace `IAssemblyName` referencia este objeto.|  
|[GetProperty (método)](iassemblyname-getproperty-method.md)|Obtiene un puntero a la propiedad a la que hace referencia `PropertyId`el especificado.|  
|[GetVersion (método)](iassemblyname-getversion-method.md)|Obtiene la información de versión para el ensamblado al que `IAssemblyName` hace referencia este objeto.|  
|[IsEqual (método)](iassemblyname-isequal-method.md)|Determina si un objeto `IAssemblyName` especificado es igual a este `IAssemblyName`, en función de las marcas de comparación especificadas.|  
|[SetProperty (método)](iassemblyname-setproperty-method.md)|Establece el valor de la propiedad a la que hace referencia `PropertyId`el especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IAssemblyEnum (interfaz)](iassemblyenum-interface.md)
