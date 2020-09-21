---
title: Exposición de los componentes de .NET a COM
description: Exponga los componentes de .NET a COM. Califique los tipos de .NET para la interoperación. Aplique los atributos de interoperabilidad. Empaquete un ensamblado para COM. Consuma un tipo administrado desde COM.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
ms.openlocfilehash: dc808f3e8d6bd89ba979d43e5b4ec9d787bd09b1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545264"
---
# <a name="exposing-net-components-to-com"></a><span data-ttu-id="beac3-107">Exposición de los componentes de .NET a COM</span><span class="sxs-lookup"><span data-stu-id="beac3-107">Exposing .NET components to COM</span></span>

<span data-ttu-id="beac3-108">Escribir un tipo .NET y consumirlo desde código no administrado son actividades distintas para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="beac3-108">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="beac3-109">En esta sección se describen varias sugerencias para escribir código administrado que interopere con clientes COM:</span><span class="sxs-lookup"><span data-stu-id="beac3-109">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>

- <span data-ttu-id="beac3-110">[Habilitar tipos de .NET para la interoperación](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="beac3-110">[Qualifying .NET types for interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

     <span data-ttu-id="beac3-111">Todos los tipos, métodos, propiedades, campos y eventos administrados que desee exponer a COM deben ser públicos.</span><span class="sxs-lookup"><span data-stu-id="beac3-111">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="beac3-112">Los tipos deben tener un constructor público sin parámetros, que es el único al que se puede llamar mediante COM.</span><span class="sxs-lookup"><span data-stu-id="beac3-112">Types must have a public parameterless constructor, which is the only constructor that can be invoked through COM.</span></span>

- <span data-ttu-id="beac3-113">[Aplicar atributos de interoperabilidad](../../standard/native-interop/apply-interop-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="beac3-113">[Applying interop attributes](../../standard/native-interop/apply-interop-attributes.md).</span></span>

     <span data-ttu-id="beac3-114">Los atributos personalizados de código administrado pueden mejorar la interoperabilidad de un componente.</span><span class="sxs-lookup"><span data-stu-id="beac3-114">Custom attributes within managed code can enhance the interoperability of a component.</span></span>

- <span data-ttu-id="beac3-115">[Empaquetar un ensamblado para COM](packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="beac3-115">[Packaging an assembly for COM](packaging-an-assembly-for-com.md).</span></span>

     <span data-ttu-id="beac3-116">Es posible que los programadores de COM requieran que resuma los pasos necesarios para hacer referencia a los ensamblados e implementarlos.</span><span class="sxs-lookup"><span data-stu-id="beac3-116">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>

 <span data-ttu-id="beac3-117">Además, en esta sección se identifican las tareas relacionadas con el consumo de un tipo administrado desde un cliente COM.</span><span class="sxs-lookup"><span data-stu-id="beac3-117">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>

## <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="beac3-118">Para consumir un tipo administrado desde COM</span><span class="sxs-lookup"><span data-stu-id="beac3-118">To consume a managed type from COM</span></span>

1. <span data-ttu-id="beac3-119">[Registrar ensamblados con COM](registering-assemblies-with-com.md).</span><span class="sxs-lookup"><span data-stu-id="beac3-119">[Register assemblies with COM](registering-assemblies-with-com.md).</span></span>

     <span data-ttu-id="beac3-120">Los tipos de un ensamblado (y bibliotecas de tipos) deben registrarse en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="beac3-120">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="beac3-121">Si un instalador no registra el ensamblado, indique a los programadores de COM que usen Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="beac3-121">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>

2. <span data-ttu-id="beac3-122">[Hacer referencia a tipos de .NET desde COM](how-to-reference-net-types-from-com.md).</span><span class="sxs-lookup"><span data-stu-id="beac3-122">[Reference .NET types from COM](how-to-reference-net-types-from-com.md).</span></span>

     <span data-ttu-id="beac3-123">Los desarrolladores de COM pueden hacer referencia a tipos en un ensamblado con las mismas herramientas y técnicas que usan actualmente.</span><span class="sxs-lookup"><span data-stu-id="beac3-123">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>

3. <span data-ttu-id="beac3-124">[Llamar a un objeto de .NET](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="beac3-124">[Call a .NET object](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>

     <span data-ttu-id="beac3-125">Los desarrolladores de COM pueden llamar a métodos en el objeto .NET de la misma manera que llaman a los métodos de cualquier tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="beac3-125">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="beac3-126">Por ejemplo, la API **CoCreateInstance** de COM activa objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="beac3-126">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>

4. <span data-ttu-id="beac3-127">[Implementar una aplicación para obtener acceso a COM](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="beac3-127">[Deploy an application for COM access](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>

     <span data-ttu-id="beac3-128">Un ensamblado con nombre seguro puede instalarse en la caché global de ensamblados y requiere una firma de su editor.</span><span class="sxs-lookup"><span data-stu-id="beac3-128">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="beac3-129">Los ensamblados que no tienen nombre seguro deben instalarse en el directorio de aplicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="beac3-129">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>

## <a name="see-also"></a><span data-ttu-id="beac3-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="beac3-130">See also</span></span>

- [<span data-ttu-id="beac3-131">Interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="beac3-131">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="beac3-132">Ejemplo de interoperabilidad COM: Cliente COM y servidor .NET</span><span class="sxs-lookup"><span data-stu-id="beac3-132">COM Interop Sample: COM Client and .NET Server</span></span>](com-interop-sample-com-client-and-net-server.md)
