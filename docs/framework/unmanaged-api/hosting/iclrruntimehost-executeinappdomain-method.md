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
ms.openlocfilehash: c012e4e2b5e41737f7bbe6a0fb887693b0ba22c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176427"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="f3825-102">ICLRRuntimeHost::ExecuteInAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="f3825-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="f3825-103">Especifica el <xref:System.AppDomain> en qué ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="f3825-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3825-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3825-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3825-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3825-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="f3825-106">[en] El identificador numérico <xref:System.AppDomain> del método en el que se va a ejecutar el método especificado.</span><span class="sxs-lookup"><span data-stu-id="f3825-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="f3825-107">[en] Un puntero a la función <xref:System.AppDomain>que se va a ejecutar dentro del archivo .</span><span class="sxs-lookup"><span data-stu-id="f3825-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="f3825-108">[en] Puntero a memoria asignada por el autor de la llamada opaca.</span><span class="sxs-lookup"><span data-stu-id="f3825-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="f3825-109">El Common Language Runtime (CLR) pasa este parámetro a la devolución de llamada del dominio.</span><span class="sxs-lookup"><span data-stu-id="f3825-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="f3825-110">No es memoria de montón administrada por tiempo de ejecución; Tanto la asignación como la duración de esta memoria son controladas por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f3825-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3825-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f3825-111">Return Value</span></span>  
  
|<span data-ttu-id="f3825-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3825-112">HRESULT</span></span>|<span data-ttu-id="f3825-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3825-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3825-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3825-114">S_OK</span></span>|<span data-ttu-id="f3825-115">`ExecuteInAppDomain`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="f3825-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="f3825-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f3825-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f3825-117">El CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3825-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f3825-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f3825-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f3825-119">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="f3825-119">The call timed out.</span></span>|  
|<span data-ttu-id="f3825-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f3825-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f3825-121">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="f3825-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f3825-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f3825-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f3825-123">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="f3825-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f3825-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3825-124">E_FAIL</span></span>|<span data-ttu-id="f3825-125">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="f3825-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f3825-126">Si un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="f3825-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f3825-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f3825-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3825-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3825-128">Remarks</span></span>  
 <span data-ttu-id="f3825-129">`ExecuteInAppDomain`permite que el host ejerza <xref:System.AppDomain> el control sobre el que se debe ejecutar el método administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="f3825-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="f3825-130">Puede obtener el valor del identificador de un dominio de aplicación, que corresponde al valor de la <xref:System.AppDomain.Id%2A> propiedad, llamando al método [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="f3825-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3825-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3825-131">Requirements</span></span>  
 <span data-ttu-id="f3825-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3825-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3825-133">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="f3825-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3825-134">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3825-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3825-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3825-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3825-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3825-136">See also</span></span>

- [<span data-ttu-id="f3825-137">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3825-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
