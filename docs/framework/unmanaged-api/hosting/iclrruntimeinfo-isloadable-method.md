---
title: ICLRRuntimeInfo::IsLoadable (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 586882ad7577c367576da9b32e6d3b8fe2f806c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501219"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="1ec45-102">ICLRRuntimeInfo::IsLoadable (Método)</span><span class="sxs-lookup"><span data-stu-id="1ec45-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="1ec45-103">Indica si el tiempo de ejecución asociado a esta interfaz se puede cargar en el proceso actual, teniendo en cuenta otros tiempos de ejecución que ya es posible que cargarán en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1ec45-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ec45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ec45-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ec45-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ec45-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="1ec45-106">[out] `true` si este tiempo de ejecución se puede cargar en el proceso actual; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1ec45-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ec45-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ec45-107">Return Value</span></span>  
 <span data-ttu-id="1ec45-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="1ec45-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1ec45-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ec45-109">HRESULT</span></span>|<span data-ttu-id="1ec45-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ec45-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ec45-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ec45-111">S_OK</span></span>|<span data-ttu-id="1ec45-112">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ec45-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="1ec45-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1ec45-113">E_POINTER</span></span>|<span data-ttu-id="1ec45-114">`pbLoadable` es null.</span><span class="sxs-lookup"><span data-stu-id="1ec45-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ec45-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ec45-115">Remarks</span></span>  
 <span data-ttu-id="1ec45-116">Si otro tiempo de ejecución ya está cargado en el proceso y el tiempo de ejecución asociado a esta interfaz se puede cargar para su ejecución en paralelo en proceso `pbLoadable` devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="1ec45-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="1ec45-117">Si los dos tiempos de ejecución no pueden ejecutar en paralelo en proceso, `pbLoadable` devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="1ec45-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="1ec45-118">Por ejemplo, puede ejecutar common language runtime (CLR) versión 4 side-by-side en el mismo proceso con la versión 2.0 de CLR o CLR versión 1.1.</span><span class="sxs-lookup"><span data-stu-id="1ec45-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="1ec45-119">Sin embargo, CLR versión 1.1 y versión 2.0 de CLR no pueden ejecutar en paralelo en proceso.</span><span class="sxs-lookup"><span data-stu-id="1ec45-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="1ec45-120">Si no se cargan tiempos de ejecución en el proceso, este método siempre devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="1ec45-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ec45-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ec45-121">Requirements</span></span>  
 <span data-ttu-id="1ec45-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ec45-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ec45-123">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1ec45-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1ec45-124">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ec45-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ec45-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ec45-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec45-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ec45-126">See also</span></span>
- [<span data-ttu-id="1ec45-127">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ec45-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="1ec45-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1ec45-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1ec45-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="1ec45-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
