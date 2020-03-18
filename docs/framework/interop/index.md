---
title: Interoperar con código no administrado
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: 12183f390a5178f038c6dd2122a72a33e31ae0ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457969"
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="d5328-102">Interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="d5328-102">Interoperating with unmanaged code</span></span>

<span data-ttu-id="d5328-103">.NET Framework promueve la interacción con componentes COM, servicios COM+, bibliotecas de tipos externas y muchos servicios del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d5328-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="d5328-104">Los tipos de datos, las firmas de método y los mecanismos de control de errores varían entre los modelos de objetos administrados y no administrados.</span><span class="sxs-lookup"><span data-stu-id="d5328-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="d5328-105">Para simplificar la interoperación entre los componentes de .NET Framework y el código no administrado, así como para facilitar la ruta de migración, Common Language Runtime oculta a los clientes y servidores las diferencias en estos modelos de objetos.</span><span class="sxs-lookup"><span data-stu-id="d5328-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>

<span data-ttu-id="d5328-106">El código que se ejecuta bajo el control del tiempo de ejecución se denomina código administrado.</span><span class="sxs-lookup"><span data-stu-id="d5328-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="d5328-107">Por el contrario, el código que se ejecuta fuera del tiempo de ejecución se denomina código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d5328-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="d5328-108">Los componentes COM, las interfaces ActiveX y las funciones de la API de Windows son ejemplos de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d5328-108">COM components, ActiveX interfaces, and Windows API functions are examples of unmanaged code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d5328-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5328-109">In this section</span></span>

[<span data-ttu-id="d5328-110">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d5328-110">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
<span data-ttu-id="d5328-111">Se describe cómo usar los componentes COM desde las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5328-111">Describes how to use COM components from .NET Framework applications.</span></span>

[<span data-ttu-id="d5328-112">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="d5328-112">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
<span data-ttu-id="d5328-113">Se describe cómo usar los componentes de .NET Framework desde las aplicaciones COM.</span><span class="sxs-lookup"><span data-stu-id="d5328-113">Describes how to use .NET Framework components from COM applications.</span></span>

[<span data-ttu-id="d5328-114">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="d5328-114">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
<span data-ttu-id="d5328-115">Se describe cómo llamar a funciones DLL no administradas mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="d5328-115">Describes how to call unmanaged DLL functions using platform invoke.</span></span>

[<span data-ttu-id="d5328-116">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d5328-116">Interop Marshaling</span></span>](interop-marshaling.md)  
<span data-ttu-id="d5328-117">Se describe la serialización de la interoperabilidad COM y la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="d5328-117">Describes marshaling for COM interop and platform invoke.</span></span>

[<span data-ttu-id="d5328-118">Asignar resultados HRESULT y excepciones</span><span class="sxs-lookup"><span data-stu-id="d5328-118">How to: Map HRESULTs and Exceptions</span></span>](how-to-map-hresults-and-exceptions.md)  
<span data-ttu-id="d5328-119">Se describe la asignación entre las excepciones y los valores HRESULT.</span><span class="sxs-lookup"><span data-stu-id="d5328-119">Describes the mapping between exceptions and HRESULTs.</span></span>

[<span data-ttu-id="d5328-120">Equivalencia de tipos y tipos de interoperabilidad incrustados</span><span class="sxs-lookup"><span data-stu-id="d5328-120">Type Equivalence and Embedded Interop Types</span></span>](type-equivalence-and-embedded-interop-types.md)  
<span data-ttu-id="d5328-121">Describe cómo la información de tipo para tipos COM está insertada en los ensamblados y cómo Common Language Runtime determina la equivalencia de los tipos COM insertados.</span><span class="sxs-lookup"><span data-stu-id="d5328-121">Describes how type information for COM types is embedded in assemblies, and how the common language runtime determines the equivalence of embedded COM types.</span></span>

[<span data-ttu-id="d5328-122">Cómo: Generar ensamblados de interoperabilidad primarios mediante Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="d5328-122">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
<span data-ttu-id="d5328-123">Describe cómo producir ensamblados de interoperabilidad primarios con *Tlbimp.exe*  (importador de bibliotecas de tipos).</span><span class="sxs-lookup"><span data-stu-id="d5328-123">Describes how to produce primary interop assemblies using *Tlbimp.exe* (Type Library Importer).</span></span>

[<span data-ttu-id="d5328-124">Cómo: Registrar ensamblados de interoperabilidad primarios</span><span class="sxs-lookup"><span data-stu-id="d5328-124">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)  
<span data-ttu-id="d5328-125">Describe cómo registrar los ensamblados de interoperabilidad primarios antes de hacer referencia a ellos en los proyectos.</span><span class="sxs-lookup"><span data-stu-id="d5328-125">Describes how to register the primary interop assemblies before you can reference them in your projects.</span></span>

[<span data-ttu-id="d5328-126">Interoperabilidad COM sin registro</span><span class="sxs-lookup"><span data-stu-id="d5328-126">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
<span data-ttu-id="d5328-127">Describe cómo la interoperabilidad COM puede activar componentes sin usar el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="d5328-127">Describes how COM interop can activate components without using the Windows registry.</span></span>

[<span data-ttu-id="d5328-128">Cómo: Configurar componentes COM basados en .NET Framework para la activación sin registro</span><span class="sxs-lookup"><span data-stu-id="d5328-128">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](configure-net-framework-based-com-components-for-reg.md)  
<span data-ttu-id="d5328-129">Describe cómo crear un manifiesto de aplicación y cómo crear e insertar un manifiesto de componente.</span><span class="sxs-lookup"><span data-stu-id="d5328-129">Describes how to create an application manifest and how to create and embed a component manifest.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d5328-130">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d5328-130">Related sections</span></span>

[<span data-ttu-id="d5328-131">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="d5328-131">COM Wrappers</span></span>](../../standard/native-interop/com-wrappers.md)  
<span data-ttu-id="d5328-132">Describe los contenedores proporcionados por la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="d5328-132">Describes the wrappers provided by COM interop.</span></span>
