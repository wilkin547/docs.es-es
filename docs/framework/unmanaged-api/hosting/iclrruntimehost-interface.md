---
title: ICLRRuntimeHost (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 247c50eb88f3b1814fd5342ded4ed3c98d4b60a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="e8f01-102">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8f01-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="e8f01-103">Proporciona una funcionalidad similar a la de la [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaz proporcionada en .NET Framework versión 1, con los cambios siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8f01-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
-   <span data-ttu-id="e8f01-104">La adición de la [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) método para establecer la interfaz de control de host.</span><span class="sxs-lookup"><span data-stu-id="e8f01-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
-   <span data-ttu-id="e8f01-105">La omisión de algunos métodos proporcionados por `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="e8f01-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8f01-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="e8f01-106">Methods</span></span>  
  
|<span data-ttu-id="e8f01-107">Método</span><span class="sxs-lookup"><span data-stu-id="e8f01-107">Method</span></span>|<span data-ttu-id="e8f01-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8f01-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8f01-109">ExecuteApplication (método)</span><span class="sxs-lookup"><span data-stu-id="e8f01-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="e8f01-110">Se utiliza en escenarios de implementación de ClickOnce basada en manifiestos para especificar la aplicación que se debe activar en un nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="e8f01-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="e8f01-111">ExecuteInAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="e8f01-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="e8f01-112">Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="e8f01-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="e8f01-113">ExecuteInDefaultAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="e8f01-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="e8f01-114">Se invoca el método especificado del tipo especificado en el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="e8f01-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="e8f01-115">GetCLRControl (método)</span><span class="sxs-lookup"><span data-stu-id="e8f01-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="e8f01-116">Obtiene un puntero de interfaz de tipo [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) que los hosts pueden usar para personalizar algunos aspectos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e8f01-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="e8f01-117">GetCurrentAppDomainId (método)</span><span class="sxs-lookup"><span data-stu-id="e8f01-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="e8f01-118">Obtiene el identificador numérico de la <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="e8f01-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="e8f01-119">SetHostControl (método)</span><span class="sxs-lookup"><span data-stu-id="e8f01-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="e8f01-120">Establece la interfaz de control de host.</span><span class="sxs-lookup"><span data-stu-id="e8f01-120">Sets the host control interface.</span></span> <span data-ttu-id="e8f01-121">Debe llamar a `SetHostControl` antes de llamar a `Start`.</span><span class="sxs-lookup"><span data-stu-id="e8f01-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="e8f01-122">Start (método)</span><span class="sxs-lookup"><span data-stu-id="e8f01-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="e8f01-123">Inicializa el CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="e8f01-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="e8f01-124">Stop (método)</span><span class="sxs-lookup"><span data-stu-id="e8f01-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="e8f01-125">Detiene la ejecución del código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e8f01-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="e8f01-126">UnloadAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="e8f01-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="e8f01-127">Descarga el <xref:System.AppDomain> que se corresponde con el identificador numérico especificado.</span><span class="sxs-lookup"><span data-stu-id="e8f01-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8f01-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8f01-128">Remarks</span></span>  
 <span data-ttu-id="e8f01-129">A partir de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use la [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interfaz para obtener un puntero a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) de interfaz y, a continuación, llame a la [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) método para obtener un puntero a `ICLRRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="e8f01-129">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="e8f01-130">En versiones anteriores de .NET Framework, el host obtiene un puntero a un `ICLRRuntimeHost` instancia mediante una llamada a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="e8f01-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="e8f01-131">Para proporcionar implementaciones de cualquiera de las tecnologías proporcionadas en la versión 2.0 de .NET Framework, debe usar `ICLRRuntimeHost` en lugar de `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="e8f01-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8f01-132">No llame a la [iniciar](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método antes de llamar a la [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) método para activar una aplicación basada en manifiestos.</span><span class="sxs-lookup"><span data-stu-id="e8f01-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="e8f01-133">Si el `Start` método se llama en primer lugar, el `ExecuteApplication` se producirá un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="e8f01-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8f01-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8f01-134">Requirements</span></span>  
 <span data-ttu-id="e8f01-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8f01-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f01-136">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e8f01-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8f01-137">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8f01-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8f01-138">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8f01-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f01-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8f01-139">See Also</span></span>  
 [<span data-ttu-id="e8f01-140">CorBindToCurrentRuntime (función)</span><span class="sxs-lookup"><span data-stu-id="e8f01-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="e8f01-141">CorBindToRuntimeEx (función)</span><span class="sxs-lookup"><span data-stu-id="e8f01-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="e8f01-142">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8f01-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="e8f01-143">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8f01-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="e8f01-144">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e8f01-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="e8f01-145">CLRRuntimeHost (coclase)</span><span class="sxs-lookup"><span data-stu-id="e8f01-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
