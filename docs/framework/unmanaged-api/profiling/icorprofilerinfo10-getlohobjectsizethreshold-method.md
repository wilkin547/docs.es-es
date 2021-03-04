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
ms.openlocfilehash: 96c502dba5b2807f9cd9c3c5cceb6b3b9985a406
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106961"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="e094e-103">ICorProfilerInfo10:: GetLOHObjectSizeThreshold (método)</span><span class="sxs-lookup"><span data-stu-id="e094e-103">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="e094e-104">Obtiene el valor del umbral del montón de objetos grandes (montón) configurado.</span><span class="sxs-lookup"><span data-stu-id="e094e-104">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="e094e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e094e-105">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="e094e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e094e-106">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="e094e-107">\[out] el umbral del montón de objetos grandes en bytes.</span><span class="sxs-lookup"><span data-stu-id="e094e-107">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="e094e-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e094e-108">Remarks</span></span>

<span data-ttu-id="e094e-109">Los objetos mayores que el umbral del montón de objetos grandes se asignarán en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="e094e-109">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="e094e-110">A partir de .NET Core 3,0, se puede configurar el umbral del montón de objetos grandes, `pThreshold` que contendrá el tamaño de umbral del montón del objeto grande activo en bytes.</span><span class="sxs-lookup"><span data-stu-id="e094e-110">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="e094e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e094e-111">Requirements</span></span>

<span data-ttu-id="e094e-112">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="e094e-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="e094e-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e094e-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="e094e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e094e-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e094e-115">**Versiones de .net:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e094e-115">**.NET Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e094e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e094e-116">See also</span></span>

- [<span data-ttu-id="e094e-117">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="e094e-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
