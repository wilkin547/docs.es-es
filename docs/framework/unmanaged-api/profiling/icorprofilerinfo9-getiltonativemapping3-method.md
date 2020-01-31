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
ms.openlocfilehash: 5c49d75432980d2f3af77ee040bc6eb20886b027
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861676"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="3d2e1-102">ICorProfilerInfo9:: GetILToNativeMapping3 (método)</span><span class="sxs-lookup"><span data-stu-id="3d2e1-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="3d2e1-103">Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código.</span><span class="sxs-lookup"><span data-stu-id="3d2e1-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="3d2e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d2e1-104">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a><span data-ttu-id="3d2e1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3d2e1-105">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="3d2e1-106">\[in] un puntero al inicio de una función nativa.</span><span class="sxs-lookup"><span data-stu-id="3d2e1-106">\[in] A pointer to the start of a native function.</span></span>

- `cMap`

  <span data-ttu-id="3d2e1-107">\[en] el tamaño máximo de la matriz de `map`.</span><span class="sxs-lookup"><span data-stu-id="3d2e1-107">\[in] The maximum size of the `map` array.</span></span>

- `pcMap`

  <span data-ttu-id="3d2e1-108">\[out] el número total de estructuras de COR_DEBUG_IL_TO_NATIVE_MAP disponibles.</span><span class="sxs-lookup"><span data-stu-id="3d2e1-108">\[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

- `map`

  <span data-ttu-id="3d2e1-109">\[out] una matriz de estructuras de [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , cada una de las cuales especifica los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="3d2e1-109">\[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="3d2e1-110">Después de que el método `GetILToNativeMapping3` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="3d2e1-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="3d2e1-111">Notas</span><span class="sxs-lookup"><span data-stu-id="3d2e1-111">Remarks</span></span>

<span data-ttu-id="3d2e1-112">Cuando la compilación en capas está habilitada, un método puede tener más de un cuerpo de código nativo.</span><span class="sxs-lookup"><span data-stu-id="3d2e1-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="3d2e1-113">[ICorProfilerInfo9:: GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) devolverá las direcciones de inicio para todos los cuerpos de código nativo.</span><span class="sxs-lookup"><span data-stu-id="3d2e1-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="3d2e1-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3d2e1-114">Requirements</span></span>

<span data-ttu-id="3d2e1-115">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="3d2e1-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="3d2e1-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d2e1-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="3d2e1-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d2e1-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3d2e1-118">**.NET Framework versiones:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d2e1-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3d2e1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d2e1-119">See also</span></span>

- [<span data-ttu-id="3d2e1-120">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="3d2e1-120">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
