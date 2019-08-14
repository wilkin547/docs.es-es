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
ms.openlocfilehash: 05f25d8fb61a16f41a82a987529017db6a687740
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973995"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="98230-102">ICorProfilerInfo10:: IsFrozenObject (método)</span><span class="sxs-lookup"><span data-stu-id="98230-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>
  
 <span data-ttu-id="98230-103">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="98230-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="98230-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98230-104">Syntax</span></span>  
  
```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```  
  
#### <a name="parameters"></a><span data-ttu-id="98230-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98230-105">Parameters</span></span>  
 
 `objectId` \
 <span data-ttu-id="98230-106">de Objeto que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="98230-106">[in] The object to examine.</span></span>

 `pbFrozen` \
 <span data-ttu-id="98230-107">enuncia Un `BOOL` valor de tipo que indica si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="98230-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="98230-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98230-108">Requirements</span></span>  
 <span data-ttu-id="98230-109">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="98230-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="98230-110">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="98230-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="98230-111">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98230-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98230-112">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98230-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="98230-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="98230-113">See also</span></span>
- [<span data-ttu-id="98230-114">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="98230-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

