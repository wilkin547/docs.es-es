---
title: "ICLRRuntimeHost::GetCLRControl (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4072c21ea002523fe8086151a40c4e17b775ebbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="435d0-102">ICLRRuntimeHost::GetCLRControl (Método)</span><span class="sxs-lookup"><span data-stu-id="435d0-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="435d0-103">Obtiene un puntero de interfaz de tipo [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) que los hosts pueden usar para personalizar algunos aspectos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="435d0-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="435d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="435d0-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="435d0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="435d0-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="435d0-106">[out] Un puntero de interfaz de tipo [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) que permite a los hosts configurar aspectos adicionales de CLR.</span><span class="sxs-lookup"><span data-stu-id="435d0-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="435d0-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="435d0-107">Return Value</span></span>  
  
|<span data-ttu-id="435d0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="435d0-108">HRESULT</span></span>|<span data-ttu-id="435d0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="435d0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="435d0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="435d0-110">S_OK</span></span>|<span data-ttu-id="435d0-111">`GetCLRControl`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="435d0-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="435d0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="435d0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="435d0-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="435d0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="435d0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="435d0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="435d0-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="435d0-115">The call timed out.</span></span>|  
|<span data-ttu-id="435d0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="435d0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="435d0-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="435d0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="435d0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="435d0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="435d0-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="435d0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="435d0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="435d0-120">E_FAIL</span></span>|<span data-ttu-id="435d0-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="435d0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="435d0-122">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="435d0-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="435d0-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="435d0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="435d0-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="435d0-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="435d0-125">Ya ha iniciado el CLR.</span><span class="sxs-lookup"><span data-stu-id="435d0-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="435d0-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="435d0-126">Remarks</span></span>  
 <span data-ttu-id="435d0-127">`ICLRControl`proporciona el [GetCLRManager (método)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método, que permite que el host obtener un puntero de interfaz a uno de los tipos de administrador.</span><span class="sxs-lookup"><span data-stu-id="435d0-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="435d0-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="435d0-128">Requirements</span></span>  
 <span data-ttu-id="435d0-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="435d0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="435d0-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="435d0-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="435d0-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="435d0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="435d0-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="435d0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="435d0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="435d0-133">See Also</span></span>  
 [<span data-ttu-id="435d0-134">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="435d0-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="435d0-135">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="435d0-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
