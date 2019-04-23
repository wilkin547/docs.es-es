---
title: Interfaz ICorDebugStepper
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f83b9796bb692ce234a03c596387960bd879ebf3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212523"
---
# <a name="icordebugstepper-interface"></a>Interfaz ICorDebugStepper
Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Deactivate (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|Hace que esta `ICorDebugStepper` para cancelar el último comando de paso que recibió.|  
|[IsActive (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|Obtiene un valor que indica si este `ICorDebugStepper` está ejecutando un paso.|  
|[SetInterceptMask (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|Establece un valor CorDebugIntercept que especifica los tipos de código que se ejecutar paso a paso.|  
|[SetRangeIL (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|Establece un valor que indica si las llamadas a [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pasar los valores de argumento en relación con el código nativo o código de lenguaje intermedio (MSIL) de Microsoft del método que se está ejecutando paso a través.|  
|[SetUnmappedStopMask (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|Establece un valor CorDebugUnmappedStop que especifica el tipo de código no asignado en el que se detendrá la ejecución.|  
|[Step (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|Hace que esta `ICorDebugStepper` paso a paso a través del subproceso que la contiene y, opcionalmente, para continuar pasando solo a través de funciones que se llaman dentro del subproceso.|  
|[StepOut (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|Hace que esta `ICorDebugStepper` paso a paso a través del subproceso que la contiene y a completa cuando el marco actual devuelve el control al marco que realiza la llamada.|  
|[StepRange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|Hace que esta `ICorDebugStepper` paso a paso a través del subproceso que la contiene y que se devuelve cuando llegue al código más allá del último de los intervalos especificados.|  
  
## <a name="remarks"></a>Comentarios  
 El `ICorDebugStepper` interfaz tiene los siguientes objetivos:  
  
-   Actúa como identificador entre un comando de paso que se emite y la finalización de ese comando.  
  
-   Proporciona una interfaz central para encapsular toda la ejecución paso a paso que se puede realizar.  
  
-   Proporciona una manera de cancelar prematuramente una operación de ejecución paso a paso.  
  
 Puede haber más de un motor paso a paso por subproceso. Por ejemplo, se puede alcanzar un punto de interrupción durante la ejecución paso a paso a través de una función, y el usuario que desee iniciar una nueva operación de ejecución paso a paso dentro de esa función. Es el depurador para determinar cómo controlar esta situación. El depurador desear cancelar la operación de ejecución paso a paso original o anidar las dos operaciones. El `ICorDebugStepper` interfaz admite ambas opciones.  
  
 Puede migrar un motor paso a paso entre subprocesos si common language runtime (CLR) realiza una llamada entre subprocesos, cálculo de referencias.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
