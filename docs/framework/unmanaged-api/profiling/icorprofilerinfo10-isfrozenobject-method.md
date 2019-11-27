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
ms.openlocfilehash: 250021c9eb475d0cbcb1bd14c8515b969fc9d30b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449822"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="4a17b-102">ICorProfilerInfo10:: IsFrozenObject (método)</span><span class="sxs-lookup"><span data-stu-id="4a17b-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="4a17b-103">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4a17b-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a17b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a17b-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

#### <a name="parameters"></a><span data-ttu-id="4a17b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a17b-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="4a17b-106">de Objeto que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="4a17b-106">[in] The object to examine.</span></span>

`pbFrozen` \
<span data-ttu-id="4a17b-107">enuncia `BOOL` que indica si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4a17b-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="4a17b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a17b-108">Requirements</span></span>

<span data-ttu-id="4a17b-109">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="4a17b-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="4a17b-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a17b-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="4a17b-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a17b-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="4a17b-112">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a17b-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4a17b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a17b-113">See also</span></span>

- [<span data-ttu-id="4a17b-114">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="4a17b-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
