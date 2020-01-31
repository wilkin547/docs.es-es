---
title: ICorDebugFunction3::GetActiveReJitRequestILCode (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: 70a55b833acb7fa946c694a63e1e8b51562938bc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777727"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a>ICorDebugFunction3::GetActiveReJitRequestILCode (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Obtiene un puntero de interfaz a un [ICorDebugILCode](icordebugilcode-interface.md) que contiene el Il de una solicitud ReJIT activa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppReJitedILCode`  
 Puntero al IL desde una solicitud ReJIT activa.  
  
## <a name="remarks"></a>Notas  
 Si el método que representa este objeto `ICorDebugFunction3` tiene una solicitud ReJIT activa, `ppReJitedILCode` devuelve un puntero a su IL. Si no hay ninguna solicitud activa, que es un caso común, `ppReJitedILCode` es **null**.  
  
 Una solicitud ReJIT se activa justo después de que la ejecución vuelva de la llamada al método [ICorProfilerCallback4:: getrejitparameters (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) . Puede que JIT aún no la haya compilado y que los subprocesos se estén ejecutando en la versión original del código. Una solicitud ReJIT pasa a estar inactiva durante la llamada del generador de perfiles al método [ICorProfilerInfo4:: requestrevert (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) . Incluso después de revertir el IL, un subproceso puede seguir ejecutándose en el código JIT nuevamente compilado (ReJIT).  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugFunction3 (interfaz)](icordebugfunction3-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [ReJIT: Guía de procedimientos](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
