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
ms.openlocfilehash: 8d987614c1a5a2c90ccb3faa11c605767ae5cfda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178020"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="0eee4-102">IHostPolicyManager::OnDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="0eee4-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="0eee4-103">Notifica al host que Common Language Runtime (CLR) está a punto de realizar la acción predeterminada establecida mediante una llamada al <xref:System.AppDomain> método [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) en respuesta a una anulación o descarga de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="0eee4-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eee4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eee4-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eee4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0eee4-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="0eee4-106">[en] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica el tipo de evento al que responde CLR.</span><span class="sxs-lookup"><span data-stu-id="0eee4-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="0eee4-107">[en] Uno de los [ePolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción que el CLR está realizando en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="0eee4-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0eee4-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0eee4-108">Return Value</span></span>  
  
|<span data-ttu-id="0eee4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0eee4-109">HRESULT</span></span>|<span data-ttu-id="0eee4-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eee4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0eee4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0eee4-111">S_OK</span></span>|<span data-ttu-id="0eee4-112">`OnDefaultAction`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="0eee4-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="0eee4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0eee4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0eee4-114">El CLR no se ha cargado en un proceso o el CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada.</span><span class="sxs-lookup"><span data-stu-id="0eee4-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="0eee4-115">Exitosamente</span><span class="sxs-lookup"><span data-stu-id="0eee4-115">successfully</span></span>|  
|<span data-ttu-id="0eee4-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0eee4-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0eee4-117">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="0eee4-117">The call timed out.</span></span>|  
|<span data-ttu-id="0eee4-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0eee4-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0eee4-119">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="0eee4-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0eee4-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0eee4-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0eee4-121">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="0eee4-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0eee4-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0eee4-122">E_FAIL</span></span>|<span data-ttu-id="0eee4-123">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="0eee4-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0eee4-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="0eee4-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0eee4-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0eee4-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0eee4-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0eee4-126">Requirements</span></span>  
 <span data-ttu-id="0eee4-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eee4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eee4-128">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="0eee4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0eee4-129">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0eee4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0eee4-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eee4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eee4-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0eee4-131">See also</span></span>

- [<span data-ttu-id="0eee4-132">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0eee4-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="0eee4-133">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0eee4-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="0eee4-134">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0eee4-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="0eee4-135">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0eee4-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
