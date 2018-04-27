---
title: Interoperabilidad COM (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, COM interop
- COM interop [Visual Basic], in Visual Basic
ms.assetid: 3ffd1bdf-1b8d-47f5-87eb-75b659f64294
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3f9d7fb51198041356cfc68d49cc703dfdf78b5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="com-interop-visual-basic"></a><span data-ttu-id="0d065-102">Interoperabilidad COM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d065-102">COM Interop (Visual Basic)</span></span>
<span data-ttu-id="0d065-103">El Modelo de objetos componentes (COM) permite que un objeto exponga su funcionalidad a otros componentes y aplicaciones host.</span><span class="sxs-lookup"><span data-stu-id="0d065-103">The Component Object Model (COM) allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="0d065-104">La mayoría del software actual incluye objetos COM.</span><span class="sxs-lookup"><span data-stu-id="0d065-104">Most of today's software includes COM objects.</span></span> <span data-ttu-id="0d065-105">Aunque los ensamblados .NET son la mejor opción para las aplicaciones nuevas, en ocasiones deberá usar objetos COM.</span><span class="sxs-lookup"><span data-stu-id="0d065-105">Although .NET assemblies are the best choice for new applications, you may at times need to employ COM objects.</span></span> <span data-ttu-id="0d065-106">En esta sección se trata algunos de los problemas asociados con la creación y uso de objetos COM con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0d065-106">This section covers some of the issues associated with creating and using COM objects with Visual Basic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d065-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0d065-107">In This Section</span></span>  
 [<span data-ttu-id="0d065-108">Introducción a la interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="0d065-108">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)  
 <span data-ttu-id="0d065-109">Proporciona información general sobre la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="0d065-109">Provides an overview of COM interoperability.</span></span>  
  
 [<span data-ttu-id="0d065-110">Cómo: Hacer referencia a objetos COM desde Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d065-110">How to: Reference COM Objects from Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-reference-com-objects.md)  
 <span data-ttu-id="0d065-111">Describe cómo agregar referencias a objetos COM que tienen bibliotecas de tipos.</span><span class="sxs-lookup"><span data-stu-id="0d065-111">Covers how to add references to COM objects that have type libraries.</span></span>  
  
 [<span data-ttu-id="0d065-112">Trabajar con controles ActiveX</span><span class="sxs-lookup"><span data-stu-id="0d065-112">How to: Work with ActiveX Controls</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-work-with-activex-controls.md)  
 <span data-ttu-id="0d065-113">Muestra cómo usar controles ActiveX existentes para agregar características al cuadro de herramientas de [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d065-113">Demonstrates how to use existing ActiveX controls to add features to the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Toolbox.</span></span>  
  
 [<span data-ttu-id="0d065-114">Tutorial: Llamar a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="0d065-114">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 <span data-ttu-id="0d065-115">Describe el proceso de llamar a las API que forman parte del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="0d065-115">Steps you through the process of calling the APIs that are part of the Windows operating system.</span></span>  
  
 [<span data-ttu-id="0d065-116">Llamar a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="0d065-116">How to: Call Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-windows-apis.md)  
 <span data-ttu-id="0d065-117">Muestra cómo definir y llamar a la función `MessageBox` en User32.dll.</span><span class="sxs-lookup"><span data-stu-id="0d065-117">Demonstrates how to define and call the `MessageBox` function in User32.dll.</span></span>  
  
 [<span data-ttu-id="0d065-118">Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="0d065-118">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 <span data-ttu-id="0d065-119">Muestra cómo llamar a una función de Windows que tiene un parámetro de un tipo sin signo.</span><span class="sxs-lookup"><span data-stu-id="0d065-119">Demonstrates how to call a Windows function that has a parameter of an unsigned type.</span></span>  
  
 [<span data-ttu-id="0d065-120">Tutorial: Crear objetos COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d065-120">Walkthrough: Creating COM Objects with Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-creating-com-objects.md)  
 <span data-ttu-id="0d065-121">Describe el proceso de crear objetos COM con y sin la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="0d065-121">Steps you through the process of creating COM objects with and without the COM class template.</span></span>  
  
 [<span data-ttu-id="0d065-122">Solución de problemas de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="0d065-122">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 <span data-ttu-id="0d065-123">Trata algunos de los problemas que pueden producirse al usar COM.</span><span class="sxs-lookup"><span data-stu-id="0d065-123">Covers some of the problems you may encounter when using COM.</span></span>  
  
 [<span data-ttu-id="0d065-124">Interoperabilidad COM en aplicaciones .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0d065-124">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 <span data-ttu-id="0d065-125">Proporciona información general sobre cómo usar objetos COM y .NET Framework en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d065-125">Provides an overview of how to use COM objects and .NET Framework objects in the same application.</span></span>  
  
 [<span data-ttu-id="0d065-126">Tutorial: Implementación de la herencia mediante objetos COM</span><span class="sxs-lookup"><span data-stu-id="0d065-126">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 <span data-ttu-id="0d065-127">Describe cómo usar objetos COM existentes como base para nuevos objetos.</span><span class="sxs-lookup"><span data-stu-id="0d065-127">Describes using existing COM objects as the basis for new objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0d065-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0d065-128">Related Sections</span></span>  
 <span data-ttu-id="0d065-129">[Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="0d065-129">[Interoperating with Unmanaged Code](../../../framework/interop/index.md)</span></span>  
 <span data-ttu-id="0d065-130">Describe los servicios de interoperabilidad proporcionados por Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0d065-130">Describes interoperability services provided by the common language runtime.</span></span>  
  
 [<span data-ttu-id="0d065-131">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0d065-131">Exposing COM Components to the .NET Framework</span></span>](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730)  
 <span data-ttu-id="0d065-132">Describe el proceso de llamar a tipos COM mediante la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="0d065-132">Describes the process of calling COM types through COM interop.</span></span>  
  
 [<span data-ttu-id="0d065-133">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="0d065-133">Exposing .NET Framework Components to COM</span></span>](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6)  
 <span data-ttu-id="0d065-134">Describe la preparación y el uso de tipos administrados desde COM.</span><span class="sxs-lookup"><span data-stu-id="0d065-134">Describes the preparation and use of managed types from COM.</span></span>  
  
 [<span data-ttu-id="0d065-135">Aplicar atributos de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="0d065-135">Applying Interop Attributes</span></span>](../../../framework/interop/applying-interop-attributes.md)  
 <span data-ttu-id="0d065-136">Describe los atributos que se pueden usar al trabajar con código no administrado.</span><span class="sxs-lookup"><span data-stu-id="0d065-136">Covers attributes you can use when working with unmanaged code.</span></span>
