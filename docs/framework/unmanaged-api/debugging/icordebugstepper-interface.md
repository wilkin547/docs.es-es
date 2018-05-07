---
title: ICorDebugStepper Interfaz1
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
ms.openlocfilehash: 339b823e5e9f38ffd175c79e379e28ccc3565c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstepper-interface1"></a>ICorDebugStepper Interfaz1
Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Deactivate (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|Hace que esta `ICorDebugStepper` para cancelar el último comando de paso que recibió.|  
|[IsActive (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|Obtiene un valor que indica si esta `ICorDebugStepper` se está ejecutando actualmente un paso.|  
|[SetInterceptMask (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|Establece un valor de CorDebugIntercept que especifica los tipos de código que se recorren paso a paso.|  
|[SetRangeIL (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|Establece un valor que indica si las llamadas a [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pasan valores de argumento en relación con el código nativo o al código de lenguaje intermedio (MSIL) de Microsoft del método que se está ejecutando en el paso a paso.|  
|[SetUnmappedStopMask (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|Establece un valor de CorDebugUnmappedStop que especifica el tipo de código no asignado en el que se detendrá la ejecución.|  
|[Step (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|Hace que esta `ICorDebugStepper` paso a paso a través de un subproceso que lo contiene y, opcionalmente, para seguir paso único a través de funciones que se llaman desde el subproceso.|  
|[StepOut (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|Hace que esta `ICorDebugStepper` paso a paso a través de un subproceso que lo contiene y completado cuando el marco actual devuelve el control al marco que realiza la llamada.|  
|[StepRange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|Hace que esta `ICorDebugStepper` paso a paso a través de un subproceso que lo contiene y para devolver cuando llegue al código situado más allá del último de los intervalos especificados.|  
  
## <a name="remarks"></a>Comentarios  
 La `ICorDebugStepper` interfaz tiene los siguientes objetivos:  
  
-   Actúa como identificador entre un comando de paso emitido y la finalización de ese comando.  
  
-   Proporciona una interfaz central para encapsular la versión que se pueden realizar.  
  
-   Proporciona una manera de cancelar prematuramente una operación de ejecución paso a paso.  
  
 Puede haber más de un paso a paso desencadene por subproceso. Por ejemplo, puede ser alcanzado un punto de interrupción al avanzar a través de una función, y el usuario que desee iniciar una nueva operación de ejecución paso a paso dentro de esa función. Es decisión del depurador para determinar cómo controlar esta situación. El depurador puede cancelar la operación de ejecución paso a paso original o anidar las dos operaciones. La `ICorDebugStepper` interfaz es compatible con ambas opciones.  
  
 Un paso a paso desencadene puede migrar entre subprocesos si common language runtime (CLR) realiza una llamada entre subprocesos, calcular las referencias.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
