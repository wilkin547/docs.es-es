---
title: IAssemblyCacheItem (Interfaz)
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
ms.openlocfilehash: 72922d1fd0f8ae5e59fe76c7aa50f9c52dcd5302
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719949"
---
# <a name="iassemblycacheitem-interface"></a>IAssemblyCacheItem (Interfaz)

Representa un ensamblado único en la caché global de ensamblados.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método AbortItem](iassemblycacheitem-abortitem-method.md)|Permite que el ensamblado de la caché global de ensamblados realice las operaciones de limpieza antes de que se libere.|  
|[Commit (Método)](iassemblycacheitem-commit-method.md)|Confirma la referencia de ensamblado en caché a la memoria.|  
|[Método CreateStream](iassemblycacheitem-createstream-method.md)|Crea una secuencia con el nombre y el formato especificados.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de Fusion](fusion-interfaces.md)
- [Caché global de ensamblados](../../app-domains/gac.md)
- [IAssemblyCache (Interfaz)](iassemblycache-interface.md)
