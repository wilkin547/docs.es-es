---
description: 'Más información sobre: ICorProfilerCallback:: AppDomainCreationFinished ((método)'
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
ms.openlocfilehash: 6995c6cda168b5be5815e6f7b2b4d900ae0d4d67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648368"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="df408-103">ICorProfilerCallback::AppDomainCreationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="df408-103">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>

<span data-ttu-id="df408-104">Notifica al generador de perfiles que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="df408-104">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df408-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df408-105">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="df408-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df408-106">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="df408-107">\[en] identifica el dominio que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="df408-107">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="df408-108">\[in] un valor HRESULT que indica si la creación del dominio de aplicación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="df408-108">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="df408-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="df408-109">Remarks</span></span>  

 <span data-ttu-id="df408-110">El ID. de aplicación no es válido para ninguna solicitud de información hasta que `AppDomainCreationFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="df408-110">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="df408-111">Algunas partes de la carga del dominio de aplicación pueden continuar después de la `AppDomainCreationFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="df408-111">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="df408-112">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="df408-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="df408-113">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la creación del dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="df408-113">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df408-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df408-114">Requirements</span></span>  

 <span data-ttu-id="df408-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df408-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df408-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="df408-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="df408-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df408-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df408-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df408-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df408-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="df408-119">See also</span></span>

- [<span data-ttu-id="df408-120">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df408-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
