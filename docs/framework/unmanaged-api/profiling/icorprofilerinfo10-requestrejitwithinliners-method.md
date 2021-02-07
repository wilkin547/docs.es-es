---
description: 'Más información sobre: ICorProfilerInfo10:: RequestReJITWithInliners (método)'
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
ms.openlocfilehash: da3434926b36408adfdee2171d56f23ba764f0eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753268"
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

  \[en] número de funciones que se van a volver a compilar.

- `moduleIds`

  \[en] especifica la `moduleId` parte de los `module` pares (, `methodDef` ) que identifican las funciones que se van a volver a compilar.

- `methodIds`

  \[en] especifica la `methodId` parte de los `module` pares (, `methodDef` ) que identifican las funciones que se van a volver a compilar.

## <a name="remarks"></a>Observaciones

[Requestrejit (](icorprofilerinfo4-requestrejit-method.md) no realiza ningún seguimiento de los métodos insertados. Se espera que el generador de perfiles bloquee la inserción o realice un seguimiento de la inserción y llame a `RequestReJIT` para todos los inlineers para asegurarse de que se ReJITted cada instancia de un método insertado. Esto supone un problema con ReJIT en attach, ya que el generador de perfiles no está presente para supervisar la inserción. Se puede llamar a este método para garantizar que el conjunto completo de inlineers también se ReJITted.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo10](icorprofilerinfo10-interface.md)
