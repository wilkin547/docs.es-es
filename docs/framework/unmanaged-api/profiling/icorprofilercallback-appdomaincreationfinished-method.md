---
title: "ICorProfilerCallback::AppDomainCreationFinished (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainCreationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f779e5a7b0b38558593e84c26b33784383765ca0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="a413e-102">ICorProfilerCallback::AppDomainCreationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="a413e-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="a413e-103">Notifica al generador de perfiles que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a413e-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a413e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a413e-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="a413e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a413e-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="a413e-106">[in] Identifica el dominio que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="a413e-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a413e-107">[in] Un valor HRESULT que indica si la creación del dominio de aplicación se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a413e-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a413e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a413e-108">Remarks</span></span>  
 <span data-ttu-id="a413e-109">El identificador de aplicación no es válido para cualquier solicitud de información hasta que el `AppDomainCreationFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="a413e-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="a413e-110">Algunas partes de la carga del dominio de aplicación podrían continuar después de la `AppDomainCreationFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a413e-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="a413e-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="a413e-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a413e-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la creación del dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a413e-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a413e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a413e-113">Requirements</span></span>  
 <span data-ttu-id="a413e-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a413e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a413e-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a413e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a413e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a413e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a413e-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a413e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a413e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a413e-118">See Also</span></span>  
 [<span data-ttu-id="a413e-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a413e-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
