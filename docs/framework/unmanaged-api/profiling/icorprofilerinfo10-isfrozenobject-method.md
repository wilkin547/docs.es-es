---
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
ms.openlocfilehash: b6dabefceba038a129148f7ba36d4ffcfc425c80
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790040"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="1bd64-102">ICorProfilerInfo10:: IsFrozenObject (método)</span><span class="sxs-lookup"><span data-stu-id="1bd64-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="1bd64-103">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1bd64-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="1bd64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bd64-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="1bd64-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1bd64-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="1bd64-106">\[en] el objeto que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="1bd64-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="1bd64-107">\[out] un `BOOL` que indica si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1bd64-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="1bd64-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1bd64-108">Requirements</span></span>

<span data-ttu-id="1bd64-109">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="1bd64-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="1bd64-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1bd64-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1bd64-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bd64-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1bd64-112">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bd64-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1bd64-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bd64-113">See also</span></span>

- [<span data-ttu-id="1bd64-114">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="1bd64-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
