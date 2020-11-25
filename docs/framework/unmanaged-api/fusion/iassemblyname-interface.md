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
ms.openlocfilehash: f6feed9f59715f9a2801cd3a2a99a087957d4377
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715074"
---
# <a name="iassemblyname-interface"></a>IAssemblyName (Interfaz)

Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (Método)](iassemblyname-clone-method.md)|Crea una copia superficial de este `IAssemblyName` objeto.|  
|[Método Finalize](iassemblyname-finalize-method.md)|Permite `IAssemblyName` a este objeto liberar recursos y realizar otras operaciones de limpieza antes de que se llame a su destructor.|  
|[GetDisplayName (Método)](iassemblyname-getdisplayname-method.md)|Obtiene el nombre legible del ensamblado al que hace referencia este `IAssemblyName` objeto.|  
|[GetName (Método)](iassemblyname-getname-method.md)|Obtiene el nombre simple y sin cifrar del ensamblado al que hace referencia este `IAssemblyName` objeto.|  
|[Método GetProperty](iassemblyname-getproperty-method.md)|Obtiene un puntero a la propiedad a la que hace referencia el especificado `PropertyId` .|  
|[GetVersion (Método)](iassemblyname-getversion-method.md)|Obtiene la información de versión para el ensamblado al que hace referencia este `IAssemblyName` objeto.|  
|[Método IsEqual](iassemblyname-isequal-method.md)|Determina si un `IAssemblyName` objeto especificado es igual a este `IAssemblyName` , en función de las marcas de comparación especificadas.|  
|[Método SetProperty](iassemblyname-setproperty-method.md)|Establece el valor de la propiedad a la que hace referencia el especificado `PropertyId` .|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IAssemblyEnum (Interfaz)](iassemblyenum-interface.md)
