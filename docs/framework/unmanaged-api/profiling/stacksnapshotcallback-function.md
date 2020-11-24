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
ms.openlocfilehash: 2d6ca18ce48f69d8c94b465efac2b9fe0e10f070
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685310"
---
# <a name="stacksnapshotcallback-function"></a>StackSnapshotCallback (Función)

Proporciona al generador de perfiles información sobre cada marco administrado y cada ejecución de marcos no administrados en la pila durante un recorrido de pila, iniciado por el método [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
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
 de `COR_PRF_FRAME_INFO` Valor que hace referencia a información sobre el marco de pila. Este valor solo es válido para su uso durante esta devolución de llamada.  
  
 `contextSize`  
 de Tamaño de la `CONTEXT` estructura, al que hace referencia el `context` parámetro.  
  
 `context`  
 de Puntero a una `CONTEXT` estructura de Win32 que representa el estado de la CPU para este marco.  
  
 El `context` parámetro solo es válido si se ha pasado la marca COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot` .  
  
 `clientData`  
 de Puntero a los datos del cliente, que se pasa directamente a partir de `ICorProfilerInfo2::DoStackSnapshot` .  
  
## <a name="remarks"></a>Comentarios  

 El `StackSnapshotCallback` escritor del generador de perfiles implementa la función. Debe limitar la complejidad del trabajo realizado en `StackSnapshotCallback` . Por ejemplo, cuando `ICorProfilerInfo2::DoStackSnapshot` se usa de forma asincrónica, el subproceso de destino puede estar manteniendo bloqueos. Si el código dentro de `StackSnapshotCallback` requiere los mismos bloqueos, podría producirse un interbloqueo.  
  
 El `ICorProfilerInfo2::DoStackSnapshot` método llama a la `StackSnapshotCallback` función una vez por cada marco administrado o una vez por cada ejecución de fotogramas no administrados. Si `StackSnapshotCallback` se llama a para una ejecución de marcos no administrados, el generador de perfiles puede usar el contexto de registro (al que hace referencia el `context` parámetro) para realizar su propio recorrido de pila no administrado. En este caso, la estructura de Win32 `CONTEXT` representa el estado de la CPU para el marco insertado más recientemente en la ejecución de fotogramas no administrados. Aunque la `CONTEXT` estructura Win32 incluye valores para todos los registros, solo debe confiar en los valores del registro de puntero de pila, el registro de puntero de marco, el registro de puntero de instrucción y los registros de entero no volátiles (es decir, conservados).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
