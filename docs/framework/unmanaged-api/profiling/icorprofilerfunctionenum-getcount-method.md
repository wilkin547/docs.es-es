---
title: "ICorProfilerFunctionEnum::GetCount (Método)"
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
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3ac7e1e4c13578859c02f531dbc3b5e6f01e55cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="7d290-102">ICorProfilerFunctionEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="7d290-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="7d290-103">Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.</span><span class="sxs-lookup"><span data-stu-id="7d290-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d290-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d290-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d290-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d290-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7d290-106">[out] El número de funciones que se cargaron.</span><span class="sxs-lookup"><span data-stu-id="7d290-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d290-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d290-107">Requirements</span></span>  
 <span data-ttu-id="7d290-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d290-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d290-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7d290-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d290-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d290-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d290-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d290-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d290-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d290-112">See Also</span></span>  
 [<span data-ttu-id="7d290-113">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d290-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="7d290-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7d290-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
