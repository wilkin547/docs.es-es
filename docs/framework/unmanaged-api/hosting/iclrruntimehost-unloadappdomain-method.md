---
title: ICLRRuntimeHost::UnloadAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 490af9ca67b538e0093115a6b371b65d9788772f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222970"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="d64c4-102">ICLRRuntimeHost::UnloadAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="d64c4-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="d64c4-103">Descarga de los recursos administrados <xref:System.AppDomain> que se corresponde con el identificador numérico especificado.</span><span class="sxs-lookup"><span data-stu-id="d64c4-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d64c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d64c4-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d64c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d64c4-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="d64c4-106">[in] El identificador numérico del dominio de aplicación para descargar.</span><span class="sxs-lookup"><span data-stu-id="d64c4-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="d64c4-107">[in] `true` para indicar que common language runtime (CLR) debe esperar hasta que ha terminado de ejecutarse el subproceso actual de la aplicación antes de intentar descargar el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d64c4-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d64c4-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d64c4-108">Return Value</span></span>  
  
|<span data-ttu-id="d64c4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d64c4-109">HRESULT</span></span>|<span data-ttu-id="d64c4-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d64c4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d64c4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d64c4-111">S_OK</span></span>|<span data-ttu-id="d64c4-112">`UnloadAppDomain` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d64c4-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="d64c4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d64c4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d64c4-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d64c4-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d64c4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d64c4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d64c4-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d64c4-116">The call timed out.</span></span>|  
|<span data-ttu-id="d64c4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d64c4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d64c4-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d64c4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d64c4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d64c4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d64c4-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="d64c4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d64c4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d64c4-121">E_FAIL</span></span>|<span data-ttu-id="d64c4-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="d64c4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d64c4-123">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d64c4-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d64c4-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d64c4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d64c4-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d64c4-125">Remarks</span></span>  
 <span data-ttu-id="d64c4-126">Puede obtener el identificador numérico del dominio de aplicación en el que se está ejecutando el subproceso actual mediante una llamada a [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="d64c4-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="d64c4-127">Este identificador se corresponde con el <xref:System.AppDomain.Id%2A> propiedad de los recursos administrados <xref:System.AppDomain> tipo.</span><span class="sxs-lookup"><span data-stu-id="d64c4-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d64c4-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d64c4-128">Requirements</span></span>  
 <span data-ttu-id="d64c4-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d64c4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d64c4-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d64c4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d64c4-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d64c4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d64c4-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d64c4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d64c4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="d64c4-133">See also</span></span>

- [<span data-ttu-id="d64c4-134">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d64c4-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
