---
title: Interfaz ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 7e483bae9b7898e25c376fa92d0449fc49c6f9ee
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548691"
---
# <a name="icorprofilerinfo10-interface"></a>Interfaz ICorProfilerInfo10

Una subclase de [ICorProfilerInfo9](icorprofilerinfo9-interface.md) que proporciona métodos para modificar el Il de la función, consultar información del tiempo de ejecución y suspender y reanudar el tiempo de ejecución.

## <a name="methods"></a>Métodos  

| Método|Descripción|  
| ------------|-----------------|  
|[Método EnumerateObjectReferences](icorprofilerinfo10-enumerateobjectreferences-method.md)|Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe). |
|[Método IsFrozenObject](icorprofilerinfo10-isfrozenobject-method.md)|Dado un ObjectID, determina si el objeto está en un segmento de solo lectura. |
|[Método GetLOHObjectSizeThreshold](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Obtiene el valor del umbral de montón configurado. |
|[Método RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md)| ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.  |
|[Método SuspendRuntime](icorprofilerinfo10-suspendruntime-method.md)| Suspende el tiempo de ejecución sin realizar un GC. |
|[Método ResumeRuntime](icorprofilerinfo10-resumeruntime-method.md)| Reanuda el tiempo de ejecución sin realizar un GC. |

## <a name="requirements"></a>Requisitos  
**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
