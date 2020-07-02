---
title: Interoperar con código no administrado
description: Revise la interoperación con código no administrado. CLR oculta a los clientes y servidores de qué manera difieren los modelos de objetos de los componentes de .NET y el código no administrado.
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
ms.openlocfilehash: 1cebd75907fd202715cb337593186d248107bdbb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621878"
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="55866-104">Interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="55866-104">Interoperating with unmanaged code</span></span>

<span data-ttu-id="55866-105">.NET Framework promueve la interacción con componentes COM, servicios COM+, bibliotecas de tipos externas y muchos servicios del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="55866-105">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="55866-106">Los tipos de datos, las firmas de método y los mecanismos de control de errores varían entre los modelos de objetos administrados y no administrados.</span><span class="sxs-lookup"><span data-stu-id="55866-106">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="55866-107">Para simplificar la interoperación entre los componentes de .NET Framework y el código no administrado, así como para facilitar la ruta de migración, Common Language Runtime oculta a los clientes y servidores las diferencias en estos modelos de objetos.</span><span class="sxs-lookup"><span data-stu-id="55866-107">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>

<span data-ttu-id="55866-108">El código que se ejecuta bajo el control del tiempo de ejecución se denomina código administrado.</span><span class="sxs-lookup"><span data-stu-id="55866-108">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="55866-109">Por el contrario, el código que se ejecuta fuera del tiempo de ejecución se denomina código no administrado.</span><span class="sxs-lookup"><span data-stu-id="55866-109">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="55866-110">Los componentes COM, las interfaces ActiveX y las funciones de la API de Windows son ejemplos de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="55866-110">COM components, ActiveX interfaces, and Windows API functions are examples of unmanaged code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="55866-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="55866-111">In this section</span></span>

[<span data-ttu-id="55866-112">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="55866-112">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
<span data-ttu-id="55866-113">Se describe cómo usar los componentes COM desde las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="55866-113">Describes how to use COM components from .NET Framework applications.</span></span>

[<span data-ttu-id="55866-114">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="55866-114">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
<span data-ttu-id="55866-115">Se describe cómo usar los componentes de .NET Framework desde las aplicaciones COM.</span><span class="sxs-lookup"><span data-stu-id="55866-115">Describes how to use .NET Framework components from COM applications.</span></span>

[<span data-ttu-id="55866-116">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="55866-116">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
<span data-ttu-id="55866-117">Se describe cómo llamar a funciones DLL no administradas mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="55866-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>

[<span data-ttu-id="55866-118">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="55866-118">Interop Marshaling</span></span>](interop-marshaling.md)  
<span data-ttu-id="55866-119">Se describe la serialización de la interoperabilidad COM y la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="55866-119">Describes marshaling for COM interop and platform invoke.</span></span>

[<span data-ttu-id="55866-120">Cómo: Asignar resultados HRESULT y excepciones</span><span class="sxs-lookup"><span data-stu-id="55866-120">How to: Map HRESULTs and Exceptions</span></span>](how-to-map-hresults-and-exceptions.md)  
<span data-ttu-id="55866-121">Se describe la asignación entre las excepciones y los valores HRESULT.</span><span class="sxs-lookup"><span data-stu-id="55866-121">Describes the mapping between exceptions and HRESULTs.</span></span>

[<span data-ttu-id="55866-122">Equivalencia de tipos y tipos de interoperabilidad incrustados</span><span class="sxs-lookup"><span data-stu-id="55866-122">Type Equivalence and Embedded Interop Types</span></span>](type-equivalence-and-embedded-interop-types.md)  
<span data-ttu-id="55866-123">Describe cómo la información de tipo para tipos COM está insertada en los ensamblados y cómo Common Language Runtime determina la equivalencia de los tipos COM insertados.</span><span class="sxs-lookup"><span data-stu-id="55866-123">Describes how type information for COM types is embedded in assemblies, and how the common language runtime determines the equivalence of embedded COM types.</span></span>

[<span data-ttu-id="55866-124">Cómo: para generar ensamblados de interoperabilidad primarios mediante Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="55866-124">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
<span data-ttu-id="55866-125">Describe cómo producir ensamblados de interoperabilidad primarios con *Tlbimp.exe*  (importador de bibliotecas de tipos).</span><span class="sxs-lookup"><span data-stu-id="55866-125">Describes how to produce primary interop assemblies using *Tlbimp.exe* (Type Library Importer).</span></span>

[<span data-ttu-id="55866-126">Cómo: Registrar ensamblados de interoperabilidad primarios</span><span class="sxs-lookup"><span data-stu-id="55866-126">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)  
<span data-ttu-id="55866-127">Describe cómo registrar los ensamblados de interoperabilidad primarios antes de hacer referencia a ellos en los proyectos.</span><span class="sxs-lookup"><span data-stu-id="55866-127">Describes how to register the primary interop assemblies before you can reference them in your projects.</span></span>

[<span data-ttu-id="55866-128">Interoperabilidad COM sin registro</span><span class="sxs-lookup"><span data-stu-id="55866-128">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
<span data-ttu-id="55866-129">Describe cómo la interoperabilidad COM puede activar componentes sin usar el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="55866-129">Describes how COM interop can activate components without using the Windows registry.</span></span>

[<span data-ttu-id="55866-130">Cómo: Configurar componentes COM basados en .NET Framework para la activación sin registro</span><span class="sxs-lookup"><span data-stu-id="55866-130">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](configure-net-framework-based-com-components-for-reg.md)  
<span data-ttu-id="55866-131">Describe cómo crear un manifiesto de aplicación y cómo crear e insertar un manifiesto de componente.</span><span class="sxs-lookup"><span data-stu-id="55866-131">Describes how to create an application manifest and how to create and embed a component manifest.</span></span>

## <a name="related-sections"></a><span data-ttu-id="55866-132">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="55866-132">Related sections</span></span>

[<span data-ttu-id="55866-133">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="55866-133">COM Wrappers</span></span>](../../standard/native-interop/com-wrappers.md)  
<span data-ttu-id="55866-134">Describe los contenedores proporcionados por la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="55866-134">Describes the wrappers provided by COM interop.</span></span>
