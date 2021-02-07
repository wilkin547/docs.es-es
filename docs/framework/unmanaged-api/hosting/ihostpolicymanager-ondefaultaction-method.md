---
description: 'Más información sobre: IHostPolicyManager:: Ondefaultaction ((método)'
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
ms.openlocfilehash: ea474734f7bc0a5210c5aecf605452909b261a87
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671931"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="22c9e-103">IHostPolicyManager::OnDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="22c9e-103">IHostPolicyManager::OnDefaultAction Method</span></span>

<span data-ttu-id="22c9e-104">Notifica al host que el Common Language Runtime (CLR) está a punto de realizar la acción predeterminada establecida por una llamada al método [ICLRPolicyManager:: SetDefaultAction (](iclrpolicymanager-setdefaultaction-method.md) en respuesta a una anulación o descarga del subproceso <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="22c9e-104">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c9e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22c9e-105">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22c9e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22c9e-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="22c9e-107">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica el tipo de evento al que responde el CLR.</span><span class="sxs-lookup"><span data-stu-id="22c9e-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="22c9e-108">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción que el CLR está llevando a cabo en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="22c9e-108">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22c9e-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="22c9e-109">Return Value</span></span>  
  
|<span data-ttu-id="22c9e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22c9e-110">HRESULT</span></span>|<span data-ttu-id="22c9e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="22c9e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22c9e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="22c9e-112">S_OK</span></span>|<span data-ttu-id="22c9e-113">`OnDefaultAction` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="22c9e-113">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="22c9e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22c9e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22c9e-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada.</span><span class="sxs-lookup"><span data-stu-id="22c9e-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="22c9e-116">successfully</span><span class="sxs-lookup"><span data-stu-id="22c9e-116">successfully</span></span>|  
|<span data-ttu-id="22c9e-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22c9e-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22c9e-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="22c9e-118">The call timed out.</span></span>|  
|<span data-ttu-id="22c9e-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22c9e-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22c9e-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="22c9e-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22c9e-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22c9e-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22c9e-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="22c9e-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22c9e-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22c9e-123">E_FAIL</span></span>|<span data-ttu-id="22c9e-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="22c9e-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22c9e-125">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="22c9e-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22c9e-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="22c9e-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22c9e-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22c9e-127">Requirements</span></span>  

 <span data-ttu-id="22c9e-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22c9e-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22c9e-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="22c9e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22c9e-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22c9e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22c9e-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22c9e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c9e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="22c9e-132">See also</span></span>

- [<span data-ttu-id="22c9e-133">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="22c9e-133">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="22c9e-134">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="22c9e-134">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="22c9e-135">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22c9e-135">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="22c9e-136">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22c9e-136">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
