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
ms.openlocfilehash: 00ebbe35f6f4446caeee5ebcd56b853d6e6dc80c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648264"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="90c94-103">ICorProfilerCallback::AppDomainCreationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="90c94-103">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>

<span data-ttu-id="90c94-104">Notifica al generador de perfiles que se está creando un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="90c94-104">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c94-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90c94-105">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90c94-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90c94-106">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="90c94-107">\[en] identifica el dominio que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="90c94-107">\[in] Identifies the domain which is being created.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="90c94-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="90c94-108">Remarks</span></span>  

 <span data-ttu-id="90c94-109">El identificador no es válido para ninguna solicitud de información hasta que se llama al método [ICorProfilerCallback:: AppDomainCreationFinished (](icorprofilercallback-appdomaincreationfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="90c94-109">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c94-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90c94-110">Requirements</span></span>  

 <span data-ttu-id="90c94-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90c94-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90c94-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90c94-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="90c94-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90c94-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90c94-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90c94-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c94-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="90c94-115">See also</span></span>

- [<span data-ttu-id="90c94-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="90c94-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
