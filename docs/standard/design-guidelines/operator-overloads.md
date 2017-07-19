---
title: "Sobrecargas de operador | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "sobrecargas de los operadores [.NET Framework]"
  - "operadores sobrecargados de nombres [.NET Framework]"
  - "instrucciones de diseño de miembros, operadores"
  - "operadores sobrecargados"
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Sobrecargas de operador
Sobrecargas de operador permiten tipos de framework que aparezca como si fueran primitivas del lenguaje integrado.  
  
 Aunque permitidos y útil en algunas situaciones, las sobrecargas de operador deben utilizarse con precaución. Hay muchos casos en qué operador se sobrecarga ha se haya manipulado, como cuando se inicia diseñadores de framework utilizar operadores para las operaciones que deben ser métodos sencillos. Las siguientes directrices le ayudarán a decidir cuándo y cómo utilizar la sobrecarga de operadores.  
  
 **Evitar X** definir sobrecargas de operador, excepto en los tipos que se deberían parecer a los tipos primitivos \(integrados\).  
  
 **✓ considere** definir sobrecargas de operador en un tipo que se debería parecer a un tipo primitivo.  
  
 Por ejemplo, <xref:System.String?displayProperty=fullName> tiene `operator==` y `operator!=` definido.  
  
 **✓ hacer** definir sobrecargas de operadores en estructuras que representan números \(como <xref:System.Decimal?displayProperty=fullName>\).  
  
 **X no** ser bonita al definir las sobrecargas de operador.  
  
 Sobrecarga de operadores es útil en casos en los que es obvio cuál será el resultado de la operación. Por ejemplo, tiene sentido poder restar uno <xref:System.DateTime> desde otro `DateTime` y obtenga un <xref:System.TimeSpan>. Sin embargo, no es adecuado utilizar el operador de unión lógico para las consultas de unión de dos bases de datos o usar el operador de desplazamiento para escribir en una secuencia.  
  
 **X no** proporcionan sobrecargas de operador, a menos que al menos uno de los operandos es de tipo que define la sobrecarga.  
  
 **✓ hacer** sobrecargar los operadores de forma simétrica.  
  
 Por ejemplo, si se sobrecarga el `operator==`, también debe sobrecargar el `operator!=`. De forma similar, si se sobrecarga el `operator<`, también debe sobrecargar el `operator>`, y así sucesivamente.  
  
 **✓ considere** proporcionar métodos con nombres descriptivos que corresponden a cada operador sobrecargado.  
  
 Muchos lenguajes no admiten la sobrecarga de operadores. Por este motivo, se recomienda que los tipos que sobrecargan operadores incluyen un método secundario con un nombre específico de dominio adecuado que proporciona una funcionalidad equivalente.  
  
 En la tabla siguiente contiene una lista de operadores y los nombres de método descriptivo correspondiente.  
  
|Símbolo de operador de C\#|Nombre de los metadatos|Nombre descriptivo|  
|--------------------------------|-----------------------------|------------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|`&#124;`|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|`&#124;&#124;`|`op_LogicalOr`|`Or`|  
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
|`&#124;=`|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### Sobrecargar el operador \=\=  
 Sobrecarga `operator ==` es bastante complicado. La semántica del operador necesita ser compatible con otros miembros, como <xref:System.Object.Equals%2A?displayProperty=fullName>.  
  
### Operadores de conversión  
 Operadores de conversión son operadores unarios que permiten la conversión de un tipo a otro. Los operadores deben definirse como miembros estáticos en el operando o el tipo de valor devuelto. Hay dos tipos de operadores de conversión: implícitas y explícitas.  
  
 **X no** proporcionar un operador de conversión si los usuarios finales no esperan claramente dicha conversión.  
  
 **X no** definir operadores de conversión fuera del dominio de un tipo.  
  
 Por ejemplo, <xref:System.Int32>, <xref:System.Double>, y <xref:System.Decimal> son todos los tipos numéricos, mientras que <xref:System.DateTime> no es. Por lo tanto, no debería haber ningún operador de conversión para convertir un `Double(long)` para un `DateTime`. En tal caso, se prefiere un constructor.  
  
 **X no** proporciona un operador de conversión implícita si la conversión es potencialmente con pérdida.  
  
 Por ejemplo, no debería haber una conversión implícita de `Double` a `Int32` porque `Double` tiene un intervalo más amplio que `Int32`. Incluso si la conversión es potencialmente con pérdida de datos, se puede proporcionar un operador de conversión explícita.  
  
 **X no** generar excepciones desde conversiones implícitas.  
  
 Es muy difícil para los usuarios finales a comprender qué está pasando, porque podrían no ser conscientes de que está realizando una conversión.  
  
 **✓ hacer** throw <xref:System.InvalidCastException?displayProperty=fullName> Si una llamada a un operador de conversión produce una conversión con pérdida de datos y el contrato del operador no admite conversiones con pérdida de datos.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)