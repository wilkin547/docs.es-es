---
title: IHostPolicyManager::OnFailure (Método)
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87b4d4a9606723e5cf55fac19469809e1014b7c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439692"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="4cbc3-102">IHostPolicyManager::OnFailure (Método)</span><span class="sxs-lookup"><span data-stu-id="4cbc3-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="4cbc3-103">Notifica al host que common language runtime (CLR) está a punto de realizar la acción especificada por una llamada a la [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) método en respuesta a una asignación de recursos para el error de recuperación.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cbc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cbc3-104">Syntax</span></span>  
  
```  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cbc3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4cbc3-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="4cbc3-106">[in] Uno de los [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valores, que indica el tipo de error a la que está respondiendo CLR.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="4cbc3-107">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción CLR está tardando en respuesta a `failure`.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cbc3-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4cbc3-108">Return Value</span></span>  
  
|<span data-ttu-id="4cbc3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cbc3-109">HRESULT</span></span>|<span data-ttu-id="4cbc3-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4cbc3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cbc3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cbc3-111">S_OK</span></span>|<span data-ttu-id="4cbc3-112">`OnFailure` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="4cbc3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4cbc3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4cbc3-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4cbc3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4cbc3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4cbc3-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-116">The call timed out.</span></span>|  
|<span data-ttu-id="4cbc3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4cbc3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4cbc3-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4cbc3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4cbc3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4cbc3-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4cbc3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cbc3-121">E_FAIL</span></span>|<span data-ttu-id="4cbc3-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cbc3-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4cbc3-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4cbc3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cbc3-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4cbc3-125">Requirements</span></span>  
 <span data-ttu-id="4cbc3-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cbc3-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cbc3-127">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4cbc3-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cbc3-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cbc3-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cbc3-129">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cbc3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cbc3-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cbc3-130">See Also</span></span>  
 [<span data-ttu-id="4cbc3-131">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="4cbc3-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="4cbc3-132">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="4cbc3-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="4cbc3-133">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cbc3-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="4cbc3-134">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cbc3-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
