---
title: "Modificadores de acceso (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
caps.latest.revision: 32
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
ms.openlocfilehash: 38b259b4d85d54467cd15cd49e5987f6198e8d99
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-programming-guide"></a><span data-ttu-id="d20ce-102">Modificadores de acceso (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d20ce-102">Access Modifiers (C# Programming Guide)</span></span>
<span data-ttu-id="d20ce-103">Todos los tipos y miembros de tipo tienen un nivel de accesibilidad que controla si se pueden usar desde otro código del ensamblado u otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d20ce-103">All types and type members have an accessibility level, which controls whether they can be used from other code in your assembly or other assemblies.</span></span> <span data-ttu-id="d20ce-104">Puede usar los siguientes modificadores de acceso para especificar la accesibilidad de un tipo o miembro cuando lo declare:</span><span class="sxs-lookup"><span data-stu-id="d20ce-104">You can use the following access modifiers to specify the accessibility of a type or member when you declare it:</span></span>  
  
 [<span data-ttu-id="d20ce-105">public</span><span class="sxs-lookup"><span data-stu-id="d20ce-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 <span data-ttu-id="d20ce-106">Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.</span><span class="sxs-lookup"><span data-stu-id="d20ce-106">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>  
  
 [<span data-ttu-id="d20ce-107">private</span><span class="sxs-lookup"><span data-stu-id="d20ce-107">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 <span data-ttu-id="d20ce-108">Solamente el código de la misma clase o estructura puede acceder al tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="d20ce-108">The type or member can be accessed only by code in the same class or struct.</span></span>  
  
 [<span data-ttu-id="d20ce-109">protected</span><span class="sxs-lookup"><span data-stu-id="d20ce-109">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 <span data-ttu-id="d20ce-110">Solamente el código de la misma clase o estructura, o de una clase derivada de esa clase, puede acceder al tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="d20ce-110">The type or member can be accessed only by code in the same class or struct, or in a class that is derived from that class.</span></span>  
  
 [<span data-ttu-id="d20ce-111">internal</span><span class="sxs-lookup"><span data-stu-id="d20ce-111">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="d20ce-112">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.</span><span class="sxs-lookup"><span data-stu-id="d20ce-112">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>  
  
 `protected internal`  
 <span data-ttu-id="d20ce-113">Cualquier código del ensamblado en el que se ha declarado, o desde cualquier clase derivada de otro ensamblado, puede acceder al tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="d20ce-113">The type or member can be accessed by any code in the assembly in which it is declared, or from within a derived class in another assembly.</span></span> <span data-ttu-id="d20ce-114">El acceso desde otro ensamblado debe producirse en una declaración de clase que derive de la clase en la que se haya declarado el elemento interno protegido y se debe realizar mediante una instancia del tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d20ce-114">Access from another assembly must take place within a class declaration that derives from the class in which the protected internal element is declared, and it must take place through an instance of the derived class type.</span></span>  
  
 <span data-ttu-id="d20ce-115">En los ejemplos siguientes se muestra cómo especificar modificadores de acceso en un tipo y miembro:</span><span class="sxs-lookup"><span data-stu-id="d20ce-115">The following examples demonstrate how to specify access modifiers on a type and member:</span></span>  
  
 <span data-ttu-id="d20ce-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d20ce-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span></span>  
  
 <span data-ttu-id="d20ce-117">No todos los tipos o miembros pueden usar todos los modificadores de acceso en todos los contextos; en algunos casos la accesibilidad de un miembro de tipo está restringida por la accesibilidad de su tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="d20ce-117">Not all access modifiers can be used by all types or members in all contexts, and in some cases the accessibility of a type member is constrained by the accessibility of its containing type.</span></span> <span data-ttu-id="d20ce-118">En las secciones siguientes se proporcionan más detalles sobre la accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="d20ce-118">The following sections provide more details about accessibility.</span></span>  
  
## <a name="class-and-struct-accessibility"></a><span data-ttu-id="d20ce-119">Accesibilidad de clase y estructura</span><span class="sxs-lookup"><span data-stu-id="d20ce-119">Class and Struct Accessibility</span></span>  
 <span data-ttu-id="d20ce-120">Las clases y estructuras que se declaran directamente en un espacio de nombres (es decir, que no están anidadas en otras clases o estructuras) pueden ser públicas o internas.</span><span class="sxs-lookup"><span data-stu-id="d20ce-120">Classes and structs that are declared directly within a namespace (in other words, that are not nested within other classes or structs) can be either public or internal.</span></span> <span data-ttu-id="d20ce-121">Si no se especifica ningún modificador de acceso, el valor predeterminado es internal.</span><span class="sxs-lookup"><span data-stu-id="d20ce-121">Internal is the default if no access modifier is specified.</span></span>  
  
 <span data-ttu-id="d20ce-122">Los miembros de estructura, incluidas las clases y las estructuras anidadas, se pueden declarar como public, internal, o private.</span><span class="sxs-lookup"><span data-stu-id="d20ce-122">Struct members, including nested classes and structs, can be declared as public, internal, or private.</span></span> <span data-ttu-id="d20ce-123">Los miembros de clase, incluidas las clases y las estructuras anidadas, pueden ser public, protected internal, protected, internal o private.</span><span class="sxs-lookup"><span data-stu-id="d20ce-123">Class members, including nested classes and structs, can be public, protected internal, protected, internal, or private.</span></span> <span data-ttu-id="d20ce-124">El nivel de acceso de los miembros de clase y los miembros de estructura, incluidas las clases y estructuras anidadas, es private de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d20ce-124">The access level for class members and struct members, including nested classes and structs, is private by default.</span></span> <span data-ttu-id="d20ce-125">Los tipos anidados privados no son accesibles desde fuera del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="d20ce-125">Private nested types are not accessible from outside the containing type.</span></span>  
  
 <span data-ttu-id="d20ce-126">Las clases derivadas no pueden tener mayor accesibilidad que sus tipos base.</span><span class="sxs-lookup"><span data-stu-id="d20ce-126">Derived classes cannot have greater accessibility than their base types.</span></span> <span data-ttu-id="d20ce-127">En otras palabras, no puede tener una clase pública `B` que derive de una clase interna `A`.</span><span class="sxs-lookup"><span data-stu-id="d20ce-127">In other words, you cannot have a public class `B` that derives from an internal class `A`.</span></span> <span data-ttu-id="d20ce-128">Si se permitiera, convertiría `A` en público, porque todos los miembros protegidos o internos de `A` son accesibles desde la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d20ce-128">If this were allowed, it would have the effect of making `A` public, because all protected or internal members of `A` are accessible from the derived class.</span></span>  
  
 <span data-ttu-id="d20ce-129">Puede habilitar otros ensamblados concretos para acceder a los tipos internos mediante InternalsVisibleToAttribute.</span><span class="sxs-lookup"><span data-stu-id="d20ce-129">You can enable specific other assemblies to access your internal types by using the InternalsVisibleToAttribute.</span></span> <span data-ttu-id="d20ce-130">Para más información, vea [Ensamblados de confianza](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span><span class="sxs-lookup"><span data-stu-id="d20ce-130">For more information, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
## <a name="class-and-struct-member-accessibility"></a><span data-ttu-id="d20ce-131">Accesibilidad de miembros de clase y estructura</span><span class="sxs-lookup"><span data-stu-id="d20ce-131">Class and Struct Member Accessibility</span></span>  
 <span data-ttu-id="d20ce-132">Los miembros de clase (incluidas las clases y las estructuras anidadas) se pueden declarar con cualquiera de los cinco tipos de acceso.</span><span class="sxs-lookup"><span data-stu-id="d20ce-132">Class members (including nested classes and structs) can be declared with any of the five types of access.</span></span> <span data-ttu-id="d20ce-133">Los miembros de estructura no se pueden declarar como protegidos porque las estructuras no admiten la herencia.</span><span class="sxs-lookup"><span data-stu-id="d20ce-133">Struct members cannot be declared as protected because structs do not support inheritance.</span></span>  
  
 <span data-ttu-id="d20ce-134">Normalmente, la accesibilidad de un miembro no es mayor que la del tipo que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="d20ce-134">Normally, the accessibility of a member is not greater than the accessibility of the type that contains it.</span></span> <span data-ttu-id="d20ce-135">Pero un miembro público de una clase interna podría ser accesible desde fuera del ensamblado si el miembro implementa los métodos de interfaz o invalida los métodos virtuales definidos en una clase base pública.</span><span class="sxs-lookup"><span data-stu-id="d20ce-135">However, a public member of an internal class might be accessible from outside the assembly if the member implements interface methods or overrides virtual methods that are defined in a public base class.</span></span>  
  
 <span data-ttu-id="d20ce-136">El tipo de cualquier miembro que sea un campo, propiedad o evento debe ser al menos tan accesible como el propio miembro.</span><span class="sxs-lookup"><span data-stu-id="d20ce-136">The type of any member that is a field, property, or event must be at least as accessible as the member itself.</span></span> <span data-ttu-id="d20ce-137">Del mismo modo, el tipo devuelto y los tipos de parámetro de cualquier miembro que sea un método, indizador o delegado deben ser al menos tan accesibles como el propio miembro.</span><span class="sxs-lookup"><span data-stu-id="d20ce-137">Similarly, the return type and the parameter types of any member that is a method, indexer, or delegate must be at least as accessible as the member itself.</span></span> <span data-ttu-id="d20ce-138">Por ejemplo, no puede tener un método público `M` que devuelva una clase `C` a menos que `C` también sea público.</span><span class="sxs-lookup"><span data-stu-id="d20ce-138">For example, you cannot have a public method `M` that returns a class `C` unless `C` is also public.</span></span> <span data-ttu-id="d20ce-139">Del mismo modo, no puede tener una propiedad protegida de tipo `A` si `A` se declara como private.</span><span class="sxs-lookup"><span data-stu-id="d20ce-139">Likewise, you cannot have a protected property of type `A` if `A` is declared as private.</span></span>  
  
 <span data-ttu-id="d20ce-140">Los operadores definidos por el usuario siempre deben declararse como public.</span><span class="sxs-lookup"><span data-stu-id="d20ce-140">User-defined operators must always be declared as public.</span></span> <span data-ttu-id="d20ce-141">Para más información, vea [Operador (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="d20ce-141">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
 <span data-ttu-id="d20ce-142">Los finalizadores no pueden tener modificadores de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="d20ce-142">Finalizers cannot have accessibility modifiers.</span></span>  
  
 <span data-ttu-id="d20ce-143">Para establecer el nivel de acceso de un miembro de clase o estructura, agregue la palabra clave adecuada a la declaración de miembro, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d20ce-143">To set the access level for a class or struct member, add the appropriate keyword to the member declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="d20ce-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d20ce-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d20ce-145">El nivel de accesibilidad protected internal significa protected O internal, no protected E internal.</span><span class="sxs-lookup"><span data-stu-id="d20ce-145">The protected internal accessibility level means protected OR internal, not protected AND internal.</span></span> <span data-ttu-id="d20ce-146">Es decir, se puede acceder a un miembro protegido interno desde cualquier clase del mismo ensamblado, incluidas las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="d20ce-146">In other words, a protected internal member can be accessed from any class in the same assembly, including derived classes.</span></span> <span data-ttu-id="d20ce-147">Para limitar la accesibilidad a las clases derivadas del mismo ensamblado, declare la propia clase como internal y sus miembros como protected.</span><span class="sxs-lookup"><span data-stu-id="d20ce-147">To limit accessibility to only derived classes in the same assembly, declare the class itself internal, and declare its members as protected.</span></span>  
  
## <a name="other-types"></a><span data-ttu-id="d20ce-148">Otros tipos</span><span class="sxs-lookup"><span data-stu-id="d20ce-148">Other Types</span></span>  
 <span data-ttu-id="d20ce-149">Las interfaces declaradas directamente en un espacio de nombres se pueden declarar como public o internal y, al igual que las clases y las estructuras, su valor predeterminado es el acceso interno.</span><span class="sxs-lookup"><span data-stu-id="d20ce-149">Interfaces declared directly within a namespace can be declared as public or internal and, just like classes and structs, interfaces default to internal access.</span></span> <span data-ttu-id="d20ce-150">Los miembros de interfaz son siempre públicos porque el propósito de una interfaz es permitir que otros tipos accedan a una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d20ce-150">Interface members are always public because the purpose of an interface is to enable other types to access a class or struct.</span></span> <span data-ttu-id="d20ce-151">A los miembros de interfaz no se les puede aplicar ningún modificador de acceso.</span><span class="sxs-lookup"><span data-stu-id="d20ce-151">No access modifiers can be applied to interface members.</span></span>  
  
 <span data-ttu-id="d20ce-152">Los miembros de enumeración siempre son públicos y no se les puede aplicar ningún modificador de acceso.</span><span class="sxs-lookup"><span data-stu-id="d20ce-152">Enumeration members are always public, and no access modifiers can be applied.</span></span>  
  
 <span data-ttu-id="d20ce-153">Los delegados se comportan como las clases y las estructuras.</span><span class="sxs-lookup"><span data-stu-id="d20ce-153">Delegates behave like classes and structs.</span></span> <span data-ttu-id="d20ce-154">De forma predeterminada, tienen acceso interno cuando se declaran directamente en un espacio de nombres y acceso privado cuando están anidados.</span><span class="sxs-lookup"><span data-stu-id="d20ce-154">By default, they have internal access when declared directly within a namespace, and private access when nested.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d20ce-155">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d20ce-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d20ce-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="d20ce-156">See Also</span></span>  
 <span data-ttu-id="d20ce-157">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d20ce-157">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d20ce-158">[Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="d20ce-158">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="d20ce-159">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="d20ce-159">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="d20ce-160">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="d20ce-160">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="d20ce-161">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="d20ce-161">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="d20ce-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="d20ce-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="d20ce-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="d20ce-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 <span data-ttu-id="d20ce-164">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="d20ce-164">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="d20ce-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="d20ce-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="d20ce-166">interface</span><span class="sxs-lookup"><span data-stu-id="d20ce-166">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

