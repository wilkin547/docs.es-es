---
title: Interfaz ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: e90a1ffbc037636e4296bbd4f4c3c5082885e9f3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863249"
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

## <a name="requirements"></a>Requisitos de  
**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
