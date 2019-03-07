---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 734bd51131ea922f00362e7306d34e5241231c13
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466848"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="c2fa1-102">ICLRPolicyManager::SetUnhandledExceptionPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="c2fa1-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="c2fa1-103">Especifica el comportamiento de common language runtime (CLR) cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2fa1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2fa1-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2fa1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2fa1-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="c2fa1-106">[in] Uno de los [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) valores, que indica si se establece el comportamiento de CLR o el host.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2fa1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c2fa1-107">Return Value</span></span>  
  
|<span data-ttu-id="c2fa1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2fa1-108">HRESULT</span></span>|<span data-ttu-id="c2fa1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2fa1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2fa1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2fa1-110">S_OK</span></span>|<span data-ttu-id="c2fa1-111">`SetUnhandledExceptionPolicy` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="c2fa1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2fa1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2fa1-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2fa1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2fa1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2fa1-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-115">The call timed out.</span></span>|  
|<span data-ttu-id="c2fa1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2fa1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2fa1-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2fa1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2fa1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2fa1-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2fa1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2fa1-120">E_FAIL</span></span>|<span data-ttu-id="c2fa1-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2fa1-122">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2fa1-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2fa1-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2fa1-124">Remarks</span></span>  
 <span data-ttu-id="c2fa1-125">De forma predeterminada, el CLR es el último controlador de todas las excepciones no controladas, y su comportamiento predeterminado es destruir el proceso.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="c2fa1-126">El host puede cambiar este comportamiento estableciendo el `policy` valor a eHostDeterminedPolicy.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="c2fa1-127">Este valor permite al host implementar su propio comportamiento predeterminado, al igual que con versiones anteriores de CLR.</span><span class="sxs-lookup"><span data-stu-id="c2fa1-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2fa1-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2fa1-128">Requirements</span></span>  
 <span data-ttu-id="c2fa1-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2fa1-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2fa1-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2fa1-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2fa1-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2fa1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2fa1-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2fa1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fa1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2fa1-133">See also</span></span>
- [<span data-ttu-id="c2fa1-134">EClrUnhandledException (enumeración)</span><span class="sxs-lookup"><span data-stu-id="c2fa1-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="c2fa1-135">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2fa1-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c2fa1-136">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2fa1-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="c2fa1-137">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2fa1-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
