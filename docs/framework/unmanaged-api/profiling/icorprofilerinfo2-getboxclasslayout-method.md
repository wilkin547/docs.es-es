---
title: "ICorProfilerInfo2::GetBoxClassLayout (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9ef6df997a4ba4369b87789e47ac7ead2206162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="49acc-102">ICorProfilerInfo2::GetBoxClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="49acc-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="49acc-103">Obtiene información sobre dónde se encuentra el tipo de valor especificado cuando se adquirió en caja.</span><span class="sxs-lookup"><span data-stu-id="49acc-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49acc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49acc-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49acc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="49acc-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="49acc-106">[in] El identificador de la clase que describe el tipo de valor que es una conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="49acc-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="49acc-107">[out] Un entero que es el desplazamiento, en relación con el puntero de identificador de objeto sometido a conversión boxing del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="49acc-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49acc-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="49acc-108">Remarks</span></span>  
 <span data-ttu-id="49acc-109">El `pBufferOffset` valor es la ubicación del tipo de valor dentro de un cuadro.</span><span class="sxs-lookup"><span data-stu-id="49acc-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="49acc-110">Después de `pBufferOffset` se aplica a un objeto sometido a conversión boxing, diseño de la clase del tipo de valor puede usarse para interpretar el valor del objeto.</span><span class="sxs-lookup"><span data-stu-id="49acc-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49acc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49acc-111">Requirements</span></span>  
 <span data-ttu-id="49acc-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49acc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49acc-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49acc-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49acc-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49acc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49acc-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49acc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49acc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="49acc-116">See Also</span></span>  
 [<span data-ttu-id="49acc-117">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="49acc-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="49acc-118">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="49acc-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
