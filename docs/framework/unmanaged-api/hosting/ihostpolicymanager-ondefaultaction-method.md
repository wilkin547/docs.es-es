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
ms.openlocfilehash: cdf0a720ac440d156b5b8bdc8dc2c78d3bb5ba86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128563"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="59e71-102">IHostPolicyManager::OnDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="59e71-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="59e71-103">Notifica al host que el Common Language Runtime (CLR) está a punto de realizar la acción predeterminada establecida por una llamada al método [ICLRPolicyManager:: SetDefaultAction (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) en respuesta a una anulación del subproceso o <xref:System.AppDomain> descarga.</span><span class="sxs-lookup"><span data-stu-id="59e71-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59e71-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59e71-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59e71-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="59e71-106">de Uno de los valores de [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , que indica el tipo de evento al que responde el CLR.</span><span class="sxs-lookup"><span data-stu-id="59e71-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="59e71-107">de Uno de los valores de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , que indica la acción que el CLR está llevando a cabo en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="59e71-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59e71-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="59e71-108">Return Value</span></span>  
  
|<span data-ttu-id="59e71-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59e71-109">HRESULT</span></span>|<span data-ttu-id="59e71-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="59e71-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59e71-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="59e71-111">S_OK</span></span>|<span data-ttu-id="59e71-112">`OnDefaultAction` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="59e71-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="59e71-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="59e71-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="59e71-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada.</span><span class="sxs-lookup"><span data-stu-id="59e71-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="59e71-115">successfully</span><span class="sxs-lookup"><span data-stu-id="59e71-115">successfully</span></span>|  
|<span data-ttu-id="59e71-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="59e71-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="59e71-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59e71-117">The call timed out.</span></span>|  
|<span data-ttu-id="59e71-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="59e71-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="59e71-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="59e71-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="59e71-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="59e71-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="59e71-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="59e71-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="59e71-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="59e71-122">E_FAIL</span></span>|<span data-ttu-id="59e71-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="59e71-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="59e71-124">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="59e71-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="59e71-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="59e71-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59e71-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59e71-126">Requirements</span></span>  
 <span data-ttu-id="59e71-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59e71-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59e71-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="59e71-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59e71-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="59e71-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59e71-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59e71-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59e71-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="59e71-131">See also</span></span>

- [<span data-ttu-id="59e71-132">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="59e71-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="59e71-133">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="59e71-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="59e71-134">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="59e71-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="59e71-135">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="59e71-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
