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
ms.openlocfilehash: 1b7d321eec2bbc2beb47c5de034bb4ef5d534c9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120469"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="a16c3-102">ICLRRuntimeHost::GetCurrentAppDomainId (Método)</span><span class="sxs-lookup"><span data-stu-id="a16c3-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="a16c3-103">Obtiene el identificador numérico de la <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="a16c3-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a16c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a16c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a16c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a16c3-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="a16c3-106">enuncia Identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="a16c3-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a16c3-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a16c3-107">Return Value</span></span>  
  
|<span data-ttu-id="a16c3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a16c3-108">HRESULT</span></span>|<span data-ttu-id="a16c3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a16c3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a16c3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a16c3-110">S_OK</span></span>|<span data-ttu-id="a16c3-111">`GetCurrentAppDomainId` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a16c3-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="a16c3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a16c3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a16c3-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a16c3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a16c3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a16c3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a16c3-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a16c3-115">The call timed out.</span></span>|  
|<span data-ttu-id="a16c3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a16c3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a16c3-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a16c3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a16c3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a16c3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a16c3-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a16c3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a16c3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a16c3-120">E_FAIL</span></span>|<span data-ttu-id="a16c3-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a16c3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a16c3-122">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a16c3-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a16c3-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a16c3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a16c3-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a16c3-124">Remarks</span></span>  
 <span data-ttu-id="a16c3-125">El parámetro `pdwAppDomainId` se establece en el valor de la propiedad <xref:System.AppDomain.Id%2A> de la <xref:System.AppDomain> en la que se está ejecutando el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a16c3-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a16c3-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a16c3-126">Requirements</span></span>  
 <span data-ttu-id="a16c3-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a16c3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a16c3-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a16c3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a16c3-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a16c3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a16c3-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a16c3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a16c3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a16c3-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="a16c3-132">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a16c3-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
