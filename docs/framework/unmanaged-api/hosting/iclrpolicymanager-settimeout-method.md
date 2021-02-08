---
description: 'Más información acerca de: ICLRPolicyManager:: SetTimeout (método)'
title: ICLRPolicyManager::SetTimeout (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
ms.openlocfilehash: 5fb65e93cc6eea7826498ff6b03147773f06e0b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781901"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="02a3a-103">ICLRPolicyManager::SetTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="02a3a-103">ICLRPolicyManager::SetTimeout Method</span></span>

<span data-ttu-id="02a3a-104">Establece un valor de tiempo de espera para la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="02a3a-104">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a3a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02a3a-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02a3a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02a3a-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="02a3a-107">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica la operación de Common Language Runtime (CLR) para la que se va a establecer un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="02a3a-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="02a3a-108">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="02a3a-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="02a3a-109">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="02a3a-109">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="02a3a-110">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="02a3a-110">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="02a3a-111">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="02a3a-111">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="02a3a-112">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="02a3a-112">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="02a3a-113">de Nuevo valor de tiempo de espera, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="02a3a-113">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="02a3a-114">Un valor de Infinite hace que la operación nunca agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="02a3a-114">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02a3a-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="02a3a-115">Return Value</span></span>  
  
|<span data-ttu-id="02a3a-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02a3a-116">HRESULT</span></span>|<span data-ttu-id="02a3a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="02a3a-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02a3a-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="02a3a-118">S_OK</span></span>|<span data-ttu-id="02a3a-119">`SetTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="02a3a-119">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="02a3a-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02a3a-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02a3a-121">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="02a3a-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02a3a-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02a3a-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02a3a-123">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="02a3a-123">The call timed out.</span></span>|  
|<span data-ttu-id="02a3a-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02a3a-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02a3a-125">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="02a3a-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02a3a-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02a3a-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02a3a-127">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="02a3a-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02a3a-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02a3a-128">E_FAIL</span></span>|<span data-ttu-id="02a3a-129">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="02a3a-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02a3a-130">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="02a3a-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02a3a-131">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="02a3a-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="02a3a-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="02a3a-132">E_INVALIDARG</span></span>|<span data-ttu-id="02a3a-133">No se puede establecer un tiempo de espera para el especificado `operation` o se proporcionó un valor no válido para `operation` .</span><span class="sxs-lookup"><span data-stu-id="02a3a-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02a3a-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02a3a-134">Requirements</span></span>  

 <span data-ttu-id="02a3a-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02a3a-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a3a-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="02a3a-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02a3a-137">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="02a3a-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02a3a-138">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a3a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a3a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="02a3a-139">See also</span></span>

- [<span data-ttu-id="02a3a-140">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="02a3a-140">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="02a3a-141">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02a3a-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="02a3a-142">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02a3a-142">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
