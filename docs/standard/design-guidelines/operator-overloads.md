---
description: 'Más información acerca de: Sobrecargas de operador'
title: Sobrecargas de operador
ms.date: 10/22/2008
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: e6552f35081afa542e4dc14239206a63c7c1bd59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713330"
---
# <a name="operator-overloads"></a><span data-ttu-id="6fff2-103">Sobrecargas de operador</span><span class="sxs-lookup"><span data-stu-id="6fff2-103">Operator Overloads</span></span>

<span data-ttu-id="6fff2-104">Las sobrecargas de operador permiten que los tipos de marco aparezcan como si fueran primitivos de lenguaje integrados.</span><span class="sxs-lookup"><span data-stu-id="6fff2-104">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="6fff2-105">Aunque se permiten y son útiles en algunas situaciones, las sobrecargas de operador deben usarse con precaución.</span><span class="sxs-lookup"><span data-stu-id="6fff2-105">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="6fff2-106">Hay muchos casos en los que se ha abusado de la sobrecarga de operador, por ejemplo, cuando los diseñadores de marcos empezaron a usar operadores para aquellas operaciones que deberían ser métodos simples.</span><span class="sxs-lookup"><span data-stu-id="6fff2-106">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="6fff2-107">Las instrucciones siguientes deberían ayudarle a decidir cuándo y cómo usar la sobrecarga de operador.</span><span class="sxs-lookup"><span data-stu-id="6fff2-107">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="6fff2-108">❌ EVITE definir sobrecargas de operador, excepto en aquellos tipos que deberían ser similares a los tipos primitivos (integrados).</span><span class="sxs-lookup"><span data-stu-id="6fff2-108">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="6fff2-109">✔️ CONSIDERE la posibilidad de definir sobrecargas de operador en un tipo que debería ser similar a un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="6fff2-109">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="6fff2-110">Por ejemplo, <xref:System.String?displayProperty=nameWithType> tiene `operator==` y `operator!=` definidas.</span><span class="sxs-lookup"><span data-stu-id="6fff2-110">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="6fff2-111">✔️ DEFINA sobrecargas de operador en estructuras que representan números (como <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="6fff2-111">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="6fff2-112">❌ NO sea ingenioso a la hora de definir sobrecargas de operador.</span><span class="sxs-lookup"><span data-stu-id="6fff2-112">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="6fff2-113">La sobrecarga de operadores es útil en los casos en los que es inmediatamente obvio cuál será el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="6fff2-113">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="6fff2-114">Por ejemplo, tiene sentido poder restar <xref:System.DateTime> de otro valor `DateTime` y obtener <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="6fff2-114">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="6fff2-115">Sin embargo, no es apropiado usar el operador de unión lógica para unir dos consultas de base de datos o usar el operador de desplazamiento para escribir en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="6fff2-115">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="6fff2-116">❌ NO proporcione sobrecargas de operador a no ser que al menos uno de los operandos sea del tipo que define la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="6fff2-116">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="6fff2-117">✔️ SOBRECARGUE operadores de forma simétrica.</span><span class="sxs-lookup"><span data-stu-id="6fff2-117">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="6fff2-118">Por ejemplo, si sobrecarga `operator==`, también debe sobrecargar `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="6fff2-118">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="6fff2-119">Del mismo modo, si sobrecarga `operator<`, también debe sobrecargar `operator>`, etc.</span><span class="sxs-lookup"><span data-stu-id="6fff2-119">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="6fff2-120">✔️ CONSIDERE la posibilidad de proporcionar métodos con nombres descriptivos que se correspondan con cada operador sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="6fff2-120">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="6fff2-121">Muchos lenguajes no admiten la sobrecarga de operador.</span><span class="sxs-lookup"><span data-stu-id="6fff2-121">Many languages do not support operator overloading.</span></span> <span data-ttu-id="6fff2-122">Por esta razón, se recomienda que los tipos que sobrecarguen operadores incluyan un método secundario con un nombre específico del dominio adecuado que proporcione una funcionalidad equivalente.</span><span class="sxs-lookup"><span data-stu-id="6fff2-122">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="6fff2-123">La tabla siguiente contiene una lista de operadores y los nombres de método descriptivos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="6fff2-123">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="6fff2-124">Símbolo de operador de C#</span><span class="sxs-lookup"><span data-stu-id="6fff2-124">C# Operator Symbol</span></span>|<span data-ttu-id="6fff2-125">Nombre de los metadatos</span><span class="sxs-lookup"><span data-stu-id="6fff2-125">Metadata Name</span></span>|<span data-ttu-id="6fff2-126">Nombre descriptivo</span><span class="sxs-lookup"><span data-stu-id="6fff2-126">Friendly Name</span></span>|
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

### <a name="overloading-operator-"></a><span data-ttu-id="6fff2-127">Sobrecarga del operador ==</span><span class="sxs-lookup"><span data-stu-id="6fff2-127">Overloading Operator ==</span></span>

 <span data-ttu-id="6fff2-128">La sobrecarga de `operator ==` es bastante compleja.</span><span class="sxs-lookup"><span data-stu-id="6fff2-128">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="6fff2-129">La semántica del operador debe ser compatible con otros miembros, como <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6fff2-129">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="6fff2-130">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="6fff2-130">Conversion Operators</span></span>

 <span data-ttu-id="6fff2-131">Los operadores de conversión son operadores unarios que permiten la conversión de un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="6fff2-131">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="6fff2-132">Los operadores deben definirse como miembros estáticos en el tipo de valor devuelto o de operando.</span><span class="sxs-lookup"><span data-stu-id="6fff2-132">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="6fff2-133">Hay dos tipos de operadores de conversión: implícitos y explícitos.</span><span class="sxs-lookup"><span data-stu-id="6fff2-133">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="6fff2-134">❌ NO proporcione un operador de conversión si los usuarios finales no esperan claramente esa conversión.</span><span class="sxs-lookup"><span data-stu-id="6fff2-134">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="6fff2-135">❌ NO defina operadores de conversión fuera del dominio de un tipo.</span><span class="sxs-lookup"><span data-stu-id="6fff2-135">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="6fff2-136">Por ejemplo, <xref:System.Int32>, <xref:System.Double>y <xref:System.Decimal> son tipos numéricos, mientras que <xref:System.DateTime> no lo es.</span><span class="sxs-lookup"><span data-stu-id="6fff2-136">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="6fff2-137">Por lo tanto, no debería haber ningún operador de conversión para convertir `Double(long)` en `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="6fff2-137">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="6fff2-138">En tal caso, se prefiere un constructor.</span><span class="sxs-lookup"><span data-stu-id="6fff2-138">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="6fff2-139">❌ NO proporcione un operador de conversión implícito si es posible que la conversión tenga pérdidas.</span><span class="sxs-lookup"><span data-stu-id="6fff2-139">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="6fff2-140">Por ejemplo, no debería haber una conversión implícita de `Double` a `Int32` porque `Double` tiene un intervalo más amplio que `Int32`.</span><span class="sxs-lookup"><span data-stu-id="6fff2-140">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="6fff2-141">Se puede proporcionar un operador de conversión explícito incluso siendo posible que la conversión tenga pérdidas.</span><span class="sxs-lookup"><span data-stu-id="6fff2-141">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="6fff2-142">❌ NO inicie excepciones desde conversiones implícitas.</span><span class="sxs-lookup"><span data-stu-id="6fff2-142">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="6fff2-143">Es muy difícil que los usuarios finales sepan lo que sucede, ya que es posible que no sean conscientes de que se está llevando a cabo una conversión.</span><span class="sxs-lookup"><span data-stu-id="6fff2-143">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="6fff2-144">✔️ INICIE <xref:System.InvalidCastException?displayProperty=nameWithType> si una llamada a un operador de conversión da lugar a una conversión con pérdidas y el contrato del operador no permite conversiones con pérdidas.</span><span class="sxs-lookup"><span data-stu-id="6fff2-144">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="6fff2-145">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="6fff2-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="6fff2-146">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="6fff2-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="6fff2-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fff2-147">See also</span></span>

- [<span data-ttu-id="6fff2-148">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="6fff2-148">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="6fff2-149">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6fff2-149">Framework Design Guidelines</span></span>](index.md)
