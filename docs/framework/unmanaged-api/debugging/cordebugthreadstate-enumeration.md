---
description: 'Más información sobre: enumeración CorDebugThreadState ('
title: CorDebugThreadState (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 0cf83ee31547e49ccc7d09e0ab4ee85548688b36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661814"
---
# <a name="cordebugthreadstate-enumeration"></a>CorDebugThreadState (Enumeración)

Especifica el estado de un subproceso de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`THREAD_RUN`|El subproceso se ejecuta libremente, a menos que se produzca un evento de depuración.|  
|`THREAD_SUSPEND`|No se puede ejecutar el subproceso.|  
  
## <a name="remarks"></a>Observaciones  

 El depurador utiliza la `CorDebugThreadState` enumeración para controlar la ejecución de un subproceso. El estado de un subproceso se puede establecer mediante el método [ICorDebugThread:: setdebugstate (](icordebugthread-setdebugstate-method.md) o [ICorDebugController:: setallthreadsdebugstate (](icordebugcontroller-setallthreadsdebugstate-method.md) .  
  
 Una devolución de llamada proporcionada a la [API de hospedaje](../hosting/index.md) permite el suministro de mensajes, por lo que no se necesita un estado interrumpido.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
