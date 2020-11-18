---
title: Sobrecargas de operador
ms.date: 10/22/2008
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: 40e1c6a4a65bfc20c94223e4012e34928b25a2ab
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830043"
---
# <a name="operator-overloads"></a><span data-ttu-id="0f279-102">Sobrecargas de operador</span><span class="sxs-lookup"><span data-stu-id="0f279-102">Operator Overloads</span></span>
<span data-ttu-id="0f279-103">Las sobrecargas de operador permiten que los tipos de marco aparezcan como si fueran primitivos de lenguaje integrados.</span><span class="sxs-lookup"><span data-stu-id="0f279-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="0f279-104">Aunque se permite y útil en algunas situaciones, las sobrecargas de operador deben usarse con precaución.</span><span class="sxs-lookup"><span data-stu-id="0f279-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="0f279-105">Hay muchos casos en los que la sobrecarga de operadores se ha desusado, por ejemplo, cuando los diseñadores de Marcos empezaron a usar operadores para las operaciones que deberían ser métodos simples.</span><span class="sxs-lookup"><span data-stu-id="0f279-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="0f279-106">Las instrucciones siguientes le ayudarán a decidir cuándo y cómo usar la sobrecarga de operadores.</span><span class="sxs-lookup"><span data-stu-id="0f279-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="0f279-107">❌ Evite definir sobrecargas de operador, excepto en los tipos que deben sentir como tipos primitivos (integrados).</span><span class="sxs-lookup"><span data-stu-id="0f279-107">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="0f279-108">✔️ considere la posibilidad de definir sobrecargas de operador en un tipo que se parezca a un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="0f279-108">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="0f279-109">Por ejemplo, <xref:System.String?displayProperty=nameWithType> tiene `operator==` y ha `operator!=` definido.</span><span class="sxs-lookup"><span data-stu-id="0f279-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="0f279-110">✔️ definir sobrecargas de operador en Structs que representan números (como <xref:System.Decimal?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="0f279-110">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="0f279-111">❌ NO se debe aplicar a la definición de sobrecargas de operador.</span><span class="sxs-lookup"><span data-stu-id="0f279-111">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="0f279-112">La sobrecarga de operadores es útil en los casos en los que es inmediatamente obvio cuál será el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="0f279-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="0f279-113">Por ejemplo, tiene sentido poder restar un <xref:System.DateTime> de otro `DateTime` y obtener <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="0f279-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="0f279-114">Sin embargo, no es apropiado usar el operador de Unión lógica para unir dos consultas de base de datos o usar el operador Shift para escribir en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="0f279-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="0f279-115">❌ NO proporcione sobrecargas de operador a menos que al menos uno de los operandos sea del tipo que define la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="0f279-115">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="0f279-116">✔️ operadores de sobrecarga de manera simétrica.</span><span class="sxs-lookup"><span data-stu-id="0f279-116">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="0f279-117">Por ejemplo, si sobrecarga el `operator==` , también debe sobrecargar `operator!=` .</span><span class="sxs-lookup"><span data-stu-id="0f279-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="0f279-118">Del mismo modo, si sobrecarga el `operator<` , también debe sobrecargar el `operator>` , y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="0f279-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="0f279-119">✔️ considere la posibilidad de proporcionar métodos con nombres descriptivos que se correspondan con cada operador sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="0f279-119">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="0f279-120">Muchos lenguajes no admiten la sobrecarga de operadores.</span><span class="sxs-lookup"><span data-stu-id="0f279-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="0f279-121">Por esta razón, se recomienda que los tipos que sobrecargan operadores incluyan un método secundario con un nombre específico del dominio adecuado que proporcione una funcionalidad equivalente.</span><span class="sxs-lookup"><span data-stu-id="0f279-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="0f279-122">La tabla siguiente contiene una lista de operadores y los nombres de método descriptivos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="0f279-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="0f279-123">Símbolo del operador de C#</span><span class="sxs-lookup"><span data-stu-id="0f279-123">C# Operator Symbol</span></span>|<span data-ttu-id="0f279-124">Nombre de metadatos</span><span class="sxs-lookup"><span data-stu-id="0f279-124">Metadata Name</span></span>|<span data-ttu-id="0f279-125">Nombre descriptivo</span><span class="sxs-lookup"><span data-stu-id="0f279-125">Friendly Name</span></span>|
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

### <a name="overloading-operator-"></a><span data-ttu-id="0f279-126">Sobrecargar operador = =</span><span class="sxs-lookup"><span data-stu-id="0f279-126">Overloading Operator ==</span></span>
 <span data-ttu-id="0f279-127">La sobrecarga `operator ==` es bastante complicada.</span><span class="sxs-lookup"><span data-stu-id="0f279-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="0f279-128">La semántica del operador debe ser compatible con otros miembros, como <xref:System.Object.Equals%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0f279-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="0f279-129">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="0f279-129">Conversion Operators</span></span>
 <span data-ttu-id="0f279-130">Los operadores de conversión son operadores unarios que permiten la conversión de un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="0f279-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="0f279-131">Los operadores deben definirse como miembros estáticos en el operando o en el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0f279-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="0f279-132">Hay dos tipos de operadores de conversión: implícito y explícito.</span><span class="sxs-lookup"><span data-stu-id="0f279-132">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="0f279-133">❌ NO proporcione un operador de conversión si los usuarios finales no esperan claramente esa conversión.</span><span class="sxs-lookup"><span data-stu-id="0f279-133">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="0f279-134">❌ NO defina operadores de conversión fuera del dominio de un tipo.</span><span class="sxs-lookup"><span data-stu-id="0f279-134">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="0f279-135">Por ejemplo, <xref:System.Int32> , <xref:System.Double> y <xref:System.Decimal> son todos los tipos numéricos, mientras que <xref:System.DateTime> no es.</span><span class="sxs-lookup"><span data-stu-id="0f279-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="0f279-136">Por consiguiente, no debería haber ningún operador de conversión para convertir un `Double(long)` en `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="0f279-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="0f279-137">En tal caso, se prefiere un constructor.</span><span class="sxs-lookup"><span data-stu-id="0f279-137">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="0f279-138">❌ NO proporcione un operador de conversión implícito si la conversión es potencialmente perdida.</span><span class="sxs-lookup"><span data-stu-id="0f279-138">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="0f279-139">Por ejemplo, no debería haber una conversión implícita de `Double` a `Int32` porque `Double` tiene un intervalo más amplio que `Int32` .</span><span class="sxs-lookup"><span data-stu-id="0f279-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="0f279-140">Se puede proporcionar un operador de conversión explícito aunque la conversión sea potencialmente perdida.</span><span class="sxs-lookup"><span data-stu-id="0f279-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="0f279-141">❌ NO genere excepciones a partir de conversiones implícitas.</span><span class="sxs-lookup"><span data-stu-id="0f279-141">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="0f279-142">Es muy difícil que los usuarios finales sepan lo que sucede, ya que es posible que no sean conscientes de que se está llevando a cabo una conversión.</span><span class="sxs-lookup"><span data-stu-id="0f279-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="0f279-143">✔️ se inician <xref:System.InvalidCastException?displayProperty=nameWithType> si una llamada a un operador de conversión produce una conversión de pérdida y el contrato del operador no permite conversiones de pérdida.</span><span class="sxs-lookup"><span data-stu-id="0f279-143">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="0f279-144">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="0f279-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="0f279-145">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="0f279-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="0f279-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f279-146">See also</span></span>

- [<span data-ttu-id="0f279-147">Instrucciones para el diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="0f279-147">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="0f279-148">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="0f279-148">Framework Design Guidelines</span></span>](index.md)
