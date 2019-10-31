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
ms.openlocfilehash: 757fb996b268892818a54a3f80a54edfd89c7630
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124429"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="00210-102">IHostCrst::Enter (Método)</span><span class="sxs-lookup"><span data-stu-id="00210-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="00210-103">Entra en la sección crítica que representa la instancia de [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="00210-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00210-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00210-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00210-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00210-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="00210-106">de Uno de los valores de [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , que indica qué acción debe realizar el host si se bloquea la operación.</span><span class="sxs-lookup"><span data-stu-id="00210-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00210-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="00210-107">Return Value</span></span>  
  
|<span data-ttu-id="00210-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00210-108">HRESULT</span></span>|<span data-ttu-id="00210-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="00210-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00210-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="00210-110">S_OK</span></span>|<span data-ttu-id="00210-111">`Enter` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="00210-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="00210-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00210-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00210-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="00210-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00210-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00210-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00210-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="00210-115">The call timed out.</span></span>|  
|<span data-ttu-id="00210-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00210-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00210-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="00210-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00210-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00210-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00210-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="00210-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00210-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00210-120">E_FAIL</span></span>|<span data-ttu-id="00210-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="00210-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00210-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="00210-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00210-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="00210-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00210-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00210-124">Remarks</span></span>  
 <span data-ttu-id="00210-125">`Enter` refleja la función de `EnterCriticalSection` de Win32.</span><span class="sxs-lookup"><span data-stu-id="00210-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00210-126">Este método no devuelve ningún resultado hasta que se especifica la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="00210-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00210-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00210-127">Requirements</span></span>  
 <span data-ttu-id="00210-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00210-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00210-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="00210-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00210-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="00210-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00210-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00210-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00210-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="00210-132">See also</span></span>

- [<span data-ttu-id="00210-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="00210-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="00210-134">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="00210-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="00210-135">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="00210-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
