---
title: ICLRDebugManager::IsDebuggerAttached (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aaa085d9883f2a94a623f7800278c74a88e6a69a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432913"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="9aa36-102">ICLRDebugManager::IsDebuggerAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="9aa36-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="9aa36-103">Obtiene un valor que indica si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="9aa36-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aa36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9aa36-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9aa36-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9aa36-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="9aa36-106">[out] `true` si hay un depurador asociado al proceso; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9aa36-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9aa36-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9aa36-107">Return Value</span></span>  
  
|<span data-ttu-id="9aa36-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9aa36-108">HRESULT</span></span>|<span data-ttu-id="9aa36-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9aa36-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9aa36-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9aa36-110">S_OK</span></span>|<span data-ttu-id="9aa36-111">`IsDebuggerAttached` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9aa36-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="9aa36-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9aa36-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9aa36-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9aa36-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9aa36-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9aa36-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9aa36-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="9aa36-115">The call timed out.</span></span>|  
|<span data-ttu-id="9aa36-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9aa36-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9aa36-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9aa36-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9aa36-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9aa36-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9aa36-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="9aa36-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9aa36-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9aa36-120">E_FAIL</span></span>|<span data-ttu-id="9aa36-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="9aa36-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9aa36-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9aa36-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9aa36-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9aa36-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9aa36-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9aa36-124">Remarks</span></span>  
 <span data-ttu-id="9aa36-125">`IsDebuggerAttached` permite al host CLR para determinar si hay un depurador asociado al proceso de consulta.</span><span class="sxs-lookup"><span data-stu-id="9aa36-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aa36-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9aa36-126">Requirements</span></span>  
 <span data-ttu-id="9aa36-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9aa36-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aa36-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9aa36-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9aa36-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9aa36-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9aa36-130">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aa36-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa36-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="9aa36-131">See Also</span></span>  
 [<span data-ttu-id="9aa36-132">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9aa36-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="9aa36-133">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9aa36-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="9aa36-134">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9aa36-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
