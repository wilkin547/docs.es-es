---
title: ICorProfilerInfo2::GetThreadAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b351c30c8eadd8c55543f664376cc4c7e5e73af
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481487"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="c78c9-102">ICorProfilerInfo2::GetThreadAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="c78c9-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="c78c9-103">Obtiene el identificador del dominio de aplicación en el que el subproceso especificado está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="c78c9-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c78c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c78c9-104">Syntax</span></span>  
  
```  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c78c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c78c9-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="c78c9-106">[in] Identificador que especifica el subproceso.</span><span class="sxs-lookup"><span data-stu-id="c78c9-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="c78c9-107">[out] Un puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c78c9-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c78c9-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c78c9-108">Requirements</span></span>  
 <span data-ttu-id="c78c9-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c78c9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c78c9-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c78c9-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c78c9-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c78c9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c78c9-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c78c9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78c9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c78c9-113">See also</span></span>
- [<span data-ttu-id="c78c9-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c78c9-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c78c9-115">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c78c9-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
