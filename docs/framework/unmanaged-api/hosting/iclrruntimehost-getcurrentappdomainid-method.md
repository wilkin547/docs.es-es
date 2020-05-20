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
ms.openlocfilehash: 1c667b19ac4bfa0bea95b85cf099906e351e5b71
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703671"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="11fff-102">ICLRRuntimeHost::GetCurrentAppDomainId (Método)</span><span class="sxs-lookup"><span data-stu-id="11fff-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="11fff-103">Obtiene el identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="11fff-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11fff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11fff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11fff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11fff-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="11fff-106">enuncia Identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="11fff-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11fff-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11fff-107">Return Value</span></span>  
  
|<span data-ttu-id="11fff-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11fff-108">HRESULT</span></span>|<span data-ttu-id="11fff-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="11fff-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11fff-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="11fff-110">S_OK</span></span>|<span data-ttu-id="11fff-111">`GetCurrentAppDomainId`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="11fff-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="11fff-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11fff-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11fff-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="11fff-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11fff-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11fff-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11fff-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="11fff-115">The call timed out.</span></span>|  
|<span data-ttu-id="11fff-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11fff-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11fff-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="11fff-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11fff-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11fff-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11fff-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="11fff-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11fff-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11fff-120">E_FAIL</span></span>|<span data-ttu-id="11fff-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="11fff-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="11fff-122">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="11fff-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11fff-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="11fff-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11fff-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="11fff-124">Remarks</span></span>  
 <span data-ttu-id="11fff-125">El `pdwAppDomainId` parámetro se establece en el valor de la <xref:System.AppDomain.Id%2A> propiedad de <xref:System.AppDomain> en la que se está ejecutando el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="11fff-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11fff-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11fff-126">Requirements</span></span>  
 <span data-ttu-id="11fff-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11fff-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11fff-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="11fff-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11fff-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="11fff-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11fff-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11fff-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11fff-131">Consulta también</span><span class="sxs-lookup"><span data-stu-id="11fff-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="11fff-132">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11fff-132">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
