---
title: "LockClrVersion (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LockClrVersion
helpviewer_keywords: LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be41ae47f78a41e2f2be10a1e38d938dde9a4701
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="lockclrversion-function"></a><span data-ttu-id="1441a-102">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="1441a-102">LockClrVersion Function</span></span>
<span data-ttu-id="1441a-103">Permite al host determinar qué versión de common language runtime (CLR) que se utilizará en el proceso antes de inicializar el CLR de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="1441a-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="1441a-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1441a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1441a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1441a-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1441a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1441a-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="1441a-107">[in] La función que invocará el CLR en la inicialización.</span><span class="sxs-lookup"><span data-stu-id="1441a-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="1441a-108">[in] La función para ser llamado por el host para informar a CLR que la inicialización se está iniciando.</span><span class="sxs-lookup"><span data-stu-id="1441a-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="1441a-109">[in] La función para ser llamado por el host para informar a CLR que la inicialización está completa.</span><span class="sxs-lookup"><span data-stu-id="1441a-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1441a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1441a-110">Return Value</span></span>  
 <span data-ttu-id="1441a-111">Este método devuelve códigos de error COM estándar, tal como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="1441a-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="1441a-112">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="1441a-112">Return code</span></span>|<span data-ttu-id="1441a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1441a-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1441a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1441a-114">S_OK</span></span>|<span data-ttu-id="1441a-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1441a-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="1441a-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1441a-116">E_INVALIDARG</span></span>|<span data-ttu-id="1441a-117">Uno o varios de los argumentos son null.</span><span class="sxs-lookup"><span data-stu-id="1441a-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1441a-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1441a-118">Remarks</span></span>  
 <span data-ttu-id="1441a-119">El host llama `LockClrVersion` antes de inicializar el CLR.</span><span class="sxs-lookup"><span data-stu-id="1441a-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="1441a-120">`LockClrVersion`toma tres parámetros, todos los cuales son devoluciones de llamada de tipo [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="1441a-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="1441a-121">Este tipo se define como sigue.</span><span class="sxs-lookup"><span data-stu-id="1441a-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="1441a-122">Los pasos siguientes se producen cuando se inicializa el tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="1441a-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1.  <span data-ttu-id="1441a-123">El host llama [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o una de las demás funciones de inicialización en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1441a-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="1441a-124">Como alternativa, el host puede inicializar el tiempo de ejecución mediante la activación de objetos COM.</span><span class="sxs-lookup"><span data-stu-id="1441a-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2.  <span data-ttu-id="1441a-125">El tiempo de ejecución llama a la función especificada por el `hostCallback` parámetro.</span><span class="sxs-lookup"><span data-stu-id="1441a-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3.  <span data-ttu-id="1441a-126">La función especificada por `hostCallback` , a continuación, realiza la siguiente secuencia de llamadas:</span><span class="sxs-lookup"><span data-stu-id="1441a-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    -   <span data-ttu-id="1441a-127">La función especificada por el `pBeginHostSetup` parámetro.</span><span class="sxs-lookup"><span data-stu-id="1441a-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    -   <span data-ttu-id="1441a-128">`CorBindToRuntimeEx`(o a otra función de inicialización en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="1441a-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    -   <span data-ttu-id="1441a-129">[ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="1441a-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    -   <span data-ttu-id="1441a-130">[ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="1441a-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    -   <span data-ttu-id="1441a-131">La función especificada por el `pEndHostSetup` parámetro.</span><span class="sxs-lookup"><span data-stu-id="1441a-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="1441a-132">Todas las llamadas de `pBeginHostSetup` a `pEndHostSetup` se debe producir en un único subproceso o fibra, con la misma pila lógica.</span><span class="sxs-lookup"><span data-stu-id="1441a-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="1441a-133">Este subproceso puede ser diferente del subproceso en el que `hostCallback` se llama.</span><span class="sxs-lookup"><span data-stu-id="1441a-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1441a-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1441a-134">Requirements</span></span>  
 <span data-ttu-id="1441a-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1441a-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1441a-136">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1441a-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1441a-137">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1441a-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1441a-138">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1441a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1441a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="1441a-139">See Also</span></span>  
 [<span data-ttu-id="1441a-140">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="1441a-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
