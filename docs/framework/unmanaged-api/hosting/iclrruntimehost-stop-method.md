---
description: 'Más información acerca de: ICLRRuntimeHost:: STOP (método)'
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
ms.openlocfilehash: 3e6b1cf2aee95af6354905f6dcdcb678ff785aa6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799742"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="65bfc-103">ICLRRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="65bfc-103">ICLRRuntimeHost::Stop Method</span></span>

<span data-ttu-id="65bfc-104">Detiene la ejecución de código por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="65bfc-104">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="65bfc-105">Este método no libera los recursos en el host, descarga los dominios de aplicación ni destruye los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="65bfc-105">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="65bfc-106">Debe finalizar el proceso para liberar estos recursos.</span><span class="sxs-lookup"><span data-stu-id="65bfc-106">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65bfc-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65bfc-107">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="65bfc-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="65bfc-108">Return Value</span></span>  
  
|<span data-ttu-id="65bfc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65bfc-109">HRESULT</span></span>|<span data-ttu-id="65bfc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="65bfc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65bfc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="65bfc-111">S_OK</span></span>|<span data-ttu-id="65bfc-112">`Stop` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="65bfc-112">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="65bfc-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65bfc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65bfc-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="65bfc-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65bfc-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65bfc-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65bfc-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="65bfc-116">The call timed out.</span></span>|  
|<span data-ttu-id="65bfc-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65bfc-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65bfc-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="65bfc-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65bfc-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65bfc-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65bfc-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="65bfc-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65bfc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65bfc-121">E_FAIL</span></span>|<span data-ttu-id="65bfc-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="65bfc-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65bfc-123">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="65bfc-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65bfc-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="65bfc-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65bfc-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65bfc-125">Requirements</span></span>  

 <span data-ttu-id="65bfc-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65bfc-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65bfc-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="65bfc-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65bfc-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65bfc-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65bfc-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65bfc-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65bfc-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="65bfc-130">See also</span></span>

- [<span data-ttu-id="65bfc-131">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65bfc-131">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
