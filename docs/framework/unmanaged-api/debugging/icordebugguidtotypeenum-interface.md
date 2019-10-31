---
title: ICorDebugGuidToTypeEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: da921644c4d967efb0d88060ada0332c5eb63965
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138530"
---
# <a name="icordebugguidtotypeenum-interface"></a>ICorDebugGuidToTypeEnum (Interfaz)
Proporciona un enumerador que define la asignación entre un conjunto de GUID y sus tipos correspondientes, que están representados por instancias de ICorDebugType. Esta interfaz hereda los métodos de la interfaz ICorDebugEnum.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Icordebugguidtotypeenum (:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|Obtiene el número especificado de instancias de [cordebugguidtotypemapping (](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) que asignan los GUID a la información de tipo.|  
  
## <a name="remarks"></a>Comentarios  
 Un objeto de interfaz de `ICorDebugGuidToTypeEnum` se puede recuperar llamando al método [ICorDebugAppDomain3:: getcachedwinrttypes (](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) . Un depurador puede llamar al [siguiente](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) método de la interfaz para recuperar objetos [cordebugguidtotypemapping (](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) que representan asignaciones de representaciones administradas de Windows Runtime tipos cargados en el dominio de aplicación que se usa para la llamada a [. Método ICorDebugAppDomain3:: Getcachedwinrttypes (](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Windows Runtime  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
