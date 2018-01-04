---
title: "ICLRRuntimeHost::ExecuteInDefaultAppDomain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec4cf37150cab7b52066a884b6fe117b0e611106
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="8928b-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="8928b-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="8928b-103">Llama al método especificado del tipo especificado en el ensamblado administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="8928b-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8928b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8928b-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8928b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8928b-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="8928b-106">[in] La ruta de acceso a la <xref:System.Reflection.Assembly> que define la <xref:System.Type> cuyo método es que se debe invocar.</span><span class="sxs-lookup"><span data-stu-id="8928b-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="8928b-107">[in] El nombre de la <xref:System.Type> que define el método que se invoca.</span><span class="sxs-lookup"><span data-stu-id="8928b-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="8928b-108">[in] El nombre del método que se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="8928b-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="8928b-109">[in] El parámetro de cadena para pasar al método.</span><span class="sxs-lookup"><span data-stu-id="8928b-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="8928b-110">[out] El valor entero devuelto por el método invocado.</span><span class="sxs-lookup"><span data-stu-id="8928b-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8928b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8928b-111">Return Value</span></span>  
  
|<span data-ttu-id="8928b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8928b-112">HRESULT</span></span>|<span data-ttu-id="8928b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8928b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8928b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8928b-114">S_OK</span></span>|<span data-ttu-id="8928b-115">`ExecuteInDefaultAppDomain`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8928b-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="8928b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8928b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8928b-117">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8928b-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8928b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8928b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8928b-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8928b-119">The call timed out.</span></span>|  
|<span data-ttu-id="8928b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8928b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8928b-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8928b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8928b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8928b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8928b-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="8928b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8928b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8928b-124">E_FAIL</span></span>|<span data-ttu-id="8928b-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="8928b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8928b-126">Si el método devuelve E_FAIL, ya no es utilizable dentro del proceso de la CRL.</span><span class="sxs-lookup"><span data-stu-id="8928b-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="8928b-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8928b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8928b-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8928b-128">Remarks</span></span>  
 <span data-ttu-id="8928b-129">El método invocado debe tener la siguiente firma:</span><span class="sxs-lookup"><span data-stu-id="8928b-129">The invoked method must have the following signature:</span></span>  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="8928b-130">donde `pwzMethodName` representa el nombre del método invocado, y `pwzArgument` representa el valor de cadena que se pasa como un parámetro a ese método.</span><span class="sxs-lookup"><span data-stu-id="8928b-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="8928b-131">Si el valor HRESULT se establece en S_OK, `pReturnValue` se establece en el valor entero devuelto por el método invocado.</span><span class="sxs-lookup"><span data-stu-id="8928b-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="8928b-132">En caso contrario, `pReturnValue` no se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="8928b-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8928b-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8928b-133">Requirements</span></span>  
 <span data-ttu-id="8928b-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8928b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8928b-135">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8928b-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8928b-136">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8928b-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8928b-137">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8928b-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8928b-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="8928b-138">See Also</span></span>  
 [<span data-ttu-id="8928b-139">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8928b-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
