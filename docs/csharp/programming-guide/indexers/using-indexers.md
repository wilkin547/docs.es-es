---
title: 'Uso de indizadores: Guía de programación de C#'
ms.date: 07/15/2020
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: e742e4dd5ea92ec3baf37c915e024e713022b7b6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416244"
---
# <a name="using-indexers-c-programming-guide"></a>Uso de indizadores (Guía de programación de C#)

Los indizadores son una comodidad sintáctica que le permiten crear una [clase](../../language-reference/keywords/class.md), [estructura](../../language-reference/builtin-types/struct.md) o [interfaz](../../language-reference/keywords/interface.md) a la que las aplicaciones cliente pueden acceder como una matriz. El compilador generará una propiedad `Item` (o una propiedad con otro nombre si está presente <xref:System.Runtime.CompilerServices.IndexerNameAttribute>) y los métodos de descriptor de acceso adecuados. Los indexadores se implementan con más frecuencia en tipos cuyo propósito principal consiste en encapsular una matriz o colección interna. Por ejemplo, imagine que tiene una clase `TempRecord` que representa la temperatura en grados Fahrenheit que se registra en 10 momentos diferentes durante un período de 24 horas. La clase contiene una matriz `temps` de tipo `float[]` para almacenar los valores de temperatura. Si implementa un indizador en esta clase, los clientes pueden tener acceso a las temperaturas en una instancia de `TempRecord` como `float temp = tempRecord[4]` en lugar de como `float temp = tempRecord.temps[4]`. La notación del indizador no solo simplifica la sintaxis para las aplicaciones cliente; también hace que la clase y su finalidad sean más intuitivas para que otros desarrolladores las entiendan.

Para declarar un indizador en una clase o un struct, use la palabra clave [this](../../language-reference/keywords/this.md), como en este ejemplo:

```csharp
// Indexer declaration
public int this[int index]
{
    // get and set accessors
}
```

> [!IMPORTANT]
> Al declarar un indizador, se generará automáticamente una propiedad denominada `Item` en el objeto. No se puede acceder directamente a la propiedad `Item` desde la instancia de [expresión de acceso a miembros](../../language-reference/operators/member-access-operators.md#member-access-expression-). Además, si agrega una propiedad `Item` propia a un objeto con un indizador, obtendrá un [error del compilador CS0102](../../misc/cs0102.md). Para evitar este error, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute> para cambiar el nombre del indizador como se detalla a continuación.

## <a name="remarks"></a>Comentarios

Los tipos de un indexador y de sus parámetros deben ser al menos igual de accesibles que el propio indexador. Para obtener más información sobre los niveles de accesibilidad, vea [Modificadores de acceso](../../language-reference/keywords/access-modifiers.md).

Para obtener más información sobre cómo usar los indexadores con una interfaz, vea [Indizadores en interfaces](./indexers-in-interfaces.md).

La firma de un indexador consta del número y los tipos de sus parámetros formales. No incluye el tipo de indizador ni los nombres de los parámetros formales. Si declara más de un indexador en la misma clase, deben tener firmas diferentes.

Un valor de indexador no está clasificado como una variable; por tanto, no se puede pasar un valor de indexador como un parámetro [ref](../../language-reference/keywords/ref.md) u [out](../../language-reference/keywords/out-parameter-modifier.md).

Para proporcionar el indizador con un nombre que puedan usar otros lenguajes, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:

```csharp
// Indexer declaration
[System.Runtime.CompilerServices.IndexerName("TheItem")]
public int this[int index]
{
    // get and set accessors
}
```

Este indizador tendrá el nombre `TheItem`, ya que lo reemplaza el atributo de nombre del indizador. De forma predeterminada, el nombre del indizador es `Item`.

## <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente, se muestra cómo declarar un campo de matriz privada, `temps`, como un indexador. El indexador permite el acceso directo a la instancia `tempRecord[i]`. La alternativa a usar el indexador es declarar la matriz como un miembro [public](../../language-reference/keywords/public.md) y tener acceso directamente a sus miembros `tempRecord.temps[i]`.

:::code language="csharp" source="snippets/Temperatures/TempRecord.cs":::

Tenga en cuenta que, cuando se evalúa el acceso de un indexador (por ejemplo, en una instrucción `Console.Write`), se invoca al descriptor de acceso [get](../../language-reference/keywords/get.md). Por tanto, si no hay ningún descriptor de acceso `get`, se produce un error en tiempo de compilación.

:::code language="csharp" source="snippets/Temperatures/Program.cs":::

## <a name="indexing-using-other-values"></a>Indexación con otros valores

C# no limita el tipo de parámetro indizador a un entero. Por ejemplo, puede ser útil usar una cadena con un indexador. Este tipo de indexador podría implementarse al buscar la cadena de la colección y devolver el valor adecuado. Como los descriptores de acceso se pueden sobrecargar, pueden coexistir las versiones de cadena y entero.

## <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se declara una clase que almacena los días de la semana. Un descriptor de acceso `get` toma una cadena, el nombre de un día, y devuelve el entero correspondiente. Por ejemplo, "Sunday" devuelve 0, "Monday" devuelve 1 y así sucesivamente.

:::code language="csharp" source="snippets/StringIndexers/DayCollection.cs":::

### <a name="consuming-example-2"></a>Ejemplo de consumo 2

:::code language="csharp" source="snippets/StringIndexers/Program.cs":::

## <a name="example-3"></a>Ejemplo 3

En el ejemplo siguiente se declara una clase que almacena los días de la semana mediante la enumeración <xref:System.DayOfWeek?displayProperty=fullName>. Un descriptor de acceso `get` toma un valor `DayOfWeek`, el nombre de un día, y devuelve el entero correspondiente. Por ejemplo, `DayOfWeek.Sunday` devuelve 0, `DayOfWeek.Monday` devuelve 1, y así sucesivamente.

:::code language="csharp" source="snippets/DayOfWeekIndexers/DayOfWeekCollection.cs":::

### <a name="consuming-example-3"></a>Ejemplo de consumo 3

:::code language="csharp" source="snippets/DayOfWeekIndexers/Program.cs":::

## <a name="robust-programming"></a>Programación sólida

Hay dos formas principales en que se pueden mejorar la seguridad y confiabilidad de los indexadores:

- Asegúrese de incorporar algún tipo de estrategia de control de errores para controlar la posibilidad de que el código de cliente pase un valor de índice no válido. En el primer ejemplo de este tema, la clase TempRecord proporciona una propiedad Length que permite al código de cliente comprobar la entrada antes de pasarla al indexador. También puede colocar el código de control de errores en el propio indexador. Asegúrese de documentar para los usuarios cualquier excepción que se produzca dentro de un descriptor de acceso del indexador.

- Establezca la accesibilidad de los descriptores de acceso [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) para que sea tan restrictiva como razonable. Esto es importante para el descriptor de acceso `set` en particular. Para más información, vea [Restringir la accesibilidad del descriptor de acceso](../classes-and-structs/restricting-accessor-accessibility.md).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Indizadores](./index.md)
- [Propiedades](../classes-and-structs/properties.md)
