---
title: 'Conversiones de tipos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
ms.openlocfilehash: cd989b47c87ef32371b45650d531bd8cbeb85032
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306951"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a>Conversiones de tipos (Guía de programación de C#)

Dado que C# tiene tipos estáticos en tiempo de compilación, después de declarar una variable, no se puede volver a declarar ni se le puede asignar un valor de otro tipo a menos que ese tipo sea convertible de forma implícita al tipo de la variable. Por ejemplo, `string` no se puede convertir de forma implícita a `int`. Por tanto, después de declarar `i` como un valor `int`, no se le puede asignar la cadena "Hello", como se muestra en el código siguiente:
  
```csharp  
int i;  
i = "Hello"; // error CS0029: Cannot implicitly convert type 'string' to 'int'
```  
  
 Pero es posible que en ocasiones sea necesario copiar un valor en una variable o parámetro de método de otro tipo. Por ejemplo, es posible que tenga una variable de entero que se necesita pasar a un método cuyo parámetro es de tipo `double`. O es posible que tenga que asignar una variable de clase a una variable de tipo de interfaz. Estos tipos de operaciones se denominan *conversiones de tipos*. En C#, se pueden realizar las siguientes conversiones de tipos:  
  
- **Conversiones implícitas**: no se requiere ninguna sintaxis especial porque la conversión tiene seguridad de tipos y no se perderá ningún dato. Los ejemplos incluyen conversiones de tipos enteros más pequeños a más grandes, y conversiones de clases derivadas a clases base.  
  
- **Conversiones explícitas**: las conversiones explícitas requieren un operador de conversión. La conversión es necesaria si es posible que se pierda información en la conversión, o cuando es posible que la conversión no sea correcta por otros motivos.  Entre los ejemplos típicos están la conversión numérica a un tipo que tiene menos precisión o un intervalo más pequeño, y la conversión de una instancia de clase base a una clase derivada.  
  
- **Conversiones definidas por el usuario**: las conversiones definidas por el usuario se realizan por medio de métodos especiales que se pueden definir para habilitar las conversiones explícitas e implícitas entre tipos personalizados que no tienen una relación de clase base-clase derivada. Para obtener más información, vea [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).  
  
- **Conversiones con clases del asistente**: para realizar conversiones entre tipos no compatibles, como enteros y objetos <xref:System.DateTime?displayProperty=nameWithType>, o cadenas hexadecimales y matrices de bytes puede usar la clase <xref:System.BitConverter?displayProperty=nameWithType>, la clase <xref:System.Convert?displayProperty=nameWithType> y los métodos `Parse` de los tipos numéricos integrados, como <xref:System.Int32.Parse%2A?displayProperty=nameWithType>. Para obtener más información, vea [Cómo: Convertir una matriz de bytes en un valor int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) y [Cómo: Convertir cadenas hexadecimales en tipos numéricos](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).  
  
## <a name="implicit-conversions"></a>Conversiones implícitas

 Para los tipos numéricos integrados, se puede realizar una conversión implícita cuando el valor que se va a almacenar se puede encajar en la variable sin truncarse ni redondearse. Por ejemplo, una variable de tipo [long](../../../csharp/language-reference/keywords/long.md) (entero de 64 bits) puede almacenar cualquier valor que un tipo [int](../../../csharp/language-reference/keywords/int.md) (entero de 32 bits) pueda almacenar. En el ejemplo siguiente, el compilador convierte de forma implícita el valor de `num` en la parte derecha a un tipo `long` antes de asignarlo a `bigNum`.  
  
 [!code-csharp[csProgGuideTypes#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#34)]  
  
 Para obtener una lista completa de todas las conversiones numéricas implícitas, vea [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Para los tipos de referencia, siempre existe una conversión implícita desde una clase a cualquiera de sus interfaces o clases base directas o indirectas. No se necesita ninguna sintaxis especial porque una clase derivada siempre contiene a todos los miembros de una clase base.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a>Conversiones explícitas

 Pero si no se puede realizar una conversión sin riesgo de perder información, el compilador requiere que se realice una conversión explícita, que se denomina *conversión*. Una conversión de tipos es una manera de informar explícitamente al compilador de que se pretende realizar la conversión y se es consciente de que se puede producir pérdida de datos. Para realizar una conversión, especifique el tipo al que se va a convertir entre paréntesis delante del valor o la variable que se va a convertir. El siguiente programa convierte un tipo [double](../../../csharp/language-reference/keywords/double.md) en un tipo [int](../../../csharp/language-reference/keywords/int.md). El programa no se compilará sin la conversión.  
  
 [!code-csharp[csProgGuideTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#2)]  
  
 Para obtener una lista de las conversiones numéricas explícitas permitidas, vea [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
 Para los tipos de referencia, se requiere una conversión explícita si es necesario convertir de un tipo base a un tipo derivado:  
  
```csharp  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 Una operación de conversión entre tipos de referencia no cambia el tipo en tiempo de ejecución del objeto subyacente. Solo cambia el tipo del valor que se usa como referencia a ese objeto. Para obtener más información, vea [Polimorfismo ](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).  
  
## <a name="type-conversion-exceptions-at-run-time"></a>Excepciones de conversión de tipos en tiempo de ejecución

 En algunas conversiones de tipos de referencia, el compilador no puede determinar si una conversión será válida. Es posible que una operación de conversión que se compile correctamente produzca un error en tiempo de ejecución. Como se muestra en el ejemplo siguiente, una conversión de tipo que produce un error en tiempo de ejecución produce una excepción <xref:System.InvalidCastException>.  
  
 [!code-csharp[csProgGuideTypes#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#41)]  
  
 C# proporciona el operador [is](../../language-reference/operators/type-testing-and-conversion-operators.md#is-operator) para permitir probar la compatibilidad antes de realizar una conversión. Para más información, consulte [Cómo: Convertir de forma segura mediante la coincidencia de patrones y los operadores is y as](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Tipos](../../../csharp/programming-guide/types/index.md)
- [Operator ()](../../../csharp/language-reference/operators/type-testing-and-conversion-operators.md#cast-operator-)
- [explicit](../../../csharp/language-reference/keywords/explicit.md)
- [implicit](../../../csharp/language-reference/keywords/implicit.md)
- [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
- [Conversión de tipos generalizada](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))
- [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)
