---
title: "ICorProfilerCallback::ManagedToUnmanagedTransition (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59e36f9285f57b54935e40243e87d44b687686da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>ICorProfilerCallback::ManagedToUnmanagedTransition (Método)
Notifica al generador de perfiles que se ha producido una transición de código administrado a código no administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función que se está llamando.  
  
 `reason`  
 [in] Un valor de la [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeración que indica si la transición se produjo debido a una llamada a código no administrado desde el código administrado, o debido a una devolución de una función administrada llamada por una no administrada.  
  
## <a name="remarks"></a>Comentarios  
 Si el valor de `reason` es COR_PRF_TRANSITION_CALL, la función ID es que de la función no administrada, que nunca habrá sido compilada mediante el compilador just-in-time. Funciones no administradas tengan información básica asociada a ellos, como el nombre y algunos metadatos. Si se llamara a la función no administrada usando implícita de plataforma (PInvoke) de invocación, el tiempo de ejecución no puede determinar el destino de la llamada y el valor de `functionId` será null. Para obtener más información sobre PInvoke implícito, consulte [uso de la interoperabilidad de C++ (PInvoke implícito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [UnmanagedToManagedTransition (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)  
 [Usar un elemento PInvoke explícito en C++ (Atributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
