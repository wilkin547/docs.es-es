---
title: Empaquetar un ensamblado de .NET Framework para COM
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, packaging assemblies
- packaging assemblies for COM
- Tlbexp.exe
- TypeLibConverter class
- .NET Services Installation tool
- Assembly Registration tool
- Type Library Exporter
- Reqsvcs.exe
- interoperation with unmanaged code, exposing .NET Framework components
- interoperation with unmanaged code, packaging assemblies
- COM interop, exposing COM components
- Reqasm.exe
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
ms.openlocfilehash: 6866da283cc7cdd180aada252007d67bd72cd862
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124092"
---
# <a name="packaging-a-net-framework-assembly-for-com"></a><span data-ttu-id="f2edf-102">Empaquetar un ensamblado de .NET Framework para COM</span><span class="sxs-lookup"><span data-stu-id="f2edf-102">Packaging a .NET Framework Assembly for COM</span></span>

<span data-ttu-id="f2edf-103">Los programadores de COM pueden beneficiarse de la siguiente información sobre los tipos administrados que piensan incluir en su aplicación:</span><span class="sxs-lookup"><span data-stu-id="f2edf-103">COM developers can benefit from the following information about the managed types they plan to incorporate in their application:</span></span>

- <span data-ttu-id="f2edf-104">Una lista de tipos que las aplicaciones COM pueden consumir</span><span class="sxs-lookup"><span data-stu-id="f2edf-104">A list of types that COM applications can consume</span></span>

  <span data-ttu-id="f2edf-105">Algunos tipos administrados son invisibles para COM; algunos son visibles, pero no pueden crearse y otros son visibles y se pueden crear.</span><span class="sxs-lookup"><span data-stu-id="f2edf-105">Some managed types are invisible to COM; some are visible but not creatable; and some are both visible and creatable.</span></span> <span data-ttu-id="f2edf-106">Un ensamblado puede contener cualquier combinación de tipos invisibles, visibles, que no se pueden crear y que se pueden crear.</span><span class="sxs-lookup"><span data-stu-id="f2edf-106">An assembly can comprise any combination of invisible, visible, not creatable, and creatable types.</span></span> <span data-ttu-id="f2edf-107">Para completar, identifique los tipos de un ensamblado que se van a exponer a COM, especialmente cuando esos tipos son un subconjunto de los tipos expuestos a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2edf-107">For completeness, identify the types in an assembly that you intend to expose to COM, especially when those types are a subset of the types exposed to the .NET Framework.</span></span>

  <span data-ttu-id="f2edf-108">Para obtener información adicional, vea [Habilitar tipos de .NET para la interoperación](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="f2edf-108">For additional information, see [Qualifying .NET Types for Interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

- <span data-ttu-id="f2edf-109">Instrucciones de control de versiones</span><span class="sxs-lookup"><span data-stu-id="f2edf-109">Versioning instructions</span></span>

  <span data-ttu-id="f2edf-110">Las clases administradas que implementan la interfaz de clase (una interfaz de COM generada por la interoperabilidad) están sujetas a restricciones de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="f2edf-110">Managed classes that implement the class interface (a COM interop-generated interface) are subject to versioning restrictions.</span></span>

  <span data-ttu-id="f2edf-111">Para obtener instrucciones sobre el uso de la interfaz de clase, consulte [Presentar la interfaz de clase](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="f2edf-111">For guidelines on using the class interface, see [Introducing the class interface](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span></span>

- <span data-ttu-id="f2edf-112">Instrucciones de implementación</span><span class="sxs-lookup"><span data-stu-id="f2edf-112">Deployment instructions</span></span>

  <span data-ttu-id="f2edf-113">Los ensamblados con nombre seguro que están firmados por un editor se pueden instalar en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f2edf-113">Strong-named assemblies that are signed by a publisher can be installed into the global assembly cache.</span></span> <span data-ttu-id="f2edf-114">Los ensamblados no firmados deben instalarse en el equipo del usuario como ensamblados privados.</span><span class="sxs-lookup"><span data-stu-id="f2edf-114">Unsigned assemblies must be installed on the user's machine as private assemblies.</span></span>

  <span data-ttu-id="f2edf-115">Para más información, vea [Consideraciones de seguridad sobre ensamblados](../../standard/assembly/security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="f2edf-115">For additional information, see [Assembly Security Considerations](../../standard/assembly/security-considerations.md).</span></span>

- <span data-ttu-id="f2edf-116">Inclusión de la biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="f2edf-116">Type library inclusion</span></span>

  <span data-ttu-id="f2edf-117">La mayoría de los tipos requiere una biblioteca de tipos cuando una aplicación COM los consume.</span><span class="sxs-lookup"><span data-stu-id="f2edf-117">Most types require a type library when consumed by a COM application.</span></span> <span data-ttu-id="f2edf-118">Puede generar una biblioteca de tipos o hacer que los desarrolladores de COM realicen esta tarea.</span><span class="sxs-lookup"><span data-stu-id="f2edf-118">You can generate a type library or have COM developers perform this task.</span></span> <span data-ttu-id="f2edf-119">Windows SDK proporciona las opciones siguientes para generar una biblioteca de tipos:</span><span class="sxs-lookup"><span data-stu-id="f2edf-119">The Windows SDK provides the following options for generating a type library:</span></span>

  - [<span data-ttu-id="f2edf-120">Exportador de la biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="f2edf-120">Type Library Exporter</span></span>](#cpconpackagingassemblyforcomanchor1)

  - [<span data-ttu-id="f2edf-121">TypeLibConverter (clase)</span><span class="sxs-lookup"><span data-stu-id="f2edf-121">TypeLibConverter Class</span></span>](#cpconpackagingassemblyforcomanchor2)

  - [<span data-ttu-id="f2edf-122">Herramienta de registro de ensamblados</span><span class="sxs-lookup"><span data-stu-id="f2edf-122">Assembly Registration Tool</span></span>](#cpconpackagingassemblyforcomanchor3)

  - [<span data-ttu-id="f2edf-123">Herramienta de instalación de servicios de .NET</span><span class="sxs-lookup"><span data-stu-id="f2edf-123">.NET Services Installation Tool</span></span>](#cpconpackagingassemblyforcomanchor4)

  <span data-ttu-id="f2edf-124">Independientemente del mecanismo que elija, en la biblioteca de tipos generada solo se incluyen los tipos públicos definidos en el ensamblado que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="f2edf-124">Regardless of the mechanism you choose, only public types defined in the assembly you supply are included in the generated type library.</span></span>

<span data-ttu-id="f2edf-125">Para obtener instrucciones, vea [Cómo: Insertar bibliotecas de tipos como recursos de Win32 en aplicaciones basadas en .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f2edf-125">For instructions, see [How to: Embed Type Libraries as Win32 Resources in .NET-Based Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span></span>

<a name="cpconpackagingassemblyforcomanchor1"></a>

## <a name="type-library-exporter"></a><span data-ttu-id="f2edf-126">Exportador de la biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="f2edf-126">Type Library Exporter</span></span>

<span data-ttu-id="f2edf-127">El [exportador de la biblioteca de tipos (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) es una herramienta de línea de comandos que convierte las clases e interfaces contenidas en un ensamblado en una biblioteca de tipos COM.</span><span class="sxs-lookup"><span data-stu-id="f2edf-127">The [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) is a command-line tool that converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="f2edf-128">Una vez que la información de tipos de la clase está disponible, los clientes COM pueden crear una instancia de la clase de .NET y llamar a los métodos de la instancia, como si se tratase de un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="f2edf-128">Once the type information of the class is available, COM clients can create an instance of the .NET class and call the methods of the instance, just as if it were a COM object.</span></span> <span data-ttu-id="f2edf-129">Tlbexp.exe convierte todo el ensamblado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f2edf-129">Tlbexp.exe converts an entire assembly at one time.</span></span> <span data-ttu-id="f2edf-130">No se puede utilizar Tlbexp.exe para generar información de tipos correspondiente a un subconjunto de los tipos definidos en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f2edf-130">You cannot use Tlbexp.exe to generate type information for a subset of the types defined in an assembly.</span></span>

<a name="cpconpackagingassemblyforcomanchor2"></a>

## <a name="typelibconverter-class"></a><span data-ttu-id="f2edf-131">TypeLibConverter (clase)</span><span class="sxs-lookup"><span data-stu-id="f2edf-131">TypeLibConverter Class</span></span>

<span data-ttu-id="f2edf-132">La clase <xref:System.Runtime.InteropServices.TypeLibConverter>, que se encuentra en el espacio de nombres **System.Runtime.Interop**, convierte las clases e interfaces de un ensamblado en una biblioteca de tipos COM.</span><span class="sxs-lookup"><span data-stu-id="f2edf-132">The <xref:System.Runtime.InteropServices.TypeLibConverter> class, located in the **System.Runtime.Interop** namespace, converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="f2edf-133">Esta API genera la misma información de tipos que el Exportador de la biblioteca de tipos, descrito en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="f2edf-133">This API produces the same type information as the Type Library Exporter, described in the previous section.</span></span>

<span data-ttu-id="f2edf-134">La **clase TypeLibConverter** implementa el <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span><span class="sxs-lookup"><span data-stu-id="f2edf-134">The **TypeLibConverter class** implements the <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span></span>

<a name="cpconpackagingassemblyforcomanchor3"></a>

## <a name="assembly-registration-tool"></a><span data-ttu-id="f2edf-135">Herramienta de registro de ensamblados</span><span class="sxs-lookup"><span data-stu-id="f2edf-135">Assembly Registration Tool</span></span>

<span data-ttu-id="f2edf-136">La [Herramienta de registro de ensamblados (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) puede generar y registrar una biblioteca de tipos cuando se aplica la opción **/tlb:** .</span><span class="sxs-lookup"><span data-stu-id="f2edf-136">The [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) can generate and register a type library when you apply the **/tlb:** option.</span></span> <span data-ttu-id="f2edf-137">Los clientes COM requieren que las bibliotecas de tipos se instalen en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="f2edf-137">COM clients require that type libraries be installed in the Windows registry.</span></span> <span data-ttu-id="f2edf-138">Sin esta opción, Regasm.exe solo registra los tipos en un ensamblado, no la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="f2edf-138">Without this option, Regasm.exe only registers the types in an assembly, not the type library.</span></span> <span data-ttu-id="f2edf-139">Registrar los tipos en un ensamblado y registrar la biblioteca de tipos son actividades distintas.</span><span class="sxs-lookup"><span data-stu-id="f2edf-139">Registering the types in an assembly and registering the type library are distinct activities.</span></span>

<a name="cpconpackagingassemblyforcomanchor4"></a>

## <a name="net-services-installation-tool"></a><span data-ttu-id="f2edf-140">Herramienta de instalación de servicios de .NET</span><span class="sxs-lookup"><span data-stu-id="f2edf-140">.NET Services Installation Tool</span></span>

<span data-ttu-id="f2edf-141">La [Herramienta de instalación de servicios de .NET (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) agrega clases administradas a servicios de componentes de Windows 2000 y combina varias tareas en una única herramienta.</span><span class="sxs-lookup"><span data-stu-id="f2edf-141">The [.NET Services Installation Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) adds managed classes to Windows 2000 Component Services and combines several tasks within a single tool.</span></span> <span data-ttu-id="f2edf-142">Además de cargar y registrar un ensamblado, Regsvcs.exe puede generar, registrar e instalar la biblioteca de tipos en una aplicación COM+ 1.0 existente.</span><span class="sxs-lookup"><span data-stu-id="f2edf-142">In addition to loading and registering an assembly, Regsvcs.exe can generate, register, and install the type library into an existing COM+ 1.0 application.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2edf-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2edf-143">See also</span></span>

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- <xref:System.Runtime.InteropServices.ITypeLibConverter>
- [<span data-ttu-id="f2edf-144">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="f2edf-144">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="f2edf-145">Habilitar tipos de .NET para la interoperación</span><span class="sxs-lookup"><span data-stu-id="f2edf-145">Qualifying .NET Types for Interoperation</span></span>](../../standard/native-interop/qualify-net-types-for-interoperation.md)
- [<span data-ttu-id="f2edf-146">Presentar la interfaz de clase</span><span class="sxs-lookup"><span data-stu-id="f2edf-146">Introducing the class interface</span></span>](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="f2edf-147">Consideraciones de seguridad sobre ensamblados</span><span class="sxs-lookup"><span data-stu-id="f2edf-147">Assembly Security Considerations</span></span>](../../standard/assembly/security-considerations.md)
- [<span data-ttu-id="f2edf-148">Tlbexp.exe (Exportador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="f2edf-148">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="f2edf-149">Registrar ensamblados con COM</span><span class="sxs-lookup"><span data-stu-id="f2edf-149">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="f2edf-150">[Cómo: Insertar bibliotecas de tipos como recursos de Win32 en aplicaciones](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f2edf-150">[How to: Embed Type Libraries as Win32 Resources in Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span></span>
