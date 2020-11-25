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
ms.openlocfilehash: 2b1c9e99604664c99960a0741de6eae6b38fe963
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728854"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="7e679-102">ICLRRuntimeHost::GetCurrentAppDomainId (Método)</span><span class="sxs-lookup"><span data-stu-id="7e679-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>

<span data-ttu-id="7e679-103">Obtiene el identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="7e679-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e679-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e679-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e679-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e679-105">Parameters</span></span>  

 `pdwAppDomainId`  
 <span data-ttu-id="7e679-106">enuncia Identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="7e679-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e679-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7e679-107">Return Value</span></span>  
  
|<span data-ttu-id="7e679-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e679-108">HRESULT</span></span>|<span data-ttu-id="7e679-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e679-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e679-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e679-110">S_OK</span></span>|<span data-ttu-id="7e679-111">`GetCurrentAppDomainId` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e679-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="7e679-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e679-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e679-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e679-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e679-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e679-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e679-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7e679-115">The call timed out.</span></span>|  
|<span data-ttu-id="7e679-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e679-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e679-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7e679-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e679-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e679-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e679-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="7e679-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e679-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e679-120">E_FAIL</span></span>|<span data-ttu-id="7e679-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7e679-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e679-122">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7e679-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e679-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7e679-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e679-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e679-124">Remarks</span></span>  

 <span data-ttu-id="7e679-125">El `pdwAppDomainId` parámetro se establece en el valor de la <xref:System.AppDomain.Id%2A> propiedad de <xref:System.AppDomain> en la que se está ejecutando el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="7e679-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e679-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e679-126">Requirements</span></span>  

 <span data-ttu-id="7e679-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e679-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e679-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7e679-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e679-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e679-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e679-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e679-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e679-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e679-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="7e679-132">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e679-132">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
