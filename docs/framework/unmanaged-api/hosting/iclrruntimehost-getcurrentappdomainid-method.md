---
title: ICLRRuntimeHost::GetCurrentAppDomainId (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f262c416a6998ed182d0c42d7f00ea7dcb3f898
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768682"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="a87b7-102">ICLRRuntimeHost::GetCurrentAppDomainId (Método)</span><span class="sxs-lookup"><span data-stu-id="a87b7-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="a87b7-103">Obtiene el identificador numérico de la <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="a87b7-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a87b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a87b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a87b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a87b7-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="a87b7-106">[out] El identificador numérico de la <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="a87b7-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a87b7-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a87b7-107">Return Value</span></span>  
  
|<span data-ttu-id="a87b7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a87b7-108">HRESULT</span></span>|<span data-ttu-id="a87b7-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a87b7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a87b7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a87b7-110">S_OK</span></span>|<span data-ttu-id="a87b7-111">`GetCurrentAppDomainId` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a87b7-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="a87b7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a87b7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a87b7-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a87b7-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a87b7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a87b7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a87b7-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a87b7-115">The call timed out.</span></span>|  
|<span data-ttu-id="a87b7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a87b7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a87b7-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a87b7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a87b7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a87b7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a87b7-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a87b7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a87b7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a87b7-120">E_FAIL</span></span>|<span data-ttu-id="a87b7-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a87b7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a87b7-122">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a87b7-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a87b7-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a87b7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a87b7-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a87b7-124">Remarks</span></span>  
 <span data-ttu-id="a87b7-125">El `pdwAppDomainId` parámetro se establece en el valor de la <xref:System.AppDomain.Id%2A> propiedad de la <xref:System.AppDomain> en las que se está ejecutando el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a87b7-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a87b7-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a87b7-126">Requirements</span></span>  
 <span data-ttu-id="a87b7-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a87b7-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a87b7-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a87b7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a87b7-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a87b7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a87b7-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a87b7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a87b7-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a87b7-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="a87b7-132">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a87b7-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
