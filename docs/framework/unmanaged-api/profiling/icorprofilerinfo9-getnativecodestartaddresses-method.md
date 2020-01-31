---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 8412020fb98fde245b873a2f0c6a355f6436f712
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868283"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="06ea4-102">ICorProfilerInfo9:: GetNativeCodeStartAddresses (método)</span><span class="sxs-lookup"><span data-stu-id="06ea4-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="06ea4-103">Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente.</span><span class="sxs-lookup"><span data-stu-id="06ea4-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="06ea4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06ea4-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="06ea4-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="06ea4-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="06ea4-106">\[en] identificador de la función cuyas direcciones de inicio de código nativo deben devolverse.</span><span class="sxs-lookup"><span data-stu-id="06ea4-106">\[in] The ID of the function whose native code start addresses should be returned.</span></span>

- `reJitId`

  <span data-ttu-id="06ea4-107">\[en] la identidad de la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="06ea4-107">\[in] The identity of the JIT-recompiled function.</span></span>

- `cCodeStartAddresses`

  <span data-ttu-id="06ea4-108">\[en] el tamaño máximo de la matriz de `codeStartAddresses`.</span><span class="sxs-lookup"><span data-stu-id="06ea4-108">\[in] The maximum size of the `codeStartAddresses` array.</span></span>

- `pcCodeStartAddresses`

  <span data-ttu-id="06ea4-109">\[out] el número de direcciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="06ea4-109">\[out] The number of available addresses.</span></span>

- `codeStartAddresses`

  <span data-ttu-id="06ea4-110">\[out] una matriz de `UINT_PTR`, cada una de las cuales es la dirección inicial de un cuerpo nativo para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="06ea4-110">\[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="06ea4-111">Notas</span><span class="sxs-lookup"><span data-stu-id="06ea4-111">Remarks</span></span>

<span data-ttu-id="06ea4-112">Cuando la compilación en capas está habilitada, una función puede tener más de un cuerpo de código nativo.</span><span class="sxs-lookup"><span data-stu-id="06ea4-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="06ea4-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="06ea4-113">Requirements</span></span>

<span data-ttu-id="06ea4-114">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="06ea4-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="06ea4-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06ea4-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="06ea4-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06ea4-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="06ea4-117">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06ea4-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="06ea4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="06ea4-118">See also</span></span>

- [<span data-ttu-id="06ea4-119">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="06ea4-119">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
