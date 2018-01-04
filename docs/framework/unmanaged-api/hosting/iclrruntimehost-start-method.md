---
title: "ICLRRuntimeHost::Start (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.Start
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9705e4449da3b485bef7e7250ca08473d51387b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="0be38-102">ICLRRuntimeHost::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="0be38-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="0be38-103">Inicializa common language runtime (CLR) en un proceso.</span><span class="sxs-lookup"><span data-stu-id="0be38-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0be38-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0be38-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0be38-105">Return Value</span></span>  
  
|<span data-ttu-id="0be38-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0be38-106">HRESULT</span></span>|<span data-ttu-id="0be38-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0be38-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0be38-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0be38-108">S_OK</span></span>|<span data-ttu-id="0be38-109">`Start`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0be38-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="0be38-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0be38-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0be38-111">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0be38-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0be38-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0be38-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0be38-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="0be38-113">The call timed out.</span></span>|  
|<span data-ttu-id="0be38-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0be38-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0be38-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0be38-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0be38-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0be38-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0be38-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="0be38-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0be38-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0be38-118">E_FAIL</span></span>|<span data-ttu-id="0be38-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="0be38-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0be38-120">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="0be38-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0be38-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0be38-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0be38-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0be38-122">Remarks</span></span>  
 <span data-ttu-id="0be38-123">En muchos escenarios no es necesario llamar a `Start`, ya que el tiempo de ejecución se inicializará automáticamente tras la primera solicitud para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="0be38-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="0be38-124">Sin embargo, puede usar `Start` para especificar exactamente cuándo debe llevarse a cabo el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0be38-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0be38-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0be38-125">Requirements</span></span>  
 <span data-ttu-id="0be38-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0be38-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0be38-127">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0be38-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0be38-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0be38-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0be38-129">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be38-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be38-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="0be38-130">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="0be38-131">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0be38-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
