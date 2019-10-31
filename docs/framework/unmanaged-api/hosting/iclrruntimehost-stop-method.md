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
ms.openlocfilehash: 0b59532d18848f1896977aa37f0a9f54a939aa75
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120378"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="8a0e5-102">ICLRRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="8a0e5-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="8a0e5-103">Detiene la ejecución de código por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8a0e5-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8a0e5-104">Este método no libera los recursos en el host, descarga los dominios de aplicación ni destruye los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="8a0e5-105">Debe finalizar el proceso para liberar estos recursos.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a0e5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a0e5-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8a0e5-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8a0e5-107">Return Value</span></span>  
  
|<span data-ttu-id="8a0e5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a0e5-108">HRESULT</span></span>|<span data-ttu-id="8a0e5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a0e5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a0e5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a0e5-110">S_OK</span></span>|<span data-ttu-id="8a0e5-111">`Stop` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="8a0e5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a0e5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a0e5-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a0e5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a0e5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a0e5-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-115">The call timed out.</span></span>|  
|<span data-ttu-id="8a0e5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a0e5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a0e5-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a0e5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a0e5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a0e5-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a0e5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a0e5-120">E_FAIL</span></span>|<span data-ttu-id="8a0e5-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a0e5-122">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a0e5-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8a0e5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a0e5-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a0e5-124">Requirements</span></span>  
 <span data-ttu-id="8a0e5-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a0e5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a0e5-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8a0e5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a0e5-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8a0e5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a0e5-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a0e5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a0e5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a0e5-129">See also</span></span>

- [<span data-ttu-id="8a0e5-130">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a0e5-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
