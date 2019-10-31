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
ms.openlocfilehash: c847f177f48d72f28192d1efabe93c65a7b3f4b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120493"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="e95a3-102">ICLRRuntimeHost::ExecuteInAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="e95a3-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="e95a3-103">Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="e95a3-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e95a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e95a3-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e95a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e95a3-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="e95a3-106">de IDENTIFICADOR numérico del <xref:System.AppDomain> en el que se va a ejecutar el método especificado.</span><span class="sxs-lookup"><span data-stu-id="e95a3-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="e95a3-107">de Puntero a la función que se va a ejecutar en el <xref:System.AppDomain>especificado.</span><span class="sxs-lookup"><span data-stu-id="e95a3-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="e95a3-108">de Puntero a la memoria opaca asignada por el llamador.</span><span class="sxs-lookup"><span data-stu-id="e95a3-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="e95a3-109">El Common Language Runtime (CLR) pasa este parámetro a la devolución de llamada del dominio.</span><span class="sxs-lookup"><span data-stu-id="e95a3-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="e95a3-110">No es memoria del montón administrado en tiempo de ejecución; el autor de la llamada controla tanto la asignación como la duración de esta memoria.</span><span class="sxs-lookup"><span data-stu-id="e95a3-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e95a3-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e95a3-111">Return Value</span></span>  
  
|<span data-ttu-id="e95a3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e95a3-112">HRESULT</span></span>|<span data-ttu-id="e95a3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e95a3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e95a3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e95a3-114">S_OK</span></span>|<span data-ttu-id="e95a3-115">`ExecuteInAppDomain` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e95a3-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="e95a3-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e95a3-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e95a3-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e95a3-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e95a3-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e95a3-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e95a3-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e95a3-119">The call timed out.</span></span>|  
|<span data-ttu-id="e95a3-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e95a3-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e95a3-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e95a3-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e95a3-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e95a3-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e95a3-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e95a3-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e95a3-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e95a3-124">E_FAIL</span></span>|<span data-ttu-id="e95a3-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e95a3-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e95a3-126">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e95a3-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e95a3-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e95a3-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e95a3-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e95a3-128">Remarks</span></span>  
 <span data-ttu-id="e95a3-129">`ExecuteInAppDomain` permite al host controlar el <xref:System.AppDomain> administrado en el que se debe ejecutar el método administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="e95a3-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="e95a3-130">Puede obtener el valor del identificador de un dominio de aplicación, que corresponde al valor de la propiedad <xref:System.AppDomain.Id%2A>, llamando al [método GetCurrentAppDomainId (](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="e95a3-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e95a3-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e95a3-131">Requirements</span></span>  
 <span data-ttu-id="e95a3-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e95a3-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e95a3-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e95a3-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e95a3-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e95a3-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e95a3-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e95a3-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e95a3-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="e95a3-136">See also</span></span>

- [<span data-ttu-id="e95a3-137">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e95a3-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
