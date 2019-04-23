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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108659"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="ffedb-102">IHostPolicyManager::OnDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="ffedb-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="ffedb-103">Notifica al host que common language runtime (CLR) está a punto de realizar la acción predeterminada que se ha establecido mediante una llamada a la [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) método en respuesta a una anulación de subproceso o <xref:System.AppDomain> descargar.</span><span class="sxs-lookup"><span data-stu-id="ffedb-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffedb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ffedb-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffedb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ffedb-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="ffedb-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica el tipo de evento al que está respondiendo CLR.</span><span class="sxs-lookup"><span data-stu-id="ffedb-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="ffedb-107">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción que está realizando el CLR en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="ffedb-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffedb-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ffedb-108">Return Value</span></span>  
  
|<span data-ttu-id="ffedb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffedb-109">HRESULT</span></span>|<span data-ttu-id="ffedb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffedb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffedb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffedb-111">S_OK</span></span>|<span data-ttu-id="ffedb-112">`OnDefaultAction` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ffedb-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="ffedb-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ffedb-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ffedb-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada.</span><span class="sxs-lookup"><span data-stu-id="ffedb-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="ffedb-115">correctamente</span><span class="sxs-lookup"><span data-stu-id="ffedb-115">successfully</span></span>|  
|<span data-ttu-id="ffedb-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ffedb-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ffedb-117">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ffedb-117">The call timed out.</span></span>|  
|<span data-ttu-id="ffedb-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ffedb-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ffedb-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ffedb-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ffedb-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ffedb-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ffedb-121">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="ffedb-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ffedb-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffedb-122">E_FAIL</span></span>|<span data-ttu-id="ffedb-123">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="ffedb-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffedb-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ffedb-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ffedb-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ffedb-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffedb-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ffedb-126">Requirements</span></span>  
 <span data-ttu-id="ffedb-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffedb-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffedb-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ffedb-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffedb-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffedb-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffedb-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffedb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffedb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffedb-131">See also</span></span>

- [<span data-ttu-id="ffedb-132">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ffedb-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="ffedb-133">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ffedb-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="ffedb-134">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffedb-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="ffedb-135">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffedb-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
