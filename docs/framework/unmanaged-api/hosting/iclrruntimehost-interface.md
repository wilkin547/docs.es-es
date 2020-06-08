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
ms.openlocfilehash: 72caac0aafe7f9c5919057a6ad2565258aec6a50
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504087"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="d3235-102">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3235-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="d3235-103">Proporciona una funcionalidad similar a la de la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) proporcionada en el .NET Framework versión 1, con los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="d3235-103">Provides functionality similar to that of the [ICorRuntimeHost](icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="d3235-104">La adición del método [SetHostControl](iclrruntimehost-sethostcontrol-method.md) para establecer la interfaz de control host.</span><span class="sxs-lookup"><span data-stu-id="d3235-104">The addition of the [SetHostControl](iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="d3235-105">La omisión de algunos métodos proporcionados por `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="d3235-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3235-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="d3235-106">Methods</span></span>  
  
|<span data-ttu-id="d3235-107">Método</span><span class="sxs-lookup"><span data-stu-id="d3235-107">Method</span></span>|<span data-ttu-id="d3235-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3235-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3235-109">Método ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="d3235-109">ExecuteApplication Method</span></span>](iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="d3235-110">Se usa en escenarios de implementación ClickOnce basados en manifiesto para especificar la aplicación que se va a activar en un dominio nuevo.</span><span class="sxs-lookup"><span data-stu-id="d3235-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="d3235-111">Método ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="d3235-111">ExecuteInAppDomain Method</span></span>](iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="d3235-112">Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="d3235-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="d3235-113">Método ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="d3235-113">ExecuteInDefaultAppDomain Method</span></span>](iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="d3235-114">Invoca el método especificado del tipo especificado en el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="d3235-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="d3235-115">Método GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="d3235-115">GetCLRControl Method</span></span>](iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="d3235-116">Obtiene un puntero de interfaz de tipo [ICLRControl](iclrcontrol-interface.md) que los hosts pueden utilizar para personalizar los aspectos del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d3235-116">Gets an interface pointer of type [ICLRControl](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="d3235-117">Método GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="d3235-117">GetCurrentAppDomainId Method</span></span>](iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="d3235-118">Obtiene el identificador numérico del <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="d3235-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="d3235-119">Método SetHostControl</span><span class="sxs-lookup"><span data-stu-id="d3235-119">SetHostControl Method</span></span>](iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="d3235-120">Establece la interfaz de control host.</span><span class="sxs-lookup"><span data-stu-id="d3235-120">Sets the host control interface.</span></span> <span data-ttu-id="d3235-121">Debe llamar a `SetHostControl` antes de llamar a `Start` .</span><span class="sxs-lookup"><span data-stu-id="d3235-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="d3235-122">Start (método)</span><span class="sxs-lookup"><span data-stu-id="d3235-122">Start Method</span></span>](iclrruntimehost-start-method.md)|<span data-ttu-id="d3235-123">Inicializa CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="d3235-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="d3235-124">Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="d3235-124">Stop Method</span></span>](iclrruntimehost-stop-method.md)|<span data-ttu-id="d3235-125">Detiene la ejecución del código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d3235-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="d3235-126">Método UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d3235-126">UnloadAppDomain Method</span></span>](iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="d3235-127">Descarga el <xref:System.AppDomain> que corresponde al identificador numérico especificado.</span><span class="sxs-lookup"><span data-stu-id="d3235-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3235-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3235-128">Remarks</span></span>  
 <span data-ttu-id="d3235-129">A partir de la .NET Framework 4, use la interfaz [ICLRMetaHost](iclrmetahost-interface.md) para obtener un puntero a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) y, a continuación, llame al método [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) para obtener un puntero a `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="d3235-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="d3235-130">En versiones anteriores del .NET Framework, el host obtiene un puntero a una instancia llamando a `ICLRRuntimeHost` [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="d3235-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="d3235-131">Para proporcionar implementaciones de cualquiera de las tecnologías que se proporcionan en la .NET Framework versión 2,0, debe utilizar `ICLRRuntimeHost` en lugar de `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="d3235-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d3235-132">No llame al método [Start](iclrruntimehost-start-method.md) antes de llamar al método [ExecuteApplication (](iclrruntimehost-executeapplication-method.md) para activar una aplicación basada en manifiesto.</span><span class="sxs-lookup"><span data-stu-id="d3235-132">Do not call the [Start](iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="d3235-133">Si `Start` se llama primero al método, `ExecuteApplication` se producirá un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="d3235-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3235-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3235-134">Requirements</span></span>  
 <span data-ttu-id="d3235-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3235-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3235-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d3235-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3235-137">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d3235-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3235-138">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3235-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3235-139">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="d3235-139">See also</span></span>

- [<span data-ttu-id="d3235-140">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="d3235-140">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="d3235-141">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="d3235-141">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="d3235-142">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3235-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="d3235-143">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3235-143">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="d3235-144">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d3235-144">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d3235-145">CLRRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="d3235-145">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
