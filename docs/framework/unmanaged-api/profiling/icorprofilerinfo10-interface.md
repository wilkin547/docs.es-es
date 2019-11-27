---
title: Interfaz ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f2bc716110c14972e5b2c32bceb3123b16e87c61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449844"
---
# <a name="icorprofilerinfo10-interface"></a>Interfaz ICorProfilerInfo10

Una subclase de [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) que proporciona métodos para modificar el Il de la función, consultar información del tiempo de ejecución y suspender y reanudar el tiempo de ejecución.

## <a name="methods"></a>Métodos  

| Método|Descripción|  
| ------------|-----------------|  
|[Método EnumerateObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe). |
|[Método IsFrozenObject](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|Dado un ObjectID, determina si el objeto está en un segmento de solo lectura. |
|[Método GetLOHObjectSizeThreshold](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Obtiene el valor del umbral de montón configurado. |
|[Método RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.  |
|[Método SuspendRuntime](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| Suspende el tiempo de ejecución sin realizar un GC. |
|[Método ResumeRuntime](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| Reanuda el tiempo de ejecución sin realizar un GC. |

## <a name="requirements"></a>Requisitos  
**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
