---
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
ms.openlocfilehash: 7a0f6f6bea5bc919ebfe9c9acc3b02a31eaa7cd0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452219"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="00833-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold (método)</span><span class="sxs-lookup"><span data-stu-id="00833-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="00833-103">Obtiene el valor del umbral del montón de objetos grandes (montón) configurado.</span><span class="sxs-lookup"><span data-stu-id="00833-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="00833-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00833-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="00833-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00833-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="00833-106">\[out] el umbral del montón de objetos grandes en bytes.</span><span class="sxs-lookup"><span data-stu-id="00833-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="00833-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00833-107">Remarks</span></span>

<span data-ttu-id="00833-108">Los objetos mayores que el umbral del montón de objetos grandes se asignarán en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="00833-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="00833-109">A partir de .NET Core 3,0, se puede configurar el umbral del montón de objetos grandes, `pThreshold` contendrá el tamaño de umbral del montón del objeto grande activo en bytes.</span><span class="sxs-lookup"><span data-stu-id="00833-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="00833-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00833-110">Requirements</span></span>

<span data-ttu-id="00833-111">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="00833-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="00833-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="00833-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="00833-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00833-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="00833-114">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00833-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="00833-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00833-115">See also</span></span>

- [<span data-ttu-id="00833-116">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="00833-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
