---
description: 'Más información acerca de: ICLRRuntimeInfo:: IsLoaded (método)'
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
ms.openlocfilehash: e6a5984dbd2340fe07af546dd48ae6760d5b4271
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799712"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="ff20e-103">ICLRRuntimeInfo::IsLoaded (Método)</span><span class="sxs-lookup"><span data-stu-id="ff20e-103">ICLRRuntimeInfo::IsLoaded Method</span></span>

<span data-ttu-id="ff20e-104">Indica si el Common Language Runtime (CLR) asociado a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="ff20e-104">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="ff20e-105">Un tiempo de ejecución se puede cargar sin que se inicie también.</span><span class="sxs-lookup"><span data-stu-id="ff20e-105">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff20e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff20e-106">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff20e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff20e-107">Parameters</span></span>  

 `hndProcess`  
 <span data-ttu-id="ff20e-108">de Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="ff20e-108">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="ff20e-109">[out] `true` Si el CLR se carga en el proceso; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="ff20e-109">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff20e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff20e-110">Return Value</span></span>  

 <span data-ttu-id="ff20e-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ff20e-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ff20e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff20e-112">HRESULT</span></span>|<span data-ttu-id="ff20e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff20e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff20e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff20e-114">S_OK</span></span>|<span data-ttu-id="ff20e-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff20e-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="ff20e-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ff20e-116">E_POINTER</span></span>|<span data-ttu-id="ff20e-117">`pbLoaded` es null.</span><span class="sxs-lookup"><span data-stu-id="ff20e-117">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff20e-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ff20e-118">Remarks</span></span>  

 <span data-ttu-id="ff20e-119">Este método es compatible con las versiones anteriores de las siguientes funciones e interfaces:</span><span class="sxs-lookup"><span data-stu-id="ff20e-119">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="ff20e-120">[ICorRuntimeHost](icorruntimehost-interface.md) (interfaz) (en la API de hospedaje de .NET Framework versión 1).</span><span class="sxs-lookup"><span data-stu-id="ff20e-120">[ICorRuntimeHost](icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="ff20e-121">Interfaz [ICLRRuntimeHost](iclrruntimehost-interface.md) (en la API de hospedaje .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="ff20e-121">[ICLRRuntimeHost](iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="ff20e-122">`CorBindTo*`Funciones en desuso (consulte [funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="ff20e-122">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="ff20e-123">Un host puede llamar a una de las `CorBindTo*` funciones en desuso, como la función [CorBindToRuntime](corbindtoruntime-function.md) , para crear una instancia de una versión específica de CLR.</span><span class="sxs-lookup"><span data-stu-id="ff20e-123">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="ff20e-124">Después, el host podría llamar al método [ICLRMetaHost:: GetRuntime](iclrmetahost-getruntime-method.md) y especificar el mismo número de versión para obtener una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ff20e-124">The host could then call the [ICLRMetaHost::GetRuntime](iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="ff20e-125">Si el host llama a continuación al `IsLoaded` método en la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) devuelta, `pbLoaded` devuelve; de `true` lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="ff20e-125">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff20e-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff20e-126">Requirements</span></span>  

 <span data-ttu-id="ff20e-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff20e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff20e-128">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="ff20e-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ff20e-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff20e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff20e-130">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff20e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff20e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff20e-131">See also</span></span>

- [<span data-ttu-id="ff20e-132">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff20e-132">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ff20e-133">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ff20e-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="ff20e-134">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ff20e-134">Hosting</span></span>](index.md)
