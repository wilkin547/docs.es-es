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
ms.openlocfilehash: 40857620e47befce361ff8cb04af527915051df3
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804208"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="3ea4d-102">IHostSecurityContext::Capture (Método)</span><span class="sxs-lookup"><span data-stu-id="3ea4d-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="3ea4d-103">Obtiene un clon de la instancia de [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) devuelta desde una llamada a [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="3ea4d-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ea4d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ea4d-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ea4d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ea4d-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="3ea4d-106">enuncia Puntero a la dirección de un clon del `IHostSecurityContext` objeto que se va a capturar.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ea4d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ea4d-107">Return Value</span></span>  
  
|<span data-ttu-id="3ea4d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ea4d-108">HRESULT</span></span>|<span data-ttu-id="3ea4d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ea4d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ea4d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ea4d-110">S_OK</span></span>|<span data-ttu-id="3ea4d-111">`Capture`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="3ea4d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3ea4d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3ea4d-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3ea4d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3ea4d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3ea4d-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-115">The call timed out.</span></span>|  
|<span data-ttu-id="3ea4d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ea4d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3ea4d-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3ea4d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3ea4d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3ea4d-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3ea4d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3ea4d-120">E_FAIL</span></span>|<span data-ttu-id="3ea4d-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3ea4d-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3ea4d-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ea4d-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3ea4d-124">Remarks</span></span>  
 <span data-ttu-id="3ea4d-125">El puntero de interfaz devuelto desde `Capture` es un clon del contexto capturado.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="3ea4d-126">Cuando esta información se mueve a través de un punto de código asincrónico, su duración se separa del puntero en el que se realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="3ea4d-127">Por lo tanto, se puede liberar el puntero original.</span><span class="sxs-lookup"><span data-stu-id="3ea4d-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ea4d-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ea4d-128">Requirements</span></span>  
 <span data-ttu-id="3ea4d-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ea4d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ea4d-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3ea4d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ea4d-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3ea4d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ea4d-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ea4d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea4d-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ea4d-133">See also</span></span>

- [<span data-ttu-id="3ea4d-134">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ea4d-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="3ea4d-135">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ea4d-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
