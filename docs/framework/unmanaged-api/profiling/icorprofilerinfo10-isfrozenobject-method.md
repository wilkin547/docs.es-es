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
ms.openlocfilehash: d212c06c7ddc9f22095c0b95f19fd1083482435c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661220"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="087dc-102">ICorProfilerInfo10:: IsFrozenObject (método)</span><span class="sxs-lookup"><span data-stu-id="087dc-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="087dc-103">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="087dc-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="087dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="087dc-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

#### <a name="parameters"></a><span data-ttu-id="087dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="087dc-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="087dc-106">de Objeto que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="087dc-106">[in] The object to examine.</span></span>

`pbFrozen` \
<span data-ttu-id="087dc-107">enuncia Un `BOOL` valor de tipo que indica si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="087dc-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="087dc-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="087dc-108">Requirements</span></span>

<span data-ttu-id="087dc-109">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="087dc-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="087dc-110">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="087dc-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="087dc-111">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="087dc-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="087dc-112">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="087dc-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="087dc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="087dc-113">See also</span></span>

- [<span data-ttu-id="087dc-114">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="087dc-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
