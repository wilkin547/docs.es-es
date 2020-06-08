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
ms.openlocfilehash: e1df31ed8b652837a33b360b1378f99e6800cbea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501526"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="62ddd-102">IHostSecurityContext::Capture (Método)</span><span class="sxs-lookup"><span data-stu-id="62ddd-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="62ddd-103">Obtiene un clon de la instancia de [IHostSecurityContext](ihostsecuritycontext-interface.md) devuelta desde una llamada a [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="62ddd-103">Gets a clone of the [IHostSecurityContext](ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62ddd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62ddd-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62ddd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62ddd-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="62ddd-106">enuncia Puntero a la dirección de un clon del `IHostSecurityContext` objeto que se va a capturar.</span><span class="sxs-lookup"><span data-stu-id="62ddd-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62ddd-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="62ddd-107">Return Value</span></span>  
  
|<span data-ttu-id="62ddd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62ddd-108">HRESULT</span></span>|<span data-ttu-id="62ddd-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="62ddd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62ddd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="62ddd-110">S_OK</span></span>|<span data-ttu-id="62ddd-111">`Capture`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="62ddd-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="62ddd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62ddd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62ddd-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="62ddd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62ddd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62ddd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62ddd-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="62ddd-115">The call timed out.</span></span>|  
|<span data-ttu-id="62ddd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62ddd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62ddd-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="62ddd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62ddd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62ddd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62ddd-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="62ddd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62ddd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62ddd-120">E_FAIL</span></span>|<span data-ttu-id="62ddd-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="62ddd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62ddd-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="62ddd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62ddd-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="62ddd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62ddd-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62ddd-124">Remarks</span></span>  
 <span data-ttu-id="62ddd-125">El puntero de interfaz devuelto desde `Capture` es un clon del contexto capturado.</span><span class="sxs-lookup"><span data-stu-id="62ddd-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="62ddd-126">Cuando esta información se mueve a través de un punto de código asincrónico, su duración se separa del puntero en el que se realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="62ddd-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="62ddd-127">Por lo tanto, se puede liberar el puntero original.</span><span class="sxs-lookup"><span data-stu-id="62ddd-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62ddd-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62ddd-128">Requirements</span></span>  
 <span data-ttu-id="62ddd-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62ddd-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62ddd-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="62ddd-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62ddd-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62ddd-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62ddd-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62ddd-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ddd-133">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="62ddd-133">See also</span></span>

- [<span data-ttu-id="62ddd-134">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62ddd-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="62ddd-135">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62ddd-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
