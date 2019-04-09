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
ms.openlocfilehash: 6e42a8ab23705703770c8214b8c641b48c86094a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117227"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="bd6c4-102">ICorProfilerCallback::AppDomainCreationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="bd6c4-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="bd6c4-103">Notifica al generador de perfiles que se está creando un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bd6c4-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd6c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd6c4-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd6c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd6c4-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="bd6c4-106">[in] Identifica el dominio que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="bd6c4-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd6c4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd6c4-107">Remarks</span></span>  
 <span data-ttu-id="bd6c4-108">El identificador no es válido para cualquier solicitud de información hasta la [AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="bd6c4-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd6c4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd6c4-109">Requirements</span></span>  
 <span data-ttu-id="bd6c4-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd6c4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd6c4-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd6c4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd6c4-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd6c4-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bd6c4-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bd6c4-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bd6c4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd6c4-114">See also</span></span>

- [<span data-ttu-id="bd6c4-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd6c4-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
