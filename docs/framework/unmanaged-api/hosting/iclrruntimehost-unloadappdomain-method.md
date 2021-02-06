---
description: 'Más información acerca de: ICLRRuntimeHost:: UnloadAppDomain ((método)'
title: ICLRRuntimeHost::UnloadAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
ms.openlocfilehash: 2a47c6250434c3ee4122f8eeae75f25ee4c08a34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637292"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="1274f-103">ICLRRuntimeHost::UnloadAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="1274f-103">ICLRRuntimeHost::UnloadAppDomain Method</span></span>

<span data-ttu-id="1274f-104">Descarga el administrado <xref:System.AppDomain> que corresponde al identificador numérico especificado.</span><span class="sxs-lookup"><span data-stu-id="1274f-104">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1274f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1274f-105">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1274f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1274f-106">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="1274f-107">de Identificador numérico del dominio de aplicación que se va a descargar.</span><span class="sxs-lookup"><span data-stu-id="1274f-107">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="1274f-108">[in] `true` para indicar que el Common Language Runtime (CLR) debe esperar hasta que haya finalizado la ejecución del subproceso actual de la aplicación antes de intentar descargar el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1274f-108">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1274f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1274f-109">Return Value</span></span>  
  
|<span data-ttu-id="1274f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1274f-110">HRESULT</span></span>|<span data-ttu-id="1274f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="1274f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1274f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1274f-112">S_OK</span></span>|<span data-ttu-id="1274f-113">`UnloadAppDomain` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1274f-113">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="1274f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1274f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1274f-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1274f-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1274f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1274f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1274f-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1274f-117">The call timed out.</span></span>|  
|<span data-ttu-id="1274f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1274f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1274f-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1274f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1274f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1274f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1274f-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="1274f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1274f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1274f-122">E_FAIL</span></span>|<span data-ttu-id="1274f-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1274f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1274f-124">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1274f-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1274f-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1274f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1274f-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1274f-126">Remarks</span></span>  

 <span data-ttu-id="1274f-127">Puede obtener el identificador numérico del dominio de aplicación en el que se está ejecutando el subproceso actual llamando a [GetCurrentAppDomainId (](iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="1274f-127">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="1274f-128">Este identificador corresponde a la <xref:System.AppDomain.Id%2A> propiedad del <xref:System.AppDomain> tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="1274f-128">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1274f-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1274f-129">Requirements</span></span>  

 <span data-ttu-id="1274f-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1274f-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1274f-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1274f-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1274f-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1274f-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1274f-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1274f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1274f-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1274f-134">See also</span></span>

- [<span data-ttu-id="1274f-135">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1274f-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
