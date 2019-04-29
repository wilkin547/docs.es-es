---
title: ICLRRuntimeHost::Stop (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85116244ad21842fab025ddd48106deef75f210b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771838"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="bd0a1-102">ICLRRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="bd0a1-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="bd0a1-103">Detiene la ejecución de código por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bd0a1-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bd0a1-104">Este método no liberar los recursos en el host, descargar dominios de aplicación o destruir subprocesos.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="bd0a1-105">Debe finalizar el proceso para liberar estos recursos.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0a1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd0a1-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bd0a1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bd0a1-107">Return Value</span></span>  
  
|<span data-ttu-id="bd0a1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd0a1-108">HRESULT</span></span>|<span data-ttu-id="bd0a1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd0a1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd0a1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd0a1-110">S_OK</span></span>|<span data-ttu-id="bd0a1-111">`Stop` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="bd0a1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bd0a1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd0a1-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd0a1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd0a1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd0a1-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-115">The call timed out.</span></span>|  
|<span data-ttu-id="bd0a1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd0a1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd0a1-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd0a1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd0a1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd0a1-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd0a1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd0a1-120">E_FAIL</span></span>|<span data-ttu-id="bd0a1-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd0a1-122">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd0a1-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd0a1-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd0a1-124">Requirements</span></span>  
 <span data-ttu-id="bd0a1-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd0a1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd0a1-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd0a1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd0a1-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd0a1-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd0a1-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd0a1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0a1-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd0a1-129">See also</span></span>

- [<span data-ttu-id="bd0a1-130">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd0a1-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
