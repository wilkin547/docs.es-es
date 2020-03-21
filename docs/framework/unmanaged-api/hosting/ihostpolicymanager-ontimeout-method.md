---
title: IHostPolicyManager::OnTimeout (Método)
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
ms.openlocfilehash: d5b5fa5198ae2c0bba30ae0f8d6d3834f2891672
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178005"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="214b5-102">IHostPolicyManager::OnTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="214b5-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="214b5-103">Notifica al host que Common Language Runtime (CLR) está a punto de realizar la acción especificada por una llamada al método [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="214b5-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="214b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="214b5-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="214b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="214b5-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="214b5-106">[en] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica el tipo de operación que adelantó.</span><span class="sxs-lookup"><span data-stu-id="214b5-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="214b5-107">[en] Uno de los [ePolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción que el CLR está realizando en respuesta al tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="214b5-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="214b5-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="214b5-108">Return Value</span></span>  
  
|<span data-ttu-id="214b5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="214b5-109">HRESULT</span></span>|<span data-ttu-id="214b5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="214b5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="214b5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="214b5-111">S_OK</span></span>|<span data-ttu-id="214b5-112">`OnTimeout`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="214b5-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="214b5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="214b5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="214b5-114">El CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="214b5-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="214b5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="214b5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="214b5-116">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="214b5-116">The call timed out.</span></span>|  
|<span data-ttu-id="214b5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="214b5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="214b5-118">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="214b5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="214b5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="214b5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="214b5-120">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="214b5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="214b5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="214b5-121">E_FAIL</span></span>|<span data-ttu-id="214b5-122">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="214b5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="214b5-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="214b5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="214b5-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="214b5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="214b5-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="214b5-125">Requirements</span></span>  
 <span data-ttu-id="214b5-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="214b5-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="214b5-127">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="214b5-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="214b5-128">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="214b5-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="214b5-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="214b5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214b5-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="214b5-130">See also</span></span>

- [<span data-ttu-id="214b5-131">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="214b5-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="214b5-132">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="214b5-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="214b5-133">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="214b5-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="214b5-134">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="214b5-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
