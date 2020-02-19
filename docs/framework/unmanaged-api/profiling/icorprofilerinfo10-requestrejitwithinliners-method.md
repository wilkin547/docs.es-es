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
ms.openlocfilehash: 99b6893854c358720259095bf3c0270cb3676483
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452180"
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

## <a name="parameters"></a>Parámetros

- `dwRejitFlags`

  \[en] una máscara de [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).

- `cFunctions`

  \[en] el número de funciones que se van a volver a compilar.

- `moduleIds`

  \[en] especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a volver a compilar.

- `methodIds`

  \[en] especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a volver a compilar.

## <a name="remarks"></a>Observaciones

[Requestrejit (](icorprofilerinfo4-requestrejit-method.md) no realiza ningún seguimiento de los métodos insertados. Se esperaba que el generador de perfiles bloqueara la inserción o realice un seguimiento de la inserción y llama a `RequestReJIT` de todos los inlineers para asegurarse de que se ReJITted cada instancia de un método insertado. Esto supone un problema con ReJIT en attach, ya que el generador de perfiles no está presente para supervisar la inserción. Se puede llamar a este método para garantizar que el conjunto completo de inlineers también se ReJITted.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?pivots=os-windows).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Consulte también

- [Interfaz ICorProfilerInfo10](icorprofilerinfo10-interface.md)
