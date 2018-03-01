---
title: "ICorProfilerCallback::UnmanagedToManagedTransition (Método)"
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
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1653a92563f0031fcb4c215dd58e4e1ac73030d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>ICorProfilerCallback::UnmanagedToManagedTransition (Método)
Notifica al generador de perfiles que se ha producido una transición desde código no administrado a código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función que se está llamando.  
  
 `reason`  
 [in] Un valor de la [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeración que indica si la transición se produjo debido a una llamada a código administrado desde código no administrado, o debido a una devolución de una función no administrada que se llama a uno administrada.  
  
## <a name="remarks"></a>Comentarios  
 Si el valor de `reason` es COR_PRF_TRANSITION_RETURN y `functionId` no es nulo, la función ID es el de la función no administrada y nunca habrá sido compilada mediante el compilador just-in-time (JIT). Funciones no administradas tengan cierta información básica asociado a ellos, como el nombre y algunos metadatos.  
  
 Si el valor de `reason` es COR_PRF_TRANSITION_CALL, es posible que la función llamada (es decir, la función administrada) no se ha recibido la compilación JIT.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ManagedToUnmanagedTransition (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [Usar un elemento PInvoke explícito en C++ (Atributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [Usar la interoperabilidad de C++ (PInvoke implícito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
