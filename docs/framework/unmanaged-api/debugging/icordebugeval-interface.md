---
title: ICorDebugEval Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval
helpviewer_keywords: ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77e97e31a20c392eebae1b373bb1af53f87c23e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval-interface1"></a>ICorDebugEval Interfaz1
Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Abort (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Anula el cálculo esto `ICorDebugEval` objeto está realizando actualmente.|  
|[CallFunction (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Configura una llamada a la función especificada. (Obsoleto en .NET Framework versión 2.0; utilice [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) en su lugar.)|  
|[CreateValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Obtiene un puntero de interfaz a un objeto de "ICorDebugValue" del tipo especificado, con un valor inicial de cero o null. (Obsoleto en .NET Framework 2.0; utilice [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) en su lugar.)|  
|[GetResult (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Obtiene un puntero de interfaz a un `ICorDebugValue` que contiene los resultados de la evaluación.|  
|[GetThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Obtiene un puntero de interfaz a la "ICorDebugThread" donde se está ejecutando o se ejecutará esta evaluación.|  
|[IsActive (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Obtiene un valor que indica si este `ICorDebugEval` objeto se está ejecutando actualmente.|  
|[NewArray (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Asigna una nueva matriz del tipo de elemento especificado y dimensiones. (Obsoleto en .NET Framework 2.0; utilice [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) en su lugar.)|  
|[NewObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Asigna una nueva instancia de objeto y llama al método de constructor especificado. (Obsoleto en .NET Framework 2.0; utilice [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) en su lugar.)|  
|[NewObjectNoConstructor (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Asigna una nueva instancia de objeto del tipo especificado, sin intentar llamar a un método de constructor. (Obsoleto en .NET Framework 2.0; utilice [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) en su lugar.)|  
|[NewString (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Asigna un nuevo objeto de cadena con el contenido especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Un `ICorDebugEval` objeto se crea en el contexto de un subproceso concreto que se usa para realizar la evaluación. Todos los objetos y tipos que se utilizan en una evaluación determinada deben residir dentro del mismo dominio de aplicación. Ese dominio de aplicación no debe ser el mismo que el dominio de aplicación actual del subproceso. Se pueden anidar las evaluaciones.  
  
 Las operaciones de evaluación no se completan hasta que el depurador llama [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)y, a continuación, recibe un [ICorDebugManagedCallback:: EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) devolución de llamada. Si tiene que utilizar la funcionalidad de evaluación sin permitir que otros subprocesos ejecutar, suspender los subprocesos utilizando [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) o [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)antes de llamar a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Porque se está ejecutando código de usuario cuando la evaluación está en curso, puede producirse cualquier evento de depuración, incluso cargas de clase y los puntos de interrupción. El depurador recibirá las devoluciones de llamada, como es habitual, para estos eventos. El estado de la evaluación se verán como parte de la inspección del estado normal del programa. La cadena de pila será una `CHAIN_FUNC_EVAL` cadena (vea la enumeración "CorDebugStepReason" y el [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) método). La API del depurador seguirá funcionando con normalidad.  
  
 Si se produce una situación bucle de interbloqueada o infinita, es no posible que el código de usuario nunca finalice. En tal caso, debe llamar a [ICorDebugEval:: Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) antes de reanudar el programa.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
    
    
    
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
