---
title: Miembros con cuerpo de expresión (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 800280ed9ceaf69b825bb2a3c2c3d0d5f829922d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332759"
---
# <a name="expression-bodied-members-c-programming-guide"></a>Miembros con cuerpo de expresión (Guía de programación de C#)
Las definiciones de cuerpos de expresión permiten proporcionar la implementación de un miembro de una forma muy concisa y legible. Se puede usar una definición de cuerpo de expresión siempre que la lógica de cualquier miembro compatible, como un método o propiedad, se componga de una expresión única. Una definición de cuerpo de expresión tiene la siguiente sintaxis general:

```csharp
member => expression;
```

donde *expresión* es una expresión válida. 

La compatibilidad con las definiciones de cuerpos de expresión se introdujo para los métodos y descriptores de acceso get de propiedad en C# 6 y se expandió en C# 7.0. Las definiciones de cuerpos de expresión se pueden usar con los miembros de tipo que se muestran en la tabla siguiente: 

|Miembro  |Se admite desde... |
|---------|---------|
|[Método](#methods)  |C# 6 |
|[Constructor](#constructors)   |C# 7.0 |
|[Finalizador](#finalizers)     |C# 7.0 |
|[Descriptor de acceso get de propiedad](#property-get-statements)  |C# 6 |
|[Descriptor de acceso set de propiedad](#property-set-statements)  |C# 7.0 |
|[Indizador](#indexers)       |C# 7.0 |

## <a name="methods"></a>Métodos

Un método con cuerpo de expresión consta de una sola expresión que devuelve un valor cuyo tipo coincide con el tipo de valor devuelto del método, o bien, para los métodos que devuelven `void`, que realiza alguna operación. Por ejemplo, los tipos que reemplazan el método <xref:System.Object.ToString%2A> normalmente incluyen una sola expresión que devuelve la representación de cadena del objeto actual. 

En el ejemplo siguiente se define una clase `Person` que reemplaza el método <xref:System.Object.ToString%2A> con una definición de cuerpo de expresión. También define un método `Show` que muestra un nombre en la consola. Tenga en cuenta que la palabra clave `return` no se usa en la definición de cuerpo de expresión de `ToString`.

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

Para más información, vea [Métodos (Guía de programación de C#)](../classes-and-structs/methods.md).
 
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

## <a name="property-get-statements"></a>Instrucciones get de propiedad

Si decide implementar un descriptor de acceso get de la propiedad usted mismo, puede usar una definición de cuerpo de expresión para expresiones únicas que simplemente devuelven el valor de la propiedad. Tenga en cuenta que se usa la instrucción `return`.

En el ejemplo siguiente se define una propiedad `Location.Name` cuyo descriptor de acceso get de propiedad devuelve el valor del campo `locationName` privado que respalda la propiedad. 

[!code-csharp[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Las propiedades de solo lectura que usan una definición de cuerpo de expresión se pueden implementar sin una instrucción `set` explícita. La sintaxis es la siguiente:

```csharp
PropertyName => returnValue;
```

En el ejemplo siguiente se define una clase `Location` cuya propiedad `Name` de solo lectura se implementa como una definición de cuerpo de expresión que devuelve el valor del campo privado `locationName`.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

Para más información, vea [Propiedades (Guía de programación de C#)](../classes-and-structs/properties.md).

## <a name="property-set-statements"></a>Instrucciones set de propiedad

Si decide implementar un descriptor de acceso set de propiedad usted mismo, puede usar una definición de cuerpo de expresión para una expresión de una sola línea que asigne un valor al campo que respalda la propiedad.

En el ejemplo siguiente se define una propiedad `Location.Name` cuya instrucción set de propiedad asigna su argumento de entrada al valor del campo `locationName` privado que respalda la propiedad.

[!code-csharp[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Para más información, vea [Propiedades (Guía de programación de C#)](../classes-and-structs/properties.md).

## <a name="indexers"></a>Indizadores

Como las propiedades, los descriptores de acceso get y set de un indizador constan de las definiciones de cuerpos de expresión si el descriptor de acceso get está formado por una sola instrucción que devuelve un valor o el descriptor de acceso set realiza una asignación simple.

En el ejemplo siguiente se define una clase denominada `Sports` que incluye una matriz <xref:System.String> interna que contiene los nombres de varios deportes. Los descriptores de acceso get y set del indizador se implementan como definiciones de cuerpos de expresión.

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

Para más información, vea [Indizadores (Guía de programación de C#)](../indexers/index.md).

