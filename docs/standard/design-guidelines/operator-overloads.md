---
title: Sobrecargas de operador
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ca42d25a5f3456c6a10eff76d7015656322abae
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44192475"
---
# <a name="operator-overloads"></a><span data-ttu-id="578c0-102">Sobrecargas de operador</span><span class="sxs-lookup"><span data-stu-id="578c0-102">Operator Overloads</span></span>
<span data-ttu-id="578c0-103">Las sobrecargas del operador permiten tipos de marco de trabajo que aparezca como si fueran primitivas del lenguaje integrado.</span><span class="sxs-lookup"><span data-stu-id="578c0-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="578c0-104">Aunque permitidos y útil en algunas situaciones, las sobrecargas del operador deben usarse con precaución.</span><span class="sxs-lookup"><span data-stu-id="578c0-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="578c0-105">Hay muchos casos en qué operador sobrecarga ha sido en peligro, como los diseñadores de framework que comenzó a usar operadores para las operaciones que deben ser métodos sencillos.</span><span class="sxs-lookup"><span data-stu-id="578c0-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="578c0-106">Las instrucciones siguientes le ayudarán a decidir cuándo y cómo usar la sobrecarga de operadores.</span><span class="sxs-lookup"><span data-stu-id="578c0-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="578c0-107">**X AVOID** definir sobrecargas de operador, excepto en tipos que se sentirá como los tipos primitivos (integrados).</span><span class="sxs-lookup"><span data-stu-id="578c0-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="578c0-108">**✓ CONSIDER** definir sobrecargas de operador en un tipo que se sentirá como un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="578c0-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="578c0-109">Por ejemplo, <xref:System.String?displayProperty=nameWithType> tiene `operator==` y `operator!=` definido.</span><span class="sxs-lookup"><span data-stu-id="578c0-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="578c0-110">**✓ DO** definir sobrecargas de operador en las estructuras que representan números (como <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="578c0-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="578c0-111">**X DO NOT** ser hermosa al definir las sobrecargas de operador.</span><span class="sxs-lookup"><span data-stu-id="578c0-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="578c0-112">Sobrecarga de operadores es útil en casos en los que es evidente de inmediato cuál será el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="578c0-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="578c0-113">Por ejemplo, tiene sentido que poder restar uno <xref:System.DateTime> desde otro `DateTime` y obtenga un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="578c0-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="578c0-114">Sin embargo, no es adecuado para utilizar el operador de unión lógico para las consultas de unión de dos bases de datos, o utilizar el operador de desplazamiento para escribir en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="578c0-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="578c0-115">**X DO NOT** proporcionan las sobrecargas de operador, a menos que al menos uno de los operandos es de tipo que define la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="578c0-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="578c0-116">**✓ DO** sobrecargar los operadores de forma simétrica.</span><span class="sxs-lookup"><span data-stu-id="578c0-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="578c0-117">Por ejemplo, si sobrecarga el `operator==`, también debe sobrecargar el `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="578c0-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="578c0-118">De forma similar, si sobrecarga el `operator<`, también debe sobrecargar el `operator>`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="578c0-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="578c0-119">**✓ CONSIDER** proporcionar métodos con nombres descriptivos que corresponden a cada operador sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="578c0-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="578c0-120">Muchos lenguajes no admiten la sobrecarga de operadores.</span><span class="sxs-lookup"><span data-stu-id="578c0-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="578c0-121">Por este motivo, se recomienda que los tipos que sobrecargan operadores incluyen un método secundario con un nombre específico de dominio adecuado que proporciona una funcionalidad equivalente.</span><span class="sxs-lookup"><span data-stu-id="578c0-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="578c0-122">En la tabla siguiente contiene una lista de operadores y los nombres de método descriptivo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="578c0-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="578c0-123">Símbolo de operador de C#</span><span class="sxs-lookup"><span data-stu-id="578c0-123">C# Operator Symbol</span></span>|<span data-ttu-id="578c0-124">Nombre de metadatos</span><span class="sxs-lookup"><span data-stu-id="578c0-124">Metadata Name</span></span>|<span data-ttu-id="578c0-125">Nombre descriptivo</span><span class="sxs-lookup"><span data-stu-id="578c0-125">Friendly Name</span></span>|  
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
  
### <a name="overloading-operator-"></a><span data-ttu-id="578c0-126">Sobrecargar el operador ==</span><span class="sxs-lookup"><span data-stu-id="578c0-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="578c0-127">Sobrecarga `operator ==` es bastante complicado.</span><span class="sxs-lookup"><span data-stu-id="578c0-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="578c0-128">La semántica del operador debe ser compatible con otros miembros, como <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="578c0-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="578c0-129">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="578c0-129">Conversion Operators</span></span>  
 <span data-ttu-id="578c0-130">Operadores de conversión son operadores unarios que permiten la conversión de un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="578c0-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="578c0-131">Los operadores se deben definir como miembros estáticos en el operando o el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="578c0-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="578c0-132">Hay dos tipos de operadores de conversión: implícitos y explícitos.</span><span class="sxs-lookup"><span data-stu-id="578c0-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="578c0-133">**X DO NOT** proporcionar un operador de conversión si los usuarios finales no esperan claramente dicha conversión.</span><span class="sxs-lookup"><span data-stu-id="578c0-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="578c0-134">**X DO NOT** definir operadores de conversión fuera del dominio de un tipo.</span><span class="sxs-lookup"><span data-stu-id="578c0-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="578c0-135">Por ejemplo, <xref:System.Int32>, <xref:System.Double>, y <xref:System.Decimal> son todos los tipos numéricos, mientras que <xref:System.DateTime> no es.</span><span class="sxs-lookup"><span data-stu-id="578c0-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="578c0-136">Por lo tanto, no debe haber ningún operador de conversión para convertir un `Double(long)` a un `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="578c0-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="578c0-137">En tal caso, es preferible un constructor.</span><span class="sxs-lookup"><span data-stu-id="578c0-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="578c0-138">**X DO NOT** proporciona un operador de conversión implícita si la conversión es potencialmente pérdida.</span><span class="sxs-lookup"><span data-stu-id="578c0-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="578c0-139">Por ejemplo, no debería haber una conversión implícita de `Double` a `Int32` porque `Double` tiene un intervalo más amplio que `Int32`.</span><span class="sxs-lookup"><span data-stu-id="578c0-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="578c0-140">Incluso si la conversión es potencialmente con pérdida de datos, se puede proporcionar un operador de conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="578c0-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="578c0-141">**X DO NOT** genere excepciones desde conversiones implícitas.</span><span class="sxs-lookup"><span data-stu-id="578c0-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="578c0-142">Es muy difícil para los usuarios finales a saber qué está ocurriendo, ya que no pueden tener en cuenta que está realizando una conversión.</span><span class="sxs-lookup"><span data-stu-id="578c0-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="578c0-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> si una llamada a un operador de conversión produce una conversión con pérdida de datos y el contrato del operador no permite conversiones con pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="578c0-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="578c0-144">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="578c0-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="578c0-145">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="578c0-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="578c0-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="578c0-146">See also</span></span>

- [<span data-ttu-id="578c0-147">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="578c0-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="578c0-148">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="578c0-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
