---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6817a2154e876dfa83540e3496f42acdcdb25a83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771824"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="692f0-102">ICLRRuntimeHost::SetHostControl (Método)</span><span class="sxs-lookup"><span data-stu-id="692f0-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="692f0-103">Establece el puntero de interfaz que common language runtime (CLR) puede usar para obtener la implementación del host de [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="692f0-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="692f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="692f0-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="692f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="692f0-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="692f0-106">[in] Un puntero de interfaz a la implementación del host de [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="692f0-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="692f0-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="692f0-107">Return Value</span></span>  
  
|<span data-ttu-id="692f0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="692f0-108">HRESULT</span></span>|<span data-ttu-id="692f0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="692f0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="692f0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="692f0-110">S_OK</span></span>|<span data-ttu-id="692f0-111">`SetHostControl` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="692f0-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="692f0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="692f0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="692f0-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="692f0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="692f0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="692f0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="692f0-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="692f0-115">The call timed out.</span></span>|  
|<span data-ttu-id="692f0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="692f0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="692f0-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="692f0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="692f0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="692f0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="692f0-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="692f0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="692f0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="692f0-120">E_FAIL</span></span>|<span data-ttu-id="692f0-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="692f0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="692f0-122">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="692f0-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="692f0-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="692f0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="692f0-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="692f0-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="692f0-125">Ya se ha inicializado el CLR.</span><span class="sxs-lookup"><span data-stu-id="692f0-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="692f0-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="692f0-126">Remarks</span></span>  
 <span data-ttu-id="692f0-127">Debe llamar a `SetHostControl` antes de que se inicializa el CLR, es decir, antes de llamar a [método Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) o usar cualquiera de los [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="692f0-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="692f0-128">Se recomienda que llame a `SetHostControl` inmediatamente después de llamar a [CorBindToCurrentRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) o [CorBindToRuntimeEx (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="692f0-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="692f0-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="692f0-129">Requirements</span></span>  
 <span data-ttu-id="692f0-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="692f0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="692f0-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="692f0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="692f0-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="692f0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="692f0-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="692f0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="692f0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="692f0-134">See also</span></span>

- [<span data-ttu-id="692f0-135">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="692f0-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="692f0-136">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="692f0-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
