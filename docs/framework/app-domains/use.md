---
title: Utilizar dominios de aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ebd1de46eb2757098a369b58dd9a6c0009e5b95
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742476"
---
# <a name="using-application-domains"></a><span data-ttu-id="834c8-102">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="834c8-102">Using Application Domains</span></span>
<span data-ttu-id="834c8-103">Los dominios de aplicación proporcionan una unidad de aislamiento para Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="834c8-103">Application domains provide a unit of isolation for the common language runtime.</span></span> <span data-ttu-id="834c8-104">Se crean y se ejecutan dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="834c8-104">They are created and run inside a process.</span></span> <span data-ttu-id="834c8-105">Los dominios de aplicación suele crearlos un host en tiempo de ejecución, que es una aplicación encargada de cargar el tiempo de ejecución en un proceso y ejecutar el código de usuario dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="834c8-105">Application domains are usually created by a runtime host, which is an application responsible for loading the runtime into a process and executing user code within an application domain.</span></span> <span data-ttu-id="834c8-106">El host en tiempo de ejecución crea un proceso y un dominio de aplicación predeterminado y ejecuta el código administrado dentro de él.</span><span class="sxs-lookup"><span data-stu-id="834c8-106">The runtime host creates a process and a default application domain, and runs managed code inside it.</span></span> <span data-ttu-id="834c8-107">Entre los hosts en tiempo de ejecución se incluyen ASP.NET, Microsoft Internet Explorer y el shell de Windows.</span><span class="sxs-lookup"><span data-stu-id="834c8-107">Runtime hosts include ASP.NET, Microsoft Internet Explorer, and the Windows shell.</span></span>  
  
 <span data-ttu-id="834c8-108">En la mayoría de las aplicaciones, no es necesario que cree su propio dominio de aplicación, ya que el host en tiempo de ejecución crea automáticamente los dominios de aplicación necesarios.</span><span class="sxs-lookup"><span data-stu-id="834c8-108">For most applications, you do not need to create your own application domain; the runtime host creates any necessary application domains for you.</span></span> <span data-ttu-id="834c8-109">A pesar de ello, puede crear y configurar dominios de aplicación adicionales si su aplicación necesita aislar el código o usar y descargar archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="834c8-109">However, you can create and configure additional application domains if your application needs to isolate code or to use and unload DLLs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="834c8-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="834c8-110">In This Section</span></span>  
 [<span data-ttu-id="834c8-111">Crear un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="834c8-111">How to: Create an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 <span data-ttu-id="834c8-112">Describe cómo crear mediante programación un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="834c8-112">Describes how to programmatically create an application domain.</span></span>  
  
 [<span data-ttu-id="834c8-113">Descargar un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="834c8-113">How to: Unload an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 <span data-ttu-id="834c8-114">Describe cómo descargar mediante programación un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="834c8-114">Describes how to programmatically unload an application domain.</span></span>  
  
 [<span data-ttu-id="834c8-115">Configurar un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="834c8-115">How to: Configure an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 <span data-ttu-id="834c8-116">Proporciona una introducción a la configuración de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="834c8-116">Provides an introduction to configuring an application domain.</span></span>  
  
 [<span data-ttu-id="834c8-117">Recuperar información de instalación de un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="834c8-117">Retrieving Setup Information from an Application Domain</span></span>](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 <span data-ttu-id="834c8-118">Describe cómo recuperar información de instalación de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="834c8-118">Describes how to retrieve setup information from an application domain.</span></span>  
  
 [<span data-ttu-id="834c8-119">Cómo: Cargar ensamblados en un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="834c8-119">How to: Load Assemblies into an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 <span data-ttu-id="834c8-120">Describe cómo cargar un ensamblado en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="834c8-120">Describes how to load an assembly into an application domain.</span></span>  
  
 [<span data-ttu-id="834c8-121">Obtener información sobre tipos y miembros desde un ensamblado</span><span class="sxs-lookup"><span data-stu-id="834c8-121">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="834c8-122">Describe cómo recuperar información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="834c8-122">Describes how to retrieve information about an assembly.</span></span>  
  
 [<span data-ttu-id="834c8-123">Copias sombra de ensamblados</span><span class="sxs-lookup"><span data-stu-id="834c8-123">Shadow Copying Assemblies</span></span>](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 <span data-ttu-id="834c8-124">Describe la manera en que la creación de instantáneas permite actualizaciones en los ensamblados mientras están en uso y cómo se configura la creación de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="834c8-124">Describes how shadow copying allows updates to assemblies while they are in use, and how to configure shadow copying.</span></span>  
  
 [<span data-ttu-id="834c8-125">Recibir notificaciones de excepciones de primera oportunidad</span><span class="sxs-lookup"><span data-stu-id="834c8-125">How to: Receive First-Chance Exception Notifications</span></span>](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 <span data-ttu-id="834c8-126">Explica cómo se puede recibir una notificación de que se ha producido una excepción antes de que Common Language Runtime empiece a buscar controladores de excepciones.</span><span class="sxs-lookup"><span data-stu-id="834c8-126">Explains how you can receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
 [<span data-ttu-id="834c8-127">Resolver cargas de ensamblado</span><span class="sxs-lookup"><span data-stu-id="834c8-127">Resolving Assembly Loads</span></span>](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 <span data-ttu-id="834c8-128">Proporciona instrucciones sobre cómo usar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para resolver errores en la carga de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="834c8-128">Provides guidance on using the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event to resolve assembly load failures.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="834c8-129">Referencia</span><span class="sxs-lookup"><span data-stu-id="834c8-129">Reference</span></span>  
 <xref:System.AppDomain>  
 <span data-ttu-id="834c8-130">Representa un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="834c8-130">Represents an application domain.</span></span> <span data-ttu-id="834c8-131">Proporciona métodos para crear y controlar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="834c8-131">Provides methods for creating and controlling application domains.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="834c8-132">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="834c8-132">Related Sections</span></span>  
 [<span data-ttu-id="834c8-133">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="834c8-133">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="834c8-134">Proporciona información general sobre las funciones que desempeñan los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="834c8-134">Provides an overview of the functions performed by assemblies.</span></span>  
  
 [<span data-ttu-id="834c8-135">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="834c8-135">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="834c8-136">Describe cómo crear, firmar y establecer atributos en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="834c8-136">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
 [<span data-ttu-id="834c8-137">Emitir métodos y ensamblados dinámicos</span><span class="sxs-lookup"><span data-stu-id="834c8-137">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="834c8-138">Describe la creación de ensamblados dinámicos.</span><span class="sxs-lookup"><span data-stu-id="834c8-138">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="834c8-139">Dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="834c8-139">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="834c8-140">Proporciona una introducción general a los conceptos de los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="834c8-140">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="834c8-141">Información general de la reflexión</span><span class="sxs-lookup"><span data-stu-id="834c8-141">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="834c8-142">Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="834c8-142">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
