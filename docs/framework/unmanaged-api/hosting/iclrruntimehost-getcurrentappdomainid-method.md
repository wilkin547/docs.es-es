---
description: 'Más información acerca de: ICLRRuntimeHost:: GetCurrentAppDomainId ((método)'
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
ms.openlocfilehash: 88d5288e2e8ee7d8d1f5430261e21052334240be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799737"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="54c95-103">ICLRRuntimeHost::GetCurrentAppDomainId (Método)</span><span class="sxs-lookup"><span data-stu-id="54c95-103">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>

<span data-ttu-id="54c95-104">Obtiene el identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="54c95-104">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54c95-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54c95-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54c95-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54c95-106">Parameters</span></span>  

 `pdwAppDomainId`  
 <span data-ttu-id="54c95-107">enuncia Identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="54c95-107">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54c95-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="54c95-108">Return Value</span></span>  
  
|<span data-ttu-id="54c95-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54c95-109">HRESULT</span></span>|<span data-ttu-id="54c95-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="54c95-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54c95-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="54c95-111">S_OK</span></span>|<span data-ttu-id="54c95-112">`GetCurrentAppDomainId` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="54c95-112">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="54c95-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="54c95-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="54c95-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="54c95-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="54c95-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="54c95-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="54c95-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54c95-116">The call timed out.</span></span>|  
|<span data-ttu-id="54c95-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="54c95-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="54c95-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="54c95-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="54c95-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="54c95-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="54c95-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="54c95-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="54c95-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="54c95-121">E_FAIL</span></span>|<span data-ttu-id="54c95-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="54c95-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="54c95-123">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="54c95-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="54c95-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="54c95-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54c95-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54c95-125">Remarks</span></span>  

 <span data-ttu-id="54c95-126">El `pdwAppDomainId` parámetro se establece en el valor de la <xref:System.AppDomain.Id%2A> propiedad de <xref:System.AppDomain> en la que se está ejecutando el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="54c95-126">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54c95-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54c95-127">Requirements</span></span>  

 <span data-ttu-id="54c95-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54c95-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54c95-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="54c95-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54c95-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54c95-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54c95-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54c95-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c95-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="54c95-132">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="54c95-133">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="54c95-133">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
