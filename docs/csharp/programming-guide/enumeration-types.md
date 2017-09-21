---
title: "Tipos de enumeración (Guía de programación de C#)"
ms.date: 09/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 6b58466f8dd70a3eefb73c3d1ac21ec42a370b47
ms.openlocfilehash: 71ddf47259ce55a6a7c5a9e5f4999ed786154f52
ms.contentlocale: es-es
ms.lasthandoff: 09/19/2017

---
# <a name="enumeration-types-c-programming-guide"></a>Tipos de enumeración (Guía de programación de C#)

Un tipo de enumeración (también denominado enumeración) proporciona una manera eficaz de definir un conjunto de constantes enteras con nombre que se pueden asignar a una variable. Por ejemplo, suponga que tiene que definir una variable cuyo valor representará un día de la semana. Dicha variable solo almacenará siete valores significativos. Para definir esos valores, puede usar un tipo de enumeración, que se declara mediante la palabra clave [enum](../../csharp/language-reference/keywords/enum.md).

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

De forma predeterminada, el tipo subyacente de cada elemento de la enumeración es [int](../../csharp/language-reference/keywords/int.md). Puede especificar otro tipo numérico entero mediante el uso del signo de dos puntos, como se muestra en el ejemplo anterior. Para obtener una lista completa de los tipos posibles, vea [enum (Referencia de C#)](../../csharp/language-reference/keywords/enum.md).

Puede comprobar los valores numéricos subyacentes mediante la conversión al tipo subyacente, como se muestra en el ejemplo siguiente.

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

Estas son las ventajas de usar una enumeración en lugar de un tipo numérico:

- Se especifica claramente para el código de cliente qué valores son válidos para la variable.

- En [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense muestra los valores definidos.

Cuando no se especifican valores para los elementos de la lista de enumeradores, los valores se incrementan automáticamente en 1. En el ejemplo anterior, `Day.Sunday` tiene un valor de 0, `Day.Monday` tiene un valor de 1, y así sucesivamente. Cuando cree un nuevo objeto `Day`, tendrá un valor predeterminado de `Day.Sunday` (0) si no le asigna explícitamente un valor. Cuando cree una enumeración, seleccione el valor predeterminado más lógico y asígnele un valor de cero. Esto hará que todas las enumeraciones tengan ese valor predeterminado si no se les asigna explícitamente un valor cuando se crean.

Si la variable `meetingDay` es de tipo `Day`, solo puede asignarle (sin una conversión explícita) uno de los valores definidos por `Day`. Si el día de la reunión cambia, puede asignarle un nuevo valor de `Day` a `meetingDay`:

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> Es posible asignar un valor entero cualquiera a `meetingDay`. Por ejemplo, esta línea de código no genera un error: `meetingDay = (Day) 42`. Pero no debe hacerlo, ya que la expectativa implícita es que una variable de enumeración contenga solamente uno de los valores definidos por la enumeración. La acción de asignar un valor arbitrario a una variable de un tipo de enumeración aumenta el riesgo de errores.

Puede asignar cualquier valor a los elementos de la lista de enumeradores de un tipo de enumeración, y también puede usar valores calculados:

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a>Tipos de enumeración como marcas de bits

Puede usar un tipo de enumeración para definir marcas de bits, lo que permite que una instancia del tipo de enumeración almacene cualquier combinación de los valores que se definen en la lista de enumeradores. (Obviamente, es posible que algunas combinaciones no sean significativas o no se permitan en el código del programa).

Para crear una enumeración de marcas de bits, aplique el atributo <xref:System.FlagsAttribute?displayProperty=fullName> y defina los valores de forma adecuada para que se puedan realizar en ellos operaciones bit a bit `AND`, `OR`, `NOT` y `XOR`. En una enumeración de marcas de bits, incluya una constante con nombre con un valor de cero que signifique "no se establecen marcas". No le asigne a una marca un valor de cero si no significa "no se establecen marcas".

En el ejemplo siguiente, se define otra versión de la enumeración `Day`, denominada `Days`. `Days` tiene el atributo `Flags` y a cada valor se le asigna la siguiente potencia de 2 superior. Esto le permite crear una variable `Days` cuyo valor es `Days.Tuesday | Days.Thursday`.

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

Para establecer una marca en una enumeración, use el operador bit a bit `OR` tal como se muestra en el ejemplo siguiente:

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

Para determinar si se ha establecido una marca específica, use una operación bit a bit `AND`, tal como se muestra en el ejemplo siguiente:

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

Para obtener más información sobre lo que debe tener en cuenta para definir tipos de enumeraciones con el atributo <xref:System.FlagsAttribute?displayProperty=fullName>, vea <xref:System.Enum?displayProperty=fullName>.

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a>Usar los métodos System.Enum para detectar y manipular valores de enumeración

Todas las enumeraciones son instancias del tipo <xref:System.Enum?displayProperty=fullName>. No se pueden derivar clases nuevas de <xref:System.Enum?displayProperty=fullName>, pero puede usar sus métodos para detectar información relacionada y manipular los valores de una instancia de enumeración.

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

Para obtener más información, consulta <xref:System.Enum?displayProperty=fullName>.

También puede crear un método nuevo para una enumeración mediante un método de extensión. Para obtener más información, vea [Cómo: Crear un método nuevo para una enumeración](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).

## <a name="see-also"></a>Vea también
 <xref:System.Enum?displayProperty=fullName>   
 [Guía de programación de C#](../../csharp/programming-guide/index.md)   
 [enum](../../csharp/language-reference/keywords/enum.md)

