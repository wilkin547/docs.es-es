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
ms.openlocfilehash: 00bfc9fc21ed39226fd21c4096305c254d73ee11
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665725"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="5a245-102">ICorProfilerInfo10:: RequestReJITWithInliners (método)</span><span class="sxs-lookup"><span data-stu-id="5a245-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="5a245-103">ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.</span><span class="sxs-lookup"><span data-stu-id="5a245-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a245-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a245-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

#### <a name="parameters"></a><span data-ttu-id="5a245-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a245-105">Parameters</span></span>

`dwRejitFlags` \
<span data-ttu-id="5a245-106">de Máscara de [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5a245-106">[in] A bitmask of [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).</span></span>

`cFunctions` \
<span data-ttu-id="5a245-107">[in] Número de funciones que se va a recompilar.</span><span class="sxs-lookup"><span data-stu-id="5a245-107">[in] The number of functions to recompile.</span></span>

`moduleIds` \
<span data-ttu-id="5a245-108">[in] Especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.</span><span class="sxs-lookup"><span data-stu-id="5a245-108">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

`methodIds` \
<span data-ttu-id="5a245-109">[in] Especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.</span><span class="sxs-lookup"><span data-stu-id="5a245-109">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a245-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a245-110">Remarks</span></span>

<span data-ttu-id="5a245-111">[Requestrejit (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) no realiza ningún seguimiento de los métodos insertados.</span><span class="sxs-lookup"><span data-stu-id="5a245-111">[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="5a245-112">Se espera que el generador de perfiles bloquee la inserción o realice un seguimiento `RequestReJIT` de la inserción y llame a para todos los inlineers para asegurarse de que se ReJITted cada instancia de un método insertado.</span><span class="sxs-lookup"><span data-stu-id="5a245-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="5a245-113">Esto supone un problema con ReJIT en attach, ya que el generador de perfiles no está presente para supervisar la inserción.</span><span class="sxs-lookup"><span data-stu-id="5a245-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="5a245-114">Se puede llamar a este método para garantizar que el conjunto completo de inlineers también se ReJITted.</span><span class="sxs-lookup"><span data-stu-id="5a245-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a245-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a245-115">Requirements</span></span>

<span data-ttu-id="5a245-116">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="5a245-116">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="5a245-117">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="5a245-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5a245-118">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a245-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5a245-119">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a245-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5a245-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a245-120">See also</span></span>

- [<span data-ttu-id="5a245-121">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="5a245-121">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
