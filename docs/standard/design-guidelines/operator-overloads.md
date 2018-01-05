---
title: Sobrecargas de operador
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1d17aa00ce551d951b0e178304632572abf592b6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="operator-overloads"></a><span data-ttu-id="3ed64-102">Sobrecargas de operador</span><span class="sxs-lookup"><span data-stu-id="3ed64-102">Operator Overloads</span></span>
<span data-ttu-id="3ed64-103">Sobrecargas de operador permite que los tipos de marco de trabajo aparecen como si fueran primitivas del lenguaje integrados.</span><span class="sxs-lookup"><span data-stu-id="3ed64-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="3ed64-104">Aunque permitidos y útil en algunas situaciones, las sobrecargas de operador deben utilizarse con precaución.</span><span class="sxs-lookup"><span data-stu-id="3ed64-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="3ed64-105">Hay muchos casos en el operador sobrecarga se se haya manipulado, por ejemplo, cuando los diseñadores de framework empezado a usar operadores para las operaciones que deben ser métodos sencillos.</span><span class="sxs-lookup"><span data-stu-id="3ed64-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="3ed64-106">Las directrices siguientes le ayudarán a decidir cuándo y cómo utilizar la sobrecarga de operadores.</span><span class="sxs-lookup"><span data-stu-id="3ed64-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="3ed64-107">**X evitar** definir sobrecargas de operador, excepto en tipos que se sentirá como los tipos primitivos (integrados).</span><span class="sxs-lookup"><span data-stu-id="3ed64-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="3ed64-108">**✓ Considere la posibilidad de** definir sobrecargas de operador en un tipo que se sentirá como un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="3ed64-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="3ed64-109">Por ejemplo, <xref:System.String?displayProperty=nameWithType> tiene `operator==` y `operator!=` definido.</span><span class="sxs-lookup"><span data-stu-id="3ed64-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="3ed64-110">**✓ HACER** definir sobrecargas de operador en las estructuras que representan números (como <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="3ed64-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="3ed64-111">**X no** ser hermosa al definir las sobrecargas de operador.</span><span class="sxs-lookup"><span data-stu-id="3ed64-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="3ed64-112">Sobrecarga de operadores es útil en casos en los que es obvio cuál será el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="3ed64-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="3ed64-113">Por ejemplo, tiene sentido que puedan reste una ubicación <xref:System.DateTime> desde otro `DateTime` y obtener un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="3ed64-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="3ed64-114">Sin embargo, no es adecuado utilizar el operador de unión lógico para las consultas de unión de dos bases de datos o usar el operador de desplazamiento para escribir en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="3ed64-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="3ed64-115">**X DO NOT** proporcionan las sobrecargas de operador, a menos que al menos uno de los operandos es de tipo que define la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="3ed64-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="3ed64-116">**✓ HACER** sobrecargar los operadores de forma simétrica.</span><span class="sxs-lookup"><span data-stu-id="3ed64-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="3ed64-117">Por ejemplo, si se sobrecarga el `operator==`, también debe sobrecargar el `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="3ed64-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="3ed64-118">De forma similar, si se sobrecarga el `operator<`, también debe sobrecargar el `operator>`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3ed64-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="3ed64-119">**✓ Considere la posibilidad de** proporcionar métodos con nombres descriptivos que corresponden a cada operador sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="3ed64-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="3ed64-120">Muchos lenguajes no admiten la sobrecarga de operadores.</span><span class="sxs-lookup"><span data-stu-id="3ed64-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="3ed64-121">Por este motivo, se recomienda que los tipos que sobrecargan operadores incluyen un método secundario con un nombre específico de dominio adecuado que proporciona una funcionalidad equivalente.</span><span class="sxs-lookup"><span data-stu-id="3ed64-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="3ed64-122">En la tabla siguiente contiene una lista de operadores y los nombres de método descriptivo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3ed64-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="3ed64-123">Símbolo de operador de C#</span><span class="sxs-lookup"><span data-stu-id="3ed64-123">C# Operator Symbol</span></span>|<span data-ttu-id="3ed64-124">Nombre de los metadatos</span><span class="sxs-lookup"><span data-stu-id="3ed64-124">Metadata Name</span></span>|<span data-ttu-id="3ed64-125">Nombre descriptivo</span><span class="sxs-lookup"><span data-stu-id="3ed64-125">Friendly Name</span></span>|  
|-------------------------|-------------------|-------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|  
|`=`|`op_Assign`|`Assign`|  
|`<<`|`op_LeftShift`|`LeftShift`|  
|`>>`|`op_RightShift`|`RightShift`|  
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|  
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|  
|`==`|`op_Equality`|`Equals`|  
|`!=`|`op_Inequality`|`Equals`|  
|`>`|`op_GreaterThan`|`CompareTo`|  
|`<`|`op_LessThan`|`CompareTo`|  
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|  
|`<=`|`op_LessThanOrEqual`|`CompareTo`|  
|`*=`|`op_MultiplicationAssignment`|`Multiply`|  
|`-=`|`op_SubtractionAssignment`|`Subtract`|  
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|  
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|  
|`%=`|`op_ModulusAssignment`|`Mod`|  
|`+=`|`op_AdditionAssignment`|`Add`|  
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|  
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### <a name="overloading-operator-"></a><span data-ttu-id="3ed64-126">Sobrecarga de operador ==</span><span class="sxs-lookup"><span data-stu-id="3ed64-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="3ed64-127">Sobrecarga `operator ==` es bastante complicado.</span><span class="sxs-lookup"><span data-stu-id="3ed64-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="3ed64-128">La semántica del operador que deba ser compatible con otros miembros, como <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ed64-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="3ed64-129">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="3ed64-129">Conversion Operators</span></span>  
 <span data-ttu-id="3ed64-130">Operadores de conversión son operadores unarios que admite la conversión de un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="3ed64-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="3ed64-131">Los operadores se deben definir como miembros estáticos en el operando o el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="3ed64-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="3ed64-132">Hay dos tipos de operadores de conversión: implícitas y explícitas.</span><span class="sxs-lookup"><span data-stu-id="3ed64-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="3ed64-133">**X DO NOT** proporcionar un operador de conversión si los usuarios finales no esperan claramente dicha conversión.</span><span class="sxs-lookup"><span data-stu-id="3ed64-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="3ed64-134">**X DO NOT** definir operadores de conversión fuera del dominio de un tipo.</span><span class="sxs-lookup"><span data-stu-id="3ed64-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="3ed64-135">Por ejemplo, <xref:System.Int32>, <xref:System.Double>, y <xref:System.Decimal> son todos los tipos numéricos, mientras que <xref:System.DateTime> no es.</span><span class="sxs-lookup"><span data-stu-id="3ed64-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="3ed64-136">Por lo tanto, no debería haber ningún operador de conversión para convertir un `Double(long)` a una `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="3ed64-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="3ed64-137">En tal caso, es preferible un constructor.</span><span class="sxs-lookup"><span data-stu-id="3ed64-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="3ed64-138">**X DO NOT** proporciona un operador de conversión implícita si la conversión es potencialmente pérdida.</span><span class="sxs-lookup"><span data-stu-id="3ed64-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="3ed64-139">Por ejemplo, no debería haber una conversión implícita de `Double` a `Int32` porque `Double` tiene un intervalo más amplio que `Int32`.</span><span class="sxs-lookup"><span data-stu-id="3ed64-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="3ed64-140">Un operador de conversión explícita puede proporcionarse incluso si la conversión es potencialmente pérdida.</span><span class="sxs-lookup"><span data-stu-id="3ed64-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="3ed64-141">**X DO NOT** genere excepciones desde conversiones implícitas.</span><span class="sxs-lookup"><span data-stu-id="3ed64-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="3ed64-142">Es muy difícil para los usuarios finales a comprender lo que está sucediendo, ya que podrían no ser consciente de que está produciendo una conversión.</span><span class="sxs-lookup"><span data-stu-id="3ed64-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="3ed64-143">**✓ HACER** throw <xref:System.InvalidCastException?displayProperty=nameWithType> si una llamada a un operador de conversión produce una conversión con pérdida de datos y el contrato del operador no permite conversiones con pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="3ed64-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="3ed64-144">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="3ed64-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3ed64-145">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="3ed64-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ed64-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ed64-146">See Also</span></span>  
 [<span data-ttu-id="3ed64-147">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="3ed64-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="3ed64-148">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3ed64-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
