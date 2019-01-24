---
title: ICorProfilerCallback::AppDomainShutdownFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c89a7671cde9e519d0fc66751ee8f95b34fe9039
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669671"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="07d6a-102">ICorProfilerCallback::AppDomainShutdownFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="07d6a-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="07d6a-103">Notifica al generador de perfiles que se ha descargado de un proceso de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="07d6a-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07d6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07d6a-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07d6a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07d6a-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="07d6a-106">[in] Identifica el dominio en el que se almacenan los ensamblados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07d6a-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="07d6a-107">[in] Un HRESULT que indica si el dominio de aplicación se descargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="07d6a-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07d6a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07d6a-108">Remarks</span></span>  
 <span data-ttu-id="07d6a-109">El valor de `appDomainId` no es válido para una solicitud de información después de la [AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) devuelve del método.</span><span class="sxs-lookup"><span data-stu-id="07d6a-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="07d6a-110">Algunas partes de la descarga el dominio de aplicación podrían continuar después de la `AppDomainCreationFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="07d6a-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="07d6a-111">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="07d6a-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="07d6a-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga el dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="07d6a-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07d6a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07d6a-113">Requirements</span></span>  
 <span data-ttu-id="07d6a-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07d6a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07d6a-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07d6a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07d6a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07d6a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07d6a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07d6a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d6a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="07d6a-118">See also</span></span>
- [<span data-ttu-id="07d6a-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="07d6a-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
