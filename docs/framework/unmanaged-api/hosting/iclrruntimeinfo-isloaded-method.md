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
ms.openlocfilehash: e0ab16348abbaff00152f2b259ccafdd331174df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136356"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="84359-102">ICLRRuntimeInfo::IsLoaded (Método)</span><span class="sxs-lookup"><span data-stu-id="84359-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="84359-103">Indica si el Common Language Runtime (CLR) asociado a la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="84359-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="84359-104">Un tiempo de ejecución se puede cargar sin que se inicie también.</span><span class="sxs-lookup"><span data-stu-id="84359-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84359-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84359-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84359-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84359-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="84359-107">de Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="84359-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="84359-108">[out] `true` si el CLR se carga en el proceso; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="84359-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84359-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="84359-109">Return Value</span></span>  
 <span data-ttu-id="84359-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="84359-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="84359-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84359-111">HRESULT</span></span>|<span data-ttu-id="84359-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="84359-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84359-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="84359-113">S_OK</span></span>|<span data-ttu-id="84359-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="84359-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="84359-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="84359-115">E_POINTER</span></span>|<span data-ttu-id="84359-116">`pbLoaded` es null.</span><span class="sxs-lookup"><span data-stu-id="84359-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84359-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="84359-117">Remarks</span></span>  
 <span data-ttu-id="84359-118">Este método es compatible con las versiones anteriores de las siguientes funciones e interfaces:</span><span class="sxs-lookup"><span data-stu-id="84359-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="84359-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) (interfaz) (en la API de hospedaje de .NET Framework versión 1).</span><span class="sxs-lookup"><span data-stu-id="84359-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="84359-120">Interfaz [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) (en la API de hospedaje .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="84359-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="84359-121">Funciones de `CorBindTo*` en desuso (consulte [funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="84359-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="84359-122">Un host puede llamar a una de las funciones `CorBindTo*` en desuso, como la función [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) , para crear una instancia de una versión específica de CLR.</span><span class="sxs-lookup"><span data-stu-id="84359-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="84359-123">Después, el host podría llamar al método [ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) y especificar el mismo número de versión para obtener una interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="84359-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="84359-124">Si el host llama a continuación al método `IsLoaded` en la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) devuelta, `pbLoaded` devuelve `true`; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="84359-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84359-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84359-125">Requirements</span></span>  
 <span data-ttu-id="84359-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84359-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84359-127">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="84359-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="84359-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84359-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84359-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84359-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84359-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="84359-130">See also</span></span>

- [<span data-ttu-id="84359-131">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84359-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="84359-132">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="84359-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="84359-133">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="84359-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
