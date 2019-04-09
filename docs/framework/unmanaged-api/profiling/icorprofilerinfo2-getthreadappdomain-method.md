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
ms.openlocfilehash: 32a69f948b936dd80ab364583dc2928778b34ba0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174413"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="0564e-102">ICorProfilerInfo2::GetThreadAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="0564e-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="0564e-103">Obtiene el identificador del dominio de aplicación en el que el subproceso especificado está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="0564e-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0564e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0564e-104">Syntax</span></span>  
  
```  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0564e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0564e-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="0564e-106">[in] Identificador que especifica el subproceso.</span><span class="sxs-lookup"><span data-stu-id="0564e-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="0564e-107">[out] Un puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0564e-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0564e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0564e-108">Requirements</span></span>  
 <span data-ttu-id="0564e-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0564e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0564e-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0564e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0564e-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0564e-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0564e-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0564e-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0564e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0564e-113">See also</span></span>

- [<span data-ttu-id="0564e-114">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0564e-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="0564e-115">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0564e-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
