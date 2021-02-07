---
description: 'Más información acerca de: IHostSecurityContext:: Capture (método)'
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
ms.openlocfilehash: d46bbae7b94dcad6d1356243c938c9d3690f26a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671716"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="f4563-103">IHostSecurityContext::Capture (Método)</span><span class="sxs-lookup"><span data-stu-id="f4563-103">IHostSecurityContext::Capture Method</span></span>

<span data-ttu-id="f4563-104">Obtiene un clon de la instancia de [IHostSecurityContext](ihostsecuritycontext-interface.md) devuelta desde una llamada a [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="f4563-104">Gets a clone of the [IHostSecurityContext](ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4563-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4563-105">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4563-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4563-106">Parameters</span></span>  

 `ppClonedContext`  
 <span data-ttu-id="f4563-107">enuncia Puntero a la dirección de un clon del `IHostSecurityContext` objeto que se va a capturar.</span><span class="sxs-lookup"><span data-stu-id="f4563-107">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4563-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f4563-108">Return Value</span></span>  
  
|<span data-ttu-id="f4563-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4563-109">HRESULT</span></span>|<span data-ttu-id="f4563-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4563-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4563-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4563-111">S_OK</span></span>|<span data-ttu-id="f4563-112">`Capture` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4563-112">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="f4563-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f4563-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f4563-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4563-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f4563-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f4563-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f4563-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f4563-116">The call timed out.</span></span>|  
|<span data-ttu-id="f4563-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f4563-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f4563-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f4563-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f4563-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f4563-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f4563-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f4563-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f4563-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f4563-121">E_FAIL</span></span>|<span data-ttu-id="f4563-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f4563-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f4563-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f4563-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f4563-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f4563-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4563-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f4563-125">Remarks</span></span>  

 <span data-ttu-id="f4563-126">El puntero de interfaz devuelto desde `Capture` es un clon del contexto capturado.</span><span class="sxs-lookup"><span data-stu-id="f4563-126">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="f4563-127">Cuando esta información se mueve a través de un punto de código asincrónico, su duración se separa del puntero en el que se realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="f4563-127">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="f4563-128">Por lo tanto, se puede liberar el puntero original.</span><span class="sxs-lookup"><span data-stu-id="f4563-128">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4563-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4563-129">Requirements</span></span>  

 <span data-ttu-id="f4563-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4563-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4563-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f4563-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4563-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4563-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4563-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4563-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4563-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4563-134">See also</span></span>

- [<span data-ttu-id="f4563-135">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4563-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="f4563-136">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4563-136">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
