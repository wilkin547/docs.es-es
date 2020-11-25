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
ms.openlocfilehash: 4c28c4a5cc64b20c9ac9c57e1aef5e7b90a20e01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728893"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="78c5c-102">ICLRRuntimeHost::ExecuteInAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="78c5c-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>

<span data-ttu-id="78c5c-103">Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="78c5c-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78c5c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78c5c-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78c5c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78c5c-105">Parameters</span></span>  

 `AppDomainId`  
 <span data-ttu-id="78c5c-106">de IDENTIFICADOR numérico del en el <xref:System.AppDomain> que se va a ejecutar el método especificado.</span><span class="sxs-lookup"><span data-stu-id="78c5c-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="78c5c-107">de Puntero a la función que se va a ejecutar dentro del especificado <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="78c5c-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="78c5c-108">de Puntero a la memoria opaca asignada por el llamador.</span><span class="sxs-lookup"><span data-stu-id="78c5c-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="78c5c-109">El Common Language Runtime (CLR) pasa este parámetro a la devolución de llamada del dominio.</span><span class="sxs-lookup"><span data-stu-id="78c5c-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="78c5c-110">No es memoria del montón administrado en tiempo de ejecución; el autor de la llamada controla tanto la asignación como la duración de esta memoria.</span><span class="sxs-lookup"><span data-stu-id="78c5c-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78c5c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="78c5c-111">Return Value</span></span>  
  
|<span data-ttu-id="78c5c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78c5c-112">HRESULT</span></span>|<span data-ttu-id="78c5c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="78c5c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78c5c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="78c5c-114">S_OK</span></span>|<span data-ttu-id="78c5c-115">`ExecuteInAppDomain` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="78c5c-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="78c5c-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="78c5c-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="78c5c-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="78c5c-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="78c5c-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="78c5c-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="78c5c-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78c5c-119">The call timed out.</span></span>|  
|<span data-ttu-id="78c5c-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="78c5c-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="78c5c-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="78c5c-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="78c5c-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="78c5c-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="78c5c-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="78c5c-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="78c5c-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78c5c-124">E_FAIL</span></span>|<span data-ttu-id="78c5c-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="78c5c-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="78c5c-126">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="78c5c-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="78c5c-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="78c5c-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78c5c-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78c5c-128">Remarks</span></span>  

 <span data-ttu-id="78c5c-129">`ExecuteInAppDomain` permite que el host ejerza el control sobre <xref:System.AppDomain> el que se debe ejecutar el método administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="78c5c-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="78c5c-130">Puede obtener el valor del identificador de un dominio de aplicación, que se corresponde con el valor de la <xref:System.AppDomain.Id%2A> propiedad, llamando al [método GetCurrentAppDomainId (](iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="78c5c-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78c5c-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78c5c-131">Requirements</span></span>  

 <span data-ttu-id="78c5c-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78c5c-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78c5c-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="78c5c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78c5c-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78c5c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78c5c-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78c5c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c5c-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78c5c-136">See also</span></span>

- [<span data-ttu-id="78c5c-137">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="78c5c-137">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
