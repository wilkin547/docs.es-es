---
title: "FunctionLeave (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave
helpviewer_keywords: FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3368a97adf6ffceaa5ac56b7ffe16d6e2802437c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="functionleave-function"></a>FunctionLeave (Función)
Notifica al generador de perfiles que una función está a punto de devolver al llamador.  
  
> [!NOTE]
>  El `FunctionLeave` función está en desuso en .NET Framework 2.0. Seguirán funcionando, pero se le cobrará una reducción del rendimiento. Use la [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) funcione en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `funcID`  
 [in] El identificador de la función que devuelve.  
  
## <a name="remarks"></a>Comentarios  
 El `FunctionLeave` función es una devolución de llamada; debe implementar. La implementación debe utilizar el `__declspec`(`naked`) el atributo de clase de almacenamiento.  
  
 El motor de ejecución no guardan los registros antes de llamar a esta función.  
  
-   En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).  
  
-   Al salir, debe restablecer la pila desactivando todos los parámetros que se han insertados por el llamador.  
  
 La implementación de `FunctionLeave` no debe bloquearse porque retrasará la recolección de elementos. La implementación no debería intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados. Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionLeave` devuelve.  
  
 Además, la `FunctionLeave` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vea también  
 [FunctionEnter2 (función)](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2 (función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [FunctionTailcall2 (función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [SetEnterLeaveFunctionHooks2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Funciones estáticas globales de generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
