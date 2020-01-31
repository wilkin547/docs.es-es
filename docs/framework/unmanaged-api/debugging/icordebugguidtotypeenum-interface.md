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
ms.openlocfilehash: 2663e5604cdd55472cc148b2d2b38599df81f11e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794437"
---
# <a name="icordebugguidtotypeenum-interface"></a>ICorDebugGuidToTypeEnum (Interfaz)
Proporciona un enumerador que define la asignación entre un conjunto de GUID y sus tipos correspondientes, que están representados por instancias de ICorDebugType. Esta interfaz hereda los métodos de la interfaz ICorDebugEnum.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ICorDebugGuidToTypeEnum::Next](icordebugguidtotypeenum-next-method.md)|Obtiene el número especificado de instancias de [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que asignan los GUID a la información de tipo.|  
  
## <a name="remarks"></a>Notas  
 Un objeto de interfaz de `ICorDebugGuidToTypeEnum` se puede recuperar llamando al método [ICorDebugAppDomain3:: getcachedwinrttypes (](icordebugappdomain3-getcachedwinrttypes-method.md) . Un depurador puede llamar al [siguiente](icordebugguidtotypeenum-next-method.md) método de la interfaz para recuperar objetos [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que representan asignaciones de representaciones administradas de Windows Runtime tipos cargados en el dominio de aplicación que se usa para la llamada al método [ICorDebugAppDomain3:: getcachedwinrttypes (](icordebugappdomain3-getcachedwinrttypes-method.md) .  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Windows Runtime  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
