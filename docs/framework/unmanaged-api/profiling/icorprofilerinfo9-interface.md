---
title: Interfaz ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 74031fd822550f8a0752d02ce0c2d89b2f5ae546
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444951"
---
# <a name="icorprofilerinfo9-interface"></a>Interfaz ICorProfilerInfo9

Una subclase de [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) que proporciona métodos para consultar información sobre las funciones con varias versiones de código nativo.  

## <a name="methods"></a>Métodos  

| Método|Descripción|  
| ------------|-----------------|  
|[Método GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente. |
|[Método GetILToNativeMapping3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código. |
|[Método GetCodeInfo4](icorprofilerinfo9-getcodeinfo4-method.md)| Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código. |

## <a name="requirements"></a>Requisitos  
**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
