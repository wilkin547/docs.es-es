---
title: "Genéricos y reflexión (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], reflection
- reflection [C#], generic types
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
caps.latest.revision: 15
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
ms.openlocfilehash: 201806cca08be0633d41e10ecb7641a0f03c975b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-reflection-c-programming-guide"></a><span data-ttu-id="f6f44-102">Genéricos y reflexión (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f6f44-102">Generics and Reflection (C# Programming Guide)</span></span>
<span data-ttu-id="f6f44-103">Dado que Common Language Runtime (CLR) tiene acceso a la información de tipos genéricos en tiempo de ejecución, se puede usar la reflexión para obtener información sobre los tipos genéricos de la misma manera que para los tipos no genéricos.</span><span class="sxs-lookup"><span data-stu-id="f6f44-103">Because the Common Language Runtime (CLR) has access to generic type information at run time, you can use reflection to obtain information about generic types in the same way as for non-generic types.</span></span> <span data-ttu-id="f6f44-104">Para obtener más información, vea [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md) (Genéricos en el tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="f6f44-104">For more information, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
 <span data-ttu-id="f6f44-105">En [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] se agregan nuevos miembros a la clase <xref:System.Type> para habilitar la información de tiempo de ejecución para tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="f6f44-105">In the [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] several new members are added to the <xref:System.Type> class to enable run-time information for generic types.</span></span> <span data-ttu-id="f6f44-106">Vea la documentación sobre estas clases para obtener más información sobre cómo usar estos métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="f6f44-106">See the documentation on these classes for more information on how to use these methods and properties.</span></span> <span data-ttu-id="f6f44-107">El espacio de nombres <xref:System.Reflection.Emit> también contiene los miembros nuevos que admiten genéricos.</span><span class="sxs-lookup"><span data-stu-id="f6f44-107">The <xref:System.Reflection.Emit> namespace also contains new members that support generics.</span></span> <span data-ttu-id="f6f44-108">Vea [Cómo: Definir un tipo genérico con emisión de reflexión](../../../framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md).</span><span class="sxs-lookup"><span data-stu-id="f6f44-108">See [How to: Define a Generic Type with Reflection Emit](../../../framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md).</span></span>  
  
 <span data-ttu-id="f6f44-109">Para obtener una lista de las condiciones invariables para los términos usados en la reflexión genérica, vea los comentarios de la propiedad <xref:System.Type.IsGenericType%2A>.</span><span class="sxs-lookup"><span data-stu-id="f6f44-109">For a list of the invariant conditions for terms used in generic reflection, see the <xref:System.Type.IsGenericType%2A> property remarks.</span></span>  
  
|<span data-ttu-id="f6f44-110">Nombre de miembro System.Type</span><span class="sxs-lookup"><span data-stu-id="f6f44-110">System.Type Member Name</span></span>|<span data-ttu-id="f6f44-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6f44-111">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Type.IsGenericType%2A>|<span data-ttu-id="f6f44-112">Devuelve true si un tipo es genérico.</span><span class="sxs-lookup"><span data-stu-id="f6f44-112">Returns true if a type is generic.</span></span>|  
|<xref:System.Type.GetGenericArguments%2A>|<span data-ttu-id="f6f44-113">Devuelve una matriz de objetos `Type` que representan los argumentos de tipo proporcionados para un tipo construido, o los parámetros de tipo de una definición de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="f6f44-113">Returns an array of `Type` objects that represent the type arguments supplied for a constructed type, or the type parameters of a generic type definition.</span></span>|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|<span data-ttu-id="f6f44-114">Devuelve la definición de tipo genérico subyacente para el tipo construido actual.</span><span class="sxs-lookup"><span data-stu-id="f6f44-114">Returns the underlying generic type definition for the current constructed type.</span></span>|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|<span data-ttu-id="f6f44-115">Devuelve una matriz de objetos `Type` que representan las restricciones en el parámetro de tipo genérico actual.</span><span class="sxs-lookup"><span data-stu-id="f6f44-115">Returns an array of `Type` objects that represent the constraints on the current generic type parameter.</span></span>|  
|<xref:System.Type.ContainsGenericParameters%2A>|<span data-ttu-id="f6f44-116">Devuelve true si el tipo o cualquiera de sus tipos o métodos envolventes contiene los parámetros de tipo para los que no se proporcionaron tipos específicos.</span><span class="sxs-lookup"><span data-stu-id="f6f44-116">Returns true if the type or any of its enclosing types or methods contain type parameters for which specific types have not been supplied.</span></span>|  
|<xref:System.Type.GenericParameterAttributes%2A>|<span data-ttu-id="f6f44-117">Obtiene una combinación de marcas `GenericParameterAttributes` que describen las restricciones especiales del parámetro de tipo genérico actual.</span><span class="sxs-lookup"><span data-stu-id="f6f44-117">Gets a combination of `GenericParameterAttributes` flags that describe the special constraints of the current generic type parameter.</span></span>|  
|<xref:System.Type.GenericParameterPosition%2A>|<span data-ttu-id="f6f44-118">Para un objeto `Type` que representa un parámetro de tipo, obtiene la posición del parámetro de tipo en la lista de parámetros de tipo de la definición de tipo genérico o de método genérico que declaró el parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="f6f44-118">For a `Type` object that represents a type parameter, gets the position of the type parameter in the type parameter list of the generic type definition or generic method definition that declared the type parameter.</span></span>|  
|<xref:System.Type.IsGenericParameter%2A>|<span data-ttu-id="f6f44-119">Obtiene un valor que indica si el objeto `Type` actual representa un parámetro de tipo de una definición de un tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="f6f44-119">Gets a value that indicates whether the current `Type` represents a type parameter of a generic type or method definition.</span></span>|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|<span data-ttu-id="f6f44-120">Obtiene un valor que indica si el objeto <xref:System.Type> actual representa una definición de tipo genérico, a partir de la cual se pueden construir otros tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="f6f44-120">Gets a value that indicates whether the current <xref:System.Type> represents a generic type definition, from which other generic types can be constructed.</span></span> <span data-ttu-id="f6f44-121">Devuelve true si el tipo representa la definición de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="f6f44-121">Returns true if the type represents the definition of a generic type.</span></span>|  
|<xref:System.Type.DeclaringMethod%2A>|<span data-ttu-id="f6f44-122">Devuelve el método genérico que definió el parámetro de tipo genérico actual o NULL si el parámetro de tipo no se definió mediante un método genérico.</span><span class="sxs-lookup"><span data-stu-id="f6f44-122">Returns the generic method that defined the current generic type parameter, or null if the type parameter was not defined by a generic method.</span></span>|  
|<xref:System.Type.MakeGenericType%2A>|<span data-ttu-id="f6f44-123">Sustituye los elementos de una matriz de tipos por los parámetros de tipo de la definición de tipo genérico actual y devuelve un objeto <xref:System.Type> que representa el tipo construido resultante.</span><span class="sxs-lookup"><span data-stu-id="f6f44-123">Substitutes the elements of an array of types for the type parameters of the current generic type definition, and returns a <xref:System.Type> object representing the resulting constructed type.</span></span>|  
  
 <span data-ttu-id="f6f44-124">Además, se agregan nuevos miembros a la clase <xref:System.Reflection.MethodInfo> para habilitar la información de tiempo de ejecución para métodos genéricos.</span><span class="sxs-lookup"><span data-stu-id="f6f44-124">In addition, new members are added to the <xref:System.Reflection.MethodInfo> class to enable run-time information for generic methods.</span></span> <span data-ttu-id="f6f44-125">Para obtener una lista de las condiciones invariables para los términos usados para reflejarse en métodos genéricos, vea los comentarios de la propiedad <xref:System.Reflection.MethodInfo.IsGenericMethod%2A>.</span><span class="sxs-lookup"><span data-stu-id="f6f44-125">See the <xref:System.Reflection.MethodInfo.IsGenericMethod%2A> property remarks for a list of invariant conditions for terms used to reflect on generic methods.</span></span>  
  
|<span data-ttu-id="f6f44-126">Nombre de miembro System.Reflection.MemberInfo</span><span class="sxs-lookup"><span data-stu-id="f6f44-126">System.Reflection.MemberInfo Member Name</span></span>|<span data-ttu-id="f6f44-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6f44-127">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<xref:System.Reflection.MethodInfo.IsGenericMethod%2A>|<span data-ttu-id="f6f44-128">Devuelve true si un método es genérico.</span><span class="sxs-lookup"><span data-stu-id="f6f44-128">Returns true if a method is generic.</span></span>|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|<span data-ttu-id="f6f44-129">Devuelve una matriz de objetos Type que representan los argumentos de tipo de un método genérico construido o los parámetros de tipo de una definición de método genérico.</span><span class="sxs-lookup"><span data-stu-id="f6f44-129">Returns an array of Type objects that represent the type arguments of a constructed generic method or the type parameters of a generic method definition.</span></span>|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|<span data-ttu-id="f6f44-130">Devuelve la definición de método genérico subyacente para el método construido actual.</span><span class="sxs-lookup"><span data-stu-id="f6f44-130">Returns the underlying generic method definition for the current constructed method.</span></span>|  
|<xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A>|<span data-ttu-id="f6f44-131">Devuelve true si el método o cualquiera de sus tipos envolventes contiene los parámetros de tipo para los que no se proporcionaron tipos específicos.</span><span class="sxs-lookup"><span data-stu-id="f6f44-131">Returns true if the method or any of its enclosing types contain any type parameters for which specific types have not been supplied.</span></span>|  
|<xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A>|<span data-ttu-id="f6f44-132">Devuelve True si el tipo <xref:System.Reflection.MethodInfo> actual representa la definición de un método genérico.</span><span class="sxs-lookup"><span data-stu-id="f6f44-132">Returns true if the current <xref:System.Reflection.MethodInfo> represents the definition of a generic method.</span></span>|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|<span data-ttu-id="f6f44-133">Sustituye los elementos de una matriz de tipos por los parámetros de tipo de la definición de método genérico actual y devuelve un objeto <xref:System.Reflection.MethodInfo> que representa el método construido resultante.</span><span class="sxs-lookup"><span data-stu-id="f6f44-133">Substitutes the elements of an array of types for the type parameters of the current generic method definition, and returns a <xref:System.Reflection.MethodInfo> object representing the resulting constructed method.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6f44-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6f44-134">See Also</span></span>  
 <span data-ttu-id="f6f44-135">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6f44-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f6f44-136">[Genéricos](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6f44-136">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="f6f44-137">[Reflexión y tipos genéricos](../../../framework/reflection-and-codedom/reflection-and-generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="f6f44-137">[Reflection and Generic Types](../../../framework/reflection-and-codedom/reflection-and-generic-types.md) </span></span>  
 [<span data-ttu-id="f6f44-138">Genéricos</span><span class="sxs-lookup"><span data-stu-id="f6f44-138">Generics</span></span>](~/docs/standard/generics/index.md)

