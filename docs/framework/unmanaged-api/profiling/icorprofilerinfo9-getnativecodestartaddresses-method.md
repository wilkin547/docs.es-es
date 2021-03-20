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
ms.openlocfilehash: 062aebf6d5bed208ea71b215bd9f857b82483673
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759056"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="3ec21-103">ICorProfilerInfo9:: GetNativeCodeStartAddresses (método)</span><span class="sxs-lookup"><span data-stu-id="3ec21-103">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="3ec21-104">Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente.</span><span class="sxs-lookup"><span data-stu-id="3ec21-104">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="3ec21-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ec21-105">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="3ec21-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ec21-106">Parameters</span></span>

<span data-ttu-id="3ec21-107">`functionId` de IDENTIFICADOR de la función cuyas direcciones de inicio de código nativo deben devolverse.</span><span class="sxs-lookup"><span data-stu-id="3ec21-107">`functionId` [in] The ID of the function whose native code start addresses should be returned.</span></span>

<span data-ttu-id="3ec21-108">`reJitId` de La identidad de la función con compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="3ec21-108">`reJitId` [in] The identity of the JIT-recompiled function.</span></span>

<span data-ttu-id="3ec21-109">`cCodeStartAddresses` de Tamaño máximo de la `codeStartAddresses` matriz.</span><span class="sxs-lookup"><span data-stu-id="3ec21-109">`cCodeStartAddresses` [in] The maximum size of the `codeStartAddresses` array.</span></span>

<span data-ttu-id="3ec21-110">`pcCodeStartAddresses` enuncia El número de direcciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="3ec21-110">`pcCodeStartAddresses` [out] The number of available addresses.</span></span>

<span data-ttu-id="3ec21-111">`codeStartAddresses` enuncia Una matriz de `UINT_PTR` , cada una de las cuales es la dirección inicial de un cuerpo nativo para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="3ec21-111">`codeStartAddresses` [out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ec21-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3ec21-112">Remarks</span></span>

<span data-ttu-id="3ec21-113">Cuando la compilación en capas está habilitada, una función puede tener más de un cuerpo de código nativo.</span><span class="sxs-lookup"><span data-stu-id="3ec21-113">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="3ec21-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ec21-114">Requirements</span></span>

<span data-ttu-id="3ec21-115">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="3ec21-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="3ec21-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ec21-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="3ec21-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ec21-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3ec21-118">**Versiones de .net:**[!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ec21-118">**.NET Versions:** [!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3ec21-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ec21-119">See also</span></span>

- [<span data-ttu-id="3ec21-120">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="3ec21-120">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
