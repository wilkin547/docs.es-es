---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f65cebff912adeb7afc34434467cf7be72f9be32
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449769"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="006cd-102">ICorProfilerInfo9:: GetCodeInfo4 (método)</span><span class="sxs-lookup"><span data-stu-id="006cd-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="006cd-103">Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código.</span><span class="sxs-lookup"><span data-stu-id="006cd-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="006cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="006cd-104">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a><span data-ttu-id="006cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="006cd-105">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="006cd-106">\[in] un puntero al inicio de una función nativa.</span><span class="sxs-lookup"><span data-stu-id="006cd-106">\[in] A pointer to the start of a native function.</span></span>

- `cCodeInfos`

  <span data-ttu-id="006cd-107">\[en] tamaño de la matriz de `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="006cd-107">\[in] The size of the `codeInfos` array.</span></span>

- `pcCodeInfos`

  <span data-ttu-id="006cd-108">\[out] un puntero al número total de estructuras de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) disponibles.</span><span class="sxs-lookup"><span data-stu-id="006cd-108">\[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>

- `codeInfos`

  <span data-ttu-id="006cd-109">\[out] búfer proporcionado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="006cd-109">\[out] A caller-provided buffer.</span></span> <span data-ttu-id="006cd-110">Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.</span><span class="sxs-lookup"><span data-stu-id="006cd-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="006cd-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="006cd-111">Remarks</span></span>

<span data-ttu-id="006cd-112">El método `GetCodeInfo4` es similar a [getcodeinfo3 (](icorprofilerinfo4-getcodeinfo3-method.md), con la salvedad de que puede buscar información de código para diferentes versiones nativas de un método.</span><span class="sxs-lookup"><span data-stu-id="006cd-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="006cd-113">`GetCodeInfo4` puede desencadenar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="006cd-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="006cd-114">Las extensiones se clasifican en orden creciente de desplazamiento de Common Intermediate Language (CIL).</span><span class="sxs-lookup"><span data-stu-id="006cd-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="006cd-115">Después de que `GetCodeInfo4` devuelve, debe comprobar que el búfer de `codeInfos` era lo suficientemente grande como para contener todas las estructuras de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="006cd-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="006cd-116">Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="006cd-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="006cd-117">Si `cCodeInfos` dividido por el tamaño de una estructura de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) es menor que `pcCodeInfos`, asigne un búfer de `codeInfos` mayor, actualice `cCodeInfos` con el nuevo tamaño y vuelva a llamar a `GetCodeInfo4`.</span><span class="sxs-lookup"><span data-stu-id="006cd-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="006cd-118">También tiene la opción de llamar primero a `GetCodeInfo4` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="006cd-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="006cd-119">Después, puede establecer el tamaño del búfer `codeInfos` en el valor devuelto en `pcCodeInfos`, multiplicado por el tamaño de una estructura [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) y volver a llamar a `GetCodeInfo4`.</span><span class="sxs-lookup"><span data-stu-id="006cd-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="006cd-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="006cd-120">Requirements</span></span>

<span data-ttu-id="006cd-121">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="006cd-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="006cd-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="006cd-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="006cd-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="006cd-123">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="006cd-124">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="006cd-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="006cd-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="006cd-125">See also</span></span>

- [<span data-ttu-id="006cd-126">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="006cd-126">ICorProfilerInfo9 Interface</span></span>](ICorProfilerInfo9-interface.md)
