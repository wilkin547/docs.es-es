---
description: 'Más información acerca de: ICorRuntimeHost (interfaz)'
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
ms.openlocfilehash: cd50d31668b2dd0718dbe644343bfe314a0afdbe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789663"
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="4cb62-103">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cb62-103">ICorRuntimeHost Interface</span></span>

<span data-ttu-id="4cb62-104">Proporciona métodos que permiten al host iniciar y detener explícitamente el Common Language Runtime (CLR), para crear y configurar dominios de aplicación, para tener acceso al dominio predeterminado y para enumerar todos los dominios que se ejecutan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4cb62-104">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="4cb62-105">En la versión .NET Framework 2,0, la interfaz es reemplazada por [ICLRRuntimeHost](iclrruntimehost-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4cb62-105">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4cb62-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="4cb62-106">Methods</span></span>  
  
|<span data-ttu-id="4cb62-107">Método</span><span class="sxs-lookup"><span data-stu-id="4cb62-107">Method</span></span>|<span data-ttu-id="4cb62-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4cb62-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4cb62-109">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="4cb62-109">CloseEnum Method</span></span>](icorruntimehost-closeenum-method.md)|<span data-ttu-id="4cb62-110">Vuelve a establecer un enumerador de dominio al principio de la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="4cb62-110">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="4cb62-111">Método CreateDomain</span><span class="sxs-lookup"><span data-stu-id="4cb62-111">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)|<span data-ttu-id="4cb62-112">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4cb62-112">Creates an application domain.</span></span> <span data-ttu-id="4cb62-113">El autor de la llamada recibe un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4cb62-113">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="4cb62-114">Método CreateDomainEx</span><span class="sxs-lookup"><span data-stu-id="4cb62-114">CreateDomainEx Method</span></span>](icorruntimehost-createdomainex-method.md)|<span data-ttu-id="4cb62-115">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4cb62-115">Creates an application domain.</span></span> <span data-ttu-id="4cb62-116">Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de la instancia de devuelta <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="4cb62-116">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="4cb62-117">Método CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="4cb62-117">CreateDomainSetup Method</span></span>](icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="4cb62-118">Obtiene un puntero de interfaz de tipo `IAppDomainSetup` a una <xref:System.AppDomainSetup> instancia de.</span><span class="sxs-lookup"><span data-stu-id="4cb62-118">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="4cb62-119">`IAppDomainSetup` proporciona métodos para configurar aspectos de un dominio de aplicación antes de que se cree.</span><span class="sxs-lookup"><span data-stu-id="4cb62-119">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="4cb62-120">Método CreateEvidence</span><span class="sxs-lookup"><span data-stu-id="4cb62-120">CreateEvidence Method</span></span>](icorruntimehost-createevidence-method.md)|<span data-ttu-id="4cb62-121">Obtiene un puntero de interfaz de tipo <xref:System.Security.Principal.IIdentity> , que permite al host crear evidencia de seguridad para pasar a [CreateDomain](icorruntimehost-createdomain-method.md) o [createdomainex (](icorruntimehost-createdomainex-method.md).</span><span class="sxs-lookup"><span data-stu-id="4cb62-121">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="4cb62-122">Método CreateLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="4cb62-122">CreateLogicalThreadState Method</span></span>](icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="4cb62-123">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="4cb62-123">Do not use.</span></span>|  
|[<span data-ttu-id="4cb62-124">Método CurrentDomain</span><span class="sxs-lookup"><span data-stu-id="4cb62-124">CurrentDomain Method</span></span>](icorruntimehost-currentdomain-method.md)|<span data-ttu-id="4cb62-125">Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio cargado en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="4cb62-125">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="4cb62-126">Método DeleteLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="4cb62-126">DeleteLogicalThreadState Method</span></span>](icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="4cb62-127">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="4cb62-127">Do not use.</span></span>|  
|[<span data-ttu-id="4cb62-128">Método EnumDomains</span><span class="sxs-lookup"><span data-stu-id="4cb62-128">EnumDomains Method</span></span>](icorruntimehost-enumdomains-method.md)|<span data-ttu-id="4cb62-129">Obtiene un enumerador para los dominios en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="4cb62-129">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="4cb62-130">GetConfiguration (método)</span><span class="sxs-lookup"><span data-stu-id="4cb62-130">GetConfiguration Method</span></span>](icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="4cb62-131">Obtiene un objeto que permite al host especificar la configuración de devolución de llamada de CLR.</span><span class="sxs-lookup"><span data-stu-id="4cb62-131">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="4cb62-132">Método GetDefaultDomain</span><span class="sxs-lookup"><span data-stu-id="4cb62-132">GetDefaultDomain Method</span></span>](icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="4cb62-133">Obtiene un puntero de interfaz de tipo <xref:System._AppDomain> que representa el dominio predeterminado para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="4cb62-133">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="4cb62-134">Método LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="4cb62-134">LocksHeldByLogicalThread Method</span></span>](icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="4cb62-135">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="4cb62-135">Do not use.</span></span>|  
|[<span data-ttu-id="4cb62-136">Método MapFile</span><span class="sxs-lookup"><span data-stu-id="4cb62-136">MapFile Method</span></span>](icorruntimehost-mapfile-method.md)|<span data-ttu-id="4cb62-137">Asigna el archivo especificado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="4cb62-137">Maps the specified file into memory.</span></span> <span data-ttu-id="4cb62-138">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="4cb62-138">This method is obsolete.</span></span>|  
|[<span data-ttu-id="4cb62-139">Método NextDomain</span><span class="sxs-lookup"><span data-stu-id="4cb62-139">NextDomain Method</span></span>](icorruntimehost-nextdomain-method.md)|<span data-ttu-id="4cb62-140">Obtiene un puntero de interfaz al siguiente dominio en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="4cb62-140">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="4cb62-141">Start (método)</span><span class="sxs-lookup"><span data-stu-id="4cb62-141">Start Method</span></span>](icorruntimehost-start-method.md)|<span data-ttu-id="4cb62-142">Inicia el CLR.</span><span class="sxs-lookup"><span data-stu-id="4cb62-142">Starts the CLR.</span></span>|  
|[<span data-ttu-id="4cb62-143">STOP (método)</span><span class="sxs-lookup"><span data-stu-id="4cb62-143">Stop Method</span></span>](icorruntimehost-stop-method.md)|<span data-ttu-id="4cb62-144">Detiene la ejecución de código en tiempo de ejecución para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="4cb62-144">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="4cb62-145">Método SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="4cb62-145">SwitchInLogicalThreadState Method</span></span>](icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="4cb62-146">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="4cb62-146">Do not use.</span></span>|  
|[<span data-ttu-id="4cb62-147">Método SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="4cb62-147">SwitchOutLogicalThreadState Method</span></span>](icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="4cb62-148">No debe usarse.</span><span class="sxs-lookup"><span data-stu-id="4cb62-148">Do not use.</span></span>|  
|[<span data-ttu-id="4cb62-149">Método UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="4cb62-149">UnloadDomain Method</span></span>](icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="4cb62-150">Descarga el dominio de aplicación especificado del proceso actual.</span><span class="sxs-lookup"><span data-stu-id="4cb62-150">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cb62-151">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4cb62-151">Requirements</span></span>  

 <span data-ttu-id="4cb62-152">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cb62-152">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb62-153">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4cb62-153">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cb62-154">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cb62-154">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cb62-155">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="4cb62-155">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb62-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cb62-156">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="4cb62-157">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="4cb62-157">Hosting</span></span>](index.md)
- [<span data-ttu-id="4cb62-158">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cb62-158">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- <span data-ttu-id="4cb62-159">[Hosts de runtime](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4cb62-159">[Runtime Hosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
- [<span data-ttu-id="4cb62-160">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4cb62-160">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="4cb62-161">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="4cb62-161">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
