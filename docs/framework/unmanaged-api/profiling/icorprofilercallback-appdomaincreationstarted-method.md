---
description: 'Más información sobre: ICorProfilerCallback:: Appdomaincreationstarted ((método)'
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
ms.openlocfilehash: b783bb652bed3b600c1e4524810620bab68f5f7a
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760709"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="94323-103">ICorProfilerCallback::AppDomainCreationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="94323-103">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>

<span data-ttu-id="94323-104">Notifica al generador de perfiles que se está creando un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="94323-104">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94323-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94323-105">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94323-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94323-106">Parameters</span></span>

<span data-ttu-id="94323-107">`appDomainId` de Identifica el dominio que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="94323-107">`appDomainId` [in] Identifies the domain which is being created.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="94323-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="94323-108">Remarks</span></span>  

 <span data-ttu-id="94323-109">El identificador no es válido para ninguna solicitud de información hasta que se llama al método [ICorProfilerCallback:: AppDomainCreationFinished (](icorprofilercallback-appdomaincreationfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="94323-109">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94323-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94323-110">Requirements</span></span>  

 <span data-ttu-id="94323-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94323-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94323-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="94323-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="94323-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94323-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94323-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94323-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94323-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94323-115">See also</span></span>

- [<span data-ttu-id="94323-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94323-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
