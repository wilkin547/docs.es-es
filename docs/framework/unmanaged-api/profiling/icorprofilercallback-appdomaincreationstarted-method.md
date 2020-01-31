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
ms.openlocfilehash: 35dbed6a723f5319dc506a44198456e3794464fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790230"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="ed5ad-102">ICorProfilerCallback::AppDomainCreationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="ed5ad-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="ed5ad-103">Notifica al generador de perfiles que se está creando un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed5ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed5ad-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed5ad-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ed5ad-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="ed5ad-106">\[en] identifica el dominio que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ed5ad-106">\[in] Identifies the domain which is being created.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ed5ad-107">Notas</span><span class="sxs-lookup"><span data-stu-id="ed5ad-107">Remarks</span></span>  
 <span data-ttu-id="ed5ad-108">El identificador no es válido para ninguna solicitud de información hasta que se llama al método [ICorProfilerCallback:: AppDomainCreationFinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ed5ad-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed5ad-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ed5ad-109">Requirements</span></span>  
 <span data-ttu-id="ed5ad-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed5ad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed5ad-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed5ad-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed5ad-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed5ad-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed5ad-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed5ad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5ad-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed5ad-114">See also</span></span>

- [<span data-ttu-id="ed5ad-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed5ad-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
