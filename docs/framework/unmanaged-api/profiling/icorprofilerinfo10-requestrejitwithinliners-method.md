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
ms.openlocfilehash: 925a61bf2521950cad7fb0dce8f1484198f3f806
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106519"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="724cd-103">ICorProfilerInfo10:: RequestReJITWithInliners (método)</span><span class="sxs-lookup"><span data-stu-id="724cd-103">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="724cd-104">ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.</span><span class="sxs-lookup"><span data-stu-id="724cd-104">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="724cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="724cd-105">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a><span data-ttu-id="724cd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="724cd-106">Parameters</span></span>

- `dwRejitFlags`

  <span data-ttu-id="724cd-107">\[en] una máscara de [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="724cd-107">\[in] A bitmask of [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span></span>

- `cFunctions`

  <span data-ttu-id="724cd-108">\[en] número de funciones que se van a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="724cd-108">\[in] The number of functions to recompile.</span></span>

- `moduleIds`

  <span data-ttu-id="724cd-109">\[en] especifica la `moduleId` parte de los `module` pares (, `methodDef` ) que identifican las funciones que se van a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="724cd-109">\[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

- `methodIds`

  <span data-ttu-id="724cd-110">\[en] especifica la `methodId` parte de los `module` pares (, `methodDef` ) que identifican las funciones que se van a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="724cd-110">\[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="724cd-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="724cd-111">Remarks</span></span>

<span data-ttu-id="724cd-112">[Requestrejit (](icorprofilerinfo4-requestrejit-method.md) no realiza ningún seguimiento de los métodos insertados.</span><span class="sxs-lookup"><span data-stu-id="724cd-112">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="724cd-113">Se espera que el generador de perfiles bloquee la inserción o realice un seguimiento de la inserción y llame a `RequestReJIT` para todos los inlineers para asegurarse de que se ReJITted cada instancia de un método insertado.</span><span class="sxs-lookup"><span data-stu-id="724cd-113">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="724cd-114">Esto supone un problema con ReJIT en attach, ya que el generador de perfiles no está presente para supervisar la inserción.</span><span class="sxs-lookup"><span data-stu-id="724cd-114">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="724cd-115">Se puede llamar a este método para garantizar que el conjunto completo de inlineers también se ReJITted.</span><span class="sxs-lookup"><span data-stu-id="724cd-115">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="724cd-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="724cd-116">Requirements</span></span>

<span data-ttu-id="724cd-117">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="724cd-117">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="724cd-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="724cd-118">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="724cd-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="724cd-119">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="724cd-120">**Versiones de .net:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="724cd-120">**.NET Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="724cd-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="724cd-121">See also</span></span>

- [<span data-ttu-id="724cd-122">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="724cd-122">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
