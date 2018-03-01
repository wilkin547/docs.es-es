---
title: "ICorProfilerCallback::AppDomainShutdownStarted (Método)"
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
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 14e515ae13e0a445580dabcdfa30253da94fd216
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="a1fe6-102">ICorProfilerCallback::AppDomainShutdownStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="a1fe6-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="a1fe6-103">Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1fe6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1fe6-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1fe6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1fe6-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="a1fe6-106">[in] Identifica el dominio en el que se almacenan los ensamblados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1fe6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1fe6-107">Remarks</span></span>  
 <span data-ttu-id="a1fe6-108">El valor de `appDomainId` no es válido para cualquier solicitud de información después de la `AppDomainShutdownStarted` devuelve del método: se trata de última oportunidad del generador de perfiles para obtener información acerca de este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1fe6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1fe6-109">Requirements</span></span>  
 <span data-ttu-id="a1fe6-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1fe6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1fe6-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1fe6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1fe6-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1fe6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1fe6-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1fe6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fe6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1fe6-114">See Also</span></span>  
 [<span data-ttu-id="a1fe6-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1fe6-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
