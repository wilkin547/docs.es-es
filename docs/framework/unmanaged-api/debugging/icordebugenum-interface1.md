---
title: Interfaz ICorDebugEnum
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
ms.openlocfilehash: b208444de3b427329988f27b9d252b54143b7240
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698798"
---
# <a name="icordebugenum-interface"></a>Interfaz ICorDebugEnum

Actúa como la interfaz base abstracta para los enumeradores que se usan en una aplicación de depuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (Método)](icordebugenum-clone-method.md)|Crea una copia de este objeto `ICorDebugEnum`.|  
|[GetCount (Método)](icordebugenum-getcount-method.md)|Obtiene el número de elementos de la enumeración.|  
|[Reset (Método)](icordebugenum-reset-method.md)|Mueve el cursor al principio de la enumeración.|  
|[Skip (Método)](icordebugenum-skip-method.md)|Mueve el cursor hacia delante en la enumeración el número de elementos especificado.|  
  
## <a name="remarks"></a>Comentarios  

 Los enumeradores siguientes derivan de `ICorDebugEnum` :  
  
- ICorDebugAppDomainEnum (  
  
- ICorDebugAssemblyEnum  
  
- [ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)  
  
- ICorDebugBreakpointEnum (  
  
- ICorDebugChainEnum (  
  
- ICorDebugCodeEnum (  
  
- Icordebugerrorinfoenum (  
  
- [Icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md)  
  
- ICorDebugFrameEnum (  
  
- [Icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md)  
  
- [Icordebugguidtotypeenum (](icordebugguidtotypeenum-interface.md)  
  
- [Icordebugheapenum (](icordebugheapenum-interface.md)  
  
- [Icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md)  
  
- ICorDebugModuleEnum (  
  
- ICorDebugObjectEnum (  
  
- Icordebugprocessenum (  
  
- ICorDebugStepperEnum (  
  
- ICorDebugThreadEnum (  
  
- ICorDebugTypeEnum  
  
- ICorDebugValueEnum  
  
- [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
