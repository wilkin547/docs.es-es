---
description: 'Más información acerca de: ICLRRuntimeHost:: SetHostControl (método)'
title: ICLRRuntimeHost::SetHostControl (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: e51c61666716badc7214f9a74ad11aa646f2316c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785119"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="df634-103">ICLRRuntimeHost::SetHostControl (Método)</span><span class="sxs-lookup"><span data-stu-id="df634-103">ICLRRuntimeHost::SetHostControl Method</span></span>

<span data-ttu-id="df634-104">Establece el puntero de interfaz que puede usar el Common Language Runtime (CLR) para obtener la implementación del host de la [interfaz IHostControl](ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="df634-104">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df634-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df634-105">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df634-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df634-106">Parameters</span></span>  

 `pHostControl`  
 <span data-ttu-id="df634-107">de Puntero de interfaz a la implementación del host de la [interfaz IHostControl](ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="df634-107">[in] An interface pointer to the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df634-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df634-108">Return Value</span></span>  
  
|<span data-ttu-id="df634-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df634-109">HRESULT</span></span>|<span data-ttu-id="df634-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="df634-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df634-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="df634-111">S_OK</span></span>|<span data-ttu-id="df634-112">`SetHostControl` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="df634-112">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="df634-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df634-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df634-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="df634-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df634-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df634-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df634-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="df634-116">The call timed out.</span></span>|  
|<span data-ttu-id="df634-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df634-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df634-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="df634-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df634-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df634-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df634-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="df634-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df634-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df634-121">E_FAIL</span></span>|<span data-ttu-id="df634-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="df634-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df634-123">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="df634-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df634-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="df634-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="df634-125">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="df634-125">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="df634-126">CLR ya se ha inicializado.</span><span class="sxs-lookup"><span data-stu-id="df634-126">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df634-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="df634-127">Remarks</span></span>  

 <span data-ttu-id="df634-128">Debe llamar a `SetHostControl` antes de que se inicialice el CLR, es decir, antes de llamar al [método de inicio](iclrruntimehost-start-method.md) o usar cualquiera de las [interfaces de metadatos](../metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="df634-128">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="df634-129">Se recomienda llamar a `SetHostControl` inmediatamente después de llamar a la función [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md) o a la [función CorBindToRuntimeEx](corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="df634-129">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df634-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df634-130">Requirements</span></span>  

 <span data-ttu-id="df634-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df634-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df634-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="df634-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df634-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df634-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df634-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df634-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df634-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="df634-135">See also</span></span>

- [<span data-ttu-id="df634-136">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df634-136">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="df634-137">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df634-137">IHostControl Interface</span></span>](ihostcontrol-interface.md)
