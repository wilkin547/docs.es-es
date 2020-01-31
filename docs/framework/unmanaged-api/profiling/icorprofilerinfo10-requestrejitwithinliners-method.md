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
ms.openlocfilehash: 5822136eb1a7f582bcfae901a99775950e586198
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863184"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="5ef42-102">ICorProfilerInfo10:: RequestReJITWithInliners (método)</span><span class="sxs-lookup"><span data-stu-id="5ef42-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="5ef42-103">ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.</span><span class="sxs-lookup"><span data-stu-id="5ef42-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ef42-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ef42-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a><span data-ttu-id="5ef42-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5ef42-105">Parameters</span></span>

- `dwRejitFlags`

  <span data-ttu-id="5ef42-106">\[en] una máscara de [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5ef42-106">\[in] A bitmask of [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span></span>

- `cFunctions`

  <span data-ttu-id="5ef42-107">\[en] el número de funciones que se van a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="5ef42-107">\[in] The number of functions to recompile.</span></span>

- `moduleIds`

  <span data-ttu-id="5ef42-108">\[en] especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="5ef42-108">\[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

- `methodIds`

  <span data-ttu-id="5ef42-109">\[en] especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="5ef42-109">\[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ef42-110">Notas</span><span class="sxs-lookup"><span data-stu-id="5ef42-110">Remarks</span></span>

<span data-ttu-id="5ef42-111">[Requestrejit (](icorprofilerinfo4-requestrejit-method.md) no realiza ningún seguimiento de los métodos insertados.</span><span class="sxs-lookup"><span data-stu-id="5ef42-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="5ef42-112">Se esperaba que el generador de perfiles bloqueara la inserción o realice un seguimiento de la inserción y llama a `RequestReJIT` de todos los inlineers para asegurarse de que se ReJITted cada instancia de un método insertado.</span><span class="sxs-lookup"><span data-stu-id="5ef42-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="5ef42-113">Esto supone un problema con ReJIT en attach, ya que el generador de perfiles no está presente para supervisar la inserción.</span><span class="sxs-lookup"><span data-stu-id="5ef42-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="5ef42-114">Se puede llamar a este método para garantizar que el conjunto completo de inlineers también se ReJITted.</span><span class="sxs-lookup"><span data-stu-id="5ef42-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="5ef42-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5ef42-115">Requirements</span></span>

<span data-ttu-id="5ef42-116">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="5ef42-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="5ef42-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ef42-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5ef42-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ef42-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5ef42-119">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ef42-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5ef42-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ef42-120">See also</span></span>

- [<span data-ttu-id="5ef42-121">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="5ef42-121">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
