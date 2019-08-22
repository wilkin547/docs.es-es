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
ms.openlocfilehash: 8c9a85e9f00027f597795eea55a9bbb0364790f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661240"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="1ec3b-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold (método)</span><span class="sxs-lookup"><span data-stu-id="1ec3b-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="1ec3b-103">Obtiene el valor del umbral del montón de objetos grandes (montón) configurado.</span><span class="sxs-lookup"><span data-stu-id="1ec3b-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ec3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ec3b-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="1ec3b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ec3b-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="1ec3b-106">enuncia Umbral del montón del objeto grande en bytes.</span><span class="sxs-lookup"><span data-stu-id="1ec3b-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ec3b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ec3b-107">Remarks</span></span>

<span data-ttu-id="1ec3b-108">Los objetos mayores que el umbral del montón de objetos grandes se asignarán en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="1ec3b-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="1ec3b-109">A partir de .net Core 3,0, se puede configurar el umbral del `pThreshold` montón de objetos grandes, que contendrá el tamaño de umbral del montón del objeto grande activo en bytes.</span><span class="sxs-lookup"><span data-stu-id="1ec3b-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ec3b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ec3b-110">Requirements</span></span>

<span data-ttu-id="1ec3b-111">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="1ec3b-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="1ec3b-112">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="1ec3b-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1ec3b-113">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ec3b-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1ec3b-114">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ec3b-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1ec3b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ec3b-115">See also</span></span>

- [<span data-ttu-id="1ec3b-116">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="1ec3b-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
