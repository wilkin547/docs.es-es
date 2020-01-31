---
title: Interfaz ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 371e85ce8f5d7b420a30ac842ec658949e47d30e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861650"
---
# <a name="icorprofilerinfo9-interface"></a>Interfaz ICorProfilerInfo9

Una subclase de [ICorProfilerInfo8](icorprofilerinfo8-interface.md) que proporciona métodos para consultar información sobre las funciones con varias versiones de código nativo.  

## <a name="methods"></a>Métodos  

| Método|Descripción|  
| ------------|-----------------|  
|[Método GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md)| Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente. |
|[Método GetILToNativeMapping3](icorprofilerinfo9-getiltonativemapping3-method.md)| Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código. |
|[Método GetCodeInfo4](icorprofilerinfo9-getcodeinfo4-method.md)| Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código. |

## <a name="requirements"></a>Requisitos de  
**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
