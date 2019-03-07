---
title: ICorProfilerObjectEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7d1273c51dcfb63e3671b7b9d893e1022d55247
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473089"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="1adf2-102">ICorProfilerObjectEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="1adf2-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="1adf2-103">Desplaza el cursor de este enumerador desde su posición actual para que el número especificado de elementos se omite.</span><span class="sxs-lookup"><span data-stu-id="1adf2-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1adf2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1adf2-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1adf2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1adf2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1adf2-106">[in] El número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="1adf2-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1adf2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1adf2-107">Remarks</span></span>  
 <span data-ttu-id="1adf2-108">La nueva posición del cursor de este enumerador es: (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="1adf2-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1adf2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1adf2-109">Requirements</span></span>  
 <span data-ttu-id="1adf2-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1adf2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1adf2-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1adf2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1adf2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1adf2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1adf2-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1adf2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1adf2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1adf2-114">See also</span></span>
- [<span data-ttu-id="1adf2-115">ICorProfilerObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1adf2-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
