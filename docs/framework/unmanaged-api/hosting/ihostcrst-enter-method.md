---
description: 'Más información acerca de: IHostCrst:: Enter (método)'
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
ms.openlocfilehash: ef8e4ce71cde75fe6b834802b08d22aedbd6fab9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789455"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="7069d-103">IHostCrst::Enter (Método)</span><span class="sxs-lookup"><span data-stu-id="7069d-103">IHostCrst::Enter Method</span></span>

<span data-ttu-id="7069d-104">Entra en la sección crítica que representa la instancia de [IHostCrst](ihostcrst-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="7069d-104">Enters the critical section that is represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7069d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7069d-105">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7069d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7069d-106">Parameters</span></span>  

 `option`  
 <span data-ttu-id="7069d-107">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) , que indica qué acción debe realizar el host si se bloquea la operación.</span><span class="sxs-lookup"><span data-stu-id="7069d-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7069d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7069d-108">Return Value</span></span>  
  
|<span data-ttu-id="7069d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7069d-109">HRESULT</span></span>|<span data-ttu-id="7069d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7069d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7069d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7069d-111">S_OK</span></span>|<span data-ttu-id="7069d-112">`Enter` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7069d-112">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="7069d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7069d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7069d-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7069d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7069d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7069d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7069d-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7069d-116">The call timed out.</span></span>|  
|<span data-ttu-id="7069d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7069d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7069d-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7069d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7069d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7069d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7069d-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="7069d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7069d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7069d-121">E_FAIL</span></span>|<span data-ttu-id="7069d-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7069d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7069d-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7069d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7069d-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7069d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7069d-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7069d-125">Remarks</span></span>  

 <span data-ttu-id="7069d-126">`Enter` refleja la función de Win32 `EnterCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="7069d-126">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7069d-127">Este método no devuelve ningún resultado hasta que se especifica la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="7069d-127">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7069d-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7069d-128">Requirements</span></span>  

 <span data-ttu-id="7069d-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7069d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7069d-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7069d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7069d-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7069d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7069d-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7069d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7069d-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="7069d-133">See also</span></span>

- [<span data-ttu-id="7069d-134">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7069d-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="7069d-135">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7069d-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="7069d-136">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7069d-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
