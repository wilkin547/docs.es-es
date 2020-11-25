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
ms.openlocfilehash: 7ab5f8826da0b38fc9f92d9be955991a88d15f69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696003"
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
  
## <a name="parameters"></a>Parámetros  

 `ppReJitedILCode`  
 Puntero al IL desde una solicitud ReJIT activa.  
  
## <a name="remarks"></a>Comentarios  

 Si el método que representa este objeto `ICorDebugFunction3` tiene una solicitud ReJIT activa, `ppReJitedILCode` devuelve un puntero a su IL. Si no hay ninguna solicitud activa, que es un caso común, `ppReJitedILCode` es **null**.  
  
 Una solicitud ReJIT se activa justo después de que la ejecución vuelva de la llamada al método [ICorProfilerCallback4:: getrejitparameters (](../profiling/icorprofilercallback4-getrejitparameters-method.md) . Puede que JIT aún no la haya compilado y que los subprocesos se estén ejecutando en la versión original del código. Una solicitud ReJIT pasa a estar inactiva durante la llamada del generador de perfiles al método [ICorProfilerInfo4:: requestrevert (](../profiling/icorprofilerinfo4-requestrevert-method.md) . Incluso después de revertir el IL, un subproceso puede seguir ejecutándose en el código JIT nuevamente compilado (ReJIT).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugFunction3 (Interfaz)](icordebugfunction3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [ReJIT: Guía de How-To](/archive/blogs/davbr/rejit-a-how-to-guide)
