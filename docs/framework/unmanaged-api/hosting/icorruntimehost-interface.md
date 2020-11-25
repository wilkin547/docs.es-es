---
title: ICorRuntimeHost (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
ms.openlocfilehash: 9fcb5e189af9f72de7635aad550a5e8ab5522dbd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720625"
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="dd3ec-102">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd3ec-102">ICorRuntimeHost Interface</span></span>

<span data-ttu-id="dd3ec-103">Proporciona métodos que permiten al host iniciar y detener explícitamente el Common Language Runtime (CLR), para crear y configurar dominios de aplicación, para tener acceso al dominio predeterminado y para enumerar todos los dominios que se ejecutan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="dd3ec-104">En la versión .NET Framework 2,0, la interfaz es reemplazada por [ICLRRuntimeHost](iclrruntimehost-interface.md).</span><span class="sxs-lookup"><span data-stu-id="dd3ec-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd3ec-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dd3ec-105">Methods</span></span>  
  
|<span data-ttu-id="dd3ec-106">Método</span><span class="sxs-lookup"><span data-stu-id="dd3ec-106">Method</span></span>|<span data-ttu-id="dd3ec-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd3ec-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd3ec-108">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="dd3ec-108">CloseEnum Method</span></span>](icorruntimehost-closeenum-method.md)|<span data-ttu-id="dd3ec-109">Vuelve a establecer un enumerador de dominio al principio de la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="dd3ec-110">Método CreateDomain</span><span class="sxs-lookup"><span data-stu-id="dd3ec-110">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)|<span data-ttu-id="dd3ec-111">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-111">Creates an application domain.</span></span> <span data-ttu-id="dd3ec-112">El autor de la llamada recibe un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="dd3ec-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="dd3ec-113">Método CreateDomainEx</span><span class="sxs-lookup"><span data-stu-id="dd3ec-113">CreateDomainEx Method</span></span>](icorruntimehost-createdomainex-method.md)|<span data-ttu-id="dd3ec-114">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-114">Creates an application domain.</span></span> <span data-ttu-id="dd3ec-115">Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de la instancia de devuelta <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="dd3ec-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="dd3ec-116">Método CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="dd3ec-116">CreateDomainSetup Method</span></span>](icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="dd3ec-117">Obtiene un puntero de interfaz de tipo `IAppDomainSetup` a una <xref:System.AppDomainSetup> instancia de.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="dd3ec-118">`IAppDomainSetup` proporciona métodos para configurar aspectos de un dominio de aplicación antes de que se cree.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="dd3ec-119">Método CreateEvidence</span><span class="sxs-lookup"><span data-stu-id="dd3ec-119">CreateEvidence Method</span></span>](icorruntimehost-createevidence-method.md)|<span data-ttu-id="dd3ec-120">Obtiene un puntero de interfaz de tipo <xref:System.Security.Principal.IIdentity> , que permite al host crear evidencia de seguridad para pasar a [CreateDomain](icorruntimehost-createdomain-method.md) o [createdomainex (](icorruntimehost-createdomainex-method.md).</span><span class="sxs-lookup"><span data-stu-id="dd3ec-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="dd3ec-121">Método CreateLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="dd3ec-121">CreateLogicalThreadState Method</span></span>](icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="dd3ec-122">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-122">Do not use.</span></span>|  
|[<span data-ttu-id="dd3ec-123">Método CurrentDomain</span><span class="sxs-lookup"><span data-stu-id="dd3ec-123">CurrentDomain Method</span></span>](icorruntimehost-currentdomain-method.md)|<span data-ttu-id="dd3ec-124">Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio cargado en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="dd3ec-125">Método DeleteLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="dd3ec-125">DeleteLogicalThreadState Method</span></span>](icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="dd3ec-126">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-126">Do not use.</span></span>|  
|[<span data-ttu-id="dd3ec-127">Método EnumDomains</span><span class="sxs-lookup"><span data-stu-id="dd3ec-127">EnumDomains Method</span></span>](icorruntimehost-enumdomains-method.md)|<span data-ttu-id="dd3ec-128">Obtiene un enumerador para los dominios en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="dd3ec-129">GetConfiguration (método)</span><span class="sxs-lookup"><span data-stu-id="dd3ec-129">GetConfiguration Method</span></span>](icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="dd3ec-130">Obtiene un objeto que permite al host especificar la configuración de devolución de llamada de CLR.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="dd3ec-131">Método GetDefaultDomain</span><span class="sxs-lookup"><span data-stu-id="dd3ec-131">GetDefaultDomain Method</span></span>](icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="dd3ec-132">Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio predeterminado para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="dd3ec-133">Método LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="dd3ec-133">LocksHeldByLogicalThread Method</span></span>](icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="dd3ec-134">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-134">Do not use.</span></span>|  
|[<span data-ttu-id="dd3ec-135">Método MapFile</span><span class="sxs-lookup"><span data-stu-id="dd3ec-135">MapFile Method</span></span>](icorruntimehost-mapfile-method.md)|<span data-ttu-id="dd3ec-136">Asigna el archivo especificado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-136">Maps the specified file into memory.</span></span> <span data-ttu-id="dd3ec-137">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="dd3ec-138">Método NextDomain</span><span class="sxs-lookup"><span data-stu-id="dd3ec-138">NextDomain Method</span></span>](icorruntimehost-nextdomain-method.md)|<span data-ttu-id="dd3ec-139">Obtiene un puntero de interfaz al siguiente dominio en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="dd3ec-140">Método Start</span><span class="sxs-lookup"><span data-stu-id="dd3ec-140">Start Method</span></span>](icorruntimehost-start-method.md)|<span data-ttu-id="dd3ec-141">Inicia el CLR.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="dd3ec-142">Método Stop</span><span class="sxs-lookup"><span data-stu-id="dd3ec-142">Stop Method</span></span>](icorruntimehost-stop-method.md)|<span data-ttu-id="dd3ec-143">Detiene la ejecución de código en tiempo de ejecución para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="dd3ec-144">Método SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="dd3ec-144">SwitchInLogicalThreadState Method</span></span>](icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="dd3ec-145">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-145">Do not use.</span></span>|  
|[<span data-ttu-id="dd3ec-146">Método SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="dd3ec-146">SwitchOutLogicalThreadState Method</span></span>](icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="dd3ec-147">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-147">Do not use.</span></span>|  
|[<span data-ttu-id="dd3ec-148">Método UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="dd3ec-148">UnloadDomain Method</span></span>](icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="dd3ec-149">Descarga el dominio de aplicación especificado del proceso actual.</span><span class="sxs-lookup"><span data-stu-id="dd3ec-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd3ec-150">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd3ec-150">Requirements</span></span>  

 <span data-ttu-id="dd3ec-151">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd3ec-151">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd3ec-152">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dd3ec-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd3ec-153">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd3ec-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd3ec-154">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="dd3ec-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd3ec-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd3ec-155">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="dd3ec-156">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="dd3ec-156">Hosting</span></span>](index.md)
- [<span data-ttu-id="dd3ec-157">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd3ec-157">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- <span data-ttu-id="dd3ec-158">[Hosts de runtime](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dd3ec-158">[Runtime Hosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
- [<span data-ttu-id="dd3ec-159">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="dd3ec-159">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="dd3ec-160">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="dd3ec-160">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
