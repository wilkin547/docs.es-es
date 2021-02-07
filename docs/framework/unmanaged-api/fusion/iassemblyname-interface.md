---
description: 'Más información acerca de: IAssemblyName (interfaz)'
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
ms.openlocfilehash: fb5949572adc533bab5ed26ee969267f430f36ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760711"
---
# <a name="iassemblyname-interface"></a>IAssemblyName (Interfaz)

Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Clone](iassemblyname-clone-method.md)|Crea una copia superficial de este `IAssemblyName` objeto.|  
|[Método Finalize](iassemblyname-finalize-method.md)|Permite `IAssemblyName` a este objeto liberar recursos y realizar otras operaciones de limpieza antes de que se llame a su destructor.|  
|[Método GetDisplayName](iassemblyname-getdisplayname-method.md)|Obtiene el nombre legible del ensamblado al que hace referencia este `IAssemblyName` objeto.|  
|[Método GetName](iassemblyname-getname-method.md)|Obtiene el nombre simple y sin cifrar del ensamblado al que hace referencia este `IAssemblyName` objeto.|  
|[GetProperty (método)](iassemblyname-getproperty-method.md)|Obtiene un puntero a la propiedad a la que hace referencia el especificado `PropertyId` .|  
|[Método GetVersion](iassemblyname-getversion-method.md)|Obtiene la información de versión para el ensamblado al que hace referencia este `IAssemblyName` objeto.|  
|[Método IsEqual](iassemblyname-isequal-method.md)|Determina si un `IAssemblyName` objeto especificado es igual a este `IAssemblyName` , en función de las marcas de comparación especificadas.|  
|[Método SetProperty](iassemblyname-setproperty-method.md)|Establece el valor de la propiedad a la que hace referencia el especificado `PropertyId` .|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IAssemblyEnum (Interfaz)](iassemblyenum-interface.md)
