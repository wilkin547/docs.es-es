---
title: ICLRRuntimeHost::ExecuteInAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86348c35a023e22d10c4ad2e08f5cb1104b895a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641416"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="ba098-102">ICLRRuntimeHost::ExecuteInAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="ba098-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="ba098-103">Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="ba098-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba098-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba098-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba098-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba098-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="ba098-106">[in] El identificador numérico de la <xref:System.AppDomain> en el que se va a ejecutar el método especificado.</span><span class="sxs-lookup"><span data-stu-id="ba098-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="ba098-107">[in] Un puntero a la función se ejecute dentro de la especificada <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="ba098-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="ba098-108">[in] Puntero a la memoria asignada por el llamador opaco.</span><span class="sxs-lookup"><span data-stu-id="ba098-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="ba098-109">Este parámetro se pasa por common language runtime (CLR) para la devolución de llamada de dominio.</span><span class="sxs-lookup"><span data-stu-id="ba098-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="ba098-110">No es memoria del montón administrado en tiempo de ejecución; la asignación y la duración de esta memoria se controlan por el llamador.</span><span class="sxs-lookup"><span data-stu-id="ba098-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba098-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ba098-111">Return Value</span></span>  
  
|<span data-ttu-id="ba098-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba098-112">HRESULT</span></span>|<span data-ttu-id="ba098-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba098-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba098-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba098-114">S_OK</span></span>|<span data-ttu-id="ba098-115">`ExecuteInAppDomain` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba098-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="ba098-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba098-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba098-117">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba098-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba098-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba098-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba098-119">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ba098-119">The call timed out.</span></span>|  
|<span data-ttu-id="ba098-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba098-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba098-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ba098-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba098-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba098-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba098-123">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="ba098-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba098-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba098-124">E_FAIL</span></span>|<span data-ttu-id="ba098-125">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="ba098-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba098-126">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ba098-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba098-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ba098-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba098-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba098-128">Remarks</span></span>  
 <span data-ttu-id="ba098-129">`ExecuteInAppDomain` permite al host ejercer un control que administra <xref:System.AppDomain> debe ejecutarse en el método administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="ba098-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="ba098-130">Puede obtener el valor del identificador de un dominio de aplicación, que corresponde al valor de la <xref:System.AppDomain.Id%2A> propiedad, mediante una llamada a [GetCurrentAppDomainId (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="ba098-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba098-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba098-131">Requirements</span></span>  
 <span data-ttu-id="ba098-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba098-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba098-133">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ba098-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba098-134">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba098-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba098-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba098-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba098-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba098-136">See also</span></span>

- [<span data-ttu-id="ba098-137">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba098-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
