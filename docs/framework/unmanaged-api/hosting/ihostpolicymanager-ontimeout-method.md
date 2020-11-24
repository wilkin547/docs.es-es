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
ms.openlocfilehash: e3f2dc7ff9beaf417184f3d09db76e611982118a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690673"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="6aaf1-102">IHostPolicyManager::OnTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="6aaf1-102">IHostPolicyManager::OnTimeout Method</span></span>

<span data-ttu-id="6aaf1-103">Notifica al host que el Common Language Runtime (CLR) está a punto de realizar la acción especificada por una llamada al método [ICLRPolicyManager:: SetActionOnTimeout (](iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aaf1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6aaf1-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aaf1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6aaf1-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="6aaf1-106">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica el tipo de operación que agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="6aaf1-107">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción que el CLR está llevando a cabo en respuesta al tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6aaf1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6aaf1-108">Return Value</span></span>  
  
|<span data-ttu-id="6aaf1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6aaf1-109">HRESULT</span></span>|<span data-ttu-id="6aaf1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="6aaf1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6aaf1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6aaf1-111">S_OK</span></span>|<span data-ttu-id="6aaf1-112">`OnTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="6aaf1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6aaf1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6aaf1-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6aaf1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6aaf1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6aaf1-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-116">The call timed out.</span></span>|  
|<span data-ttu-id="6aaf1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6aaf1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6aaf1-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6aaf1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6aaf1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6aaf1-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6aaf1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6aaf1-121">E_FAIL</span></span>|<span data-ttu-id="6aaf1-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6aaf1-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6aaf1-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6aaf1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6aaf1-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6aaf1-125">Requirements</span></span>  

 <span data-ttu-id="6aaf1-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aaf1-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aaf1-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6aaf1-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6aaf1-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6aaf1-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6aaf1-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aaf1-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aaf1-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6aaf1-130">See also</span></span>

- [<span data-ttu-id="6aaf1-131">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6aaf1-131">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="6aaf1-132">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6aaf1-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="6aaf1-133">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6aaf1-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="6aaf1-134">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6aaf1-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
