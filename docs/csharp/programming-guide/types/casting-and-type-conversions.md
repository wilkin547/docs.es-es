---
title: "Conversiones de tipos (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
caps.latest.revision: 52
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 28c6b9da6d94bd402e720db48d5c7a2977344f05
ms.lasthandoff: 03/13/2017

---
# <a name="casting-and-type-conversions-c-programming-guide"></a>Conversiones de tipos (Guía de programación de C#)
Dado que C# tiene tipos estáticos en tiempo de compilación, después de declarar una variable, no se puede volver a declarar ni usar para almacenar valores de otro tipo a menos que ese tipo sea convertible al tipo de la variable. Por ejemplo, no hay ninguna conversión de un entero a una cadena arbitraria. Por tanto, después de declarar `i` como un entero, no se le puede asignar la cadena "Hello", como se muestra en el código siguiente.  
  
```csharp  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 Pero es posible que en ocasiones sea necesario copiar un valor en una variable o parámetro de método de otro tipo. Por ejemplo, es posible que tenga una variable de entero que se necesita pasar a un método cuyo parámetro es de tipo `double`. O es posible que tenga que asignar una variable de clase a una variable de tipo de interfaz. Estos tipos de operaciones se denominan *conversiones de tipos*. En C#, se pueden realizar las siguientes conversiones de tipos:  
  
-   **Conversiones implícitas**: no se requiere ninguna sintaxis especial porque la conversión tiene seguridad de tipos y no se perderá ningún dato. Los ejemplos incluyen conversiones de tipos enteros más pequeños a más grandes, y conversiones de clases derivadas a clases base.  
  
-   **Conversiones explícitas**: las conversiones explícitas requieren un operador de conversión. La conversión es necesaria si es posible que se pierda información en la conversión, o cuando es posible que la conversión no sea correcta por otros motivos.  Entre los ejemplos típicos están la conversión numérica a un tipo que tiene menos precisión o un intervalo más pequeño, y la conversión de una instancia de clase base a una clase derivada.  
  
-   **Conversiones definidas por el usuario**: las conversiones definidas por el usuario se realizan por medio de métodos especiales que se pueden definir para habilitar las conversiones explícitas e implícitas entre tipos personalizados que no tienen una relación de clase base-clase derivada. Para obtener más información, vea [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).  
  
-   **Conversiones con clases auxiliares**: para convertir entre tipos no compatibles, como enteros y objetos <xref:System.DateTime?displayProperty=fullName>, o cadenas hexadecimales y matrices de bytes, se puede usar la clase <xref:System.BitConverter?displayProperty=fullName>, la clase <xref:System.Convert?displayProperty=fullName> y los métodos `Parse` de los tipos numéricos integrados, como <xref:System.Int32.Parse%2A?displayProperty=fullName>. Para obtener más información, vea [Cómo: Convertir una matriz de bytes en un valor int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) y [Cómo: Convertir cadenas hexadecimales en tipos numéricos](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).  
  
## <a name="implicit-conversions"></a>Conversiones implícitas  
 Para los tipos numéricos integrados, se puede realizar una conversión implícita cuando el valor que se va a almacenar se puede encajar en la variable sin truncarse ni redondearse. Por ejemplo, una variable de tipo [long](../../../csharp/language-reference/keywords/long.md) (entero de 8 bytes) puede almacenar cualquier valor que un [int](../../../csharp/language-reference/keywords/int.md) (4 bytes en un equipo de 32 bits) pueda almacenar. En el ejemplo siguiente, el compilador convierte implícitamente el valor de la derecha a un tipo `long` antes de asignarlo a `bigNum`.  
  
 [!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]  
  
 Para obtener una lista completa de todas las conversiones numéricas implícitas, vea [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Para los tipos de referencia, siempre existe una conversión implícita desde una clase a cualquiera de sus interfaces o clases base directas o indirectas. No se necesita ninguna sintaxis especial porque una clase derivada siempre contiene a todos los miembros de una clase base.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a>Conversiones explícitas  
 Pero si no se puede realizar una conversión sin riesgo de perder información, el compilador requiere que se realice una conversión explícita, que se denomina *conversión*. Una conversión de tipos es una manera de informar explícitamente al compilador de que se pretende realizar la conversión y se es consciente de que se puede producir pérdida de datos. Para realizar una conversión, especifique el tipo al que se va a convertir entre paréntesis delante del valor o la variable que se va a convertir. El siguiente programa convierte un tipo [double](../../../csharp/language-reference/keywords/double.md) en un tipo [int](../../../csharp/language-reference/keywords/int.md). El programa no se compilará sin la conversión.  
  
 [!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]  
  
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
  
 Una operación de conversión entre tipos de referencia no cambia el tipo en tiempo de ejecución del objeto subyacente. Solo cambia el tipo del valor que se usa como referencia a ese objeto. Para obtener más información, vea [Poliformismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).  
  
## <a name="type-conversion-exceptions-at-run-time"></a>Excepciones de conversión de tipos en tiempo de ejecución  
 En algunas conversiones de tipos de referencia, el compilador no puede determinar si una conversión será válida. Es posible que una operación de conversión que se compile correctamente produzca un error en tiempo de ejecución. Como se muestra en el ejemplo siguiente, una conversión de tipo que produce un error en tiempo de ejecución produce una excepción <xref:System.InvalidCastException>.  
  
 [!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]  
  
 C# proporciona los operadores [is](../../../csharp/language-reference/keywords/is.md) y [as](../../../csharp/language-reference/keywords/as.md) para permitir probar la compatibilidad antes de realizar una conversión. Para obtener más información, vea [Cómo: Realizar conversiones seguras usando los operadores is y as](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="featured-book-chapter"></a>Capítulo destacado del libro  
 [More About Variables](http://go.microsoft.com/fwlink/?LinkId=221230) (Información adicional sobre las variables) en [Beginning Visual C# 2010](http://go.microsoft.com/fwlink/?LinkId=221214) (Comenzar a usar Visual C# 2010)  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Tipos](../../../csharp/programming-guide/types/index.md)   
 [() (operador)](../../../csharp/language-reference/operators/invocation-operator.md)   
 [explicit](../../../csharp/language-reference/keywords/explicit.md)   
 [implicit](../../../csharp/language-reference/keywords/implicit.md)   
 [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [Conversión de tipos generalizada](http://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada)   
 [Conversión de tipos exportados](http://msdn.microsoft.com/en-us/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)   
 [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)
