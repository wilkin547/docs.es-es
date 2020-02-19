---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 22fe5608b0a3f86baf80abb3810a512077954ac3
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449756"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="2e586-102">ICorProfilerInfo9:: GetILToNativeMapping3 (método)</span><span class="sxs-lookup"><span data-stu-id="2e586-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="2e586-103">Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código.</span><span class="sxs-lookup"><span data-stu-id="2e586-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e586-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e586-104">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a><span data-ttu-id="2e586-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e586-105">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="2e586-106">\[in] un puntero al inicio de una función nativa.</span><span class="sxs-lookup"><span data-stu-id="2e586-106">\[in] A pointer to the start of a native function.</span></span>

- `cMap`

  <span data-ttu-id="2e586-107">\[en] el tamaño máximo de la matriz de `map`.</span><span class="sxs-lookup"><span data-stu-id="2e586-107">\[in] The maximum size of the `map` array.</span></span>

- `pcMap`

  <span data-ttu-id="2e586-108">\[out] el número total de estructuras de COR_DEBUG_IL_TO_NATIVE_MAP disponibles.</span><span class="sxs-lookup"><span data-stu-id="2e586-108">\[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

- `map`

  <span data-ttu-id="2e586-109">\[out] una matriz de estructuras de [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , cada una de las cuales especifica los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="2e586-109">\[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="2e586-110">Después de que el método `GetILToNativeMapping3` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="2e586-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e586-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2e586-111">Remarks</span></span>

<span data-ttu-id="2e586-112">Cuando la compilación en capas está habilitada, un método puede tener más de un cuerpo de código nativo.</span><span class="sxs-lookup"><span data-stu-id="2e586-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="2e586-113">[ICorProfilerInfo9:: GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) devolverá las direcciones de inicio para todos los cuerpos de código nativo.</span><span class="sxs-lookup"><span data-stu-id="2e586-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e586-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e586-114">Requirements</span></span>

<span data-ttu-id="2e586-115">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="2e586-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="2e586-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e586-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="2e586-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e586-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2e586-118">**.NET Framework versiones:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e586-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2e586-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e586-119">See also</span></span>

- [<span data-ttu-id="2e586-120">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="2e586-120">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
