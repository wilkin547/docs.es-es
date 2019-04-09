---
title: IHostPolicyManager::OnDefaultAction (Método)
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45167a2b358b9a7a39390c07f552aa3f3dabce4f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108659"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="d00cb-102">IHostPolicyManager::OnDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="d00cb-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="d00cb-103">Notifica al host que common language runtime (CLR) está a punto de realizar la acción predeterminada que se ha establecido mediante una llamada a la [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) método en respuesta a una anulación de subproceso o <xref:System.AppDomain> descargar.</span><span class="sxs-lookup"><span data-stu-id="d00cb-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d00cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d00cb-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d00cb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d00cb-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="d00cb-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica el tipo de evento al que está respondiendo CLR.</span><span class="sxs-lookup"><span data-stu-id="d00cb-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="d00cb-107">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción que está realizando el CLR en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="d00cb-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d00cb-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d00cb-108">Return Value</span></span>  
  
|<span data-ttu-id="d00cb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d00cb-109">HRESULT</span></span>|<span data-ttu-id="d00cb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d00cb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d00cb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d00cb-111">S_OK</span></span>|`OnDefaultAction` <span data-ttu-id="d00cb-112">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d00cb-112">returned successfully.</span></span>|  
|<span data-ttu-id="d00cb-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d00cb-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d00cb-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada.</span><span class="sxs-lookup"><span data-stu-id="d00cb-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="d00cb-115">correctamente</span><span class="sxs-lookup"><span data-stu-id="d00cb-115">successfully</span></span>|  
|<span data-ttu-id="d00cb-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d00cb-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d00cb-117">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d00cb-117">The call timed out.</span></span>|  
|<span data-ttu-id="d00cb-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d00cb-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d00cb-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d00cb-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d00cb-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d00cb-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d00cb-121">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="d00cb-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d00cb-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d00cb-122">E_FAIL</span></span>|<span data-ttu-id="d00cb-123">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="d00cb-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d00cb-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d00cb-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d00cb-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d00cb-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d00cb-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d00cb-126">Requirements</span></span>  
 <span data-ttu-id="d00cb-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d00cb-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d00cb-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d00cb-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d00cb-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d00cb-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d00cb-130">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d00cb-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d00cb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d00cb-131">See also</span></span>

- [<span data-ttu-id="d00cb-132">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d00cb-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="d00cb-133">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d00cb-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="d00cb-134">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d00cb-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="d00cb-135">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d00cb-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
