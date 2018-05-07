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
ms.openlocfilehash: 747fc21aceae60e362c72391ae265e45d6f8445f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="operator-overloads"></a>Sobrecargas de operador
Sobrecargas de operador permite que los tipos de marco de trabajo aparecen como si fueran primitivas del lenguaje integrados.  
  
 Aunque permitidos y útil en algunas situaciones, las sobrecargas de operador deben utilizarse con precaución. Hay muchos casos en el operador sobrecarga se se haya manipulado, por ejemplo, cuando los diseñadores de framework empezado a usar operadores para las operaciones que deben ser métodos sencillos. Las directrices siguientes le ayudarán a decidir cuándo y cómo utilizar la sobrecarga de operadores.  
  
 **X evitar** definir sobrecargas de operador, excepto en tipos que se sentirá como los tipos primitivos (integrados).  
  
 **✓ Considere la posibilidad de** definir sobrecargas de operador en un tipo que se sentirá como un tipo primitivo.  
  
 Por ejemplo, <xref:System.String?displayProperty=nameWithType> tiene `operator==` y `operator!=` definido.  
  
 **✓ HACER** definir sobrecargas de operador en las estructuras que representan números (como <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X no** ser hermosa al definir las sobrecargas de operador.  
  
 Sobrecarga de operadores es útil en casos en los que es obvio cuál será el resultado de la operación. Por ejemplo, tiene sentido que puedan reste una ubicación <xref:System.DateTime> desde otro `DateTime` y obtener un <xref:System.TimeSpan>. Sin embargo, no es adecuado utilizar el operador de unión lógico para las consultas de unión de dos bases de datos o usar el operador de desplazamiento para escribir en una secuencia.  
  
 **X DO NOT** proporcionan las sobrecargas de operador, a menos que al menos uno de los operandos es de tipo que define la sobrecarga.  
  
 **✓ HACER** sobrecargar los operadores de forma simétrica.  
  
 Por ejemplo, si se sobrecarga el `operator==`, también debe sobrecargar el `operator!=`. De forma similar, si se sobrecarga el `operator<`, también debe sobrecargar el `operator>`, y así sucesivamente.  
  
 **✓ Considere la posibilidad de** proporcionar métodos con nombres descriptivos que corresponden a cada operador sobrecargado.  
  
 Muchos lenguajes no admiten la sobrecarga de operadores. Por este motivo, se recomienda que los tipos que sobrecargan operadores incluyen un método secundario con un nombre específico de dominio adecuado que proporciona una funcionalidad equivalente.  
  
 En la tabla siguiente contiene una lista de operadores y los nombres de método descriptivo correspondiente.  
  
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
  
### <a name="overloading-operator-"></a>Sobrecarga de operador ==  
 Sobrecarga `operator ==` es bastante complicado. La semántica del operador que deba ser compatible con otros miembros, como <xref:System.Object.Equals%2A?displayProperty=nameWithType>.  
  
### <a name="conversion-operators"></a>Operadores de conversión  
 Operadores de conversión son operadores unarios que admite la conversión de un tipo a otro. Los operadores se deben definir como miembros estáticos en el operando o el tipo de valor devuelto. Hay dos tipos de operadores de conversión: implícitas y explícitas.  
  
 **X DO NOT** proporcionar un operador de conversión si los usuarios finales no esperan claramente dicha conversión.  
  
 **X DO NOT** definir operadores de conversión fuera del dominio de un tipo.  
  
 Por ejemplo, <xref:System.Int32>, <xref:System.Double>, y <xref:System.Decimal> son todos los tipos numéricos, mientras que <xref:System.DateTime> no es. Por lo tanto, no debería haber ningún operador de conversión para convertir un `Double(long)` a una `DateTime`. En tal caso, es preferible un constructor.  
  
 **X DO NOT** proporciona un operador de conversión implícita si la conversión es potencialmente pérdida.  
  
 Por ejemplo, no debería haber una conversión implícita de `Double` a `Int32` porque `Double` tiene un intervalo más amplio que `Int32`. Un operador de conversión explícita puede proporcionarse incluso si la conversión es potencialmente pérdida.  
  
 **X DO NOT** genere excepciones desde conversiones implícitas.  
  
 Es muy difícil para los usuarios finales a comprender lo que está sucediendo, ya que podrían no ser consciente de que está produciendo una conversión.  
  
 **✓ HACER** throw <xref:System.InvalidCastException?displayProperty=nameWithType> si una llamada a un operador de conversión produce una conversión con pérdida de datos y el contrato del operador no permite conversiones con pérdida de datos.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
