---
title: ICLRRuntimeInfo::IsLoaded (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69a3b0921528ed09ee4ab3a1ede6b9efe565e02a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619239"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="1a8b4-102">ICLRRuntimeInfo::IsLoaded (Método)</span><span class="sxs-lookup"><span data-stu-id="1a8b4-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="1a8b4-103">Indica si common language runtime (CLR) asociados con el [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="1a8b4-104">Un tiempo de ejecución se puede cargar sin también que se está iniciando.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a8b4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a8b4-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a8b4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a8b4-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="1a8b4-107">[in] Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="1a8b4-108">[out] `true` si el CLR se carga en el proceso; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a8b4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1a8b4-109">Return Value</span></span>  
 <span data-ttu-id="1a8b4-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1a8b4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a8b4-111">HRESULT</span></span>|<span data-ttu-id="1a8b4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a8b4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a8b4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a8b4-113">S_OK</span></span>|<span data-ttu-id="1a8b4-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="1a8b4-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1a8b4-115">E_POINTER</span></span>|<span data-ttu-id="1a8b4-116">`pbLoaded` es null.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a8b4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1a8b4-117">Remarks</span></span>  
 <span data-ttu-id="1a8b4-118">Este método es compatible con las funciones y las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a8b4-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
-   <span data-ttu-id="1a8b4-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaz (en la API de hospedaje de la versión 1 de .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="1a8b4-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
-   <span data-ttu-id="1a8b4-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaz (en la API de hospedaje de .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="1a8b4-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
-   <span data-ttu-id="1a8b4-121">En desuso `CorBindTo*` funciones (consulte [funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="1a8b4-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="1a8b4-122">Un host puede llamar a uno de los en desuso `CorBindTo*` funciones, como el [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) función, para crear instancias de una versión específica de CLR.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="1a8b4-123">El host, a continuación, podría llamar a la [ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) método y especifique el mismo número de versión para obtener un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="1a8b4-124">Si el host, a continuación, llama el `IsLoaded` método en el valor devuelto [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz, `pbLoaded` devuelve `true`; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="1a8b4-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a8b4-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a8b4-125">Requirements</span></span>  
 <span data-ttu-id="1a8b4-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a8b4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a8b4-127">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1a8b4-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1a8b4-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a8b4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a8b4-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a8b4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a8b4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a8b4-130">See also</span></span>
- [<span data-ttu-id="1a8b4-131">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a8b4-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="1a8b4-132">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1a8b4-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1a8b4-133">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="1a8b4-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
