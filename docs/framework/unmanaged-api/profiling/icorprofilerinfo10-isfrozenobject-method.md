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
ms.openlocfilehash: c4d31c96fd7470a153437ffb0125e81ca8ea77bd
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759760"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="0246a-103">ICorProfilerInfo10:: IsFrozenObject (método)</span><span class="sxs-lookup"><span data-stu-id="0246a-103">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="0246a-104">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="0246a-104">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="0246a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0246a-105">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="0246a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0246a-106">Parameters</span></span>

<span data-ttu-id="0246a-107">`objectId` de Objeto que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="0246a-107">`objectId` [in] The object to examine.</span></span>

<span data-ttu-id="0246a-108">`pbFrozen` enuncia Un valor de `BOOL` tipo que indica si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="0246a-108">`pbFrozen` [out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="0246a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0246a-109">Requirements</span></span>

<span data-ttu-id="0246a-110">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="0246a-110">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="0246a-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0246a-111">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="0246a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0246a-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0246a-113">**Versiones de .net:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0246a-113">**.NET Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0246a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0246a-114">See also</span></span>

- [<span data-ttu-id="0246a-115">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="0246a-115">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
