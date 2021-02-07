---
description: 'Más información sobre: IHostPolicyManager:: altimeout (método)'
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
ms.openlocfilehash: 3a4b1dcf632a0a67c541cacf7c872b3f994e8a07
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671833"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="c61ed-103">IHostPolicyManager::OnTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="c61ed-103">IHostPolicyManager::OnTimeout Method</span></span>

<span data-ttu-id="c61ed-104">Notifica al host que el Common Language Runtime (CLR) está a punto de realizar la acción especificada por una llamada al método [ICLRPolicyManager:: SetActionOnTimeout (](iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c61ed-104">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61ed-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c61ed-105">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c61ed-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c61ed-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="c61ed-107">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica el tipo de operación que agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c61ed-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="c61ed-108">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción que el CLR está llevando a cabo en respuesta al tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c61ed-108">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c61ed-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c61ed-109">Return Value</span></span>  
  
|<span data-ttu-id="c61ed-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c61ed-110">HRESULT</span></span>|<span data-ttu-id="c61ed-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c61ed-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c61ed-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c61ed-112">S_OK</span></span>|<span data-ttu-id="c61ed-113">`OnTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c61ed-113">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="c61ed-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c61ed-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c61ed-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c61ed-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c61ed-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c61ed-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c61ed-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c61ed-117">The call timed out.</span></span>|  
|<span data-ttu-id="c61ed-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c61ed-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c61ed-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c61ed-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c61ed-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c61ed-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c61ed-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c61ed-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c61ed-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c61ed-122">E_FAIL</span></span>|<span data-ttu-id="c61ed-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c61ed-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c61ed-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c61ed-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c61ed-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c61ed-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c61ed-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c61ed-126">Requirements</span></span>  

 <span data-ttu-id="c61ed-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c61ed-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c61ed-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c61ed-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c61ed-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c61ed-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c61ed-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c61ed-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c61ed-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c61ed-131">See also</span></span>

- [<span data-ttu-id="c61ed-132">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c61ed-132">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="c61ed-133">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c61ed-133">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="c61ed-134">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c61ed-134">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="c61ed-135">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c61ed-135">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
