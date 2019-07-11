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
ms.openlocfilehash: 97a0e6cbbd8972f58f9eedcfeb8aff1f93694064
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765671"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="a4d0c-102">ICLRRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="a4d0c-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="a4d0c-103">Detiene la ejecución de código por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a4d0c-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4d0c-104">Este método no liberar los recursos en el host, descargar dominios de aplicación o destruir subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="a4d0c-105">Debe finalizar el proceso para liberar estos recursos.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d0c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4d0c-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a4d0c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a4d0c-107">Return Value</span></span>  
  
|<span data-ttu-id="a4d0c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4d0c-108">HRESULT</span></span>|<span data-ttu-id="a4d0c-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a4d0c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4d0c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4d0c-110">S_OK</span></span>|<span data-ttu-id="a4d0c-111">`Stop` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="a4d0c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4d0c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4d0c-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4d0c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4d0c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4d0c-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-115">The call timed out.</span></span>|  
|<span data-ttu-id="a4d0c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4d0c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4d0c-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4d0c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4d0c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4d0c-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4d0c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4d0c-120">E_FAIL</span></span>|<span data-ttu-id="a4d0c-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4d0c-122">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4d0c-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a4d0c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4d0c-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4d0c-124">Requirements</span></span>  
 <span data-ttu-id="a4d0c-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4d0c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d0c-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a4d0c-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4d0c-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4d0c-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4d0c-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4d0c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d0c-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4d0c-129">See also</span></span>

- [<span data-ttu-id="a4d0c-130">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4d0c-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
