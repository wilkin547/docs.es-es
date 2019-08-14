---
title: Interfaz ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 0ba4f2b4a515143d50bc812f04ea75d821b69471
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973805"
---
# <a name="icorprofilerinfo9-interface"></a>Interfaz ICorProfilerInfo9

Una subclase de [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) que proporciona métodos para consultar información sobre las funciones con varias versiones de código nativo.  

## <a name="methods"></a>Métodos  

| Método|DESCRIPCIÓN|  
| ------------|-----------------|  
|[Método GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente. |
|[Método GetILToNativeMapping3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código. |
|[Método GetCodeInfo4](icorprofilerinfo9-getcodeinfo4-method.md)| Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código. |

## <a name="requirements"></a>Requisitos  
**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
**Encabezado**: Corprof. idl, Corprof. h  
**Versiones de .net:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  
## <a name="see-also"></a>Vea también
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
