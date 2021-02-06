---
description: 'Más información acerca de: interfaz ICorProfilerInfo8'
title: Interface ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4538c9d314283c67ab0bfe6af3f3768062cffda4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646548"
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

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
