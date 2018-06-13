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
ms.openlocfilehash: 8d479e271c2cc4ebf9ea6ff349fd28bff37c3857
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436103"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="49de1-102">ICLRRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="49de1-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="49de1-103">Detiene la ejecución de código por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="49de1-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="49de1-104">Este método no liberar recursos para el host, descargar dominios de aplicación o destruir subprocesos.</span><span class="sxs-lookup"><span data-stu-id="49de1-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="49de1-105">Debe finalizar el proceso para liberar estos recursos.</span><span class="sxs-lookup"><span data-stu-id="49de1-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49de1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49de1-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="49de1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="49de1-107">Return Value</span></span>  
  
|<span data-ttu-id="49de1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49de1-108">HRESULT</span></span>|<span data-ttu-id="49de1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="49de1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49de1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="49de1-110">S_OK</span></span>|<span data-ttu-id="49de1-111">`Stop` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="49de1-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="49de1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="49de1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="49de1-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="49de1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="49de1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="49de1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="49de1-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="49de1-115">The call timed out.</span></span>|  
|<span data-ttu-id="49de1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="49de1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="49de1-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="49de1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="49de1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="49de1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="49de1-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="49de1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="49de1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="49de1-120">E_FAIL</span></span>|<span data-ttu-id="49de1-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="49de1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="49de1-122">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="49de1-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="49de1-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="49de1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49de1-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49de1-124">Requirements</span></span>  
 <span data-ttu-id="49de1-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49de1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49de1-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="49de1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49de1-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49de1-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49de1-128">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49de1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49de1-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="49de1-129">See Also</span></span>  
 [<span data-ttu-id="49de1-130">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="49de1-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
