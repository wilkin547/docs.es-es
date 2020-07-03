---
title: Utilizar dominios de aplicación
description: Los dominios de aplicación, que proporcionan una unidad de aislamiento para Common Language Runtime (CLR), se crean y se ejecutan dentro de un proceso.
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
ms.openlocfilehash: df2a63716904ebfc6ee163121a1f07e53aa07514
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105184"
---
# <a name="using-application-domains"></a><span data-ttu-id="5646d-104">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="5646d-104">Using Application Domains</span></span>

<span data-ttu-id="5646d-105">Los dominios de aplicación proporcionan una unidad de aislamiento para Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5646d-105">Application domains provide a unit of isolation for the common language runtime.</span></span> <span data-ttu-id="5646d-106">Se crean y se ejecutan dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="5646d-106">They are created and run inside a process.</span></span> <span data-ttu-id="5646d-107">Los dominios de aplicación suele crearlos un host en tiempo de ejecución, que es una aplicación encargada de cargar el tiempo de ejecución en un proceso y ejecutar el código de usuario dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5646d-107">Application domains are usually created by a runtime host, which is an application responsible for loading the runtime into a process and executing user code within an application domain.</span></span> <span data-ttu-id="5646d-108">El host en tiempo de ejecución crea un proceso y un dominio de aplicación predeterminado y ejecuta el código administrado dentro de él.</span><span class="sxs-lookup"><span data-stu-id="5646d-108">The runtime host creates a process and a default application domain, and runs managed code inside it.</span></span> <span data-ttu-id="5646d-109">Entre los hosts en tiempo de ejecución se incluyen ASP.NET, Microsoft Internet Explorer y el shell de Windows.</span><span class="sxs-lookup"><span data-stu-id="5646d-109">Runtime hosts include ASP.NET, Microsoft Internet Explorer, and the Windows shell.</span></span>  
  
<span data-ttu-id="5646d-110">En la mayoría de las aplicaciones, no es necesario que cree su propio dominio de aplicación, ya que el host en tiempo de ejecución crea automáticamente los dominios de aplicación necesarios.</span><span class="sxs-lookup"><span data-stu-id="5646d-110">For most applications, you do not need to create your own application domain; the runtime host creates any necessary application domains for you.</span></span> <span data-ttu-id="5646d-111">A pesar de ello, puede crear y configurar dominios de aplicación adicionales si su aplicación necesita aislar el código o usar y descargar archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="5646d-111">However, you can create and configure additional application domains if your application needs to isolate code or to use and unload DLLs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5646d-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5646d-112">In This Section</span></span>  

[<span data-ttu-id="5646d-113">Cómo: Crear un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="5646d-113">How to: Create an Application Domain</span></span>](how-to-create-an-application-domain.md)  
<span data-ttu-id="5646d-114">Describe cómo crear mediante programación un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5646d-114">Describes how to programmatically create an application domain.</span></span>  
  
[<span data-ttu-id="5646d-115">Cómo: Descargar un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="5646d-115">How to: Unload an Application Domain</span></span>](how-to-unload-an-application-domain.md)  
<span data-ttu-id="5646d-116">Describe cómo descargar mediante programación un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5646d-116">Describes how to programmatically unload an application domain.</span></span>  
  
[<span data-ttu-id="5646d-117">Cómo: Configurar un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="5646d-117">How to: Configure an Application Domain</span></span>](how-to-configure-an-application-domain.md)  
<span data-ttu-id="5646d-118">Proporciona una introducción a la configuración de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5646d-118">Provides an introduction to configuring an application domain.</span></span>  
  
[<span data-ttu-id="5646d-119">Recuperar información de instalación de un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="5646d-119">Retrieving Setup Information from an Application Domain</span></span>](retrieve-setup-information.md)  
<span data-ttu-id="5646d-120">Describe cómo recuperar información de instalación de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5646d-120">Describes how to retrieve setup information from an application domain.</span></span>  
  
[<span data-ttu-id="5646d-121">Cómo: Cargar ensamblados en un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="5646d-121">How to: Load Assemblies into an Application Domain</span></span>](how-to-load-assemblies-into-an-application-domain.md)  
<span data-ttu-id="5646d-122">Describe cómo cargar un ensamblado en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5646d-122">Describes how to load an assembly into an application domain.</span></span>  
  
[<span data-ttu-id="5646d-123">Cómo: Obtener información sobre tipos y miembros desde un ensamblado</span><span class="sxs-lookup"><span data-stu-id="5646d-123">How to: Obtain Type and Member Information from an Assembly</span></span>](../reflection-and-codedom/get-type-member-information.md)  
<span data-ttu-id="5646d-124">Describe cómo recuperar información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5646d-124">Describes how to retrieve information about an assembly.</span></span>  
  
[<span data-ttu-id="5646d-125">Copias sombra de ensamblados</span><span class="sxs-lookup"><span data-stu-id="5646d-125">Shadow Copying Assemblies</span></span>](shadow-copy-assemblies.md)  
<span data-ttu-id="5646d-126">Describe la manera en que la creación de instantáneas permite actualizaciones en los ensamblados mientras están en uso y cómo se configura la creación de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="5646d-126">Describes how shadow copying allows updates to assemblies while they are in use, and how to configure shadow copying.</span></span>  
  
[<span data-ttu-id="5646d-127">Cómo: para recibir notificaciones de excepciones de primera oportunidad</span><span class="sxs-lookup"><span data-stu-id="5646d-127">How to: Receive First-Chance Exception Notifications</span></span>](how-to-receive-first-chance-exception-notifications.md)  
<span data-ttu-id="5646d-128">Explica cómo se puede recibir una notificación de que se ha producido una excepción antes de que Common Language Runtime empiece a buscar controladores de excepciones.</span><span class="sxs-lookup"><span data-stu-id="5646d-128">Explains how you can receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
[<span data-ttu-id="5646d-129">Resolver cargas de ensamblado</span><span class="sxs-lookup"><span data-stu-id="5646d-129">Resolving Assembly Loads</span></span>](../../standard/assembly/resolve-loads.md)  
<span data-ttu-id="5646d-130">Proporciona instrucciones sobre cómo usar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para resolver errores en la carga de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5646d-130">Provides guidance on using the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event to resolve assembly load failures.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5646d-131">Referencia</span><span class="sxs-lookup"><span data-stu-id="5646d-131">Reference</span></span>  

<xref:System.AppDomain>  
<span data-ttu-id="5646d-132">Representa un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5646d-132">Represents an application domain.</span></span> <span data-ttu-id="5646d-133">Proporciona métodos para crear y controlar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5646d-133">Provides methods for creating and controlling application domains.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5646d-134">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5646d-134">Related Sections</span></span>  
[<span data-ttu-id="5646d-135">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="5646d-135">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="5646d-136">Proporciona información general sobre las funciones que desempeñan los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5646d-136">Provides an overview of the functions performed by assemblies.</span></span>  
  
[<span data-ttu-id="5646d-137">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="5646d-137">Programming with Assemblies</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="5646d-138">Describe cómo crear, firmar y establecer atributos en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5646d-138">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
[<span data-ttu-id="5646d-139">Emitir métodos y ensamblados dinámicos</span><span class="sxs-lookup"><span data-stu-id="5646d-139">Emitting Dynamic Methods and Assemblies</span></span>](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
<span data-ttu-id="5646d-140">Describe la creación de ensamblados dinámicos.</span><span class="sxs-lookup"><span data-stu-id="5646d-140">Describes how to create dynamic assemblies.</span></span>  
  
[<span data-ttu-id="5646d-141">Dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="5646d-141">Application Domains</span></span>](application-domains.md)  
<span data-ttu-id="5646d-142">Proporciona una introducción general a los conceptos de los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5646d-142">Provides a conceptual overview of application domains.</span></span>  
  
[<span data-ttu-id="5646d-143">Información general de la reflexión</span><span class="sxs-lookup"><span data-stu-id="5646d-143">Reflection Overview</span></span>](../reflection-and-codedom/reflection.md)  
<span data-ttu-id="5646d-144">Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5646d-144">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
