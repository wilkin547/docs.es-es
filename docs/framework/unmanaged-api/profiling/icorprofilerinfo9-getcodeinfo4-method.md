---
description: 'Más información sobre: ICorProfilerInfo9:: GetCodeInfo4 (método)'
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
ms.openlocfilehash: c7897e266fbb84d44df719c127e24bd375b560bb
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759096"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="2310d-103">ICorProfilerInfo9:: GetCodeInfo4 (método)</span><span class="sxs-lookup"><span data-stu-id="2310d-103">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="2310d-104">Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código.</span><span class="sxs-lookup"><span data-stu-id="2310d-104">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="2310d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2310d-105">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a><span data-ttu-id="2310d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2310d-106">Parameters</span></span>

<span data-ttu-id="2310d-107">`pNativeCodeStartAddress` de Puntero al inicio de una función nativa.</span><span class="sxs-lookup"><span data-stu-id="2310d-107">`pNativeCodeStartAddress` [in] A pointer to the start of a native function.</span></span>

<span data-ttu-id="2310d-108">`cCodeInfos` de Tamaño de la `codeInfos` matriz.</span><span class="sxs-lookup"><span data-stu-id="2310d-108">`cCodeInfos` [in] The size of the `codeInfos` array.</span></span>

<span data-ttu-id="2310d-109">`pcCodeInfos` enuncia Puntero al número total de estructuras de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) disponibles.</span><span class="sxs-lookup"><span data-stu-id="2310d-109">`pcCodeInfos` [out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>

<span data-ttu-id="2310d-110">`codeInfos` enuncia Búfer proporcionado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2310d-110">`codeInfos` [out] A caller-provided buffer.</span></span> <span data-ttu-id="2310d-111">Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.</span><span class="sxs-lookup"><span data-stu-id="2310d-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2310d-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2310d-112">Remarks</span></span>

<span data-ttu-id="2310d-113">El `GetCodeInfo4` método es similar a [getcodeinfo3 (](icorprofilerinfo4-getcodeinfo3-method.md), con la salvedad de que puede buscar información de código para diferentes versiones nativas de un método.</span><span class="sxs-lookup"><span data-stu-id="2310d-113">The `GetCodeInfo4` method is similar to [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="2310d-114">`GetCodeInfo4` puede desencadenar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2310d-114">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="2310d-115">Las extensiones se clasifican en orden creciente de desplazamiento de Common Intermediate Language (CIL).</span><span class="sxs-lookup"><span data-stu-id="2310d-115">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="2310d-116">Después de `GetCodeInfo4` que devuelva, debe comprobar que el `codeInfos` búfer era lo suficientemente grande como para contener todas las estructuras de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="2310d-116">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="2310d-117">Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="2310d-117">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="2310d-118">Si `cCodeInfos` se divide por el tamaño de una estructura de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) es menor que `pcCodeInfos` , asigne un `codeInfos` búfer mayor, actualice `cCodeInfos` con el nuevo tamaño mayor y vuelva a llamar a `GetCodeInfo4` .</span><span class="sxs-lookup"><span data-stu-id="2310d-118">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="2310d-119">También tiene la opción de llamar primero a `GetCodeInfo4` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="2310d-119">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="2310d-120">Después, puede establecer el `codeInfos` tamaño del búfer en el valor devuelto en `pcCodeInfos` , multiplicado por el tamaño de una estructura de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) y volver a llamar a `GetCodeInfo4` .</span><span class="sxs-lookup"><span data-stu-id="2310d-120">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="2310d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2310d-121">Requirements</span></span>

<span data-ttu-id="2310d-122">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="2310d-122">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="2310d-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2310d-123">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="2310d-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2310d-124">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2310d-125">**Versiones de .net:**[!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2310d-125">**.NET Versions:** [!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2310d-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2310d-126">See also</span></span>

- [<span data-ttu-id="2310d-127">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="2310d-127">ICorProfilerInfo9 Interface</span></span>](ICorProfilerInfo9-interface.md)
