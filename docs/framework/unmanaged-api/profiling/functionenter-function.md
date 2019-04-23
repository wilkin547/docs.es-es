---
title: FunctionEnter (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6018b5b06a138b38b7b97df280a3e4c4ea0512d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208415"
---
# <a name="functionenter-function"></a>FunctionEnter (Función)
Notifica al generador de perfiles que se pasa a una función de control.  
  
> [!NOTE]
>  El `FunctionEnter` función está en desuso en la versión 2.0 de .NET Framework, y su uso se incurrirá en una penalización de rendimiento. Use la [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) funcione en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `funcID`  
 [in] El identificador de la función a la que se pasa el control.  
  
## <a name="remarks"></a>Comentarios  
 El `FunctionEnter` función es una devolución de llamada; debe implementar. La implementación debe usar el `__declspec`(`naked`) el atributo de clase de almacenamiento.  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
-   En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).  
  
-   En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.  
  
 La implementación de `FunctionEnter` no debe bloquearse porque retrasará la recolección de elementos. La implementación no debe intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados. Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionEnter` devuelve.  
  
 Además, el `FunctionEnter` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vea también

- [FunctionEnter2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
