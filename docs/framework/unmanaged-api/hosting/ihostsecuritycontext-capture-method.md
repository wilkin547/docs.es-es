---
title: IHostSecurityContext::Capture (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityContext.Capture
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01d8821cdcb27ed44491db41da22309147da8a36
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706740"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="beb29-102">IHostSecurityContext::Capture (Método)</span><span class="sxs-lookup"><span data-stu-id="beb29-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="beb29-103">Obtiene un clon de la [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) devuelve la instancia de una llamada a [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="beb29-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb29-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="beb29-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="beb29-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="beb29-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="beb29-106">[out] Un puntero a la dirección de un clon de la `IHostSecurityContext` objeto que va a capturar.</span><span class="sxs-lookup"><span data-stu-id="beb29-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="beb29-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="beb29-107">Return Value</span></span>  
  
|<span data-ttu-id="beb29-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="beb29-108">HRESULT</span></span>|<span data-ttu-id="beb29-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="beb29-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="beb29-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="beb29-110">S_OK</span></span>|<span data-ttu-id="beb29-111">`Capture` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="beb29-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="beb29-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="beb29-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="beb29-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="beb29-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="beb29-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="beb29-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="beb29-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="beb29-115">The call timed out.</span></span>|  
|<span data-ttu-id="beb29-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="beb29-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="beb29-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="beb29-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="beb29-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="beb29-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="beb29-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="beb29-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="beb29-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="beb29-120">E_FAIL</span></span>|<span data-ttu-id="beb29-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="beb29-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="beb29-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="beb29-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="beb29-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="beb29-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beb29-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="beb29-124">Remarks</span></span>  
 <span data-ttu-id="beb29-125">El puntero de interfaz devuelto desde `Capture` es un clon del contexto capturado.</span><span class="sxs-lookup"><span data-stu-id="beb29-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="beb29-126">Cuando esta información se mueve a través de un punto de código asincrónico, su duración se separa del puntero en la que se realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="beb29-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="beb29-127">Por lo tanto, se puede liberar el puntero original.</span><span class="sxs-lookup"><span data-stu-id="beb29-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beb29-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="beb29-128">Requirements</span></span>  
 <span data-ttu-id="beb29-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beb29-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beb29-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="beb29-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="beb29-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="beb29-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="beb29-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beb29-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb29-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="beb29-133">See also</span></span>
- [<span data-ttu-id="beb29-134">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="beb29-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="beb29-135">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="beb29-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
