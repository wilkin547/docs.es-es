---
title: ICorProfilerObjectEnum::GetCount (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65f6067fcfe0e6ef5f01a13865d002afd6da9efb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474714"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="efbd3-102">ICorProfilerObjectEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="efbd3-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="efbd3-103">Obtiene el número total de objetos inmovilizados en la colección.</span><span class="sxs-lookup"><span data-stu-id="efbd3-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efbd3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efbd3-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efbd3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="efbd3-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="efbd3-106">[out] Un puntero al número de objetos inmovilizados en la colección.</span><span class="sxs-lookup"><span data-stu-id="efbd3-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="efbd3-107">Este método siempre devolverá cero en .NET Framework versión 3.5 Service Pack 1 (SP1) y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="efbd3-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efbd3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efbd3-108">Requirements</span></span>  
 <span data-ttu-id="efbd3-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efbd3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efbd3-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="efbd3-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="efbd3-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efbd3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efbd3-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efbd3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efbd3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="efbd3-113">See also</span></span>
- [<span data-ttu-id="efbd3-114">ICorProfilerObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="efbd3-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
