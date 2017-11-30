---
title: "Programar con dominios de aplicación y ensamblados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6dcf8e4c9bf2401309b1d80d2306bd619b96460d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="20298-102">Programar con dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="20298-102">Programming with Application Domains and Assemblies</span></span>
<span data-ttu-id="20298-103">Hosts como Microsoft Internet Explorer, ASP.NET y el shell de Windows cargan Common Language Runtime en un proceso, crean un [dominio de aplicación](../../../docs/framework/app-domains/application-domains.md) en ese proceso y luego cargan y ejecutan el código de usuario en ese dominio de aplicación cuando se ejecuta una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20298-103">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](../../../docs/framework/app-domains/application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="20298-104">En la mayoría de los casos, no tiene que preocuparse por crear dominios de aplicación y cargar ensamblados en ellos porque el host en tiempo de ejecución realiza esas tareas.</span><span class="sxs-lookup"><span data-stu-id="20298-104">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
 <span data-ttu-id="20298-105">Sin embargo, si crea una aplicación que hospedará Common Language Runtime, crea herramientas o código que desea descargar mediante programación o crea componentes acoplables que se pueden descargar y cargar sobre la marcha, creará sus propios dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="20298-105">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="20298-106">Incluso si no crea un host en tiempo de ejecución, esta sección proporciona información importante sobre cómo trabajar con dominios de aplicación y los ensamblados cargados en estos.</span><span class="sxs-lookup"><span data-stu-id="20298-106">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20298-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20298-107">In This Section</span></span>  
 [<span data-ttu-id="20298-108">Temas "Cómo..." sobre dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="20298-108">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 <span data-ttu-id="20298-109">Proporciona vínculos a todos los temas de procedimientos que se encuentran en la documentación conceptual para programación con dominios de aplicación y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="20298-109">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
 [<span data-ttu-id="20298-110">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="20298-110">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)  
 <span data-ttu-id="20298-111">Proporciona ejemplos sobre cómo crear, configurar y usar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="20298-111">Provides examples of creating, configuring, and using application domains.</span></span>  
  
 [<span data-ttu-id="20298-112">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="20298-112">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="20298-113">Describe cómo crear, firmar y establecer atributos en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="20298-113">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="20298-114">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="20298-114">Related Sections</span></span>  
 [<span data-ttu-id="20298-115">Emitir métodos y ensamblados dinámicos</span><span class="sxs-lookup"><span data-stu-id="20298-115">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="20298-116">Describe la creación de ensamblados dinámicos.</span><span class="sxs-lookup"><span data-stu-id="20298-116">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="20298-117">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="20298-117">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="20298-118">Proporciona una introducción general a los conceptos de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="20298-118">Provides a conceptual overview of assemblies.</span></span>  
  
 [<span data-ttu-id="20298-119">Dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="20298-119">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="20298-120">Proporciona una introducción general a los conceptos de los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="20298-120">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="20298-121">Información general de la reflexión</span><span class="sxs-lookup"><span data-stu-id="20298-121">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="20298-122">Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="20298-122">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
