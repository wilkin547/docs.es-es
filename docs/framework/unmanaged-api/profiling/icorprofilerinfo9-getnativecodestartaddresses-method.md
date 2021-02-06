---
description: 'Más información sobre: ICorProfilerInfo9:: GetNativeCodeStartAddresses (método)'
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
ms.openlocfilehash: 1ca686cef4a45ebb9e05190fa790ed5300c0d816
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646496"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="2f651-103">ICorProfilerInfo9:: GetNativeCodeStartAddresses (método)</span><span class="sxs-lookup"><span data-stu-id="2f651-103">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="2f651-104">Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente.</span><span class="sxs-lookup"><span data-stu-id="2f651-104">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f651-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f651-105">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="2f651-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2f651-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="2f651-107">\[en] identificador de la función cuyas direcciones de inicio de código nativo deben devolverse.</span><span class="sxs-lookup"><span data-stu-id="2f651-107">\[in] The ID of the function whose native code start addresses should be returned.</span></span>

- `reJitId`

  <span data-ttu-id="2f651-108">\[en] la identidad de la función con compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="2f651-108">\[in] The identity of the JIT-recompiled function.</span></span>

- `cCodeStartAddresses`

  <span data-ttu-id="2f651-109">\[en] tamaño máximo de la `codeStartAddresses` matriz.</span><span class="sxs-lookup"><span data-stu-id="2f651-109">\[in] The maximum size of the `codeStartAddresses` array.</span></span>

- `pcCodeStartAddresses`

  <span data-ttu-id="2f651-110">\[out] el número de direcciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="2f651-110">\[out] The number of available addresses.</span></span>

- `codeStartAddresses`

  <span data-ttu-id="2f651-111">\[out] una matriz de `UINT_PTR` , cada una de las cuales es la dirección inicial de un cuerpo nativo para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="2f651-111">\[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f651-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2f651-112">Remarks</span></span>

<span data-ttu-id="2f651-113">Cuando la compilación en capas está habilitada, una función puede tener más de un cuerpo de código nativo.</span><span class="sxs-lookup"><span data-stu-id="2f651-113">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f651-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f651-114">Requirements</span></span>

<span data-ttu-id="2f651-115">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="2f651-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="2f651-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f651-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="2f651-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f651-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2f651-118">**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f651-118">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2f651-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f651-119">See also</span></span>

- [<span data-ttu-id="2f651-120">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="2f651-120">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
