---
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
ms.openlocfilehash: d280b008b34befce04159d02dfbb3de37b262c3c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866670"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="14771-102">ICorProfilerCallback::AppDomainShutdownStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="14771-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="14771-103">Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.</span><span class="sxs-lookup"><span data-stu-id="14771-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14771-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14771-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14771-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="14771-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="14771-106">\[en] identifica el dominio en el que se almacenan los ensamblados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14771-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="14771-107">Notas</span><span class="sxs-lookup"><span data-stu-id="14771-107">Remarks</span></span>  
 <span data-ttu-id="14771-108">El valor de `appDomainId` no es válido para ninguna solicitud de información después de que se devuelva el método `AppDomainShutdownStarted`; esta es la última oportunidad del generador de perfiles para obtener información acerca de este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="14771-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14771-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="14771-109">Requirements</span></span>  
 <span data-ttu-id="14771-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14771-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14771-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14771-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14771-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14771-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14771-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14771-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14771-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="14771-114">See also</span></span>

- [<span data-ttu-id="14771-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14771-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
