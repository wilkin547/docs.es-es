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
ms.openlocfilehash: ed32fe643a7722eaf1af38e6079096194690e950
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211403"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="c342b-102">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c342b-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="c342b-103">Proporciona una funcionalidad similar a la de la [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaz proporcionada en .NET Framework versión 1, con los cambios siguientes:</span><span class="sxs-lookup"><span data-stu-id="c342b-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
-   <span data-ttu-id="c342b-104">La adición de la [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) método para establecer la interfaz de control host.</span><span class="sxs-lookup"><span data-stu-id="c342b-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
-   <span data-ttu-id="c342b-105">La omisión de algunos métodos proporcionados por `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="c342b-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c342b-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="c342b-106">Methods</span></span>  
  
|<span data-ttu-id="c342b-107">Método</span><span class="sxs-lookup"><span data-stu-id="c342b-107">Method</span></span>|<span data-ttu-id="c342b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c342b-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c342b-109">Método ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="c342b-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="c342b-110">Se utiliza en escenarios de implementación de ClickOnce basada en manifiestos para especificar la aplicación que debe activarse en un nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="c342b-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="c342b-111">Método ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="c342b-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="c342b-112">Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="c342b-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="c342b-113">Método ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="c342b-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="c342b-114">Invoca el método especificado del tipo especificado en el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="c342b-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="c342b-115">Método GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="c342b-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="c342b-116">Obtiene un puntero de interfaz de tipo [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) que los hosts pueden usar para personalizar algunos aspectos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c342b-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="c342b-117">Método GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="c342b-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="c342b-118">Obtiene el identificador numérico de la <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="c342b-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="c342b-119">Método SetHostControl</span><span class="sxs-lookup"><span data-stu-id="c342b-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="c342b-120">Establece la interfaz de control host.</span><span class="sxs-lookup"><span data-stu-id="c342b-120">Sets the host control interface.</span></span> <span data-ttu-id="c342b-121">Debe llamar a `SetHostControl` antes de llamar a `Start`.</span><span class="sxs-lookup"><span data-stu-id="c342b-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="c342b-122">Método Start</span><span class="sxs-lookup"><span data-stu-id="c342b-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="c342b-123">Inicializa CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="c342b-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="c342b-124">Método Stop</span><span class="sxs-lookup"><span data-stu-id="c342b-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="c342b-125">Detiene la ejecución de código por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c342b-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="c342b-126">Método UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="c342b-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="c342b-127">Descarga el <xref:System.AppDomain> que se corresponde con el identificador numérico especificado.</span><span class="sxs-lookup"><span data-stu-id="c342b-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c342b-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c342b-128">Remarks</span></span>  
 <span data-ttu-id="c342b-129">A partir de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], utilice el [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interfaz para obtener un puntero a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz y, a continuación, llame a la [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) método para obtener un puntero a `ICLRRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="c342b-129">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="c342b-130">En versiones anteriores de .NET Framework, el host obtiene un puntero a un `ICLRRuntimeHost` instancia mediante una llamada a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="c342b-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="c342b-131">Para proporcionar implementaciones de cualquiera de las tecnologías proporcionadas en la versión 2.0 de .NET Framework, debe usar `ICLRRuntimeHost` en lugar de `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="c342b-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c342b-132">No llame a la [iniciar](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método antes de llamar a la [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) método para activar una aplicación basada en manifiesto.</span><span class="sxs-lookup"><span data-stu-id="c342b-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="c342b-133">Si el `Start` se llama al método en primer lugar, el `ExecuteApplication` se producirá un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="c342b-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c342b-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c342b-134">Requirements</span></span>  
 <span data-ttu-id="c342b-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c342b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c342b-136">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c342b-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c342b-137">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c342b-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c342b-138">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c342b-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c342b-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="c342b-139">See also</span></span>

- [<span data-ttu-id="c342b-140">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="c342b-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="c342b-141">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="c342b-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="c342b-142">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c342b-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c342b-143">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c342b-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="c342b-144">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c342b-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c342b-145">CLRRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="c342b-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
