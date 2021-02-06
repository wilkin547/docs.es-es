---
description: 'Más información sobre: ICorProfilerCallback:: AppDomainShutdownFinished ((método)'
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
ms.openlocfilehash: e08a4f7e03bfd18d9c6a2fdf56bfab8c68f9c379
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648261"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="d9b5b-103">ICorProfilerCallback::AppDomainShutdownFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="d9b5b-103">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>

<span data-ttu-id="d9b5b-104">Notifica al generador de perfiles que se ha descargado un dominio de aplicación de un proceso.</span><span class="sxs-lookup"><span data-stu-id="d9b5b-104">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9b5b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9b5b-105">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9b5b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9b5b-106">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="d9b5b-107">\[en] identifica el dominio en el que se almacenan los ensamblados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d9b5b-107">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="d9b5b-108">\[in] un valor HRESULT que indica si el dominio de aplicación se ha descargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d9b5b-108">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9b5b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d9b5b-109">Remarks</span></span>  

 <span data-ttu-id="d9b5b-110">El valor de `appDomainId` no es válido para una solicitud de información después de que el método [ICorProfilerCallback:: appdomainshutdownstarted (](icorprofilercallback-appdomainshutdownstarted-method.md) devuelva.</span><span class="sxs-lookup"><span data-stu-id="d9b5b-110">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="d9b5b-111">Algunas partes de la descarga del dominio de aplicación pueden continuar después de la `AppDomainCreationFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d9b5b-111">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="d9b5b-112">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="d9b5b-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="d9b5b-113">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la descarga del dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d9b5b-113">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9b5b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9b5b-114">Requirements</span></span>  

 <span data-ttu-id="d9b5b-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9b5b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9b5b-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9b5b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9b5b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9b5b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9b5b-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9b5b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b5b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9b5b-119">See also</span></span>

- [<span data-ttu-id="d9b5b-120">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9b5b-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
