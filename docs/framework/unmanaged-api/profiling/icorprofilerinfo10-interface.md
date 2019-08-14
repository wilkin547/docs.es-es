---
title: Interfaz ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 496959ecac5b16f1faa138aec90c5194d15cb105
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974015"
---
# <a name="icorprofilerinfo10-interface"></a>Interfaz ICorProfilerInfo10

Una subclase de [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) que proporciona métodos para modificar el Il de la función, consultar información del tiempo de ejecución y suspender y reanudar el tiempo de ejecución.

## <a name="methods"></a>Métodos  

| Método|DESCRIPCIÓN|  
| ------------|-----------------|  
|[Método EnumerateObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe). |
|[Método IsFrozenObject](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|Dado un ObjectID, determina si el objeto está en un segmento de solo lectura. |
|[Método GetLOHObjectSizeThreshold](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Obtiene el valor del umbral de montón configurado. |
|[Método RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.  |
|[Método SuspendRuntime](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| Suspende el tiempo de ejecución sin realizar un GC. |
|[Método ResumeRuntime](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| Reanuda el tiempo de ejecución sin realizar un GC. |

## <a name="requirements"></a>Requisitos  
**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
**Encabezado**: Corprof. idl, Corprof. h  
**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 
## <a name="see-also"></a>Vea también
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
