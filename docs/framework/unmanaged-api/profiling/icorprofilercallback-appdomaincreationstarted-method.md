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
ms.openlocfilehash: 141fd99ab0a96b20bfe06f1eb8612dd92b6cccc0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451495"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="9ff9f-102">ICorProfilerCallback::AppDomainCreationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="9ff9f-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="9ff9f-103">Notifica al generador de perfiles que se está creando un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ff9f-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ff9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ff9f-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ff9f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ff9f-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="9ff9f-106">[in] Identifica el dominio que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="9ff9f-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ff9f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ff9f-107">Remarks</span></span>  
 <span data-ttu-id="9ff9f-108">El identificador no es válido para cualquier solicitud de información hasta que el [ICorProfilerCallback:: AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="9ff9f-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ff9f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ff9f-109">Requirements</span></span>  
 <span data-ttu-id="9ff9f-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ff9f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ff9f-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ff9f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ff9f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ff9f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ff9f-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ff9f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ff9f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ff9f-114">See Also</span></span>  
 [<span data-ttu-id="9ff9f-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ff9f-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
