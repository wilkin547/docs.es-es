---
description: 'Más información sobre: ICorProfilerCallback:: Appdomainshutdownstarted ((método)'
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
ms.openlocfilehash: 16545142a512ca1c5f4167f61b81ea949e3d14e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648121"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="93030-103">ICorProfilerCallback::AppDomainShutdownStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="93030-103">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>

<span data-ttu-id="93030-104">Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.</span><span class="sxs-lookup"><span data-stu-id="93030-104">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93030-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93030-105">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93030-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93030-106">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="93030-107">\[en] identifica el dominio en el que se almacenan los ensamblados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93030-107">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="93030-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="93030-108">Remarks</span></span>  

 <span data-ttu-id="93030-109">El valor de `appDomainId` no es válido para ninguna solicitud de información después de que se `AppDomainShutdownStarted` devuelva el método; esta es la última oportunidad del generador de perfiles para obtener información acerca de este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="93030-109">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93030-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93030-110">Requirements</span></span>  

 <span data-ttu-id="93030-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93030-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93030-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="93030-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="93030-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93030-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93030-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93030-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93030-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="93030-115">See also</span></span>

- [<span data-ttu-id="93030-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="93030-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
