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
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743687"
---
# <a name="operator-overloads"></a>Sobrecargas de operador
Las sobrecargas de operador permiten que los tipos de marco aparezcan como si fueran primitivos de lenguaje integrados.

 Aunque se permite y útil en algunas situaciones, las sobrecargas de operador deben usarse con precaución. Hay muchos casos en los que la sobrecarga de operadores se ha desusado, por ejemplo, cuando los diseñadores de Marcos empezaron a usar operadores para las operaciones que deberían ser métodos simples. Las instrucciones siguientes le ayudarán a decidir cuándo y cómo usar la sobrecarga de operadores.

 ❌ Evite definir sobrecargas de operador, excepto en los tipos que deben sentir como tipos primitivos (integrados).

 ✔️ considere la posibilidad de definir sobrecargas de operador en un tipo que se parezca a un tipo primitivo.

 Por ejemplo, <xref:System.String?displayProperty=nameWithType> tiene `operator==` y `operator!=` definidas.

 ✔️ definir sobrecargas de operador en Structs que representan números (como <xref:System.Decimal?displayProperty=nameWithType>).

 ❌ no se pueden usar para definir sobrecargas de operador.

 La sobrecarga de operadores es útil en los casos en los que es inmediatamente obvio cuál será el resultado de la operación. Por ejemplo, tiene sentido poder restar una <xref:System.DateTime> de otra `DateTime` y obtener una <xref:System.TimeSpan>. Sin embargo, no es apropiado usar el operador de Unión lógica para unir dos consultas de base de datos o usar el operador Shift para escribir en una secuencia.

 ❌ no proporcionan sobrecargas de operador a menos que al menos uno de los operandos sea del tipo que define la sobrecarga.

 ✔️ operadores de sobrecarga de manera simétrica.

 Por ejemplo, si sobrecarga el `operator==`, también debe sobrecargar el `operator!=`. Del mismo modo, si sobrecarga el `operator<`, también debe sobrecargar el `operator>`, etc.

 ✔️ considere la posibilidad de proporcionar métodos con nombres descriptivos que se correspondan con cada operador sobrecargado.

 Muchos lenguajes no admiten la sobrecarga de operadores. Por esta razón, se recomienda que los tipos que sobrecargan operadores incluyan un método secundario con un nombre específico del dominio adecuado que proporcione una funcionalidad equivalente.

 La tabla siguiente contiene una lista de operadores y los nombres de método descriptivos correspondientes.

|C#Operador Symbol|Nombre de metadatos|Nombre descriptivo|
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

### <a name="overloading-operator-"></a>Sobrecargar operador = =
 La sobrecarga de `operator ==` es bastante complicada. La semántica del operador debe ser compatible con otros miembros, como <xref:System.Object.Equals%2A?displayProperty=nameWithType>.

### <a name="conversion-operators"></a>Operadores de conversión
 Los operadores de conversión son operadores unarios que permiten la conversión de un tipo a otro. Los operadores deben definirse como miembros estáticos en el operando o en el tipo de valor devuelto. Hay dos tipos de operadores de conversión: implícito y explícito.

 ❌ no proporcionan un operador de conversión si los usuarios finales no esperan claramente dicha conversión.

 ❌ no definen operadores de conversión fuera del dominio de un tipo.

 Por ejemplo, <xref:System.Int32>, <xref:System.Double>y <xref:System.Decimal> son tipos numéricos, mientras que <xref:System.DateTime> no. Por lo tanto, no debería haber ningún operador de conversión para convertir un `Double(long)` en un `DateTime`. En tal caso, se prefiere un constructor.

 ❌ no proporcionan un operador de conversión implícito si la conversión es potencialmente perdida.

 Por ejemplo, no debería haber una conversión implícita de `Double` a `Int32` porque `Double` tiene un intervalo más amplio que `Int32`. Se puede proporcionar un operador de conversión explícito aunque la conversión sea potencialmente perdida.

 ❌ no inician excepciones a partir de conversiones implícitas.

 Es muy difícil que los usuarios finales sepan lo que sucede, ya que es posible que no sean conscientes de que se está llevando a cabo una conversión.

 ✔️ Throw <xref:System.InvalidCastException?displayProperty=nameWithType> si una llamada a un operador de conversión produce una conversión de pérdida y el contrato del operador no permite conversiones de pérdida.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
