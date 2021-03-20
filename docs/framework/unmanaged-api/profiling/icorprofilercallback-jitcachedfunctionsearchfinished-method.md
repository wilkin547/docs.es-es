---
description: 'Más información sobre: ICorProfilerCallback:: JITCachedFunctionSearchFinished ((método)'
title: ICorProfilerCallback::JITCachedFunctionSearchFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: 3dc655c2a049a2cac08f6e4856aab98ee690b9df
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759981"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a>ICorProfilerCallback::JITCachedFunctionSearchFinished (Método)

Notifica al generador de perfiles que ha finalizado una búsqueda para una función que se compiló previamente mediante el generador de imágenes nativas (NGen.exe).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a>Parámetros

`functionId` de IDENTIFICADOR de la función para la que se realizó la búsqueda.

`result` de Un valor de la enumeración [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) que indica el resultado de la búsqueda.

## <a name="remarks"></a>Observaciones  

 En la versión .NET Framework 2,0, no se realizarán las devoluciones de llamada [ICorProfilerCallback:: jitcachedfunctionsearchstarted (](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) y `JITCachedFunctionSearchFinished` para todas las funciones de las imágenes Ngen normales. Solo las imágenes de NGen optimizadas para un generador de perfiles generarán devoluciones de llamada para todas las funciones de la imagen. Sin embargo, debido a la sobrecarga adicional, un generador de perfiles debe solicitar imágenes NGen optimizadas para el generador de perfiles solo si pretende utilizar estas devoluciones de llamada para forzar que una función se compile Just-in-Time (JIT). De lo contrario, el generador de perfiles debe usar una estrategia diferida para recopilar información de la función.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
