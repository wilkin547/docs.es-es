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
ms.openlocfilehash: e8a14dd6a6d196cea9caa6be669b2b75a167eca8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141115"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="054cd-102">IHostPolicyManager::OnTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="054cd-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="054cd-103">Notifica al host que el Common Language Runtime (CLR) está a punto de realizar la acción especificada por una llamada al método [ICLRPolicyManager:: SetActionOnTimeout (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="054cd-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="054cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="054cd-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="054cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="054cd-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="054cd-106">de Uno de los valores de [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , que indica el tipo de operación que agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="054cd-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="054cd-107">de Uno de los valores de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , que indica la acción que el CLR está llevando a cabo en respuesta al tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="054cd-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="054cd-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="054cd-108">Return Value</span></span>  
  
|<span data-ttu-id="054cd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="054cd-109">HRESULT</span></span>|<span data-ttu-id="054cd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="054cd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="054cd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="054cd-111">S_OK</span></span>|<span data-ttu-id="054cd-112">`OnTimeout` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="054cd-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="054cd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="054cd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="054cd-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="054cd-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="054cd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="054cd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="054cd-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="054cd-116">The call timed out.</span></span>|  
|<span data-ttu-id="054cd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="054cd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="054cd-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="054cd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="054cd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="054cd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="054cd-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="054cd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="054cd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="054cd-121">E_FAIL</span></span>|<span data-ttu-id="054cd-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="054cd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="054cd-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="054cd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="054cd-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="054cd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="054cd-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="054cd-125">Requirements</span></span>  
 <span data-ttu-id="054cd-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="054cd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="054cd-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="054cd-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="054cd-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="054cd-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="054cd-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="054cd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="054cd-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="054cd-130">See also</span></span>

- [<span data-ttu-id="054cd-131">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="054cd-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="054cd-132">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="054cd-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="054cd-133">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054cd-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="054cd-134">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054cd-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
