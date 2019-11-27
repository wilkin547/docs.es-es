---
title: StackSnapshotCallback (Función)
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
ms.openlocfilehash: c0cec9eb7bb8bbc94b255152a9b4d79108bdd1b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427080"
---
# <a name="stacksnapshotcallback-function"></a>StackSnapshotCallback (Función)
Proporciona al generador de perfiles información sobre cada marco administrado y cada ejecución de marcos no administrados en la pila durante un recorrido de pila, iniciado por el método [ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `funcId`  
 de Si este valor es cero, esta devolución de llamada es para una ejecución de marcos no administrados; de lo contrario, es el identificador de una función administrada y esta devolución de llamada es para un marco administrado.  
  
 `ip`  
 de El valor del puntero de instrucción de código nativo en el marco.  
  
 `frameInfo`  
 de `COR_PRF_FRAME_INFO` valor que hace referencia a información sobre el marco de pila. Este valor solo es válido para su uso durante esta devolución de llamada.  
  
 `contextSize`  
 de Tamaño de la estructura de `CONTEXT`, a la que hace referencia el parámetro `context`.  
  
 `context`  
 de Puntero a una estructura de `CONTEXT` de Win32 que representa el estado de la CPU para este marco.  
  
 El parámetro `context` solo es válido si la marca de COR_PRF_SNAPSHOT_CONTEXT se pasó en `ICorProfilerInfo2::DoStackSnapshot`.  
  
 `clientData`  
 de Puntero a los datos del cliente, que se pasa directamente desde `ICorProfilerInfo2::DoStackSnapshot`.  
  
## <a name="remarks"></a>Comentarios  
 La función `StackSnapshotCallback` se implementa mediante el escritor del generador de perfiles. Debe limitar la complejidad del trabajo realizado en `StackSnapshotCallback`. Por ejemplo, al usar `ICorProfilerInfo2::DoStackSnapshot` de forma asincrónica, el subproceso de destino puede estar manteniendo bloqueos. Si el código de `StackSnapshotCallback` requiere los mismos bloqueos, podría producirse un interbloqueo.  
  
 El método `ICorProfilerInfo2::DoStackSnapshot` llama a la función `StackSnapshotCallback` una vez por cada fotograma administrado o una vez por cada ejecución de fotogramas no administrados. Si se llama a `StackSnapshotCallback` para una ejecución de marcos no administrados, el generador de perfiles puede usar el contexto de registro (al que hace referencia el parámetro `context`) para realizar su propio recorrido de pila no administrado. En este caso, la estructura de `CONTEXT` de Win32 representa el estado de la CPU para el marco insertado más recientemente en la ejecución de fotogramas no administrados. Aunque la estructura de `CONTEXT` de Win32 incluye valores para todos los registros, debe confiar solo en los valores del registro de puntero de pila, el registro de puntero de marco, el registro de puntero de instrucción y los registros de entero no volátiles (es decir, conservados).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [DoStackSnapshot (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
