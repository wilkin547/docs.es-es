---
description: 'Palabra clave class: Referencia de C#'
title: 'Palabra clave class: Referencia de C#'
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 67c9c4be55cce25edf9ecb84b257a8523f193bec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142120"
---
# <a name="class-c-reference"></a>class (Referencia de C#)

Las clases se declaran mediante la palabra clave `class`, como se muestra en el siguiente ejemplo:

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a>Observaciones

Solo la herencia simple se permite en C#. En otras palabras, una clase puede heredar la implementación solo de una clase base. En cambio, una clase puede implementar más de una interfaz. En la tabla siguiente se muestran ejemplos de herencia de clases e implementación de interfaces:

|Herencia|Ejemplo|
|-----------------|-------------|
|None|`class ClassA { }`|
|Único|`class DerivedClass : BaseClass { }`|
|Ninguna, implementa dos interfaces|`class ImplClass : IFace1, IFace2 { }`|
|Única, implementa una interfaz|`class ImplDerivedClass : BaseClass, IFace1 { }`|

Las clases que se declaran directamente dentro de un espacio de nombres, que no están anidadas dentro de otras clases, pueden ser de tipo [public](./public.md) o [internal](./internal.md). De forma predeterminada, las clases son `internal`.

Los miembros de clase, incluidas las clases anidadas, pueden ser [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md) o [private protected](private-protected.md). De forma predeterminada, los miembros son `private`.

Para obtener más información, consulte [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md).

Puede declarar clases genéricas que tengan parámetros de tipo. Para obtener más información, consulte [Clases genéricas](../../programming-guide/generics/generic-classes.md).

Una clase puede contener declaraciones de los miembros siguientes:

- [Constructores](../../programming-guide/classes-and-structs/constructors.md)

- [Constantes](../../programming-guide/classes-and-structs/constants.md)

- [Campos](../../programming-guide/classes-and-structs/fields.md)

- [Finalizadores](../../programming-guide/classes-and-structs/destructors.md)

- [Métodos](../../programming-guide/classes-and-structs/methods.md)

- [Propiedades](../../programming-guide/classes-and-structs/properties.md)

- [Indizadores](../../programming-guide/indexers/index.md)

- [Operadores](../operators/index.md)

- [Eventos](../../programming-guide/events/index.md)

- [Delegados](../../programming-guide/delegates/index.md)

- [Clases](../../programming-guide/classes-and-structs/classes.md)

- [Interfaces](../../programming-guide/interfaces/index.md)

- [Tipos de estructura](../builtin-types/struct.md)

- [Tipos de enumeración](../builtin-types/enum.md)

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo declarar campos de clase, constructores y métodos. También se muestra la creación de instancias de objeto y la impresión de datos de instancias. En este ejemplo, se declaran dos clases. La primera clase, `Child`, contiene dos campos privados (`name` y `age`), dos constructores públicos y un método público. La segunda clase, `StringTest`, se usa para contener `Main`.

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a>Comentarios

Observe que en el ejemplo anterior solo se puede acceder a los campos privados (`name` y `age`) a través del método público de la clase `Child`. Por ejemplo, no puede imprimir el nombre de la clase child, desde el método `Main`, mediante una instrucción como esta:

```csharp
Console.Write(child1.name);   // Error
```

El acceso a miembros privados de `Child` desde `Main` solo sería posible si `Main` fuera un miembro de la clase.

Los tipos declarados dentro de una clase sin un modificador de acceso adoptan el valor predeterminado de `private`, por lo que los miembros de datos de este ejemplo seguirían siendo `private` si se quitara la palabra clave.

Por último, tenga en cuenta que, para el objeto creado mediante el constructor sin parámetros (`child3`), el campo `age` se ha inicializado en cero de forma predeterminada.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
- [Tipos de referencia](./reference-types.md)
