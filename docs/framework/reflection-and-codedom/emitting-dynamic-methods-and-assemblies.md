---
title: Emitir métodos y ensamblados dinámicos
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0ed1d02fd40a94d4ae63deea3c09b04bfc9bd8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44183137"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="d1142-102">Emitir métodos y ensamblados dinámicos</span><span class="sxs-lookup"><span data-stu-id="d1142-102">Emitting Dynamic Methods and Assemblies</span></span>
<span data-ttu-id="d1142-103">En esta sección se describe un conjunto de tipos administrados del espacio de nombres <xref:System.Reflection.Emit> que permite a un compilador o una herramienta emitir metadatos y el Lenguaje Intermedio de Microsoft (MSIL) en tiempo de ejecución y, opcionalmente, generar un archivo portable ejecutable (PE) en el disco.</span><span class="sxs-lookup"><span data-stu-id="d1142-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="d1142-104">Los motores de scripts y los compiladores son los principales usuarios de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1142-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="d1142-105">En esta sección, la funcionalidad proporcionada por el espacio de nombres <xref:System.Reflection.Emit> se conoce como emisión de la reflexión.</span><span class="sxs-lookup"><span data-stu-id="d1142-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
 <span data-ttu-id="d1142-106">La emisión de la reflexión permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1142-106">Reflection emit provides the following capabilities:</span></span>  
  
-   <span data-ttu-id="d1142-107">Definir métodos globales ligeros en tiempo de ejecución, usando la clase <xref:System.Reflection.Emit.DynamicMethod>, y ejecutarlos usando delegados.</span><span class="sxs-lookup"><span data-stu-id="d1142-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
-   <span data-ttu-id="d1142-108">Definir ensamblados en tiempo de ejecución y, después, ejecutarlos o guardarlos en el disco.</span><span class="sxs-lookup"><span data-stu-id="d1142-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="d1142-109">Definir ensamblados en tiempo de ejecución, ejecutarlos y, después, descargarlos y permitir la recolección de elementos no utilizados para reclamar sus recursos.</span><span class="sxs-lookup"><span data-stu-id="d1142-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
-   <span data-ttu-id="d1142-110">Definir módulos en nuevos ensamblados en tiempo de ejecución y, después, ejecutarlos o guardarlos en el disco.</span><span class="sxs-lookup"><span data-stu-id="d1142-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="d1142-111">Definir tipos en módulos en tiempo de ejecución, crear instancias de estos tipos y llamar a sus métodos.</span><span class="sxs-lookup"><span data-stu-id="d1142-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
-   <span data-ttu-id="d1142-112">Definir información simbólica para módulos definidos que puedan usar herramientas como depuradores y generadores de perfiles de código.</span><span class="sxs-lookup"><span data-stu-id="d1142-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
 <span data-ttu-id="d1142-113">Además de los tipos administrados del espacio de nombres <xref:System.Reflection.Emit>, hay interfaces de metadatos no administradas que se describen en la documentación de referencia [Interfaces de metadatos](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="d1142-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="d1142-114">La emisión de reflexión administrada proporciona una comprobación más estricta de los errores semánticos y un mayor nivel de abstracción de los metadatos que las interfaces de metadatos no administradas.</span><span class="sxs-lookup"><span data-stu-id="d1142-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
 <span data-ttu-id="d1142-115">Otro recurso útil para trabajar con metadatos y MSIL es la documentación de Common Language Infrastructure (CLI), especialmente la sección II sobre la definición y la semántica de los metadatos y la partición III sobre el conjunto de instrucciones de CIL.</span><span class="sxs-lookup"><span data-stu-id="d1142-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="d1142-116">La documentación está disponible en línea en [MSDN](https://go.microsoft.com/fwlink/?LinkID=65555) y en el [sitio web de Ecma](https://go.microsoft.com/fwlink/?LinkId=116487).</span><span class="sxs-lookup"><span data-stu-id="d1142-116">The documentation is available online on [MSDN](https://go.microsoft.com/fwlink/?LinkID=65555) and at the [Ecma Web site](https://go.microsoft.com/fwlink/?LinkId=116487).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1142-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d1142-117">In This Section</span></span>
  
[<span data-ttu-id="d1142-118">Problemas de seguridad de la emisión de la reflexión</span><span class="sxs-lookup"><span data-stu-id="d1142-118">Security issues in reflection emit</span></span>](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
<span data-ttu-id="d1142-119">Describe los problemas de seguridad relacionados con la creación de ensamblados dinámicos mediante emisión de la reflexión.</span><span class="sxs-lookup"><span data-stu-id="d1142-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="d1142-120">[Cómo: Definir y ejecutar métodos dinámicos](how-to-define-and-execute-dynamic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="d1142-120">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) </span></span>  
<span data-ttu-id="d1142-121">Muestra cómo ejecutar un método dinámico simple y un método dinámico enlazado a una instancia de una clase.</span><span class="sxs-lookup"><span data-stu-id="d1142-121">Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="d1142-122">[Cómo: Definir un tipo genérico con emisión de reflexión](how-to-define-a-generic-type-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="d1142-122">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) </span></span>  
<span data-ttu-id="d1142-123">Muestra cómo crear un tipo genérico simple con dos parámetros de tipo, cómo aplicar restricciones de clase, interfaz y especiales a los parámetros de tipo y cómo crear miembros que usen los parámetros de tipo de la clase como tipos de parámetro y tipos de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d1142-123">Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="d1142-124">[Cómo: Definir un método genérico con emisión de reflexión](how-to-define-a-generic-method-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="d1142-124">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) </span></span>  
<span data-ttu-id="d1142-125">Muestra cómo crear, emitir e invocar un método genérico simple.</span><span class="sxs-lookup"><span data-stu-id="d1142-125">Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="d1142-126">[Ensamblados recopilables para la generación dinámica de tipos](collectible-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="d1142-126">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) </span></span>  
<span data-ttu-id="d1142-127">Presenta los ensamblados recopilables, que son ensamblados dinámicos que se pueden descargar sin descargar el dominio de aplicación en el que se crearon.</span><span class="sxs-lookup"><span data-stu-id="d1142-127">Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="d1142-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="d1142-128">Reference</span></span>  
 <xref:System.Reflection.Emit.OpCodes>  
 <span data-ttu-id="d1142-129">Cataloga los códigos de instrucción de MSIL que puede usar para compilar cuerpos de método.</span><span class="sxs-lookup"><span data-stu-id="d1142-129">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
 <xref:System.Reflection.Emit>  
 <span data-ttu-id="d1142-130">Contiene clases administradas usadas para emitir ensamblados, tipos y métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="d1142-130">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
 <xref:System.Type>  
 <span data-ttu-id="d1142-131">Describe la clase <xref:System.Type>, que representa los tipos en reflexión administrada y emisión de la reflexión, y que es clave para el uso de estas tecnologías.</span><span class="sxs-lookup"><span data-stu-id="d1142-131">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
 <xref:System.Reflection>  
 <span data-ttu-id="d1142-132">Contiene clases administradas usadas para explorar metadatos y código administrado.</span><span class="sxs-lookup"><span data-stu-id="d1142-132">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d1142-133">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d1142-133">Related Sections</span></span>  
 [<span data-ttu-id="d1142-134">Reflexión</span><span class="sxs-lookup"><span data-stu-id="d1142-134">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="d1142-135">Explica cómo explorar metadatos y código administrado.</span><span class="sxs-lookup"><span data-stu-id="d1142-135">Explains how to explore metadata and managed code.</span></span>  
  
 [<span data-ttu-id="d1142-136">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="d1142-136">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="d1142-137">Proporciona información general sobre los ensamblados de las implementaciones de. NET.</span><span class="sxs-lookup"><span data-stu-id="d1142-137">Provides an overview of assemblies in .NET implementations.</span></span>
