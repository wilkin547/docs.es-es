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
# <a name="operator-overloads"></a>Sobrecargas de operador
Las sobrecargas de operador permiten que los tipos de marco aparezcan como si fueran primitivas de lenguaje integradas.

 Aunque se permite y útil en algunas situaciones, las sobrecargas del operador deben utilizarse con precaución. Hay muchos casos en los que se ha abusado de la sobrecarga de operadores, como cuando los diseñadores de marcos de trabajo comenzaron a usar operadores para operaciones que deberían ser métodos simples. Las siguientes directrices deben ayudarle a decidir cuándo y cómo usar la sobrecarga del operador.

 ❌EVITAR la definición de sobrecargas de operador, excepto en tipos que deben sentirse como tipos primitivos (incorporados).

 ✔️ CONSIDER que define las sobrecargas de operador en un tipo que debe sentirse como un tipo primitivo.

 Por <xref:System.String?displayProperty=nameWithType> ejemplo, `operator==` `operator!=` tiene y ha definido.

 ✔️ DO define nadeos en estructuras que representan números (como <xref:System.Decimal?displayProperty=nameWithType>).

 ❌NO sea lindo al definir las sobrecargas del operador.

 La sobrecarga del operador es útil en los casos en los que es inmediatamente obvio cuál será el resultado de la operación. Por ejemplo, tiene sentido poder restar <xref:System.DateTime> `DateTime` uno de <xref:System.TimeSpan>otro y obtener un archivo . Sin embargo, no es adecuado utilizar el operador de unión lógica para unir dos consultas de base de datos o usar el operador shift para escribir en una secuencia.

 ❌NO proporcione sobrecargas de operador a menos que al menos uno de los operandos sea del tipo que define la sobrecarga.

 ✔️ DO sobrecarga a los operadores de forma simétrica.

 Por ejemplo, si `operator==`sobrecarga el archivo `operator!=`, también debe sobrecargar el archivo . Del mismo modo, `operator<`si sobrecarga el `operator>`archivo , también debe sobrecargar el archivo , y así sucesivamente.

 ✔️ CONSIDERA proporcionar métodos con nombres descriptivos que corresponden a cada operador sobrecargado.

 Muchos lenguajes no admiten la sobrecarga del operador. Por este motivo, se recomienda que los tipos que sobrecargan operadores incluyen un método secundario con un nombre específico de dominio adecuado que proporciona una funcionalidad equivalente.

 La tabla siguiente contiene una lista de operadores y los nombres de método descriptivos correspondientes.

|Símbolo del operador de C-|Nombre de los metadatos|Nombre descriptivo|
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

### <a name="overloading-operator-"></a>Operador de sobrecarga ( Sobrecarga del operador)
 La `operator ==` sobrecarga es bastante complicada. La semántica del operador debe ser compatible con otros <xref:System.Object.Equals%2A?displayProperty=nameWithType>miembros, como .

### <a name="conversion-operators"></a>Operadores de conversión
 Los operadores de conversión son operadores unarios que permiten la conversión de un tipo a otro. Los operadores deben definirse como miembros estáticos en el operando o en el tipo de valor devuelto. Hay dos tipos de operadores de conversión: implícito y explícito.

 ❌NO proporcione un operador de conversión si los usuarios finales no esperan claramente dicha conversión.

 ❌NO defina operadores de conversión fuera del dominio de un tipo.

 Por <xref:System.Int32>ejemplo, <xref:System.Double>, <xref:System.Decimal> , y son <xref:System.DateTime> todos los tipos numéricos, mientras que no lo es. Por lo tanto, no debe `Double(long)` haber `DateTime`ningún operador de conversión para convertir a a un archivo . Un constructor es preferible en tal caso.

 ❌NO proporcione un operador de conversión implícito si la conversión es potencialmente con pérdida.

 Por ejemplo, no debe haber `Double` una `Int32` `Double` conversión implícita `Int32`de a porque tiene un rango más amplio que . Se puede proporcionar un operador de conversión explícito incluso si la conversión es potencialmente con pérdida.

 ❌NO produzca excepciones de conversiones implícitas.

 Es muy difícil para los usuarios finales entender lo que está sucediendo, porque es posible que no sean conscientes de que se está produciendo una conversión.

 ✔️ produce <xref:System.InvalidCastException?displayProperty=nameWithType> si una llamada a un operador de conversión da como resultado una conversión con pérdida y el contrato del operador no permite conversiones con pérdida.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
