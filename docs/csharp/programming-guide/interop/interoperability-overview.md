---
title: "Información general sobre interoperabilidad (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c817dcd9073a5a1d4aeee558bf53d50566bbb472
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="interoperability-overview-c-programming-guide"></a><span data-ttu-id="9bea6-102">Información general sobre interoperabilidad (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9bea6-102">Interoperability Overview (C# Programming Guide)</span></span>
<span data-ttu-id="9bea6-103">En el tema se describen métodos para habilitar la interoperabilidad entre el código administrado y el código no administrado de C#.</span><span class="sxs-lookup"><span data-stu-id="9bea6-103">The topic describes methods to enable interoperability between C# managed code and unmanaged code.</span></span>  
  
## <a name="platform-invoke"></a><span data-ttu-id="9bea6-104">Invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="9bea6-104">Platform Invoke</span></span>  
 <span data-ttu-id="9bea6-105">La *invocación de plataforma* es un servicio que permite al código administrado llamar a funciones no administradas que se implementan en bibliotecas de vínculos dinámicos (DLL), como las de la API de Microsoft Win32.</span><span class="sxs-lookup"><span data-stu-id="9bea6-105">*Platform invoke* is a service that enables managed code to call unmanaged functions that are implemented in dynamic link libraries (DLLs), such as those in the Microsoft Win32 API.</span></span> <span data-ttu-id="9bea6-106">Busca y llama a una función exportada y calcula las referencias de sus argumentos (enteros, cadenas, matrices, estructuras etc.) a través de los límites de interoperación según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9bea6-106">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="9bea6-107">Para obtener más información, vea [Consumir funciones DLL no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md) y [Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).</span><span class="sxs-lookup"><span data-stu-id="9bea6-107">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md) and [How to: Use Platform Invoke to Play a Wave File](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bea6-108">[Common Language Runtime](../../../standard/clr.md) (CLR) administra el acceso a los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="9bea6-108">The [Common Language Runtime](../../../standard/clr.md) (CLR) manages access to system resources.</span></span> <span data-ttu-id="9bea6-109">Si se llama al código no administrado que está fuera de CLR, se omite este mecanismo de seguridad y, por lo tanto, existe un riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9bea6-109">Calling unmanaged code that is outside the CLR bypasses this security mechanism, and therefore presents a security risk.</span></span> <span data-ttu-id="9bea6-110">Por ejemplo, el código no administrado podría llamar directamente a recursos en código no administrado, omitiendo los mecanismos de seguridad de CLR.</span><span class="sxs-lookup"><span data-stu-id="9bea6-110">For example, unmanaged code might call resources in unmanaged code directly, bypassing CLR security mechanisms.</span></span> <span data-ttu-id="9bea6-111">Para obtener más información, vea [Seguridad de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).</span><span class="sxs-lookup"><span data-stu-id="9bea6-111">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="c-interop"></a><span data-ttu-id="9bea6-112">Interoperabilidad de C++</span><span class="sxs-lookup"><span data-stu-id="9bea6-112">C++ Interop</span></span>  
 <span data-ttu-id="9bea6-113">Puede usar la interoperabilidad de C++, también conocida como It Just Works (IJW), para encapsular una clase de C++ nativa de modo que el código creado en C# o en otro lenguaje de .NET Framework pueda consumirla.</span><span class="sxs-lookup"><span data-stu-id="9bea6-113">You can use C++ interop, also known as It Just Works (IJW), to wrap a native C++ class so that it can be consumed by code that is authored in C# or another .NET Framework language.</span></span> <span data-ttu-id="9bea6-114">Para ello, escriba código de C++ para encapsular un componente DLL o COM nativo.</span><span class="sxs-lookup"><span data-stu-id="9bea6-114">To do this, you write C++ code to wrap a native DLL or COM component.</span></span> <span data-ttu-id="9bea6-115">A diferencia de otros lenguajes de .NET Framework, [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] cuenta con compatibilidad de interoperabilidad que permite que haya código administrado y no administrado en la misma aplicación, e incluso en el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="9bea6-115">Unlike other .NET Framework languages, [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] has interoperability support that enables managed and unmanaged code to be located in the same application and even in the same file.</span></span> <span data-ttu-id="9bea6-116">Después, compile el código de C++ mediante el modificador del compilador **/clr** para generar un ensamblado administrado.</span><span class="sxs-lookup"><span data-stu-id="9bea6-116">You then build the C++ code by using the **/clr** compiler switch to produce a managed assembly.</span></span> <span data-ttu-id="9bea6-117">Finalmente, agregue una referencia al ensamblado en el proyecto de C# y use los objetos encapsulados igual que usaría otras clases administradas.</span><span class="sxs-lookup"><span data-stu-id="9bea6-117">Finally, you add a reference to the assembly in your C# project and use the wrapped objects just as you would use other managed classes.</span></span>  
  
## <a name="exposing-com-components-to-c"></a><span data-ttu-id="9bea6-118">Exponer componentes COM en C#</span><span class="sxs-lookup"><span data-stu-id="9bea6-118">Exposing COM Components to C#</span></span>  
 <span data-ttu-id="9bea6-119">Puede usar un componente COM de un proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="9bea6-119">You can consume a COM component from a C# project.</span></span> <span data-ttu-id="9bea6-120">Los pasos generales son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9bea6-120">The general steps are as follows:</span></span>  
  
1.  <span data-ttu-id="9bea6-121">Busque un componente COM para usarlo y registrarlo.</span><span class="sxs-lookup"><span data-stu-id="9bea6-121">Locate a COM component to use and register it.</span></span> <span data-ttu-id="9bea6-122">Use regsvr32.exe para registrar un componente DLL COM o para anular su registro.</span><span class="sxs-lookup"><span data-stu-id="9bea6-122">Use regsvr32.exe to register or un–register a COM DLL.</span></span>  
  
2.  <span data-ttu-id="9bea6-123">Agregue al proyecto una referencia a la biblioteca de tipos o al componente COM.</span><span class="sxs-lookup"><span data-stu-id="9bea6-123">Add to the project a reference to the COM component or type library.</span></span>  
  
     <span data-ttu-id="9bea6-124">Al agregar la referencia, [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] usa [Tlbimp.exe (importador de la biblioteca de tipos)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), que toma una biblioteca de tipos como entrada para generar un ensamblado de interoperabilidad de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9bea6-124">When you add the reference, [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] uses the [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), which takes a type library as input, to output a .NET Framework interop assembly.</span></span> <span data-ttu-id="9bea6-125">El ensamblado, también denominado "contenedor RCW", contiene las clases e interfaces administradas que encapsulan las interfaces y clases COM que se encuentran en la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="9bea6-125">The assembly, also named a runtime callable wrapper (RCW), contains managed classes and interfaces that wrap the COM classes and interfaces that are in the type library.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="9bea6-126"> agrega al proyecto una referencia al ensamblado generado.</span><span class="sxs-lookup"><span data-stu-id="9bea6-126"> adds to the project a reference to the generated assembly.</span></span>  
  
3.  <span data-ttu-id="9bea6-127">Cree una instancia de una clase definida en el RCW.</span><span class="sxs-lookup"><span data-stu-id="9bea6-127">Create an instance of a class that is defined in the RCW.</span></span> <span data-ttu-id="9bea6-128">Este, a su vez, crea una instancia del objeto COM.</span><span class="sxs-lookup"><span data-stu-id="9bea6-128">This, in turn, creates an instance of the COM object.</span></span>  
  
4.  <span data-ttu-id="9bea6-129">Use el objeto igual que usa otros objetos administrados.</span><span class="sxs-lookup"><span data-stu-id="9bea6-129">Use the object just as you use other managed objects.</span></span> <span data-ttu-id="9bea6-130">Cuando el objeto sea reclamado por la recolección de elementos no utilizados, la instancia del objeto COM también se liberará de la memoria.</span><span class="sxs-lookup"><span data-stu-id="9bea6-130">When the object is reclaimed by garbage collection, the instance of the COM object is also released from memory.</span></span>  
  
 <span data-ttu-id="9bea6-131">Para obtener más información, vea [Exponer componentes COM en .NET Framework](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).</span><span class="sxs-lookup"><span data-stu-id="9bea6-131">For more information, see [Exposing COM Components to the .NET Framework](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).</span></span>  
  
## <a name="exposing-c-to-com"></a><span data-ttu-id="9bea6-132">Exponer C# en COM</span><span class="sxs-lookup"><span data-stu-id="9bea6-132">Exposing C# to COM</span></span>  
 <span data-ttu-id="9bea6-133">Los clientes COM pueden consumir tipos de C# que se han expuesto correctamente.</span><span class="sxs-lookup"><span data-stu-id="9bea6-133">COM clients can consume C# types that have been correctly exposed.</span></span> <span data-ttu-id="9bea6-134">Los pasos básicos para exponer tipos de C# son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9bea6-134">The basic steps to expose C# types are as follows:</span></span>  
  
1.  <span data-ttu-id="9bea6-135">Agregue atributos de interoperabilidad al proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="9bea6-135">Add interop attributes in the C# project.</span></span>  
  
     <span data-ttu-id="9bea6-136">Puede hacer que un ensamblado COM sea visible modificando las propiedades del proyecto de [!INCLUDE[csprcs](~/includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bea6-136">You can make an assembly COM visible by modifying [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties.</span></span> <span data-ttu-id="9bea6-137">Para obtener más información, vea [Información de ensamblado (Cuadro de diálogo)](/visualstudio/ide/reference/assembly-information-dialog-box).</span><span class="sxs-lookup"><span data-stu-id="9bea6-137">For more information, see [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box).</span></span>  
  
2.  <span data-ttu-id="9bea6-138">Genere una biblioteca de tipos COM y regístrela para el uso de COM.</span><span class="sxs-lookup"><span data-stu-id="9bea6-138">Generate a COM type library and register it for COM usage.</span></span>  
  
     <span data-ttu-id="9bea6-139">Puede modificar las propiedades del proyecto de [!INCLUDE[csprcs](~/includes/csprcs-md.md)] para registrar automáticamente el ensamblado de C# para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="9bea6-139">You can modify [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties to automatically register the C# assembly for COM interop.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="9bea6-140"> usa [Regasm.exe (herramienta de registro de ensamblados)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb) con el modificador de la línea de comandos `/tlb`, que toma un ensamblado administrado como entrada, para generar una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="9bea6-140"> uses the [Regasm.exe (Assembly Registration Tool)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb), using the `/tlb` command-line switch, which takes a managed assembly as input, to generate a type library.</span></span> <span data-ttu-id="9bea6-141">Esta biblioteca de tipos describe los tipos `public` del ensamblado y agrega entradas del registro para que los clientes COM puedan crear clases administradas.</span><span class="sxs-lookup"><span data-stu-id="9bea6-141">This type library describes the `public` types in the assembly and adds registry entries so that COM clients can create managed classes.</span></span>  
  
 <span data-ttu-id="9bea6-142">Para obtener más información, vea [Exponer componentes de .NET Framework en COM](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) y [Clase COM de ejemplo](../../../csharp/programming-guide/interop/example-com-class.md).</span><span class="sxs-lookup"><span data-stu-id="9bea6-142">For more information, see [Exposing .NET Framework Components to COM](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) and [Example COM Class](../../../csharp/programming-guide/interop/example-com-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bea6-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bea6-143">See Also</span></span>  
 <span data-ttu-id="9bea6-144">[Improving Interop Performance](http://go.microsoft.com/fwlink/?LinkId=99564)  (Mejorar el rendimiento interoperativo)</span><span class="sxs-lookup"><span data-stu-id="9bea6-144">[Improving Interop Performance](http://go.microsoft.com/fwlink/?LinkId=99564) </span></span>  
 <span data-ttu-id="9bea6-145">[Introducción a la interoperabilidad COM](http://go.microsoft.com/fwlink/?LinkId=112406) </span><span class="sxs-lookup"><span data-stu-id="9bea6-145">[Introduction to COM Interop](http://go.microsoft.com/fwlink/?LinkId=112406) </span></span>  
 <span data-ttu-id="9bea6-146">[Marshaling between Managed and Unmanaged Code](http://go.microsoft.com/fwlink/?LinkId=112398)  (Calcular las referencias entre el código administrado y el código no administrado)</span><span class="sxs-lookup"><span data-stu-id="9bea6-146">[Marshaling between Managed and Unmanaged Code](http://go.microsoft.com/fwlink/?LinkId=112398) </span></span>  
 <span data-ttu-id="9bea6-147">[Interoperar con código no administrado](https://msdn.microsoft.com/library/sd10k43k) </span><span class="sxs-lookup"><span data-stu-id="9bea6-147">[Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k) </span></span>  
 <span data-ttu-id="9bea6-148">[Interoperabilidad COM avanzada](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span><span class="sxs-lookup"><span data-stu-id="9bea6-148">[Advanced COM Interoperability](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span></span>  
 [<span data-ttu-id="9bea6-149">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9bea6-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

