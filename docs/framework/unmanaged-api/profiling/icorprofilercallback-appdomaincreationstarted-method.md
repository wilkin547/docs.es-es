---
title: ICorProfilerCallback::AppDomainCreationStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bffa383734a96a32595b018fd6d9b3dc62d5526
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484763"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="79843-102">ICorProfilerCallback::AppDomainCreationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="79843-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="79843-103">Notifica al generador de perfiles que se está creando un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="79843-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79843-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79843-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79843-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="79843-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="79843-106">[in] Identifica el dominio que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="79843-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79843-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79843-107">Remarks</span></span>  
 <span data-ttu-id="79843-108">El identificador no es válido para cualquier solicitud de información hasta la [AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="79843-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79843-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79843-109">Requirements</span></span>  
 <span data-ttu-id="79843-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79843-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79843-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79843-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79843-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79843-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79843-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79843-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79843-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="79843-114">See also</span></span>
- [<span data-ttu-id="79843-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79843-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
