---
title: 'Herencia: Guía de programación de C#'
ms.date: 02/07/2020
helpviewer_keywords:
- abstract methods [C#]
- abstract classes [C#]
- inheritance [C#]
- derived classes [C#]
- virtual methods [C#]
- C# language, inheritance
ms.assetid: 81d64ee4-50f9-4d6c-a8dc-257c348d2eea
ms.openlocfilehash: 448b1695a4afc50f4afa20383e5fda280b9f12e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626664"
---
# <a name="inheritance-c-programming-guide"></a>Herencia (Guía de programación de C#)

La herencia, junto con la encapsulación y el polimorfismo, es una de las tres características principales de la programación orientada a objetos. La herencia permite crear clases que reutilizan, extienden y modifican el comportamiento definido en otras clases. La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*. Una clase derivada solo puede tener una clase base directa, pero la herencia es transitiva. Si `ClassC` se deriva de `ClassB` y `ClassB` se deriva de `ClassA`, `ClassC` hereda los miembros declarados en `ClassB` y `ClassA`.

> [!NOTE]
> Los structs no admiten la herencia, pero pueden implementar interfaces. Para más información, vea [Interfaces](../interfaces/index.md).

Conceptualmente, una clase derivada es una especialización de la clase base. Por ejemplo, si tiene una clase base `Animal`, podría tener una clase derivada denominada `Mammal` y otra clase derivada denominada `Reptile`. `Mammal` es `Animal` y `Reptile` también es `Animal`, pero cada clase derivada representa especializaciones diferentes de la clase base.

Las declaraciones de interfaz pueden definir una implementación predeterminada de sus miembros. Estas implementaciones las heredan las interfaces derivadas y las clases que implementan esas interfaces. Para obtener más información sobre los métodos de interfaz predeterminados, vea el artículo sobre [interfaces](../../language-reference/keywords/interface.md) en la sección de referencia del lenguaje.

Cuando se define una clase para que derive de otra clase, la clase derivada obtiene implícitamente todos los miembros de la clase base, salvo sus constructores y sus finalizadores. La clase derivada reutiliza el código de la clase base sin tener que volver a implementarlo. Puede agregar más miembros en la clase derivada. La clase derivada amplía la funcionalidad de la clase base.

En la ilustración siguiente se muestra una clase `WorkItem` que representa un elemento de trabajo de un proceso empresarial. Como con todas las clases, se deriva de <xref:System.Object?displayProperty=nameWithType> y hereda todos sus métodos. `WorkItem` agrega cinco miembros propios. Estos miembros incluyen un constructor, porque los constructores no se heredan. La clase `ChangeRequest` hereda de `WorkItem` y representa un tipo concreto de elemento de trabajo. `ChangeRequest` agrega dos miembros más a los miembros que hereda de `WorkItem` y de <xref:System.Object>. Debe agregar su propio constructor y además agrega `originalItemID`. La propiedad `originalItemID` permite que la instancia `ChangeRequest` se asocie con el `WorkItem` original al que se aplica la solicitud de cambio.

![Diagrama que muestra la herencia de clases](./media/inheritance/class-inheritance-diagram.png)

En el ejemplo siguiente se muestra cómo se expresan en C# las relaciones de clase de la ilustración anterior. En el ejemplo también se muestra cómo `WorkItem` reemplaza el método virtual <xref:System.Object.ToString%2A?displayProperty=nameWithType> y cómo la clase `ChangeRequest` hereda la implementación `WorkItem` del método. En el primer bloque se definen las clases:

[!code-csharp[DefineClasses](~/samples/snippets/csharp/objectoriented/inheritance.cs#Classes)]

En el bloque siguiente se muestra cómo usar las clases base y derivadas:

[!code-csharp[UseClasses](~/samples/snippets/csharp/objectoriented/inheritance.cs#UseClasses)]

## <a name="abstract-and-virtual-methods"></a>Métodos abstractos y virtuales

Cuando una clase base declara un método como [`virtual`](../../language-reference/keywords/virtual.md), una clase derivada puede aplicar [`override`](../../language-reference/keywords/override.md) al método con una implementación propia. Si una clase base declara un miembro como [`abstract`](../../language-reference/keywords/abstract.md), ese método se debe reemplazar en todas las clases no abstractas que hereden directamente de dicha clase. Si una clase derivada es abstracta, hereda los miembros abstractos sin implementarlos. Los miembros abstractos y virtuales son la base del polimorfismo, que es la segunda característica principal de la programación orientada a objetos. Para obtener más información, vea [Polimorfismo ](./polymorphism.md).

## <a name="abstract-base-classes"></a>Clases base abstractas

Puede declarar una clase como [abstracta](../../language-reference/keywords/abstract.md) si quiere impedir la creación directa de instancias mediante el operador [new](../../language-reference/operators/new-operator.md). Una clase abstracta solo se puede usar si a partir de ella se deriva una clase nueva. Una clase abstracta puede contener una o más firmas de método que, a su vez, se declaran como abstractas. Estas firmas especifican los parámetros y el valor devuelto, pero no tienen ninguna implementación (cuerpo del método). Una clase abstracta no tiene que contener miembros abstractos, pero si lo hace, la clase se debe declarar como abstracta. Las clases derivadas que no son abstractas deben proporcionar la implementación para todos los métodos abstractos de una clase base abstracta. Para más información, vea [Clases y miembros de clase abstractos y sellados](abstract-and-sealed-classes-and-class-members.md).

## <a name="interfaces"></a>Interfaces

Una *interfaz* es un tipo de referencia que define un conjunto de miembros. Todas las clases y estructuras que implementan esa interfaz deben implementar ese conjunto de miembros. Una interfaz puede definir una implementación predeterminada para todos o ninguno de estos miembros. Una clase puede implementar varias interfaces, aunque solo puede derivar de una única clase base directa.

Las interfaces se usan para definir funciones específicas para clases que no tienen necesariamente una relación "es un/una". Por ejemplo, la interfaz <xref:System.IEquatable%601?displayProperty=nameWithType> se puede implementar mediante cualquier clase o estructura para determinar si dos objetos del tipo son equivalentes (pero el tipo define la equivalencia). <xref:System.IEquatable%601> no implica el mismo tipo de relación "es un/una" que existe entre una clase base y una clase derivada (por ejemplo, `Mammal` es `Animal`). Para más información, vea [Interfaces](../interfaces/index.md).

## <a name="preventing-further-derivation"></a>Impedir la derivación adicional  

Una clase puede impedir que otras clases hereden de ella, o de cualquiera de sus miembros, si se declara a sí misma o al miembro como [`sealed`](../../language-reference/keywords/sealed.md). Para más información, vea [Clases y miembros de clase abstractos y sellados](./abstract-and-sealed-classes-and-class-members.md).

## <a name="derived-class-hiding-of-base-class-members"></a>Clase derivada que oculta miembros de clase base  

Una clase derivada puede ocultar miembros de clase base si declara los miembros con el mismo nombre y firma. Se puede usar el modificador [`new`](../../language-reference/keywords/new-modifier.md) para indicar de forma explícita que el miembro no está diseñado para reemplazar al miembro base. No es necesario usar [`new`](../../language-reference/keywords/new-modifier.md), pero se generará una advertencia del compilador si no se usa [`new`](../../language-reference/keywords/new-modifier.md). Para obtener más información, vea [Control de versiones con las palabras clave Override y New ](./versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New](./knowing-when-to-use-override-and-new-keywords.md).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [class](../../language-reference/keywords/class.md)
