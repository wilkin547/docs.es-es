---
title: IHostCrst::Enter (Método)
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de249928f853c5384db7a2e7615eb425109fd572
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497436"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="c369e-102">IHostCrst::Enter (Método)</span><span class="sxs-lookup"><span data-stu-id="c369e-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="c369e-103">Entra en la sección crítica que está representada por el actual [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="c369e-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c369e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c369e-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c369e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c369e-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="c369e-106">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que indica qué acción debe realizar el host si la operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="c369e-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c369e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c369e-107">Return Value</span></span>  
  
|<span data-ttu-id="c369e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c369e-108">HRESULT</span></span>|<span data-ttu-id="c369e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c369e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c369e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c369e-110">S_OK</span></span>|<span data-ttu-id="c369e-111">`Enter` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c369e-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="c369e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c369e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c369e-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c369e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c369e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c369e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c369e-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c369e-115">The call timed out.</span></span>|  
|<span data-ttu-id="c369e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c369e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c369e-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c369e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c369e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c369e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c369e-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="c369e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c369e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c369e-120">E_FAIL</span></span>|<span data-ttu-id="c369e-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="c369e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c369e-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c369e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c369e-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c369e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c369e-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c369e-124">Remarks</span></span>  
 <span data-ttu-id="c369e-125">`Enter` refleja el Win32 `EnterCriticalSection` función.</span><span class="sxs-lookup"><span data-stu-id="c369e-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c369e-126">Este método no devuelve hasta que se especifique la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="c369e-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c369e-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c369e-127">Requirements</span></span>  
 <span data-ttu-id="c369e-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c369e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c369e-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c369e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c369e-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c369e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c369e-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c369e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c369e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c369e-132">See also</span></span>
- [<span data-ttu-id="c369e-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c369e-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c369e-134">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c369e-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="c369e-135">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c369e-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
