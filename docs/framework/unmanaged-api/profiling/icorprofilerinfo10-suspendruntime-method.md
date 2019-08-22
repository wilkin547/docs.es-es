---
title: ICorProfilerInfo10::SuspendRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 74300a12d000565a63cd7ea862c759d47b87bbe1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665693"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a>ICorProfilerInfo10:: SuspendRuntime (método)

Suspende el tiempo de ejecución sin realizar un GC.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a>Requisitos

**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Encabezado**: Corprof. idl, Corprof. h

**Biblioteca** CorGuids.lib

**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
