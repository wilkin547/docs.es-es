---
title: 'Miembros con cuerpo de expresión: Guía de programación de C#'
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: f212bb707d3dd2d4a7cc917d335a83cff01ed0cf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711992"
---
# <a name="expression-bodied-members-c-programming-guide"></a>Miembros con cuerpo de expresión (Guía de programación de C#)

Las definiciones de cuerpos de expresión permiten proporcionar la implementación de un miembro de una forma muy concisa y legible. Se puede usar una definición de cuerpo de expresión siempre que la lógica de cualquier miembro compatible, como un método o propiedad, se componga de una expresión única. Una definición de cuerpo de expresión tiene la siguiente sintaxis general:

```csharp
member => expression;
```

donde *expresión* es una expresión válida.

La compatibilidad con las definiciones de cuerpos de expresión se introdujo para los métodos y las propiedades de solo lectura en C# 6 y se expandió en C# 7.0. Las definiciones de cuerpos de expresión se pueden usar con los miembros de tipo que se muestran en la tabla siguiente:

|Miembro  |Se admite desde... |
|---------|---------|
|[Método](#methods)  |C# 6 |
|[Propiedad de solo lectura](#read-only-properties)   |C# 6  |
|[Property](#properties)  |C# 7.0 |
|[Constructor](#constructors)   |C# 7.0 |
|[Finalizador](#finalizers)     |C# 7.0 |
|[Indizador](#indexers)       |C# 7.0 |

## <a name="methods"></a>Métodos

Un método con cuerpo de expresión consta de una sola expresión que devuelve un valor cuyo tipo coincide con el tipo de valor devuelto del método, o bien, para los métodos que devuelven `void`, que realiza alguna operación. Por ejemplo, los tipos que reemplazan el método <xref:System.Object.ToString%2A> normalmente incluyen una sola expresión que devuelve la representación de cadena del objeto actual.

En el ejemplo siguiente se define una clase `Person` que reemplaza el método <xref:System.Object.ToString%2A> con una definición de cuerpo de expresión. También define un método `DisplayName` que muestra un nombre en la consola. Tenga en cuenta que la palabra clave `return` no se usa en la definición de cuerpo de expresión de `ToString`.

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

Para más información, vea [Métodos (Guía de programación de C#)](../classes-and-structs/methods.md).

## <a name="read-only-properties"></a>Propiedades de solo lectura

A partir de C# 6, puede usar la definición de cuerpo de expresión para implementar una propiedad de solo lectura. Para ello, use la sintaxis siguiente:

```csharp
PropertyType PropertyName => expression;
```

En el ejemplo siguiente se define una clase `Location` cuya propiedad `Name` de solo lectura se implementa como una definición de cuerpo de expresión que devuelve el valor del campo privado `locationName`:

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

Para más información sobre las propiedades, vea [Propiedades (Guía de programación de C#)](../classes-and-structs/properties.md).

## <a name="properties"></a>Propiedades

A partir de C# 7.0, puede usar las definiciones de cuerpo de expresión para implementar los descriptores de acceso `get` y `set` de propiedades. En el ejemplo siguiente se muestra cómo hacerlo:

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

Para más información sobre las propiedades, vea [Propiedades (Guía de programación de C#)](../classes-and-structs/properties.md).

## <a name="constructors"></a>Constructores

Una definición de cuerpo de expresión para un constructor normalmente consta de una expresión de asignación única o una llamada de método que controla los argumentos del constructor o inicializa el estado de la instancia.

En el ejemplo siguiente se define una clase `Location` cuyo constructor tiene un único parámetro de cadena denominado *name*. La definición del cuerpo de expresión asigna el argumento a la propiedad `Name`.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Para más información, vea [Constructores (Guía de programación de C#)](../classes-and-structs/constructors.md).

## <a name="finalizers"></a>Finalizadores

Una definición de cuerpo de expresión para un finalizador normalmente contiene instrucciones de limpieza, como las instrucciones que liberan recursos no administrados.

En el ejemplo siguiente se define un finalizador que usa una definición de cuerpo de expresión para indicar que el finalizador se ha llamado.

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

Para más información, vea [Finalizadores (Guía de programación de C#)](../classes-and-structs/destructors.md).

## <a name="indexers"></a>Indizadores

Como las propiedades, los descriptores de acceso `get` y `set` del indizador constan de las definiciones de cuerpos de expresión si el descriptor de acceso `get` está formado por una sola expresión que devuelve un valor o el descriptor de acceso `set` realiza una asignación simple.

En el ejemplo siguiente se define una clase denominada `Sports` que incluye una matriz <xref:System.String> interna que contiene los nombres de varios deportes. Los descriptores de acceso `get` y `set` del indizador se implementan como definiciones de cuerpos de expresión.

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

Para más información, vea [Indizadores (Guía de programación de C#)](../indexers/index.md).
