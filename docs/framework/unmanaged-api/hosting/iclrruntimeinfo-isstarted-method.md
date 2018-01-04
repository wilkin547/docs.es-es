---
title: "ICLRRuntimeInfo::IsStarted (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsStarted
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 991470ca0df3e0cf0470a8c40d3e8e4c40d96026
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="00a08-102">ICLRRuntimeInfo::IsStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="00a08-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="00a08-103">Indica si se ha iniciado el tiempo de ejecución (es decir, si la [ICLRRuntimeHost::](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) se ha llamado y se ha realizado correctamente).</span><span class="sxs-lookup"><span data-stu-id="00a08-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a08-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00a08-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00a08-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00a08-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="00a08-106">[out] `true` si este tiempo de ejecución es iniciar; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="00a08-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="00a08-107">[out] Devuelve las marcas que se usaron para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="00a08-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00a08-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="00a08-108">Return Value</span></span>  
 <span data-ttu-id="00a08-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="00a08-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="00a08-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00a08-110">HRESULT</span></span>|<span data-ttu-id="00a08-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="00a08-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00a08-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="00a08-112">S_OK</span></span>|<span data-ttu-id="00a08-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="00a08-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="00a08-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="00a08-114">E_NOTIMPL</span></span>|<span data-ttu-id="00a08-115">La versión de common language runtime (CLR) es anterior a la versión CLR en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00a08-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00a08-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00a08-116">Remarks</span></span>  
 <span data-ttu-id="00a08-117">Este método no funciona con versiones de CLR anteriores a la versión CLR en el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00a08-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a08-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00a08-118">Requirements</span></span>  
 <span data-ttu-id="00a08-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00a08-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a08-120">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="00a08-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="00a08-121">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="00a08-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00a08-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a08-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a08-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="00a08-123">See Also</span></span>  
 [<span data-ttu-id="00a08-124">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="00a08-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="00a08-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="00a08-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="00a08-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="00a08-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
