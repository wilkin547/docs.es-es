---
title: ICorProfilerCallback::UnmanagedToManagedTransition (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 8734fa9c9418b818cbe14ebe87ce2af6fa59c078
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499849"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>ICorProfilerCallback::UnmanagedToManagedTransition (Método)
Notifica al generador de perfiles que se ha producido una transición de código no administrado a código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 de IDENTIFICADOR de la función a la que se está llamando.  
  
 `reason`  
 de Un valor de la enumeración [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) que indica si la transición se produjo debido a una llamada a código administrado desde código no administrado o debido a una devolución de una función no administrada a la que llama una administrada.  
  
## <a name="remarks"></a>Comentarios  
 Si el valor de `reason` es COR_PRF_TRANSITION_RETURN y `functionId` no es null, el identificador de función es el de la función no administrada y nunca se ha compilado con el compilador Just-in-Time (JIT). Las funciones no administradas tienen asociada cierta información básica, como un nombre y algunos metadatos.  
  
 Si el valor de `reason` es COR_PRF_TRANSITION_CALL, es posible que la función a la que se llama (es decir, la función administrada) todavía no se haya compilado JIT.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md)
- [Usar PInvoke explícito en C++ (atributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [Usar la interoperabilidad de C++ (PInvoke implícito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
