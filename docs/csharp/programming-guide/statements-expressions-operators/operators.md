---
title: Operadores (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: bf453d5770967f26999b8537339f1b690646b97d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150978"
---
# <a name="operators-c-programming-guide"></a>Operadores (Guía de programación de C#)
En C#, un *operador* es un elemento de programa que se aplica a uno o varios *operandos* en una expresión o instrucción. Los operadores que toman un operando, como el operador de incremento (`++`) o `new`, se conocen como operadores *unarios* . Los operadores que toman dos operandos, como los operadores aritméticos (`+`,`-`,`*`,`/`) se conocen como operadores *binarios* . Un operador, el operador condicional (`?:`), toma tres operandos y es el único operador ternario de C#.  
  
 La instrucción de C# siguiente contiene un solo operador unario y un único operando. El operador de incremento, `++`, modifica el valor del operando `y`.  
  
 [!code-csharp[csProgGuideStatements#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/operators_1.cs)]  
  
 La instrucción de C# siguiente contiene dos operadores binarios, cada uno con dos operandos. El operador de asignaciones, `=`, tiene la variable de entero `y` y la expresión `2 + 3` como operandos. La propia expresión `2 + 3` está compuesta del operador de suma y dos operandos, `2` y `3`.  
  
 [!code-csharp[csProgGuideStatements#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/operators_2.cs)]  
  
## <a name="operators-evaluation-and-operator-precedence"></a>Operadores, evaluación y prioridad de operadores  
 Un operando puede ser una expresión válida que se compone de código de una longitud indeterminada y puede incluir un número cualquiera de subexpresiones. En una expresión que contiene varios operadores, el orden de aplicación de estos viene determinado por la *prioridad de operador*, la *asociatividad*y los paréntesis.  
  
 Cada operador tiene una prioridad definida. En una expresión que contiene varios operadores con distintos niveles de prioridad, la prioridad de los operadores determina el orden en que estos se evalúan. Por ejemplo, la instrucción siguiente asigna 3 a `n1`.  
  
 `n1 = 11 - 2 * 4;`  
  
 La multiplicación se ejecuta en primer lugar porque tiene prioridad sobre la resta.  
  
 En la tabla siguiente se separan los operadores en categorías en función del tipo de operación que realizan. Las categorías se muestran en orden de prioridad.  
  
 **Operadores principales**  
  
|Expresión|Descripción|  
|----------------|-----------------|  
|x[.](../../../csharp/language-reference/operators/member-access-operator.md)y<br /><br /> x?.y|Acceso a miembros<br /><br /> Acceso a miembros condicional|  
|f[(x)](../../../csharp/language-reference/operators/invocation-operator.md)|Invocación de método y delegado|  
|a[&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md)<br /><br /> a?[x]|Acceso a matriz e indizador<br /><br /> Acceso a matriz e indizador condicional|  
|x[++](../../../csharp/language-reference/operators/increment-operator.md)|Postincremento|  
|x[--](../../../csharp/language-reference/operators/decrement-operator.md)|Postdecremento|  
|[new](../../../csharp/language-reference/keywords/new-operator.md) T(...)|Creación de objetos y delegados|  
|`new` T(...){...}|Creación de objetos con inicializador. Vea [Inicializadores de objeto y de colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).|  
|`new` {...}|Inicializador de objeto anónimo. Vea [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).|  
|`new` T[...]|Creación de matriz. Vea [Matrices](../../../csharp/programming-guide/arrays/index.md).|  
|[typeof](../../../csharp/language-reference/keywords/typeof.md)(T)|Obtener el objeto System.Type para T|  
|[checked](../../../csharp/language-reference/keywords/checked.md)(x)|Evaluar expresión en contexto comprobado|  
|[unchecked](../../../csharp/language-reference/keywords/unchecked.md)(x)|Evaluar expresión en contexto no comprobado|  
|[default](../../../csharp/language-reference/keywords/default.md) (T)|Obtener valor predeterminado de tipo T|  
|[delegate](../../../csharp/language-reference/keywords/delegate.md) {}|Función anónima (método anónimo)|  
  
 **Operadores unarios**  
  
|Expresión|Descripción|  
|----------------|-----------------|  
|[+](../../../csharp/language-reference/operators/addition-operator.md)x|identidad|  
|[-](../../../csharp/language-reference/operators/subtraction-operator.md)x|Negación|  
|[\!](../../../csharp/language-reference/operators/logical-negation-operator.md)x|Negación lógica|  
|[~](../../../csharp/language-reference/operators/bitwise-complement-operator.md)x|Negación bit a bit|  
|[++](../../../csharp/language-reference/operators/increment-operator.md)x|Preincremento|  
|[--](../../../csharp/language-reference/operators/decrement-operator.md)x|Predecremento|  
|[(T)](../../../csharp/language-reference/operators/invocation-operator.md)x|Convertir x explícitamente en tipo T|  
  
 **Operadores de multiplicación**  
  
|Expresión|Descripción|  
|----------------|-----------------|  
|[*](../../../csharp/language-reference/operators/multiplication-operator.md)|Multiplicación|  
|[/](../../../csharp/language-reference/operators/division-operator.md)|División|  
|[%](../../../csharp/language-reference/operators/modulus-operator.md)|Resto|  
  
 **Operadores de suma**  
  
|Expresión|Descripción|  
|----------------|-----------------|  
|x [+](../../../csharp/language-reference/operators/addition-operator.md) y|Suma, concatenación de cadenas, combinación de delegados|  
|x [-](../../../csharp/language-reference/operators/subtraction-operator.md) y|Resta, eliminación de delegados|  
  
 **Operadores de desplazamiento**  
  
|Expresión|Descripción|  
|----------------|-----------------|  
|x [<\<](../../../csharp/language-reference/operators/left-shift-operator.md) y|Desplazamiento a la izquierda|  
|x [>>](../../../csharp/language-reference/operators/right-shift-operator.md) y|Desplazamiento a la derecha|  
  
 **Operadores relacionales y de tipo**  
  
|Expresión|Descripción|  
|----------------|-----------------|  
|x [\<](../../../csharp/language-reference/operators/less-than-operator.md) y|Menor que|  
|x [>](../../../csharp/language-reference/operators/greater-than-operator.md) y|Mayor que|  
|x [\<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) y|Menor o igual que|  
|x [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) y|Mayor o igual que|  
|x [is](../../../csharp/language-reference/keywords/is.md) T|Devuelve true si x es T; de lo contrario, false|  
|x [as](../../../csharp/language-reference/keywords/as.md) T|Devuelve x escrito como T, o NULL si x no es T|  
  
 **Operadores de igualdad**  
  
|Expresión|Descripción|  
|----------------|-----------------|  
|x [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) y|Igual|  
|x [!=](../../../csharp/language-reference/operators/not-equal-operator.md) y|No igual|  
  
 **Operadores lógicos, condicionales y NULL**  
  
|Categoría|Expresión|Descripción|  
|--------------|----------------|-----------------|  
|AND lógico|x [&](../../../csharp/language-reference/operators/and-operator.md) y|AND bit a bit entero, AND lógico booleano|  
|XOR lógico|x [^](../../../csharp/language-reference/operators/xor-operator.md) y|XOR bit a bit entero, XOR lógico boolean|  
|OR lógico|x [&#124;](../../../csharp/language-reference/operators/or-operator.md) y|OR bit a bit entero, OR lógico booleano|  
|AND condicional|x [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y|Evalúa y solo si x es true|  
|OR condicional|x [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) y|Evalúa y solo si x es false|  
|Uso combinado de NULL|x [??](../../../csharp/language-reference/operators/null-coalescing-operator.md) s|Se evalúa como y si x es NULL; de lo contrario, se evalúa como x|  
|Condicional|x [?](../../../csharp/language-reference/operators/conditional-operator.md) y : z|Se evalúa como y si x es true y como z si x es false|  
  
 **Operadores de asignación y anónimos**  
  
|Expresión|Descripción|  
|----------------|-----------------|  
|[=](../../../csharp/language-reference/operators/assignment-operator.md)|Asignación|  
|x op= y|Asignación compuesta. Admite estos operadores: [+=](../../../csharp/language-reference/operators/addition-assignment-operator.md), [-=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md), [*=](../../../csharp/language-reference/operators/multiplication-assignment-operator.md), [/=](../../../csharp/language-reference/operators/division-assignment-operator.md), [%=](../../../csharp/language-reference/operators/modulus-assignment-operator.md), [&=](../../../csharp/language-reference/operators/and-assignment-operator.md), [&#124;=](../../../csharp/language-reference/operators/or-assignment-operator.md), [^=](../../../csharp/language-reference/operators/xor-assignment-operator.md), [<\<=](../../../csharp/language-reference/operators/left-shift-assignment-operator.md), [>>=](../../../csharp/language-reference/operators/right-shift-assignment-operator.md)|  
|(T x) [=>](../../../csharp/language-reference/operators/lambda-operator.md) y|Función anónima (expresión lambda)|  
  
## <a name="associativity"></a>Asociatividad  
 Cuando dos o más operadores con la misma prioridad están presentes en una expresión, se evalúan según su asociatividad. Los operadores asociativos a la izquierda se evalúan, por orden, de izquierda a derecha. Por ejemplo, `x * y / z` se evalúa como `(x * y) / z`. Los operadores asociativos a la derecha se evalúan, por orden, de derecha a izquierda. Por ejemplo, el operador de asignación es asociativo a la derecha. De lo contrario, el código siguiente produciría un error.  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 Otro ejemplo sería el operador ternario ([?:](../../../csharp/language-reference/operators/conditional-operator.md)), que es asociativo a la derecha. La mayoría de los operadores binarios son asociativos a la izquierda.  
  
 Independientemente de que los operadores de una expresión sean asociativos a la izquierda o a la derecha, los operandos de cada expresión se evalúan primero, de izquierda a derecha. En los siguientes ejemplos se muestra el orden de evaluación de los operadores y los operandos.  
  
|Instrucción|Orden de evaluación|  
|---------------|-------------------------|  
|`a = b`|a, b, =|  
|`a = b + c`|a, b, c, +, =|  
|`a = b + c * d`|a, b, c, d, *, +, =|  
|`a = b * c + d`|a, b, c, *, d, +, =|  
|`a = b - c + d`|a, b, c, -, d, +, =|  
|`a += b -= c`|a, b, c, -=, +=|  
  
## <a name="adding-parentheses"></a>Agregar paréntesis  
 Se puede cambiar el orden impuesto por la prioridad de operador y la asociatividad mediante el uso de paréntesis. Por ejemplo, `2 + 3 * 2` suele evaluarse como 8, porque los operadores de multiplicación tienen prioridad sobre los operadores de suma. Sin embargo, si se escribe la expresión como `(2 + 3) * 2`, la suma se evalúa antes que la multiplicación y el resultado es 10. En los siguientes ejemplos se muestra el orden de evaluación en las expresiones entre paréntesis. Como en ejemplos anteriores, los operandos se evalúan antes de aplicarse el operador.  
  
|Instrucción|Orden de evaluación|  
|---------------|-------------------------|  
|`a = (b + c) * d`|a, b, c, +, d, *, =|  
|`a = b - (c + d)`|a, b, c, d, +, -, =|  
|`a = (b + c) * (d - e)`|a, b, c, +, d, e, -, *, =|  
  
## <a name="operator-overloading"></a>Sobrecarga de operadores  
 Se puede cambiar el comportamiento de los operadores para las clases y structs personalizados. Este proceso se conoce como *sobrecarga de operadores*. Para obtener más información, vea el artículo sobre la palabra clave [operator](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md) y [Operadores sobrecargables](../../../csharp/language-reference/keywords/operator.md).  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información, vea [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md) y [Operadores de C#](../../../csharp/language-reference/operators/index.md).  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Instrucciones, expresiones y operadores](../../../csharp/programming-guide/statements-expressions-operators/index.md)
