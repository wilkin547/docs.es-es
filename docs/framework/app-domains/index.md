---
title: Programar con dominios de aplicación y ensamblados
description: Aprenda a programar con dominios de aplicación y ensamblados en .NET. Vea los vínculos a temas de procedimientos y ejemplos de creación de dominios de aplicación y ensamblados.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
ms.openlocfilehash: 1c28fe0abeb279a1dbbc6dcf043c1780c72d79df
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903443"
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="680bd-104">Programar con dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="680bd-104">Programming with Application Domains and Assemblies</span></span>

<span data-ttu-id="680bd-105">Hosts como Microsoft Internet Explorer, ASP.NET y el shell de Windows cargan Common Language Runtime en un proceso, crean un [dominio de aplicación](application-domains.md) en ese proceso y luego cargan y ejecutan el código de usuario en ese dominio de aplicación cuando se ejecuta una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="680bd-105">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="680bd-106">En la mayoría de los casos, no tiene que preocuparse por crear dominios de aplicación y cargar ensamblados en ellos porque el host en tiempo de ejecución realiza esas tareas.</span><span class="sxs-lookup"><span data-stu-id="680bd-106">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
<span data-ttu-id="680bd-107">Sin embargo, si crea una aplicación que hospedará Common Language Runtime, crea herramientas o código que desea descargar mediante programación o crea componentes acoplables que se pueden descargar y cargar sobre la marcha, creará sus propios dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="680bd-107">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="680bd-108">Incluso si no crea un host en tiempo de ejecución, esta sección proporciona información importante sobre cómo trabajar con dominios de aplicación y los ensamblados cargados en estos.</span><span class="sxs-lookup"><span data-stu-id="680bd-108">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="680bd-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="680bd-109">In This Section</span></span>  

[<span data-ttu-id="680bd-110">Temas "Cómo..." sobre dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="680bd-110">Application Domains and Assemblies How-to Topics</span></span>](application-domains-and-assemblies-how-to-topics.md)  
<span data-ttu-id="680bd-111">Proporciona vínculos a todos los temas de procedimientos que se encuentran en la documentación conceptual para programación con dominios de aplicación y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="680bd-111">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
[<span data-ttu-id="680bd-112">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="680bd-112">Using Application Domains</span></span>](use.md)  
<span data-ttu-id="680bd-113">Proporciona ejemplos sobre cómo crear, configurar y usar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="680bd-113">Provides examples of creating, configuring, and using application domains.</span></span>  
  
[<span data-ttu-id="680bd-114">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="680bd-114">Programming with Assemblies</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="680bd-115">Describe cómo crear, firmar y establecer atributos en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="680bd-115">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="680bd-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="680bd-116">Related Sections</span></span>  

[<span data-ttu-id="680bd-117">Emitir métodos y ensamblados dinámicos</span><span class="sxs-lookup"><span data-stu-id="680bd-117">Emitting Dynamic Methods and Assemblies</span></span>](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
<span data-ttu-id="680bd-118">Describe la creación de ensamblados dinámicos.</span><span class="sxs-lookup"><span data-stu-id="680bd-118">Describes how to create dynamic assemblies.</span></span>  
  
[<span data-ttu-id="680bd-119">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="680bd-119">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="680bd-120">Proporciona una introducción general a los conceptos de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="680bd-120">Provides a conceptual overview of assemblies.</span></span>  
  
[<span data-ttu-id="680bd-121">Dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="680bd-121">Application Domains</span></span>](application-domains.md)  
<span data-ttu-id="680bd-122">Proporciona una introducción general a los conceptos de los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="680bd-122">Provides a conceptual overview of application domains.</span></span>  
  
[<span data-ttu-id="680bd-123">Información general de la reflexión</span><span class="sxs-lookup"><span data-stu-id="680bd-123">Reflection Overview</span></span>](../reflection-and-codedom/reflection.md)  
<span data-ttu-id="680bd-124">Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="680bd-124">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
