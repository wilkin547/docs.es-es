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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193604068e379d62107b25f2bc348cd7c8bc6e98
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796710"
---
# <a name="iassemblycacheitem-interface"></a>IAssemblyCacheItem (Interfaz)
Representa un ensamblado único en la caché global de ensamblados.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[AbortItem (método)](iassemblycacheitem-abortitem-method.md)|Permite que el ensamblado de la caché global de ensamblados realice las operaciones de limpieza antes de que se libere.|  
|[Commit (método)](iassemblycacheitem-commit-method.md)|Confirma la referencia de ensamblado en caché a la memoria.|  
|[CreateStream (método)](iassemblycacheitem-createstream-method.md)|Crea una secuencia con el nombre y el formato especificados.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [Caché global de ensamblados](../../app-domains/gac.md)
- [IAssemblyCache (interfaz)](iassemblycache-interface.md)
