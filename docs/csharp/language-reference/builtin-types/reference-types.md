---
title: Tipos de referencia integrados - referencia de C#
description: Obtenga información sobre los tipos de referencia que tienen palabras clave de C# que puede usar para declararlas.
ms.date: 06/25/2019
f1_keywords:
- object_CSharpKeyword
- object
- delegate_CSharpKeyword
- delegate
- dynamic_CSharpKeyword
- string
- string_CSharpKeyword
helpviewer_keywords:
- object keyword [C#]
- delegate keyword [C#]
- function pointers [C#]
- dynamic [C#]
- dynamic keyword [C#]
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.openlocfilehash: c2c03f47babd9ccf87eb60d33b9d65d1a9c82e2e
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223515"
---
# <a name="built-in-reference-types-c-reference"></a>Tipos de referencia integrados (referencia de C#)

C# tiene un número de tipos de referencia integrados. Tienen palabras clave u operadores que son sinónimos para un tipo en la biblioteca de .NET.

## <a name="the-object-type"></a>El tipo de objeto

El tipo `object` es un alias de <xref:System.Object?displayProperty=nameWithType> en .NET. En el sistema de tipos unificado de C#, todos los tipos, los predefinidos y los definidos por el usuario, los tipos de referencia y los tipos de valores, heredan directa o indirectamente de <xref:System.Object?displayProperty=nameWithType>. Puede asignar valores de cualquier tipo a las variables de tipo `object`. Cualquier variable `object` puede asignarse a su valor predeterminado con el literal `null`. Cuando una variable de un tipo de valor se convierte en objeto, se dice que se aplica la *conversión boxing* . Cuando una variable de tipo `object` se convierte en un tipo de valor, se dice que se *aplica la conversión unboxing* . Para obtener más información, vea [Conversión boxing y unboxing](../../programming-guide/types/boxing-and-unboxing.md).

## <a name="the-string-type"></a>Tipo string

El tipo `string` representa una secuencia de cero o más caracteres Unicode. `string` es un alias de <xref:System.String?displayProperty=nameWithType> en .NET.

Aunque `string` es un tipo de referencia, se definen los [operadores de igualdad `==` y `!=`](../operators/equality-operators.md#string-equality) para comparar los valores de los objetos `string`, no las referencias. Esto hace que las pruebas de igualdad entre cadenas sean más intuitivas. Por ejemplo:

```csharp-interactive
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine(object.ReferenceEquals(a, b));
```

Se muestra "True" y luego "False" porque el contenido de las cadenas es equivalente, pero `a` y `b` no hacen referencia a la misma instancia de cadena.

El [operador +](../operators/addition-operator.md#string-concatenation) concatena cadenas:

```csharp
string a = "good " + "morning";
```

Crea un objeto de cadena que contiene "good morning".

Las cadenas son *inmutables* : el contenido de un objeto de cadena no se puede modificar una vez creado el objeto, aunque la sintaxis parezca indicar que se puede hacer. Por ejemplo, al escribir este código, el compilador crea en realidad otro objeto de cadena para almacenar la nueva secuencia de caracteres, y este nuevo objeto se asigna a `b`. La memoria que se había asignado para `b` (cuando contiene la cadena "h") es entonces apto para la recolección de elementos.

```csharp
string b = "h";
b += "ello";
```

El  [operador](../operators/member-access-operators.md#indexer-operator-)`[]` puede usarse para el acceso de solo lectura a determinados caracteres de una cadena. Los valores válidos comienzan por `0` y deben ser menores que la longitud de la cadena:

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

De igual manera, el operador `[]` también puede usarse para recorrer en iteración cada carácter en una cadena:

```csharp-interactive
string str = "test";

for (int i = 0; i < str.Length; i++)
{
  Console.Write(str[i] + " ");
}
// Output: t e s t
```

Los literales de cadena son del tipo `string` y se pueden escribir de dos formas, entre comillas y entre `@`. Los literales de cadena se incluyen entre comillas dobles ("):

```csharp
"good morning"  // a string literal
```

Los literales de cadena pueden contener cualquier literal de carácter. Se incluyen secuencias de escape. En el ejemplo siguiente se usa una secuencia de escape `\\` para la barra diagonal inversa, `\u0066` para la letra f y `\n` para la nueva línea.

```csharp-interactive
string a = "\\\u0066\n F";
Console.WriteLine(a);
// Output:
// \f
//  F
```

> [!NOTE]
> El código de escape `\udddd` (donde `dddd` es un número de cuatro dígitos) representa el carácter Unicode U+`dddd`. También se reconocen los códigos de escape Unicode de 8 dígitos: `\Udddddddd`.

[Los literales de cadena textual empiezan](../tokens/verbatim.md) por `@` y también se incluyen entre comillas dobles. Por ejemplo:

```csharp
@"good morning"  // a string literal
```

La ventaja de las cadenas textuales es que las secuencias de escape *no* se procesan, lo que facilita la escritura de, por ejemplo, un nombre de archivo Windows completo:

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

Para incluir un signo de comillas dobles en una cadena @-quoted, duplíquelo:

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

## <a name="the-delegate-type"></a>Tipo delegate

La declaración de un tipo delegado es similar a una firma de método. Tiene un valor devuelto y un número cualquiera de parámetros de cualquier tipo:

```csharp
public delegate void MessageDelegate(string message);
public delegate int AnotherDelegate(MyType m, long num);
```

En. NET, los tipos `System.Action` y `System.Func` proporcionan definiciones genéricas para muchos delegados comunes. Es probable que no sea necesario definir nuevos tipos delegados personalizados. En su lugar, puede crear instancias de los tipos genéricos proporcionados.

Un `delegate` es un tipo de referencia que puede usarse para encapsular un método con nombre o anónimo. Los delegados son similares a los punteros de función en C++; pero son más seguros y proporcionan mayor seguridad de tipos. Para las aplicaciones de delegados, vea [Delegados](../../programming-guide/delegates/index.md) y [Delegados genéricos](../../programming-guide/generics/generic-delegates.md). Los delegados son la base de los [eventos](../../programming-guide/events/index.md). Se pueden crear instancias de un delegado asociándolo a un método con nombre o anónimo.

Para crear instancias del delegado debe usarse un método o una expresión lambda que tenga un tipo de valor devuelto y parámetros de entrada compatibles. Para obtener más información sobre el grado de variación permitida en la firma de método, vea [Varianza en delegados](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md). Para el uso con métodos anónimos, el delegado y el código que se van a asociar se declaran juntos.

## <a name="the-dynamic-type"></a>Tipo dynamic

El tipo `dynamic` indica el uso de la variable y las referencias a su comprobación de tipos en el tiempo de compilación de omisión de miembros. En su lugar, se resuelven estas operaciones en tiempo de ejecución. El tipo `dynamic` simplifica el acceso a las API de COM como las API de automatización de Office, a API dinámicas como las bibliotecas de IronPython, y a Document Object Model (DOM) HTML.

El tipo `dynamic` se comporta como el tipo `object` en la mayoría de las circunstancias. En concreto, se puede convertir cualquier expresión no NULL para el tipo `dynamic`. El tipo `dynamic` se diferencia de `object` en que el compilador no resuelve o no comprueba el tipo de las operaciones que contienen expresiones de tipo `dynamic`. El compilador empaqueta información sobre la operación y esa información se usa después para evaluar la operación en tiempo de ejecución. Como parte del proceso, las variables de tipo `dynamic` están compiladas en las variables de tipo `object`. Por consiguiente, el tipo `dynamic` solo existe en tiempo de compilación, no en tiempo de ejecución.

En el siguiente ejemplo se contrasta una variable de tipo `dynamic` con una variable de tipo `object`. Para comprobar el tipo de cada variable en tiempo de compilación, coloque el puntero del mouse sobre `dyn` u `obj` en las instrucciones `WriteLine`. Copie el código siguiente en un editor donde IntelliSense esté disponible. IntelliSense muestra **dynamic** para `dyn` y **object** para `obj`.

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

Las instrucciones <xref:System.Console.WriteLine%2A> muestran los tipos en tiempo de ejecución de `dyn` y `obj`. En ese punto, ambos tienen el mismo tipo, entero. Se produce el siguiente resultado:

```console
System.Int32
System.Int32
```

Para ver la diferencia entre `dyn` y `obj` en tiempo de compilación, agregue las dos líneas siguientes entre las declaraciones y las instrucciones `WriteLine` en el ejemplo anterior.

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 Un error del compilador se notifica para el intento de suma de un entero y un objeto en la expresión `obj + 3`. En cambio, no se notifica ningún error para `dyn + 3`. En tiempo de compilación no se comprueba la expresión que contiene `dyn` porque el tipo de `dyn` es `dynamic`.

El ejemplo siguiente usa `dynamic` en varias declaraciones. El método `Main` también contrasta la comprobación de tipo en tiempo de compilación con la comprobación de tipo en tiempo de ejecución.

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

### <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Palabras clave de C#](../keywords/index.md)
- [Eventos](../../programming-guide/events/index.md)
- [Uso de tipo dinámico](../../programming-guide/types/using-type-dynamic.md)
- [Procedimientos recomendados para el uso de cadenas](../../../standard/base-types/best-practices-strings.md)
- [Operaciones básicas de cadenas](../../../standard/base-types/basic-string-operations.md)
- [Creación de cadenas](../../../standard/base-types/creating-new.md)
- [Operadores de conversión y prueba de tipos](../operators/type-testing-and-cast.md)
- [Procedimiento para convertir de forma segura mediante la coincidencia de patrones y los operadores is y as](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [Tutorial: Crear y usar objetos dinámicos (C# y Visual Basic)](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
