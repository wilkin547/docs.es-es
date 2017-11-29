---
title: "ICLRRuntimeInfo::IsLoadable (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsLoadable
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ada33942af97f476de25c2ea3243818808e2dc9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="ba8eb-102">ICLRRuntimeInfo::IsLoadable (Método)</span><span class="sxs-lookup"><span data-stu-id="ba8eb-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="ba8eb-103">Indica si el tiempo de ejecución asociado a esta interfaz se puede cargar en el proceso actual, teniendo en cuenta otros tiempos de ejecución que puede que ya esté cargado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba8eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba8eb-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba8eb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba8eb-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="ba8eb-106">[out] `true` si este runtime se pudo cargar en el proceso actual; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba8eb-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ba8eb-107">Return Value</span></span>  
 <span data-ttu-id="ba8eb-108">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ba8eb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba8eb-109">HRESULT</span></span>|<span data-ttu-id="ba8eb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba8eb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba8eb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba8eb-111">S_OK</span></span>|<span data-ttu-id="ba8eb-112">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="ba8eb-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ba8eb-113">E_POINTER</span></span>|<span data-ttu-id="ba8eb-114">`pbLoadable` es null.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba8eb-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba8eb-115">Remarks</span></span>  
 <span data-ttu-id="ba8eb-116">Si otro tiempo de ejecución ya se carga en el proceso y el tiempo de ejecución asociado a esta interfaz se puede cargar para la ejecución de en paralelo en proceso, `pbLoadable` devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="ba8eb-117">Si los dos tiempos de ejecución no pueden ejecutar en paralelo en proceso, `pbLoadable` devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="ba8eb-118">Por ejemplo, common language runtime (CLR) versión 4 puede ejecutar en paralelo en el mismo proceso con la versión 2.0 de CLR o CLR versión 1.1.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="ba8eb-119">Sin embargo, CLR versión 1.1 y versión 2.0 de CLR no pueden ejecutar en paralelo en proceso.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="ba8eb-120">Si el tiempo de ejecución no se carga en el proceso, este método devuelve siempre `true`.</span><span class="sxs-lookup"><span data-stu-id="ba8eb-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba8eb-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba8eb-121">Requirements</span></span>  
 <span data-ttu-id="ba8eb-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba8eb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba8eb-123">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ba8eb-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ba8eb-124">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba8eb-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba8eb-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba8eb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8eb-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba8eb-126">See Also</span></span>  
 [<span data-ttu-id="ba8eb-127">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba8eb-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="ba8eb-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ba8eb-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="ba8eb-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ba8eb-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
