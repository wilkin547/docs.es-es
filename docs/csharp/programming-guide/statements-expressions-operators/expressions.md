---
title: 'Expresiones: Guía de programación de C#'
ms.date: 05/11/2017
helpviewer_keywords:
- expressions [C#]
- C# language, expressions
ms.assetid: c7d8feb0-0e58-4f94-8bf6-4d070550a832
ms.openlocfilehash: 4bbee8f15c2591e8b172df9a6759449d48697804
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75699098"
---
# <a name="expressions-c-programming-guide"></a>Expresiones (Guía de programación de C#)

Una *expresión* es una secuencia de uno o más operandos y cero o más [operadores](../../language-reference/operators/index.md) que se pueden evaluar como un valor, objeto, método o espacio de nombres único. Las expresiones pueden constar de un valor literal, una invocación de método, un operador y sus operandos o un *nombre simple*. Los nombres simples pueden ser el nombre de una variable, el miembro de un tipo, el parámetro de un método, un espacio de nombres o un tipo.  
  
 Las expresiones pueden usar operadores que, a su vez, usan otras expresiones como parámetros o llamadas a métodos cuyos parámetros son, a su vez, otras llamadas a métodos, de modo que pueden variar de simples a muy complejas. A continuación se muestran dos ejemplos de expresiones:  
  
```csharp  
((x < 10) && ( x > 5)) || ((x > 20) && (x < 25));

System.Convert.ToInt32("35");  
```  
  
## <a name="expression-values"></a>Valores de expresión

 En la mayoría de los contextos donde se usan expresiones, por ejemplo en instrucciones o parámetros de método, se espera que la expresión se evalúe como algún valor. Si x e y son enteros, la expresión `x + y` se evalúa como un valor numérico. La expresión `new MyClass()` se evalúa como una referencia a una nueva instancia de una clase `MyClass`. La expresión `myClass.ToString()` se evalúa como una cadena porque este es el tipo de valor devuelto del método. En cambio, aunque un nombre de espacio de nombres se clasifique como una expresión, no se evalúa como un valor y por tanto nunca puede ser el resultado final de una expresión. No puede pasar un nombre de espacio de nombres a un parámetro de método, usarlo en una nueva expresión ni asignarlo a una variable. Solo puede usarlo como una subexpresión en una expresión mayor. Lo mismo sucede con los tipos (a diferencia de los objetos <xref:System.Type?displayProperty=nameWithType>), los nombres de grupo de métodos (a diferencia de los métodos específicos) y los descriptores de acceso [add](../../language-reference/keywords/add.md) y [remove](../../language-reference/keywords/remove.md) de eventos.  
  
 Todos los valores tienen un tipo asociado. Por ejemplo, si x e y son variables de tipo `int`, el valor de la expresión `x + y` también es de tipo `int`. Si el valor se asigna a una variable de un tipo diferente, o si x e y son de tipos diferentes, se aplican las reglas de conversión de tipos. Para obtener más información sobre el funcionamiento de estas conversiones, vea [Conversiones de tipos (Guía de programación de C#)](../types/casting-and-type-conversions.md).  
  
## <a name="overflows"></a>Desbordamientos

 Las expresiones numéricas pueden producir desbordamientos si el valor es mayor que el valor máximo del tipo del valor. Para obtener más información, consulte las secciones [Comprobadas y no comprobadas](../../language-reference/keywords/checked-and-unchecked.md) y [Conversiones numéricas explícitas](../../language-reference/builtin-types/numeric-conversions.md#explicit-numeric-conversions) del artículo [Conversiones numéricas integradas](../../language-reference/builtin-types/numeric-conversions.md).
  
## <a name="operator-precedence-and-associativity"></a>Prioridad y asociatividad de los operadores

 Las reglas de asociatividad y prioridad de operadores rigen la manera en la que se evalúa una expresión. Para obtener más información, vea [Operadores (Guía de programación de C#)](../../language-reference/operators/index.md).  
  
 La mayoría de las expresiones, excepto las expresiones de asignación y las expresiones de invocación de método, se deben insertar en una instrucción. Para obtener más información, vea [Instrucciones (Guía de programación de C#)](./statements.md).  
  
## <a name="literals-and-simple-names"></a>Literales y nombres simples

 Los dos tipos de expresiones más simples son literales y nombres simples. Un literal es un valor constante que no tiene ningún nombre. Por ejemplo, en el código siguiente, `5` y `"Hello World"` son valores literales:  
  
 [!code-csharp[csProgGuideStatements#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#2)]  
  
 Para obtener más información sobre literales, vea [Tipos (Referencia de C#)](/dotnet/csharp/language-reference/keywords).  
  
 En el ejemplo anterior, tanto `i` como `s` son nombres simples que identifican variables locales. Cuando estas variables se usan en una expresión, el nombre de variable se evalúa como el valor almacenado actualmente en la ubicación de la variable en memoria. Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStatements#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#3)]

## <a name="invocation-expressions"></a>Expresiones de invocación

 En el ejemplo de código siguiente, la llamada a `DoWork` es una expresión de invocación.  
  
```csharp
DoWork();  
```  
  
 Una invocación de método requiere el nombre del método, ya sea un nombre como en el ejemplo anterior o el resultado de otra expresión, seguido de paréntesis y los parámetros del método. Para más información, vea [Métodos](../classes-and-structs/methods.md). Una invocación de delegado usa el nombre de un delegado y los parámetros de método entre paréntesis. Para obtener más información, vea [Delegados (Guía de programación de C#)](../delegates/index.md). Las invocaciones de método e invocaciones de delegado se evalúan como el valor que devuelve el método, si devuelve alguno. Los métodos que devuelven un valor nulo no se pueden usar en lugar de un valor en una expresión.  

## <a name="query-expressions"></a>Expresiones de consulta

 A las expresiones de consulta se les aplican las mismas reglas que a las expresiones en general. Para más información, consulte [LINQ](../../linq/index.md).  
  
## <a name="lambda-expressions"></a>Expresiones lambda

 Las expresiones lambda representan "métodos insertados" que no tienen nombre pero pueden tener parámetros de entrada y varias instrucciones. Se usan mucho en LINQ para pasar argumentos a métodos. Las expresiones lambda se compilan en delegados o árboles de expresión, dependiendo del contexto en el que se usen. Para obtener más información, vea [Expresiones lambda](lambda-expressions.md).  
  
## <a name="expression-trees"></a>Árboles de expresión

Los árboles de expresión permiten representar las expresiones como estructuras de datos. Los proveedores LINQ los usan en gran medida para convertir expresiones de consulta en código significativo en otro contexto, como una base de datos SQL. Para obtener más información, vea [Árboles de expresión (C#)](../concepts/expression-trees/index.md).
  
## <a name="expression-body-definitions"></a>Definiciones de cuerpos de expresión

C# admite *miembros con forma de expresión*, que le permiten proporcionar una definición de cuerpo de expresión concisa para métodos, constructores, finalizadores, propiedades e indexadores. Para obtener más información, vea [Miembros con forma de expresión](expression-bodied-members.md).

## <a name="remarks"></a>Comentarios

 Siempre que se identifica un acceso a una variable, propiedad de objeto o indexador de objeto desde una expresión, el valor de ese elemento se usa como valor de la expresión. Una expresión se puede colocar en cualquier parte de C# donde se requiera un valor u objeto, siempre que la expresión finalmente se evalúe como el tipo requerido.  

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para más información, consulte la sección [Expresiones](~/_csharplang/spec/expressions.md) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Operadores](../../language-reference/operators/index.md)
- [Métodos](../classes-and-structs/methods.md)
- [Delegados](../delegates/index.md)
- [Tipos](../types/index.md)
- [LINQ](../../linq/index.md)
