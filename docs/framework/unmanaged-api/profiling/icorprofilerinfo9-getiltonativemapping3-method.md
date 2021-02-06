---
description: 'Más información sobre: ICorProfilerInfo9:: GetILToNativeMapping3 (método)'
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
ms.openlocfilehash: 867375d57f9d166ed08bf68ada81fb5cdbb8afe3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646522"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="049a3-103">ICorProfilerInfo9:: GetILToNativeMapping3 (método)</span><span class="sxs-lookup"><span data-stu-id="049a3-103">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="049a3-104">Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código.</span><span class="sxs-lookup"><span data-stu-id="049a3-104">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="049a3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="049a3-105">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a><span data-ttu-id="049a3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="049a3-106">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="049a3-107">\[in] un puntero al inicio de una función nativa.</span><span class="sxs-lookup"><span data-stu-id="049a3-107">\[in] A pointer to the start of a native function.</span></span>

- `cMap`

  <span data-ttu-id="049a3-108">\[en] tamaño máximo de la `map` matriz.</span><span class="sxs-lookup"><span data-stu-id="049a3-108">\[in] The maximum size of the `map` array.</span></span>

- `pcMap`

  <span data-ttu-id="049a3-109">\[out] el número total de estructuras de COR_DEBUG_IL_TO_NATIVE_MAP disponibles.</span><span class="sxs-lookup"><span data-stu-id="049a3-109">\[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

- `map`

  <span data-ttu-id="049a3-110">\[out] una matriz de estructuras [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , cada una de las cuales especifica los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="049a3-110">\[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="049a3-111">Después de que el método `GetILToNativeMapping3` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="049a3-111">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="049a3-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="049a3-112">Remarks</span></span>

<span data-ttu-id="049a3-113">Cuando la compilación en capas está habilitada, un método puede tener más de un cuerpo de código nativo.</span><span class="sxs-lookup"><span data-stu-id="049a3-113">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="049a3-114">[ICorProfilerInfo9:: GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) devolverá las direcciones de inicio para todos los cuerpos de código nativo.</span><span class="sxs-lookup"><span data-stu-id="049a3-114">[ICorProfilerInfo9::GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="049a3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="049a3-115">Requirements</span></span>

<span data-ttu-id="049a3-116">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="049a3-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="049a3-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="049a3-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="049a3-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="049a3-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="049a3-119">**.NET Framework versiones:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="049a3-119">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="049a3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="049a3-120">See also</span></span>

- [<span data-ttu-id="049a3-121">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="049a3-121">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
