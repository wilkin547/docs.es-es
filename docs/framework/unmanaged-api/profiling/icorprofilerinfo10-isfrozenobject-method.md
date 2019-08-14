---
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 05f25d8fb61a16f41a82a987529017db6a687740
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973995"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a>ICorProfilerInfo10:: IsFrozenObject (método)
  
 Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.   
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```  
  
#### <a name="parameters"></a>Parámetros  
 
 `objectId` \
 de Objeto que se va a examinar.

 `pbFrozen` \
 enuncia Un `BOOL` valor de tipo que indica si el objeto está en un segmento de solo lectura.

## <a name="requirements"></a>Requisitos  
 **Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Encabezado**: Corprof. idl, Corprof. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 
  
## <a name="see-also"></a>Vea también
- [Interfaz ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

