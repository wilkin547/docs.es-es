---
title: "ICorProfilerThreadEnum::GetCount (Método)"
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
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: afbcb71fdaf48d07103d6ca2db48b46095dc3acd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="fb94a-102">ICorProfilerThreadEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="fb94a-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="fb94a-103">Obtiene el número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fb94a-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb94a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb94a-104">Syntax</span></span>  
  
```  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb94a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb94a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fb94a-106">[out] El número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fb94a-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb94a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb94a-107">Requirements</span></span>  
 <span data-ttu-id="fb94a-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb94a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb94a-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb94a-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb94a-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb94a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb94a-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb94a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb94a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb94a-112">See Also</span></span>  
 [<span data-ttu-id="fb94a-113">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb94a-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="fb94a-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="fb94a-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
