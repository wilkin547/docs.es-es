---
title: ICorProfilerInfo10::RequestReJITWithInliners
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: c33a868b643cb3e3fd5dfaf436e3078bc590705c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449812"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a>ICorProfilerInfo10:: RequestReJITWithInliners (método)

ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

#### <a name="parameters"></a>Parámetros

`dwRejitFlags` \
de Máscara de [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).

`cFunctions` \
[in] Número de funciones que se va a recompilar.

`moduleIds` \
[in] Especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.

`methodIds` \
[in] Especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.

## <a name="remarks"></a>Comentarios

[Requestrejit (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) no realiza ningún seguimiento de los métodos insertados. Se esperaba que el generador de perfiles bloqueara la inserción o realice un seguimiento de la inserción y llama a `RequestReJIT` de todos los inlineers para asegurarse de que se ReJITted cada instancia de un método insertado. Esto supone un problema con ReJIT en attach, ya que el generador de perfiles no está presente para supervisar la inserción. Se puede llamar a este método para garantizar que el conjunto completo de inlineers también se ReJITted.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
