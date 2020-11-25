---
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
ms.openlocfilehash: cc5d0d65d213d952c0897a72d8ec38ea6b8b22db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700670"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="c84ff-102">ICLRRuntimeHost::UnloadAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="c84ff-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>

<span data-ttu-id="c84ff-103">Descarga el administrado <xref:System.AppDomain> que corresponde al identificador numérico especificado.</span><span class="sxs-lookup"><span data-stu-id="c84ff-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c84ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c84ff-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c84ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c84ff-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="c84ff-106">de Identificador numérico del dominio de aplicación que se va a descargar.</span><span class="sxs-lookup"><span data-stu-id="c84ff-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="c84ff-107">[in] `true` para indicar que el Common Language Runtime (CLR) debe esperar hasta que haya finalizado la ejecución del subproceso actual de la aplicación antes de intentar descargar el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c84ff-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c84ff-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c84ff-108">Return Value</span></span>  
  
|<span data-ttu-id="c84ff-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c84ff-109">HRESULT</span></span>|<span data-ttu-id="c84ff-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c84ff-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c84ff-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c84ff-111">S_OK</span></span>|<span data-ttu-id="c84ff-112">`UnloadAppDomain` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c84ff-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="c84ff-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c84ff-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c84ff-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c84ff-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c84ff-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c84ff-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c84ff-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c84ff-116">The call timed out.</span></span>|  
|<span data-ttu-id="c84ff-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c84ff-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c84ff-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c84ff-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c84ff-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c84ff-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c84ff-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c84ff-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c84ff-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c84ff-121">E_FAIL</span></span>|<span data-ttu-id="c84ff-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c84ff-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c84ff-123">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c84ff-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c84ff-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c84ff-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c84ff-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c84ff-125">Remarks</span></span>  

 <span data-ttu-id="c84ff-126">Puede obtener el identificador numérico del dominio de aplicación en el que se está ejecutando el subproceso actual llamando a [GetCurrentAppDomainId (](iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="c84ff-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="c84ff-127">Este identificador corresponde a la <xref:System.AppDomain.Id%2A> propiedad del <xref:System.AppDomain> tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="c84ff-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c84ff-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c84ff-128">Requirements</span></span>  

 <span data-ttu-id="c84ff-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c84ff-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c84ff-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c84ff-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c84ff-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c84ff-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c84ff-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c84ff-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c84ff-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c84ff-133">See also</span></span>

- [<span data-ttu-id="c84ff-134">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c84ff-134">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
