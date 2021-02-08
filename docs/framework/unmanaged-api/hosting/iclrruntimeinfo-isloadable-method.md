---
description: 'Más información acerca de: ICLRRuntimeInfo:: Isloadable ((método)'
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
ms.openlocfilehash: cf63212350bfbd18e2a312add72818b163c32d0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789793"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="8f8cf-103">ICLRRuntimeInfo::IsLoadable (Método)</span><span class="sxs-lookup"><span data-stu-id="8f8cf-103">ICLRRuntimeInfo::IsLoadable Method</span></span>

<span data-ttu-id="8f8cf-104">Indica si el tiempo de ejecución asociado a esta interfaz se puede cargar en el proceso actual, teniendo en cuenta otros tiempos de ejecución que podrían haberse cargado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8f8cf-104">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f8cf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f8cf-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f8cf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f8cf-106">Parameters</span></span>  

 `pbLoadable`  
 <span data-ttu-id="8f8cf-107">[out] `true` Si este Runtime se podría cargar en el proceso actual; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="8f8cf-107">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f8cf-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8f8cf-108">Return Value</span></span>  

 <span data-ttu-id="8f8cf-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="8f8cf-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8f8cf-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f8cf-110">HRESULT</span></span>|<span data-ttu-id="8f8cf-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f8cf-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f8cf-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f8cf-112">S_OK</span></span>|<span data-ttu-id="8f8cf-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8f8cf-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="8f8cf-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8f8cf-114">E_POINTER</span></span>|<span data-ttu-id="8f8cf-115">`pbLoadable` es null.</span><span class="sxs-lookup"><span data-stu-id="8f8cf-115">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f8cf-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8f8cf-116">Remarks</span></span>  

 <span data-ttu-id="8f8cf-117">Si ya se ha cargado otro Runtime en el proceso y el tiempo de ejecución asociado a esta interfaz se puede cargar para la ejecución en paralelo en proceso, `pbLoadable` devuelve `true` .</span><span class="sxs-lookup"><span data-stu-id="8f8cf-117">If another runtime is already loaded into the process, and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="8f8cf-118">Si los dos tiempos de ejecución no se pueden ejecutar en paralelo, `pbLoadable` devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="8f8cf-118">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="8f8cf-119">Por ejemplo, la versión 4 de Common Language Runtime (CLR) se puede ejecutar en paralelo en el mismo proceso con la versión de CLR 2,0 o la versión 1,1 de CLR.</span><span class="sxs-lookup"><span data-stu-id="8f8cf-119">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="8f8cf-120">Sin embargo, la versión de CLR 1,1 y la versión de CLR 2,0 no se pueden ejecutar en paralelo.</span><span class="sxs-lookup"><span data-stu-id="8f8cf-120">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="8f8cf-121">Si no se carga ningún Runtime en el proceso, este método siempre devuelve `true` .</span><span class="sxs-lookup"><span data-stu-id="8f8cf-121">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f8cf-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f8cf-122">Requirements</span></span>  

 <span data-ttu-id="8f8cf-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f8cf-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f8cf-124">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="8f8cf-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8f8cf-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f8cf-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f8cf-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f8cf-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8cf-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f8cf-127">See also</span></span>

- [<span data-ttu-id="8f8cf-128">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f8cf-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="8f8cf-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8f8cf-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="8f8cf-130">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="8f8cf-130">Hosting</span></span>](index.md)
