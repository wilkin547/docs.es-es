---
title: ICorProfilerCallback::AppDomainShutdownStarted (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f422e99a5f6a4153368304ff0b33bbc55381575a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597861"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="99634-102">ICorProfilerCallback::AppDomainShutdownStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="99634-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="99634-103">Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.</span><span class="sxs-lookup"><span data-stu-id="99634-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99634-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99634-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99634-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99634-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="99634-106">[in] Identifica el dominio en el que se almacenan los ensamblados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="99634-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99634-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99634-107">Remarks</span></span>  
 <span data-ttu-id="99634-108">El valor de `appDomainId` no es válido para cualquier solicitud de información después de la `AppDomainShutdownStarted` devuelve del método, se trata de la última oportunidad para obtener información acerca de este dominio de aplicación del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="99634-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99634-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99634-109">Requirements</span></span>  
 <span data-ttu-id="99634-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99634-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99634-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99634-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99634-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99634-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99634-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99634-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99634-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="99634-114">See also</span></span>

- [<span data-ttu-id="99634-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99634-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
