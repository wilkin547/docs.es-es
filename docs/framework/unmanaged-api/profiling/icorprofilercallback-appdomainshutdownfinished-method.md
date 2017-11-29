---
title: "ICorProfilerCallback::AppDomainShutdownFinished (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainShutdownFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 443f5cd48693d6ac3ce732746666bd2d5e3786fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="6b7a9-102">ICorProfilerCallback::AppDomainShutdownFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="6b7a9-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="6b7a9-103">Notifica al generador de perfiles que un dominio de aplicación se ha descargado desde un proceso.</span><span class="sxs-lookup"><span data-stu-id="6b7a9-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b7a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b7a9-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b7a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b7a9-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="6b7a9-106">[in] Identifica el dominio en el que se almacenan los ensamblados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b7a9-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="6b7a9-107">[in] Un valor HRESULT que indica si el dominio de aplicación se descargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6b7a9-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b7a9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b7a9-108">Remarks</span></span>  
 <span data-ttu-id="6b7a9-109">El valor de `appDomainId` no es válido para una solicitud de información después de la [ICorProfilerCallback:: AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) devuelve del método.</span><span class="sxs-lookup"><span data-stu-id="6b7a9-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="6b7a9-110">Algunas partes de la descarga el dominio de aplicación podrían continuar después de la `AppDomainCreationFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="6b7a9-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="6b7a9-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="6b7a9-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="6b7a9-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga el dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6b7a9-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b7a9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b7a9-113">Requirements</span></span>  
 <span data-ttu-id="6b7a9-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b7a9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b7a9-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6b7a9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6b7a9-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b7a9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b7a9-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b7a9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7a9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b7a9-118">See Also</span></span>  
 [<span data-ttu-id="6b7a9-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b7a9-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
