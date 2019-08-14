---
title: Interfaz ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 210029ed1b1c7d780f3895f975f7a72227bbea80
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973825"
---
# <a name="icorprofilerinfo8-interface"></a>Interfaz ICorProfilerInfo8

Una subclase de [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) que proporciona métodos para consultar información acerca de los métodos dinámicos.

## <a name="methods"></a>Métodos  

| Método|DESCRIPCIÓN|  
| ------------|-----------------|  
|[Método IsFunctionDynamic](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| Determina si una función no tiene metadatos asociados.|
|[Método GetFunctionFromIP3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| Asigna un puntero de instrucción de código administrado a un FunctionID. Este método funciona para los métodos dinámicos y no dinámicos. |
|[Método GetDynamicFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| Recupera información acerca de los métodos dinámicos. |

## <a name="requirements"></a>Requisitos  
**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Corprof. idl, Corprof. h  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
## <a name="see-also"></a>Vea también
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
