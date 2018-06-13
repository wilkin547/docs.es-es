---
title: ICorProfilerCallback::AppDomainCreationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b0017cff43f7a1b1bdd90806f50abb374a96dadf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450429"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="404a0-102">ICorProfilerCallback::AppDomainCreationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="404a0-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="404a0-103">Notifica al generador de perfiles que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="404a0-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="404a0-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="404a0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="404a0-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="404a0-106">[in] Identifica el dominio que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="404a0-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="404a0-107">[in] Un valor HRESULT que indica si la creación del dominio de aplicación se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="404a0-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="404a0-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="404a0-108">Remarks</span></span>  
 <span data-ttu-id="404a0-109">El identificador de aplicación no es válido para cualquier solicitud de información hasta que el `AppDomainCreationFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="404a0-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="404a0-110">Algunas partes de la carga del dominio de aplicación podrían continuar después de la `AppDomainCreationFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="404a0-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="404a0-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="404a0-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="404a0-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la creación del dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="404a0-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="404a0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="404a0-113">Requirements</span></span>  
 <span data-ttu-id="404a0-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="404a0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="404a0-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="404a0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="404a0-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="404a0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="404a0-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="404a0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404a0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="404a0-118">See Also</span></span>  
 [<span data-ttu-id="404a0-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="404a0-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
