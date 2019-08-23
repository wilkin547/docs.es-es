---
title: Interfaz ICorDebugEval
ms.date: 03/30/2017
api_name:
- ICorDebugEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval
helpviewer_keywords:
- ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfd29067f819ba69305f7ae8620729cd443915a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931950"
---
# <a name="icordebugeval-interface"></a>Interfaz ICorDebugEval

Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[Abort (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Anula el cálculo que este `ICorDebugEval` objeto está realizando actualmente.|  
|[CallFunction (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Configura una llamada a la función especificada. (Obsoleto en la .NET Framework versión 2,0; use [ICorDebugEval2:: CallParameterizedFunction (](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) en su lugar).|  
|[CreateValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Obtiene un puntero de interfaz a un objeto "ICorDebugValue" del tipo especificado, con un valor inicial de cero o null. (Obsoleto en el .NET Framework 2,0; use [ICorDebugEval2:: createvaluefortype (](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) en su lugar).|  
|[GetResult (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Obtiene un puntero de interfaz a `ICorDebugValue` un que contiene los resultados de la evaluación.|  
|[GetThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Obtiene un puntero de interfaz a la expresión "ICorDebugThread" en la que se está ejecutando o se ejecutará esta evaluación.|  
|[IsActive (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Obtiene un valor que indica si este `ICorDebugEval` objeto se está ejecutando actualmente.|  
|[NewArray (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas. (Obsoleto en el .NET Framework 2,0; use [ICorDebugEval2:: NewParameterizedArray (](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) en su lugar).|  
|[NewObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Asigna una nueva instancia de objeto y llama al método de constructor especificado. (Obsoleto en el .NET Framework 2,0; use [ICorDebugEval2:: NewParameterizedObject (](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) en su lugar).|  
|[NewObjectNoConstructor (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Asigna una nueva instancia de objeto del tipo especificado, sin intentar llamar a un método de constructor. (Obsoleto en el .NET Framework 2,0; use [ICorDebugEval2:: newparameterizedobjectnoconstructor (](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) en su lugar).|  
|[NewString (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Asigna un nuevo objeto de cadena con el contenido especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Un `ICorDebugEval` objeto se crea en el contexto de un subproceso concreto que se utiliza para realizar las evaluaciones. Todos los objetos y tipos utilizados en una evaluación determinada deben residir en el mismo dominio de aplicación. Dicho dominio de aplicación no debe ser el mismo que el dominio de aplicación actual del subproceso. Las evaluaciones se pueden anidar.  
  
 Las operaciones de la evaluación no se completan hasta que el depurador llama a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)y, a continuación, recibe una devolución de llamada [ICorDebugManagedCallback:: evalcomplete (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) . Si necesita usar la funcionalidad de evaluación sin permitir que se ejecuten otros subprocesos, suspenda los subprocesos mediante [ICorDebugController:: setallthreadsdebugstate (](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) o [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md) antes de llamar a [ ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Dado que el código de usuario se está ejecutando cuando la evaluación está en curso, pueden producirse los eventos de depuración, incluidas las cargas de clases y los puntos de interrupción. El depurador recibirá devoluciones de llamada, como es habitual, para estos eventos. El estado de la evaluación se verá como parte de la inspección del estado normal del programa. La cadena de pila será una `CHAIN_FUNC_EVAL` cadena (vea la enumeración "CorDebugStepReason (" y el método [ICorDebugChain:: GetReason (](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) ). La API de depurador completa seguirá funcionando de la manera habitual.  
  
 Si se produce una situación de bucle indefinido o infinito, el código de usuario nunca puede completarse. En tal caso, debe llamar a [ICorDebugEval:: ABORT](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) antes de reanudar el programa.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
