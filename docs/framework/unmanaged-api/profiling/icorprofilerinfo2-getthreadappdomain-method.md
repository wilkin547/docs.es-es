---
title: "ICorProfilerInfo2::GetThreadAppDomain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetThreadAppDomain
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c6e596a4610052d7586978a4e770d5df60b38ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="cc466-102">ICorProfilerInfo2::GetThreadAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="cc466-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="cc466-103">Obtiene el identificador del dominio de aplicación en el que el subproceso especificado está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="cc466-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc466-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc466-104">Syntax</span></span>  
  
```  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc466-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc466-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="cc466-106">[in] Identificador que especifica el subproceso.</span><span class="sxs-lookup"><span data-stu-id="cc466-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="cc466-107">[out] Un puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc466-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc466-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc466-108">Requirements</span></span>  
 <span data-ttu-id="cc466-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc466-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc466-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc466-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc466-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc466-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc466-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc466-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc466-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc466-113">See Also</span></span>  
 [<span data-ttu-id="cc466-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc466-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="cc466-115">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc466-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
