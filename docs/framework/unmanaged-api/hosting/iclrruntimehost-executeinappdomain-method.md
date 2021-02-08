---
description: 'Más información acerca de: ICLRRuntimeHost:: ExecuteInAppDomain ((método)'
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
ms.openlocfilehash: 6640713b55e05817f39af819d5e41ee1f2a10b68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799751"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="e6b7e-103">ICLRRuntimeHost::ExecuteInAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-103">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>

<span data-ttu-id="e6b7e-104">Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-104">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b7e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6b7e-105">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6b7e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6b7e-106">Parameters</span></span>  

 `AppDomainId`  
 <span data-ttu-id="e6b7e-107">de IDENTIFICADOR numérico del en el <xref:System.AppDomain> que se va a ejecutar el método especificado.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-107">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="e6b7e-108">de Puntero a la función que se va a ejecutar dentro del especificado <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="e6b7e-108">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="e6b7e-109">de Puntero a la memoria opaca asignada por el llamador.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-109">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="e6b7e-110">El Common Language Runtime (CLR) pasa este parámetro a la devolución de llamada del dominio.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-110">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="e6b7e-111">No es memoria del montón administrado en tiempo de ejecución; el autor de la llamada controla tanto la asignación como la duración de esta memoria.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-111">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6b7e-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e6b7e-112">Return Value</span></span>  
  
|<span data-ttu-id="e6b7e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6b7e-113">HRESULT</span></span>|<span data-ttu-id="e6b7e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6b7e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6b7e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6b7e-115">S_OK</span></span>|<span data-ttu-id="e6b7e-116">`ExecuteInAppDomain` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-116">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="e6b7e-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6b7e-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6b7e-118">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6b7e-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6b7e-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6b7e-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-120">The call timed out.</span></span>|  
|<span data-ttu-id="e6b7e-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6b7e-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6b7e-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6b7e-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6b7e-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6b7e-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6b7e-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6b7e-125">E_FAIL</span></span>|<span data-ttu-id="e6b7e-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6b7e-127">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-127">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6b7e-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6b7e-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e6b7e-129">Remarks</span></span>  

 <span data-ttu-id="e6b7e-130">`ExecuteInAppDomain` permite que el host ejerza el control sobre <xref:System.AppDomain> el que se debe ejecutar el método administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-130">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="e6b7e-131">Puede obtener el valor del identificador de un dominio de aplicación, que se corresponde con el valor de la <xref:System.AppDomain.Id%2A> propiedad, llamando al [método GetCurrentAppDomainId (](iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-131">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6b7e-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6b7e-132">Requirements</span></span>  

 <span data-ttu-id="e6b7e-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6b7e-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e6b7e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6b7e-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6b7e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6b7e-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6b7e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b7e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6b7e-137">See also</span></span>

- [<span data-ttu-id="e6b7e-138">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-138">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
