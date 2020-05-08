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
ms.openlocfilehash: 7575be3f5074243b251c80b8dd5bdbb12e5d50fd
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976335"
---
# <a name="icordebugenum-interface"></a>Interfaz ICorDebugEnum

Actúa como la interfaz base abstracta para los enumeradores que se usan en una aplicación de depuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Clone](icordebugenum-clone-method.md)|Crea una copia de este objeto `ICorDebugEnum`.|  
|[Método GetCount](icordebugenum-getcount-method.md)|Obtiene el número de elementos de la enumeración.|  
|[Reset (Método)](icordebugenum-reset-method.md)|Mueve el cursor al principio de la enumeración.|  
|[Método Skip](icordebugenum-skip-method.md)|Mueve el cursor hacia delante en la enumeración el número de elementos especificado.|  
  
## <a name="remarks"></a>Observaciones  
 Los enumeradores siguientes derivan `ICorDebugEnum`de:  
  
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
