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
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134316"
---
# <a name="iassemblyname-interface"></a>IAssemblyName (Interfaz)
Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](iassemblyname-clone-method.md)|Crea una copia superficial de este objeto `IAssemblyName`.|  
|[Finalize (método)](iassemblyname-finalize-method.md)|Permite a este objeto `IAssemblyName` liberar recursos y realizar otras operaciones de limpieza antes de que se llame a su destructor.|  
|[GetDisplayName (método)](iassemblyname-getdisplayname-method.md)|Obtiene el nombre legible del ensamblado al que hace referencia este objeto `IAssemblyName`.|  
|[GetName (método)](iassemblyname-getname-method.md)|Obtiene el nombre simple y sin cifrar del ensamblado al que hace referencia este objeto `IAssemblyName`.|  
|[GetProperty (método)](iassemblyname-getproperty-method.md)|Obtiene un puntero a la propiedad a la que hace referencia el `PropertyId`especificado.|  
|[GetVersion (método)](iassemblyname-getversion-method.md)|Obtiene la información de versión del ensamblado al que hace referencia este objeto `IAssemblyName`.|  
|[IsEqual (método)](iassemblyname-isequal-method.md)|Determina si un objeto de `IAssemblyName` especificado es igual a este `IAssemblyName`, en función de las marcas de comparación especificadas.|  
|[SetProperty (método)](iassemblyname-setproperty-method.md)|Establece el valor de la propiedad a la que hace referencia el `PropertyId`especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IAssemblyEnum (interfaz)](iassemblyenum-interface.md)
