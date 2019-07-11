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
ms.openlocfilehash: 17f7c985b27adbbb2a5c7ddc2bb62fc93a099a45
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763131"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="60827-102">ICorProfilerCallback::AppDomainCreationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="60827-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="60827-103">Notifica al generador de perfiles que se está creando un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="60827-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60827-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60827-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60827-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60827-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="60827-106">[in] Identifica el dominio que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="60827-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60827-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60827-107">Remarks</span></span>  
 <span data-ttu-id="60827-108">El identificador no es válido para cualquier solicitud de información hasta la [AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="60827-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60827-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60827-109">Requirements</span></span>  
 <span data-ttu-id="60827-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60827-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60827-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60827-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60827-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60827-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60827-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60827-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60827-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="60827-114">See also</span></span>

- [<span data-ttu-id="60827-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60827-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
