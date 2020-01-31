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
ms.openlocfilehash: e9bb69567a247472af42efb08b609d3474c87ed2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791792"
---
# <a name="icordebugstepper-interface"></a>Interfaz ICorDebugStepper
Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Deactivate (método)](icordebugstepper-deactivate-method.md)|Hace que este `ICorDebugStepper` cancele el último comando de paso que ha recibido.|  
|[IsActive (método)](icordebugstepper-isactive-method.md)|Obtiene un valor que indica si este `ICorDebugStepper` está ejecutando actualmente un paso.|  
|[SetInterceptMask (método)](icordebugstepper-setinterceptmask-method.md)|Establece un valor Cordebugintercept (que especifica los tipos de código a los que se van a recorrer.|  
|[SetRangeIL (método)](icordebugstepper-setrangeil-method.md)|Establece un valor que indica si las llamadas a [ICorDebugStepper:: steprange (](icordebugstepper-steprange-method.md) pasan valores de argumento en relación con el código nativo o con el código del lenguaje intermedio de Microsoft (MSIL) del método que se va a recorrer.|  
|[SetUnmappedStopMask (método)](icordebugstepper-setunmappedstopmask-method.md)|Establece un valor de Cordebugunmappedstop (que especifica el tipo de código no asignado en el que se detendrá la ejecución.|  
|[Step (método)](icordebugstepper-step-method.md)|Hace que este `ICorDebugStepper` un solo paso a través de su subproceso contenedor y, opcionalmente, continúe con el paso a través de las funciones a las que se llama en el subproceso.|  
|[StepOut (método)](icordebugstepper-stepout-method.md)|Hace que este `ICorDebugStepper` un solo paso a través de su subproceso contenedor y que se complete cuando el fotograma actual devuelva el control al marco que realiza la llamada.|  
|[StepRange (método)](icordebugstepper-steprange-method.md)|Hace que este `ICorDebugStepper` un solo paso a través de su subproceso contenedor y que se devuelva cuando llegue al código que se encuentra más allá del último de los intervalos especificados.|  
  
## <a name="remarks"></a>Notas  
 La interfaz `ICorDebugStepper` sirve para los siguientes fines:  
  
- Actúa como un identificador entre un comando Step que se emite y la finalización de ese comando.  
  
- Proporciona una interfaz central para encapsular todo el paso que se puede realizar.  
  
- Proporciona una manera de cancelar prematuramente una operación de ejecución paso a paso.  
  
 Puede haber más de un stepper por subproceso. Por ejemplo, se puede tener acceso a un punto de interrupción mientras se realiza la ejecución paso a paso por procedimientos y el usuario puede iniciar una nueva operación de ejecución paso a paso dentro de esa función. Depende del depurador determinar cómo tratar esta situación. Es posible que el depurador desee cancelar la operación de ejecución paso a paso original o anidar las dos operaciones. La interfaz `ICorDebugStepper` admite ambas opciones.  
  
 Un stepper se puede migrar entre subprocesos si el Common Language Runtime (CLR) realiza una llamada entre subprocesos y con referencias calculadas.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
