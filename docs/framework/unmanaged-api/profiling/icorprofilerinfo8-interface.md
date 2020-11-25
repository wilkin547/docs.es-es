---
title: Interface ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: eedd16006781de517587e5138543b9b9eca3ff90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733612"
---
# <a name="icorprofilerinfo8-interface"></a>Interface ICorProfilerInfo8

Una subclase de [ICorProfilerInfo7](icorprofilerinfo7-interface.md) que proporciona métodos para consultar información acerca de los métodos dinámicos.

## <a name="methods"></a>Métodos  

| Método|Descripción|  
| ------------|-----------------|  
|[Método IsFunctionDynamic](icorprofilerinfo8-isfunctiondynamic-method.md)| Determina si una función no tiene metadatos asociados.|
|[Método GetFunctionFromIP3](icorprofilerinfo8-getfunctionfromip3-method.md)| Asigna un puntero de instrucción de código administrado a un FunctionID. Este método funciona para los métodos dinámicos y no dinámicos. |
|[Método GetDynamicFunctionInfo](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| Recupera información acerca de los métodos dinámicos. |

## <a name="requirements"></a>Requisitos  

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** CorProf.idl, CorProf.h  
**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Consulte también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
