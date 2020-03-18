---
title: 'interface: Referencia de C#'
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 473f5f8e226f0a144746ac943afcffdccd4777c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625857"
---
# <a name="no-loc-textinterface-c-reference"></a>:::no-loc text="interface"::: (Referencia de C#)

Una interfaz define un contrato. Cualquier [`class`](class.md) o [`struct`](../builtin-types/struct.md) que implemente ese contrato debe proporcionar una implementación de los miembros definidos en la interfaz. A partir de C# 8.0, una interfaz puede definir una implementación predeterminada de miembros. También puede definir miembros [`static`](static.md) para proporcionar una única implementación de funcionalidad común.

En el ejemplo siguiente, la clase `ImplementationClass` debe implementar un método denominado `SampleMethod` que no tiene ningún parámetro y devuelve `void`.

Para obtener más información y ejemplos, vea [Interfaces](../../programming-guide/interfaces/index.md).

## <a name="example"></a>Ejemplo

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

Una interfaz puede ser un miembro de un espacio de nombres o una clase. Una declaración de interfaz puede contener declaraciones (firmas sin ninguna implementación) de los miembros siguientes:

- [Métodos](../../programming-guide/classes-and-structs/methods.md)
- [Propiedades](../../programming-guide/classes-and-structs/using-properties.md)
- [Indizadores](../../programming-guide/indexers/using-indexers.md)
- [Eventos](event.md)

Normalmente, estas declaraciones de miembros anteriores no contienen ningún cuerpo. A partir de C# 8.0, un miembro de interfaz puede declarar un cuerpo. Esto se conoce como *implementación predeterminada*. Los miembros con cuerpos permiten que la interfaz proporcione una implementación "predeterminada" de las clases y las estructuras que no proporcionan una implementación de invalidación. Además, a partir de C# 8.0, una interfaz puede incluir:

- [Constantes](const.md)
- [Operadores](../operators/operator-overloading.md)
- [Constructor estático](../../programming-guide/classes-and-structs/constructors.md#static-constructors).
- [Tipos anidados](../../programming-guide/classes-and-structs/nested-types.md)
- [Campos, métodos, propiedades, indizadores y eventos estáticos](static.md).
- Declaraciones de miembros con la sintaxis de implementación de interfaz explícita.
- Modificadores de acceso explícitos (el acceso predeterminado es [`public`](access-modifiers.md)).

Es posible que las interfaces no contengan estado de instancia. Aunque los campos estáticos ahora están permitidos, los campos de instancia no se permiten en las interfaces. Las [propiedades automáticas de instancia](../../programming-guide/classes-and-structs/auto-implemented-properties.md) no se admiten en las interfaces, ya que declararían de forma implícita un campo oculto. Esta regla tiene un efecto sutil en las declaraciones de propiedad. En una declaración de interfaz, el código siguiente no declara una propiedad implementada automáticamente como hace en una `class` o un `struct`. En su lugar, declara una propiedad que no tiene una implementación predeterminada pero que se debe implementar en cualquier tipo que implemente la interfaz:

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

Una interfaz puede heredar de una o varias interfaces base. Cuando una interfaz [invalida un método](override.md) implementado en una interfaz base, debe usar la sintaxis de [implementación de interfaz explícita](../../programming-guide/interfaces/explicit-interface-implementation.md).

Cuando una lista de tipos base contiene una clase e interfaces base, la clase base debe aparecer primero en la lista.

Una clase que implementa una interfaz puede implementar explícitamente miembros de esa interfaz. A un miembro implementado explícitamente solo se puede tener acceso mediante una instancia de la interfaz, y no mediante una instancia de la clase. Además, solo se puede acceder a los miembros de interfaz predeterminados a través de una instancia de la interfaz.

Para obtener más información sobre la implementación de interfaz explícita, vea [Implementación de interfaz explícita](../../programming-guide/interfaces/explicit-interface-implementation.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra la implementación de una interfaz. En este ejemplo, la interfaz contiene la declaración de propiedad y la clase contiene la implementación. Cualquier instancia de una clase que implemente `IPoint` tiene las propiedades de entero `x` e `y`.

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para obtener más información, vea la sección [Interfaces](~/_csharplang/spec/interfaces.md) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md) y la especificación de características de [Miembros de interfaz predeterminados (C# 8.0)](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tipos de referencia](reference-types.md)
- [Interfaces](../../programming-guide/interfaces/index.md)
- [Utilizar propiedades](../../programming-guide/classes-and-structs/using-properties.md)
- [Utilizar indizadores](../../programming-guide/indexers/using-indexers.md)
- [Interfaces](../../programming-guide/interfaces/index.md)
