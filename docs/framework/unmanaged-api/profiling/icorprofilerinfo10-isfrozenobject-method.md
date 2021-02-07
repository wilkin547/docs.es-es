---
description: 'Más información sobre: ICorProfilerInfo10:: IsFrozenObject (método)'
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: b07e456f7fa9c328217b8779733d45dfe2793fe2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753281"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="b3b5a-103">ICorProfilerInfo10:: IsFrozenObject (método)</span><span class="sxs-lookup"><span data-stu-id="b3b5a-103">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="b3b5a-104">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b3b5a-104">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3b5a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3b5a-105">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="b3b5a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3b5a-106">Parameters</span></span>

- `objectId`

  <span data-ttu-id="b3b5a-107">\[en] objeto que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="b3b5a-107">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="b3b5a-108">\[out] un valor de `BOOL` tipo que indica si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b3b5a-108">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3b5a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3b5a-109">Requirements</span></span>

<span data-ttu-id="b3b5a-110">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="b3b5a-110">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="b3b5a-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3b5a-111">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="b3b5a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3b5a-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b3b5a-113">**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3b5a-113">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b3b5a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3b5a-114">See also</span></span>

- [<span data-ttu-id="b3b5a-115">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="b3b5a-115">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
