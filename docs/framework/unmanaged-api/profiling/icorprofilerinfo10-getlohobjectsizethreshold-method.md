---
description: 'Más información sobre: ICorProfilerInfo10:: GetLOHObjectSizeThreshold (método)'
title: ICorProfilerInfo10::GetLOHObjectSizeThreshold
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 665a08ae226f04d5282b9584932078736751d5d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737315"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>ICorProfilerInfo10:: GetLOHObjectSizeThreshold (método)

Obtiene el valor del umbral del montón de objetos grandes (montón) configurado.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a>Parámetros

- `pThreshold`

  \[out] el umbral del montón de objetos grandes en bytes.

## <a name="remarks"></a>Observaciones

Los objetos mayores que el umbral del montón de objetos grandes se asignarán en el montón de objetos grandes. A partir de .NET Core 3,0, se puede configurar el umbral del montón de objetos grandes, `pThreshold` que contendrá el tamaño de umbral del montón del objeto grande activo en bytes.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo10](icorprofilerinfo10-interface.md)
