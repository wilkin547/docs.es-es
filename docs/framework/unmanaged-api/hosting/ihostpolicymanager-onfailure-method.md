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
ms.openlocfilehash: 3bb65d747d7cdc81bd534108f6189eb1c94e3b15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128543"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="84d9b-102">IHostPolicyManager::OnFailure (Método)</span><span class="sxs-lookup"><span data-stu-id="84d9b-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="84d9b-103">Notifica al host que el Common Language Runtime (CLR) está a punto de realizar la acción especificada por una llamada al método [ICLRPolicyManager:: setactiononfailure (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) en respuesta a un error de asignación de recursos o de recorte.</span><span class="sxs-lookup"><span data-stu-id="84d9b-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d9b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84d9b-104">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84d9b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84d9b-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="84d9b-106">de Uno de los valores de [eclrfailure (](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) , que indica el tipo de error al que responde el CLR.</span><span class="sxs-lookup"><span data-stu-id="84d9b-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="84d9b-107">de Uno de los valores de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , que indica la acción que el CLR está llevando a cabo en respuesta a `failure`.</span><span class="sxs-lookup"><span data-stu-id="84d9b-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84d9b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="84d9b-108">Return Value</span></span>  
  
|<span data-ttu-id="84d9b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84d9b-109">HRESULT</span></span>|<span data-ttu-id="84d9b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="84d9b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84d9b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="84d9b-111">S_OK</span></span>|<span data-ttu-id="84d9b-112">`OnFailure` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="84d9b-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="84d9b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84d9b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84d9b-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="84d9b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84d9b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84d9b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84d9b-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="84d9b-116">The call timed out.</span></span>|  
|<span data-ttu-id="84d9b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84d9b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84d9b-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="84d9b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84d9b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84d9b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84d9b-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="84d9b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84d9b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84d9b-121">E_FAIL</span></span>|<span data-ttu-id="84d9b-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="84d9b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84d9b-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="84d9b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84d9b-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="84d9b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84d9b-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84d9b-125">Requirements</span></span>  
 <span data-ttu-id="84d9b-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84d9b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84d9b-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84d9b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84d9b-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84d9b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84d9b-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84d9b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d9b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="84d9b-130">See also</span></span>

- [<span data-ttu-id="84d9b-131">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="84d9b-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="84d9b-132">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="84d9b-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="84d9b-133">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84d9b-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="84d9b-134">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84d9b-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
