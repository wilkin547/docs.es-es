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
# <a name="operator-overloads"></a>Sobrecargas de operador

Las sobrecargas de operador permiten que los tipos de marco aparezcan como si fueran primitivos de lenguaje integrados.

 Aunque se permiten y son útiles en algunas situaciones, las sobrecargas de operador deben usarse con precaución. Hay muchos casos en los que se ha abusado de la sobrecarga de operador, por ejemplo, cuando los diseñadores de marcos empezaron a usar operadores para aquellas operaciones que deberían ser métodos simples. Las instrucciones siguientes deberían ayudarle a decidir cuándo y cómo usar la sobrecarga de operador.

 ❌ EVITE definir sobrecargas de operador, excepto en aquellos tipos que deberían ser similares a los tipos primitivos (integrados).

 ✔️ CONSIDERE la posibilidad de definir sobrecargas de operador en un tipo que debería ser similar a un tipo primitivo.

 Por ejemplo, <xref:System.String?displayProperty=nameWithType> tiene `operator==` y `operator!=` definidas.

 ✔️ DEFINA sobrecargas de operador en estructuras que representan números (como <xref:System.Decimal?displayProperty=nameWithType>).

 ❌ NO sea ingenioso a la hora de definir sobrecargas de operador.

 La sobrecarga de operadores es útil en los casos en los que es inmediatamente obvio cuál será el resultado de la operación. Por ejemplo, tiene sentido poder restar <xref:System.DateTime> de otro valor `DateTime` y obtener <xref:System.TimeSpan>. Sin embargo, no es apropiado usar el operador de unión lógica para unir dos consultas de base de datos o usar el operador de desplazamiento para escribir en una secuencia.

 ❌ NO proporcione sobrecargas de operador a no ser que al menos uno de los operandos sea del tipo que define la sobrecarga.

 ✔️ SOBRECARGUE operadores de forma simétrica.

 Por ejemplo, si sobrecarga `operator==`, también debe sobrecargar `operator!=`. Del mismo modo, si sobrecarga `operator<`, también debe sobrecargar `operator>`, etc.

 ✔️ CONSIDERE la posibilidad de proporcionar métodos con nombres descriptivos que se correspondan con cada operador sobrecargado.

 Muchos lenguajes no admiten la sobrecarga de operador. Por esta razón, se recomienda que los tipos que sobrecarguen operadores incluyan un método secundario con un nombre específico del dominio adecuado que proporcione una funcionalidad equivalente.

 La tabla siguiente contiene una lista de operadores y los nombres de método descriptivos correspondientes.

|Símbolo de operador de C#|Nombre de los metadatos|Nombre descriptivo|
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

### <a name="overloading-operator-"></a>Sobrecarga del operador ==

 La sobrecarga de `operator ==` es bastante compleja. La semántica del operador debe ser compatible con otros miembros, como <xref:System.Object.Equals%2A?displayProperty=nameWithType>.

### <a name="conversion-operators"></a>Operadores de conversión

 Los operadores de conversión son operadores unarios que permiten la conversión de un tipo a otro. Los operadores deben definirse como miembros estáticos en el tipo de valor devuelto o de operando. Hay dos tipos de operadores de conversión: implícitos y explícitos.

 ❌ NO proporcione un operador de conversión si los usuarios finales no esperan claramente esa conversión.

 ❌ NO defina operadores de conversión fuera del dominio de un tipo.

 Por ejemplo, <xref:System.Int32>, <xref:System.Double>y <xref:System.Decimal> son tipos numéricos, mientras que <xref:System.DateTime> no lo es. Por lo tanto, no debería haber ningún operador de conversión para convertir `Double(long)` en `DateTime`. En tal caso, se prefiere un constructor.

 ❌ NO proporcione un operador de conversión implícito si es posible que la conversión tenga pérdidas.

 Por ejemplo, no debería haber una conversión implícita de `Double` a `Int32` porque `Double` tiene un intervalo más amplio que `Int32`. Se puede proporcionar un operador de conversión explícito incluso siendo posible que la conversión tenga pérdidas.

 ❌ NO inicie excepciones desde conversiones implícitas.

 Es muy difícil que los usuarios finales sepan lo que sucede, ya que es posible que no sean conscientes de que se está llevando a cabo una conversión.

 ✔️ INICIE <xref:System.InvalidCastException?displayProperty=nameWithType> si una llamada a un operador de conversión da lugar a una conversión con pérdidas y el contrato del operador no permite conversiones con pérdidas.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](member.md)
- [Instrucciones de diseño de .NET Framework](index.md)
