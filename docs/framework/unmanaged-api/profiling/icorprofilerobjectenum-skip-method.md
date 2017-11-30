---
title: "ICorProfilerObjectEnum::Skip (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Skip
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 84960af6e128f3a6aa9e3b45187e282ac7228e0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="58023-102">ICorProfilerObjectEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="58023-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="58023-103">Desplaza el cursor de este enumerador desde su posición actual para que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="58023-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58023-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58023-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58023-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58023-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="58023-106">[in] El número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="58023-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58023-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58023-107">Remarks</span></span>  
 <span data-ttu-id="58023-108">La nueva posición del cursor de este enumerador es: (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="58023-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58023-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58023-109">Requirements</span></span>  
 <span data-ttu-id="58023-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58023-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58023-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58023-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58023-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58023-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58023-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58023-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58023-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="58023-114">See Also</span></span>  
 [<span data-ttu-id="58023-115">ICorProfilerObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58023-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
