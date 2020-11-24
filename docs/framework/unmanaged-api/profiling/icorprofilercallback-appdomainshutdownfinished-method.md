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
ms.openlocfilehash: ddb2d6eeb75a118a12f681b354f6feccd1231c64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685396"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="57ffb-102">ICorProfilerCallback::AppDomainShutdownFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="57ffb-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>

<span data-ttu-id="57ffb-103">Notifica al generador de perfiles que se ha descargado un dominio de aplicación de un proceso.</span><span class="sxs-lookup"><span data-stu-id="57ffb-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57ffb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57ffb-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57ffb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57ffb-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="57ffb-106">\[en] identifica el dominio en el que se almacenan los ensamblados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57ffb-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="57ffb-107">\[in] un valor HRESULT que indica si el dominio de aplicación se ha descargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="57ffb-107">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="57ffb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57ffb-108">Remarks</span></span>  

 <span data-ttu-id="57ffb-109">El valor de `appDomainId` no es válido para una solicitud de información después de que el método [ICorProfilerCallback:: appdomainshutdownstarted (](icorprofilercallback-appdomainshutdownstarted-method.md) devuelva.</span><span class="sxs-lookup"><span data-stu-id="57ffb-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="57ffb-110">Algunas partes de la descarga del dominio de aplicación pueden continuar después de la `AppDomainCreationFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="57ffb-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="57ffb-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="57ffb-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="57ffb-112">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la descarga del dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="57ffb-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57ffb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57ffb-113">Requirements</span></span>  

 <span data-ttu-id="57ffb-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57ffb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57ffb-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="57ffb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="57ffb-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57ffb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57ffb-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57ffb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57ffb-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57ffb-118">See also</span></span>

- [<span data-ttu-id="57ffb-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57ffb-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
