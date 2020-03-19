---
title: Sobrecargas de operador
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401224"
---
# <a name="operator-overloads"></a><span data-ttu-id="62c94-102">Sobrecargas de operador</span><span class="sxs-lookup"><span data-stu-id="62c94-102">Operator Overloads</span></span>
<span data-ttu-id="62c94-103">Las sobrecargas de operador permiten que los tipos de marco aparezcan como si fueran primitivas de lenguaje integradas.</span><span class="sxs-lookup"><span data-stu-id="62c94-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="62c94-104">Aunque se permite y útil en algunas situaciones, las sobrecargas del operador deben utilizarse con precaución.</span><span class="sxs-lookup"><span data-stu-id="62c94-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="62c94-105">Hay muchos casos en los que se ha abusado de la sobrecarga de operadores, como cuando los diseñadores de marcos de trabajo comenzaron a usar operadores para operaciones que deberían ser métodos simples.</span><span class="sxs-lookup"><span data-stu-id="62c94-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="62c94-106">Las siguientes directrices deben ayudarle a decidir cuándo y cómo usar la sobrecarga del operador.</span><span class="sxs-lookup"><span data-stu-id="62c94-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="62c94-107">❌EVITAR la definición de sobrecargas de operador, excepto en tipos que deben sentirse como tipos primitivos (incorporados).</span><span class="sxs-lookup"><span data-stu-id="62c94-107">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="62c94-108">✔️ CONSIDER que define las sobrecargas de operador en un tipo que debe sentirse como un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="62c94-108">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="62c94-109">Por <xref:System.String?displayProperty=nameWithType> ejemplo, `operator==` `operator!=` tiene y ha definido.</span><span class="sxs-lookup"><span data-stu-id="62c94-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="62c94-110">✔️ DO define nadeos en estructuras que representan números (como <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="62c94-110">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="62c94-111">❌NO sea lindo al definir las sobrecargas del operador.</span><span class="sxs-lookup"><span data-stu-id="62c94-111">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="62c94-112">La sobrecarga del operador es útil en los casos en los que es inmediatamente obvio cuál será el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="62c94-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="62c94-113">Por ejemplo, tiene sentido poder restar <xref:System.DateTime> `DateTime` uno de <xref:System.TimeSpan>otro y obtener un archivo .</span><span class="sxs-lookup"><span data-stu-id="62c94-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="62c94-114">Sin embargo, no es adecuado utilizar el operador de unión lógica para unir dos consultas de base de datos o usar el operador shift para escribir en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="62c94-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="62c94-115">❌NO proporcione sobrecargas de operador a menos que al menos uno de los operandos sea del tipo que define la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="62c94-115">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="62c94-116">✔️ DO sobrecarga a los operadores de forma simétrica.</span><span class="sxs-lookup"><span data-stu-id="62c94-116">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="62c94-117">Por ejemplo, si `operator==`sobrecarga el archivo `operator!=`, también debe sobrecargar el archivo .</span><span class="sxs-lookup"><span data-stu-id="62c94-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="62c94-118">Del mismo modo, `operator<`si sobrecarga el `operator>`archivo , también debe sobrecargar el archivo , y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="62c94-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="62c94-119">✔️ CONSIDERA proporcionar métodos con nombres descriptivos que corresponden a cada operador sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="62c94-119">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="62c94-120">Muchos lenguajes no admiten la sobrecarga del operador.</span><span class="sxs-lookup"><span data-stu-id="62c94-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="62c94-121">Por este motivo, se recomienda que los tipos que sobrecargan operadores incluyen un método secundario con un nombre específico de dominio adecuado que proporciona una funcionalidad equivalente.</span><span class="sxs-lookup"><span data-stu-id="62c94-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="62c94-122">La tabla siguiente contiene una lista de operadores y los nombres de método descriptivos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="62c94-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="62c94-123">Símbolo del operador de C-</span><span class="sxs-lookup"><span data-stu-id="62c94-123">C# Operator Symbol</span></span>|<span data-ttu-id="62c94-124">Nombre de los metadatos</span><span class="sxs-lookup"><span data-stu-id="62c94-124">Metadata Name</span></span>|<span data-ttu-id="62c94-125">Nombre descriptivo</span><span class="sxs-lookup"><span data-stu-id="62c94-125">Friendly Name</span></span>|
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

### <a name="overloading-operator-"></a><span data-ttu-id="62c94-126">Operador de sobrecarga ( Sobrecarga del operador)</span><span class="sxs-lookup"><span data-stu-id="62c94-126">Overloading Operator ==</span></span>
 <span data-ttu-id="62c94-127">La `operator ==` sobrecarga es bastante complicada.</span><span class="sxs-lookup"><span data-stu-id="62c94-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="62c94-128">La semántica del operador debe ser compatible con otros <xref:System.Object.Equals%2A?displayProperty=nameWithType>miembros, como .</span><span class="sxs-lookup"><span data-stu-id="62c94-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="62c94-129">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="62c94-129">Conversion Operators</span></span>
 <span data-ttu-id="62c94-130">Los operadores de conversión son operadores unarios que permiten la conversión de un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="62c94-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="62c94-131">Los operadores deben definirse como miembros estáticos en el operando o en el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="62c94-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="62c94-132">Hay dos tipos de operadores de conversión: implícito y explícito.</span><span class="sxs-lookup"><span data-stu-id="62c94-132">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="62c94-133">❌NO proporcione un operador de conversión si los usuarios finales no esperan claramente dicha conversión.</span><span class="sxs-lookup"><span data-stu-id="62c94-133">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="62c94-134">❌NO defina operadores de conversión fuera del dominio de un tipo.</span><span class="sxs-lookup"><span data-stu-id="62c94-134">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="62c94-135">Por <xref:System.Int32>ejemplo, <xref:System.Double>, <xref:System.Decimal> , y son <xref:System.DateTime> todos los tipos numéricos, mientras que no lo es.</span><span class="sxs-lookup"><span data-stu-id="62c94-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="62c94-136">Por lo tanto, no debe `Double(long)` haber `DateTime`ningún operador de conversión para convertir a a un archivo .</span><span class="sxs-lookup"><span data-stu-id="62c94-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="62c94-137">Un constructor es preferible en tal caso.</span><span class="sxs-lookup"><span data-stu-id="62c94-137">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="62c94-138">❌NO proporcione un operador de conversión implícito si la conversión es potencialmente con pérdida.</span><span class="sxs-lookup"><span data-stu-id="62c94-138">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="62c94-139">Por ejemplo, no debe haber `Double` una `Int32` `Double` conversión implícita `Int32`de a porque tiene un rango más amplio que .</span><span class="sxs-lookup"><span data-stu-id="62c94-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="62c94-140">Se puede proporcionar un operador de conversión explícito incluso si la conversión es potencialmente con pérdida.</span><span class="sxs-lookup"><span data-stu-id="62c94-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="62c94-141">❌NO produzca excepciones de conversiones implícitas.</span><span class="sxs-lookup"><span data-stu-id="62c94-141">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="62c94-142">Es muy difícil para los usuarios finales entender lo que está sucediendo, porque es posible que no sean conscientes de que se está produciendo una conversión.</span><span class="sxs-lookup"><span data-stu-id="62c94-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="62c94-143">✔️ produce <xref:System.InvalidCastException?displayProperty=nameWithType> si una llamada a un operador de conversión da como resultado una conversión con pérdida y el contrato del operador no permite conversiones con pérdida.</span><span class="sxs-lookup"><span data-stu-id="62c94-143">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="62c94-144">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="62c94-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="62c94-145">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="62c94-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="62c94-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62c94-146">See also</span></span>

- [<span data-ttu-id="62c94-147">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="62c94-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="62c94-148">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="62c94-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
