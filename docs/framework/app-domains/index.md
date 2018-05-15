---
title: Programar con dominios de aplicación y ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7124b6b234601e3afc27109ac318f47e3fe40c35
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="6d84e-102">Programar con dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="6d84e-102">Programming with Application Domains and Assemblies</span></span>
<span data-ttu-id="6d84e-103">Hosts como Microsoft Internet Explorer, ASP.NET y el shell de Windows cargan Common Language Runtime en un proceso, crean un [dominio de aplicación](../../../docs/framework/app-domains/application-domains.md) en ese proceso y luego cargan y ejecutan el código de usuario en ese dominio de aplicación cuando se ejecuta una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d84e-103">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](../../../docs/framework/app-domains/application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="6d84e-104">En la mayoría de los casos, no tiene que preocuparse por crear dominios de aplicación y cargar ensamblados en ellos porque el host en tiempo de ejecución realiza esas tareas.</span><span class="sxs-lookup"><span data-stu-id="6d84e-104">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
 <span data-ttu-id="6d84e-105">Sin embargo, si crea una aplicación que hospedará Common Language Runtime, crea herramientas o código que desea descargar mediante programación o crea componentes acoplables que se pueden descargar y cargar sobre la marcha, creará sus propios dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d84e-105">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="6d84e-106">Incluso si no crea un host en tiempo de ejecución, esta sección proporciona información importante sobre cómo trabajar con dominios de aplicación y los ensamblados cargados en estos.</span><span class="sxs-lookup"><span data-stu-id="6d84e-106">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d84e-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6d84e-107">In This Section</span></span>  
 [<span data-ttu-id="6d84e-108">Temas "Cómo..." sobre dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="6d84e-108">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 <span data-ttu-id="6d84e-109">Proporciona vínculos a todos los temas de procedimientos que se encuentran en la documentación conceptual para programación con dominios de aplicación y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6d84e-109">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
 [<span data-ttu-id="6d84e-110">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="6d84e-110">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)  
 <span data-ttu-id="6d84e-111">Proporciona ejemplos sobre cómo crear, configurar y usar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d84e-111">Provides examples of creating, configuring, and using application domains.</span></span>  
  
 [<span data-ttu-id="6d84e-112">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="6d84e-112">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="6d84e-113">Describe cómo crear, firmar y establecer atributos en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6d84e-113">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6d84e-114">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6d84e-114">Related Sections</span></span>  
 [<span data-ttu-id="6d84e-115">Emitir métodos y ensamblados dinámicos</span><span class="sxs-lookup"><span data-stu-id="6d84e-115">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="6d84e-116">Describe la creación de ensamblados dinámicos.</span><span class="sxs-lookup"><span data-stu-id="6d84e-116">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="6d84e-117">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="6d84e-117">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="6d84e-118">Proporciona una introducción general a los conceptos de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6d84e-118">Provides a conceptual overview of assemblies.</span></span>  
  
 [<span data-ttu-id="6d84e-119">Dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="6d84e-119">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="6d84e-120">Proporciona una introducción general a los conceptos de los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d84e-120">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="6d84e-121">Información general de la reflexión</span><span class="sxs-lookup"><span data-stu-id="6d84e-121">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="6d84e-122">Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6d84e-122">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
