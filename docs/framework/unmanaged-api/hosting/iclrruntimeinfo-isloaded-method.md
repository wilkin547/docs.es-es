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
ms.openlocfilehash: 66ae74deba9ceab9d1ea6b2c0b96a87bf44f32ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714931"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="63e4f-102">ICLRRuntimeInfo::IsLoaded (Método)</span><span class="sxs-lookup"><span data-stu-id="63e4f-102">ICLRRuntimeInfo::IsLoaded Method</span></span>

<span data-ttu-id="63e4f-103">Indica si el Common Language Runtime (CLR) asociado a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="63e4f-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="63e4f-104">Un tiempo de ejecución se puede cargar sin que se inicie también.</span><span class="sxs-lookup"><span data-stu-id="63e4f-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63e4f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63e4f-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63e4f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63e4f-106">Parameters</span></span>  

 `hndProcess`  
 <span data-ttu-id="63e4f-107">de Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="63e4f-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="63e4f-108">[out] `true` Si el CLR se carga en el proceso; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="63e4f-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63e4f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63e4f-109">Return Value</span></span>  

 <span data-ttu-id="63e4f-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="63e4f-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="63e4f-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63e4f-111">HRESULT</span></span>|<span data-ttu-id="63e4f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="63e4f-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63e4f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="63e4f-113">S_OK</span></span>|<span data-ttu-id="63e4f-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="63e4f-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="63e4f-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="63e4f-115">E_POINTER</span></span>|<span data-ttu-id="63e4f-116">`pbLoaded` es null.</span><span class="sxs-lookup"><span data-stu-id="63e4f-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63e4f-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63e4f-117">Remarks</span></span>  

 <span data-ttu-id="63e4f-118">Este método es compatible con las versiones anteriores de las siguientes funciones e interfaces:</span><span class="sxs-lookup"><span data-stu-id="63e4f-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="63e4f-119">[ICorRuntimeHost](icorruntimehost-interface.md) (interfaz) (en la API de hospedaje de .NET Framework versión 1).</span><span class="sxs-lookup"><span data-stu-id="63e4f-119">[ICorRuntimeHost](icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="63e4f-120">Interfaz [ICLRRuntimeHost](iclrruntimehost-interface.md) (en la API de hospedaje .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="63e4f-120">[ICLRRuntimeHost](iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="63e4f-121">`CorBindTo*`Funciones en desuso (consulte [funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="63e4f-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="63e4f-122">Un host puede llamar a una de las `CorBindTo*` funciones en desuso, como la función [CorBindToRuntime](corbindtoruntime-function.md) , para crear una instancia de una versión específica de CLR.</span><span class="sxs-lookup"><span data-stu-id="63e4f-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="63e4f-123">Después, el host podría llamar al método [ICLRMetaHost:: GetRuntime](iclrmetahost-getruntime-method.md) y especificar el mismo número de versión para obtener una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="63e4f-123">The host could then call the [ICLRMetaHost::GetRuntime](iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="63e4f-124">Si el host llama a continuación al `IsLoaded` método en la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) devuelta, `pbLoaded` devuelve; de `true` lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="63e4f-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63e4f-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63e4f-125">Requirements</span></span>  

 <span data-ttu-id="63e4f-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63e4f-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63e4f-127">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="63e4f-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="63e4f-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63e4f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63e4f-129">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63e4f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e4f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63e4f-130">See also</span></span>

- [<span data-ttu-id="63e4f-131">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="63e4f-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="63e4f-132">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="63e4f-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="63e4f-133">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="63e4f-133">Hosting</span></span>](index.md)
