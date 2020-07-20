---
title: 'Interfaces: Guía de programación de C#'
ms.date: 02/20/2020
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
ms.openlocfilehash: 50f2c5fc3570b6d66ed83206660caf4bd02f1f5b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441341"
---
# <a name="interfaces-c-programming-guide"></a>Interfaces (Guía de programación de C#)

Una interfaz contiene las definiciones de un grupo de funcionalidades relacionadas que una [clase](../../language-reference/keywords/class.md) o una [estructura](../../language-reference/builtin-types/struct.md) no abstracta deben implementar. Una interfaz puede definir métodos `static`, que deben tener una implementación. A partir de C# 8.0, una interfaz puede definir una implementación predeterminada de miembros. Una interfaz no puede declarar datos de instancia, como campos, propiedades implementadas automáticamente o eventos similares a las propiedades.

Mediante las interfaces puede incluir, por ejemplo, un comportamiento de varios orígenes en una clase. Esta capacidad es importante en C# porque el lenguaje no admite la herencia múltiple de clases. Además, debe usar una interfaz si desea simular la herencia de estructuras, porque no pueden heredar de otra estructura o clase.

Para definir una interfaz, deberá usar la palabra clave [interface](../../language-reference/keywords/interface.md), tal y como se muestra en el ejemplo siguiente.

[!code-csharp[Equatable](~/samples/snippets/csharp/objectoriented/interfaces.cs#Equatable)]

El nombre de una interfaz debe ser un [nombre de identificador](../inside-a-program/identifier-names.md) de C# válido. Por convención, los nombres de interfaz comienzan con una letra `I` mayúscula.

Cualquier clase o estructura que implementa la interfaz <xref:System.IEquatable%601> debe contener una definición para un método <xref:System.IEquatable%601.Equals%2A> que coincida con la firma que la interfaz especifica. Como resultado, puede contar con una clase que implementa `IEquatable<T>` para contener un método `Equals` con el que una instancia de la clase puede determinar si es igual a otra instancia de la misma clase.

La definición de `IEquatable<T>` no facilita ninguna implementación para `Equals`. Una clase o estructura puede implementar varias interfaces, pero una clase solo puede heredar de una sola clase.

Para obtener más información sobre las clases abstractas, vea [Clases y miembros de clase abstractos y sellados (Guía de programación de C#)](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md).

Las interfaces pueden contener propiedades, eventos, indizadores o métodos de instancia, o bien cualquier combinación de estos cuatro tipos de miembros. Las interfaces pueden contener constructores estáticos, campos, constantes u operadores. Para obtener vínculos a ejemplos, vea [Secciones relacionadas](./index.md#BKMK_RelatedSections). Una interfaz no puede contener campos de instancia, constructores de instancias ni finalizadores. Los miembros de la interfaz son públicos de forma predeterminada.

Para implementar un miembro de interfaz, el miembro correspondiente de la clase de implementación debe ser público, no estático y tener el mismo nombre y firma que el miembro de interfaz.

Cuando una clase o estructura implementa una interfaz, la clase o estructura debe proporcionar una implementación para todos los miembros que la interfaz declara sin proporcionar ninguna implementación predeterminada para ellos. Sin embargo, si una clase base implementa una interfaz, cualquier clase que se derive de la clase base hereda esta implementación.

En el siguiente ejemplo se muestra una implementación de la interfaz <xref:System.IEquatable%601>. La clase de implementación `Car` debe proporcionar una implementación del método <xref:System.IEquatable%601.Equals%2A>.

[!code-csharp[ImplementEquatable](~/samples/snippets/csharp/objectoriented/interfaces.cs#ImplementEquatable)]

Las propiedades y los indizadores de una clase pueden definir descriptores de acceso adicionales para una propiedad o indizador que estén definidos en una interfaz. Por ejemplo, una interfaz puede declarar una propiedad que tenga un descriptor de acceso [get](../../language-reference/keywords/get.md). La clase que implementa la interfaz puede declarar la misma propiedad con un descriptor de acceso `get` y [set](../../language-reference/keywords/set.md). Sin embargo, si la propiedad o el indizador usan una implementación explícita, los descriptores de acceso deben coincidir. Para obtener más información sobre la implementación explícita, vea [Implementación de interfaz explícita](explicit-interface-implementation.md) y [Propiedades de interfaces](../classes-and-structs/interface-properties.md).

Las interfaces pueden heredar de una o varias interfaces. La interfaz derivada hereda los miembros de sus interfaces base. Una clase que implementa una interfaz derivada debe implementar todos los miembros de esta, incluidos los de las interfaces base. Esa clase puede convertirse implícitamente en la interfaz derivada o en cualquiera de sus interfaces base. Una clase puede incluir una interfaz varias veces mediante las clases base que hereda o mediante las interfaces que otras interfaces heredan. Sin embargo, la clase puede proporcionar una implementación de una interfaz solo una vez y solo si la clase declara la interfaz como parte de la definición de la clase (`class ClassName : InterfaceName`). Si la interfaz se hereda porque se heredó una clase base que implementa la interfaz, la clase base proporciona la implementación de los miembros de la interfaz. Sin embargo, la clase derivada puede volver a implementar cualquier miembro de la interfaz virtual, en lugar de usar la implementación heredada. Cuando una interfaz declara una implementación predeterminada de un método, cualquier clase que implemente la interfaz en cuestión hereda esa implementación. Las implementaciones definidas en interfaces son virtuales y es posible que la clase que realice la implementación las invalide.

Una clase base también puede implementar miembros de interfaz mediante el uso de los miembros virtuales. En ese caso, una clase derivada puede cambiar el comportamiento de la interfaz reemplazando los miembros virtuales. Para obtener más información sobre los miembros virtuales, vea [Polimorfismo](../classes-and-structs/polymorphism.md).

## <a name="interfaces-summary"></a>Resumen de interfaces

Una interfaz tiene las propiedades siguientes:

- Normalmente, una interfaz es como una clase base abstracta con solo miembros abstractos. Cualquier clase o estructura que implementa la interfaz debe implementar todos sus miembros. Opcionalmente, una interfaz puede definir implementaciones predeterminadas para algunos o todos sus miembros. Para obtener más información, vea [Métodos de interfaz predeterminados](../../tutorials/default-interface-methods-versions.md).
- No se puede crear una instancia de una interfaz directamente. Sus miembros se implementan por medio de cualquier clase o estructura que implementa la interfaz.
- Una clase o estructura puede implementar varias interfaces. Una clase puede heredar una clase base y también implementar una o varias interfaces.

## <a name="related-sections"></a><a name="BKMK_RelatedSections"></a> Secciones relacionadas

- [Propiedades de interfaz](../classes-and-structs/interface-properties.md)  
- [Indizadores en Interfaces](../indexers/indexers-in-interfaces.md)  
- [Procedimiento para implementar eventos de interfaz](../events/how-to-implement-interface-events.md)
- [Clases y structs](../classes-and-structs/index.md)  
- [Herencia](../classes-and-structs/inheritance.md)  
- [Interfaces](../../language-reference/keywords/interface.md)
- [Métodos](../classes-and-structs/methods.md)  
- [Polimorfismo](../classes-and-structs/polymorphism.md)  
- [Clases y miembros de clase abstractos y sellados](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
- [Propiedades](../classes-and-structs/properties.md)  
- [Eventos](../events/index.md)  
- [Indizadores](../indexers/index.md)
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Herencia](../classes-and-structs/inheritance.md)
- [Nombres de identificador](../inside-a-program/identifier-names.md)
