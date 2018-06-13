---
title: FunctionTailcall (Función)
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11cf96f5957d41e0647c309a7b0bb08fc9b31c91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452109"
---
# <a name="functiontailcall-function"></a>FunctionTailcall (Función)
Notifica al generador de perfiles que la función en ejecución está a punto de realizar una llamada de cola a otra función.  
  
> [!NOTE]
>  El `FunctionTailcall` función está desusada en la versión 2.0 de .NET Framework. Seguirán funcionando, pero se le cobrará una reducción del rendimiento. Use la [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) funcione en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `funcID`  
 [in] El identificador de la función en ejecución que se va a realizar una cola llamada.  
  
## <a name="remarks"></a>Comentarios  
 La función de destino de la llamada de cola usará el marco de pila actual y devolverá directamente al autor de llamada de la función que realizó el final de la llamada. Esto significa que un [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) devolución de llamada no se emitirá para una función que es el destino de una llamada de cola.  
  
 El `FunctionTailcall` función es una devolución de llamada; debe implementar. La implementación debe utilizar el `__declspec`(`naked`) el atributo de clase de almacenamiento.  
  
 El motor de ejecución no guardan los registros antes de llamar a esta función.  
  
-   En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).  
  
-   Al salir, debe restablecer la pila desactivando todos los parámetros que se han insertados por el llamador.  
  
 La implementación de `FunctionTailcall` no debe bloquearse porque retrasará la recolección de elementos. La implementación no debería intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados. Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionTailcall` devuelve.  
  
 Además, la `FunctionTailcall` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vea también  
 [FunctionEnter2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [SetEnterLeaveFunctionHooks2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
