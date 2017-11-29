---
title: "Interoperar con código no administrado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2db5b8c2425637e24086f54e8ef69b0e5aac3633
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="d5ddd-102">Interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="d5ddd-102">Interoperating with Unmanaged Code</span></span>
<span data-ttu-id="d5ddd-103">.NET Framework promueve la interacción con componentes COM, servicios COM+, bibliotecas de tipos externas y muchos servicios del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="d5ddd-104">Los tipos de datos, las firmas de método y los mecanismos de control de errores varían entre los modelos de objetos administrados y no administrados.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="d5ddd-105">Para simplificar la interoperación entre los componentes de .NET Framework y el código no administrado, así como para facilitar la ruta de migración, Common Language Runtime oculta a los clientes y servidores las diferencias en estos modelos de objetos.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>  
  
 <span data-ttu-id="d5ddd-106">El código que se ejecuta bajo el control del tiempo de ejecución se denomina código administrado.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="d5ddd-107">Por el contrario, el código que se ejecuta fuera del tiempo de ejecución se denomina código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="d5ddd-108">Los componentes COM, las interfaces ActiveX y las funciones de la API de Win32 son ejemplos de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-108">COM components, ActiveX interfaces, and Win32 API functions are examples of unmanaged code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5ddd-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5ddd-109">In This Section</span></span>  
 [<span data-ttu-id="d5ddd-110">Temas sobre cómo interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="d5ddd-110">Interoperating with Unmanaged Code How-to Topics</span></span>](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 <span data-ttu-id="d5ddd-111">Proporciona vínculos a todos los temas de procedimientos que se encuentran en la documentación conceptual para interoperar con código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-111">Provides links to all How-to topics found in the conceptual documentation for interoperating with unmanaged code.</span></span>  
  
 [<span data-ttu-id="d5ddd-112">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d5ddd-112">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 <span data-ttu-id="d5ddd-113">Se describe cómo usar los componentes COM desde las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-113">Describes how to use COM components from .NET Framework applications.</span></span>  
  
 [<span data-ttu-id="d5ddd-114">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="d5ddd-114">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="d5ddd-115">Se describe cómo usar los componentes de .NET Framework desde las aplicaciones COM.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-115">Describes how to use .NET Framework components from COM applications.</span></span>  
  
 [<span data-ttu-id="d5ddd-116">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="d5ddd-116">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="d5ddd-117">Se describe cómo llamar a funciones DLL no administradas mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="d5ddd-118">Consideraciones de diseño para interoperaciones</span><span class="sxs-lookup"><span data-stu-id="d5ddd-118">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 <span data-ttu-id="d5ddd-119">Proporciona sugerencias para escribir componentes COM integrados.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-119">Provides tips for writing integrated COM components.</span></span>  
  
 [<span data-ttu-id="d5ddd-120">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d5ddd-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 <span data-ttu-id="d5ddd-121">Se describe la serialización de la interoperabilidad COM y la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-121">Describes marshaling for COM interop and platform invoke.</span></span>  
  
 [<span data-ttu-id="d5ddd-122">Asignar resultados HRESULT y excepciones</span><span class="sxs-lookup"><span data-stu-id="d5ddd-122">How to: Map HRESULTs and Exceptions</span></span>](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 <span data-ttu-id="d5ddd-123">Se describe la asignación entre las excepciones y los valores HRESULT.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-123">Describes the mapping between exceptions and HRESULTs.</span></span>  
  
 [<span data-ttu-id="d5ddd-124">Interoperar utilizando tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="d5ddd-124">Interoperating Using Generic Types</span></span>](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 <span data-ttu-id="d5ddd-125">Se describe el comportamiento de los tipos genéricos cuando se usan en la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-125">Describes the behavior of generic types when used in COM interop.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5ddd-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d5ddd-126">Related Sections</span></span>  
 [<span data-ttu-id="d5ddd-127">Interoperabilidad COM avanzada</span><span class="sxs-lookup"><span data-stu-id="d5ddd-127">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="d5ddd-128">Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5ddd-128">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>
