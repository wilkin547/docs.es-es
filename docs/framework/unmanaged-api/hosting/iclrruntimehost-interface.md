---
title: ICLRRuntimeHost (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f159c0b57f2087b608fac8cbc9b9c64ceb063a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965990"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="06e80-102">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="06e80-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="06e80-103">Proporciona una funcionalidad similar a la de la interfaz [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) proporcionada en el .NET Framework versión 1, con los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="06e80-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="06e80-104">La adición del método [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) para establecer la interfaz de control host.</span><span class="sxs-lookup"><span data-stu-id="06e80-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="06e80-105">La omisión de algunos métodos proporcionados `ICorRuntimeHost`por.</span><span class="sxs-lookup"><span data-stu-id="06e80-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06e80-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="06e80-106">Methods</span></span>  
  
|<span data-ttu-id="06e80-107">Método</span><span class="sxs-lookup"><span data-stu-id="06e80-107">Method</span></span>|<span data-ttu-id="06e80-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="06e80-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06e80-109">ExecuteApplication (método)</span><span class="sxs-lookup"><span data-stu-id="06e80-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="06e80-110">Se usa en escenarios de implementación ClickOnce basados en manifiesto para especificar la aplicación que se va a activar en un dominio nuevo.</span><span class="sxs-lookup"><span data-stu-id="06e80-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="06e80-111">ExecuteInAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="06e80-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="06e80-112">Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="06e80-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="06e80-113">ExecuteInDefaultAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="06e80-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="06e80-114">Invoca el método especificado del tipo especificado en el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="06e80-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="06e80-115">GetCLRControl (método)</span><span class="sxs-lookup"><span data-stu-id="06e80-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="06e80-116">Obtiene un puntero de interfaz de tipo [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) que los hosts pueden utilizar para personalizar los aspectos del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="06e80-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="06e80-117">GetCurrentAppDomainId (método)</span><span class="sxs-lookup"><span data-stu-id="06e80-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="06e80-118">Obtiene el identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="06e80-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="06e80-119">SetHostControl (método)</span><span class="sxs-lookup"><span data-stu-id="06e80-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="06e80-120">Establece la interfaz de control host.</span><span class="sxs-lookup"><span data-stu-id="06e80-120">Sets the host control interface.</span></span> <span data-ttu-id="06e80-121">Debe llamar a `SetHostControl` antes de `Start`llamar a.</span><span class="sxs-lookup"><span data-stu-id="06e80-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="06e80-122">Start (método)</span><span class="sxs-lookup"><span data-stu-id="06e80-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="06e80-123">Inicializa CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="06e80-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="06e80-124">Stop (método)</span><span class="sxs-lookup"><span data-stu-id="06e80-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="06e80-125">Detiene la ejecución del código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="06e80-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="06e80-126">UnloadAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="06e80-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="06e80-127">Descarga el <xref:System.AppDomain> que corresponde al identificador numérico especificado.</span><span class="sxs-lookup"><span data-stu-id="06e80-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06e80-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06e80-128">Remarks</span></span>  
 <span data-ttu-id="06e80-129">A partir de la .NET Framework 4, use la interfaz [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) para obtener un puntero a la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) y, a continuación, llame al método [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) para obtener `ICLRRuntimeHost`un puntero a.</span><span class="sxs-lookup"><span data-stu-id="06e80-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="06e80-130">En versiones anteriores del .NET Framework, el host obtiene un puntero a una `ICLRRuntimeHost` instancia llamando a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="06e80-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="06e80-131">Para proporcionar implementaciones de cualquiera de las tecnologías que se proporcionan en la .NET Framework versión 2,0, debe `ICLRRuntimeHost` utilizar en lugar `ICorRuntimeHost`de.</span><span class="sxs-lookup"><span data-stu-id="06e80-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="06e80-132">No llame al método [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) antes de llamar al método [ExecuteApplication (](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) para activar una aplicación basada en manifiesto.</span><span class="sxs-lookup"><span data-stu-id="06e80-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="06e80-133">Si se `Start` llama primero al método, se `ExecuteApplication` producirá un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="06e80-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06e80-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06e80-134">Requirements</span></span>  
 <span data-ttu-id="06e80-135">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06e80-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06e80-136">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06e80-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06e80-137">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="06e80-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06e80-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06e80-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e80-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="06e80-139">See also</span></span>

- [<span data-ttu-id="06e80-140">CorBindToCurrentRuntime (función)</span><span class="sxs-lookup"><span data-stu-id="06e80-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="06e80-141">CorBindToRuntimeEx (función)</span><span class="sxs-lookup"><span data-stu-id="06e80-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="06e80-142">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06e80-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="06e80-143">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06e80-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="06e80-144">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="06e80-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="06e80-145">CLRRuntimeHost (coclase)</span><span class="sxs-lookup"><span data-stu-id="06e80-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
