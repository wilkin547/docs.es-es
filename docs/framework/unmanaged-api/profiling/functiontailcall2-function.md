---
title: FunctionTailcall2 (Función)
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 06dd3b028f4f43ca8681c80a5caa4716104068dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080896"
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2 (Función)
Notifica al generador de perfiles que la función actualmente en ejecución que va a realizar una llamada de cola a otra función y proporciona información sobre el marco de pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `funcId`  
 [in] El identificador de la función que se ejecuta actualmente que se va a llamar a una cola.  
  
 `clientData`  
 [in] El identificador de la función reasignada, que el generador de perfiles especificado anteriormente a través de [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), de la función actualmente en ejecución que se va a llamar a una cola.  
  
 `func`  
 [in] Un `COR_PRF_FRAME_INFO` valor al que apunta a la información sobre el marco de pila.  
  
 El generador de perfiles debe tratar como un identificador opaco que puede pasarse al motor de ejecución en el [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) método.  
  
## <a name="remarks"></a>Comentarios  
 La función de destino de la llamada de cola usará el marco de pila actual y se devolverá directamente al llamador de la función que realizó la cola llamada. Esto significa que un [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) devolución de llamada no se emitirá para una función que es el destino de una llamada de cola.  
  
 El valor de la `func` parámetro no es válido tras la `FunctionTailcall2` función devuelve porque el valor puede cambiar o se destruye.  
  
 El `FunctionTailcall2` función es una devolución de llamada; debe implementar. La implementación debe usar el `__declspec`(`naked`) el atributo de clase de almacenamiento.  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
-   En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).  
  
-   En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.  
  
 La implementación de `FunctionTailcall2` no debe bloquearse porque retrasará la recolección de elementos. La implementación no debe intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados. Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionTailcall2` devuelve.  
  
 Además, el `FunctionTailcall2` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [FunctionEnter2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [Método SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
