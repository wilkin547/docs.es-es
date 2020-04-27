---
title: Habilitar tipos de .NET para la interoperación con COM
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
ms.openlocfilehash: f0b9bc03225ae3d2365a21fd3b78d09c08d4fc1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091580"
---
# <a name="qualifying-net-types-for-com-interoperation"></a><span data-ttu-id="c96d4-102">Habilitar tipos de .NET para la interoperación con COM</span><span class="sxs-lookup"><span data-stu-id="c96d4-102">Qualifying .NET Types for COM Interoperation</span></span>
<span data-ttu-id="c96d4-103">Si tiene previsto exponer tipos en un ensamblado a las aplicaciones COM, tenga en cuenta los requisitos de interoperabilidad COM en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="c96d4-103">If you intend to expose types in an assembly to COM applications, consider the requirements of COM interop at design time.</span></span> <span data-ttu-id="c96d4-104">Los tipos administrados (clase, interfaz, estructura y enumeración) se integran fácilmente con los tipos COM si se cumplen las directrices siguientes:</span><span class="sxs-lookup"><span data-stu-id="c96d4-104">Managed types (class, interface, structure, and enumeration) seamlessly integrate with COM types when you adhere to the following guidelines:</span></span>  
  
- <span data-ttu-id="c96d4-105">Las clases deben implementar interfaces de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="c96d4-105">Classes should implement interfaces explicitly.</span></span>  
  
     <span data-ttu-id="c96d4-106">Aunque la interoperabilidad COM proporciona un mecanismo para generar automáticamente una interfaz que contiene todos los miembros de la clase y los miembros de su clase base, es mucho mejor proporcionar interfaces explícitas.</span><span class="sxs-lookup"><span data-stu-id="c96d4-106">Although COM interop provides a mechanism to automatically generate an interface containing all members of the class and the members of its base class, it is far better to provide explicit interfaces.</span></span> <span data-ttu-id="c96d4-107">La interfaz generada automáticamente se denomina interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="c96d4-107">The automatically generated interface is called the class interface.</span></span> <span data-ttu-id="c96d4-108">Para obtener instrucciones, consulte [Presentar la interfaz de clase](com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="c96d4-108">For guidelines, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
     <span data-ttu-id="c96d4-109">Puede usar Visual Basic, C# y C++ para incorporar las definiciones de interfaz en el código, en lugar de tener que usar el Lenguaje de definición de interfaz (IDL) o su equivalente.</span><span class="sxs-lookup"><span data-stu-id="c96d4-109">You can use Visual Basic, C#, and C++ to incorporate interface definitions in your code, instead of having to use Interface Definition Language (IDL) or its equivalent.</span></span> <span data-ttu-id="c96d4-110">Para obtener información detallada de la sintaxis, vea la documentación del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="c96d4-110">For syntax details, see your language documentation.</span></span>  
  
- <span data-ttu-id="c96d4-111">Los tipos administrados deben ser públicos.</span><span class="sxs-lookup"><span data-stu-id="c96d4-111">Managed types must be public.</span></span>  
  
     <span data-ttu-id="c96d4-112">Solo los tipos públicos de un ensamblado se registran y se exportan a la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c96d4-112">Only public types in an assembly are registered and exported to the type library.</span></span> <span data-ttu-id="c96d4-113">Como resultado, solo los tipos públicos son visibles para COM.</span><span class="sxs-lookup"><span data-stu-id="c96d4-113">As a result, only public types are visible to COM.</span></span>  
  
     <span data-ttu-id="c96d4-114">Los tipos administrados exponen características a otro código administrado que es posible que no se expongan a COM.</span><span class="sxs-lookup"><span data-stu-id="c96d4-114">Managed types expose features to other managed code that might not be exposed to COM.</span></span> <span data-ttu-id="c96d4-115">Por ejemplo, los constructores con parámetros, los métodos estáticos y los campos de constante no se exponen a los clientes COM.</span><span class="sxs-lookup"><span data-stu-id="c96d4-115">For instance, parameterized constructors, static methods, and constant fields are not exposed to COM clients.</span></span> <span data-ttu-id="c96d4-116">Además, como el tiempo de ejecución serializa los datos dentro y fuera de un tipo, es posible que los datos se copien o se transformen.</span><span class="sxs-lookup"><span data-stu-id="c96d4-116">Further, as the runtime marshals data in and out of a type, the data might be copied or transformed.</span></span>  
  
- <span data-ttu-id="c96d4-117">Los métodos, las propiedades, los campos y los eventos deben ser públicos.</span><span class="sxs-lookup"><span data-stu-id="c96d4-117">Methods, properties, fields, and events must be public.</span></span>  
  
     <span data-ttu-id="c96d4-118">Los miembros de tipos públicos también deben ser públicos si van a ser visibles para COM.</span><span class="sxs-lookup"><span data-stu-id="c96d4-118">Members of public types must also be public if they are to be visible to COM.</span></span> <span data-ttu-id="c96d4-119">La aplicación de <xref:System.Runtime.InteropServices.ComVisibleAttribute> permite restringir la visibilidad de un ensamblado, un tipo público o miembros públicos de un tipo público.</span><span class="sxs-lookup"><span data-stu-id="c96d4-119">You can restrict the visibility of an assembly, a public type, or public members of a public type by applying the <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span></span> <span data-ttu-id="c96d4-120">De forma predeterminada, todos los tipos y miembros públicos son visibles.</span><span class="sxs-lookup"><span data-stu-id="c96d4-120">By default, all public types and members are visible.</span></span>  
  
- <span data-ttu-id="c96d4-121">Los tipos deben tener un constructor público sin parámetros para que se activen desde COM.</span><span class="sxs-lookup"><span data-stu-id="c96d4-121">Types must have a public parameterless constructor to be activated from COM.</span></span>  
  
     <span data-ttu-id="c96d4-122">Los tipos públicos administrados son visibles para COM.</span><span class="sxs-lookup"><span data-stu-id="c96d4-122">Managed, public types are visible to COM.</span></span> <span data-ttu-id="c96d4-123">Pero sin un constructor público sin parámetros (un constructor sin argumentos), los clientes COM no pueden crear el tipo.</span><span class="sxs-lookup"><span data-stu-id="c96d4-123">However, without a public parameterless constructor (a constructor with no arguments), COM clients cannot create the type.</span></span> <span data-ttu-id="c96d4-124">Los clientes COM todavía pueden usar el tipo si se activa por otros medios.</span><span class="sxs-lookup"><span data-stu-id="c96d4-124">COM clients can still use the type if it is activated by some other means.</span></span>  
  
- <span data-ttu-id="c96d4-125">Los tipos no pueden ser abstractos.</span><span class="sxs-lookup"><span data-stu-id="c96d4-125">Types cannot be abstract.</span></span>  
  
     <span data-ttu-id="c96d4-126">Ni los clientes COM ni los clientes .NET pueden crear tipos abstractos.</span><span class="sxs-lookup"><span data-stu-id="c96d4-126">Neither COM clients nor .NET clients can create abstract types.</span></span>  
  
 <span data-ttu-id="c96d4-127">Cuando se exporta a COM, se simplifica la jerarquía de herencia de un tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="c96d4-127">When exported to COM, the inheritance hierarchy of a managed type is flattened.</span></span> <span data-ttu-id="c96d4-128">El control de versiones también difiere entre los entornos administrados y no administrados.</span><span class="sxs-lookup"><span data-stu-id="c96d4-128">Versioning also differs between managed and unmanaged environments.</span></span> <span data-ttu-id="c96d4-129">Los tipos expuestos a COM no tienen las mismas características de control de versiones que otros tipos administrados.</span><span class="sxs-lookup"><span data-stu-id="c96d4-129">Types exposed to COM do not have the same versioning characteristics as other managed types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96d4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="c96d4-130">See also</span></span>

- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- [<span data-ttu-id="c96d4-131">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="c96d4-131">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="c96d4-132">Presentar la interfaz de clase</span><span class="sxs-lookup"><span data-stu-id="c96d4-132">Introducing the class interface</span></span>](com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="c96d4-133">Aplicar atributos de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="c96d4-133">Applying Interop Attributes</span></span>](../../../docs/standard/native-interop/apply-interop-attributes.md)
- [<span data-ttu-id="c96d4-134">Empaquetar un ensamblado de .NET Framework para COM</span><span class="sxs-lookup"><span data-stu-id="c96d4-134">Packaging a .NET Framework Assembly for COM</span></span>](../../../docs/framework/interop/packaging-an-assembly-for-com.md)
