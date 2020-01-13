---
title: 'Herencia: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- abstract methods [C#]
- abstract classes [C#]
- inheritance [C#]
- derived classes [C#]
- virtual methods [C#]
- C# language, inheritance
ms.assetid: 81d64ee4-50f9-4d6c-a8dc-257c348d2eea
ms.openlocfilehash: 3c59741fa646111d27f6d1087a9275178c1a41a1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705553"
---
# <a name="inheritance-c-programming-guide"></a>Herencia (Guía de programación de C#)

La herencia, junto con la encapsulación y el polimorfismo, es una de las tres características principales de la programación orientada a objetos. La herencia permite crear clases nuevas que reutilizan, extienden y modifican el comportamiento que se define en otras clases. La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*. Una clase derivada solo puede tener una clase base directa, pero la herencia es transitiva. Si ClaseC se deriva de ClaseB y ClaseB se deriva de ClaseA, ClaseC hereda los miembros declarados en ClaseB y ClaseA.  
  
> [!NOTE]
> Los structs no admiten la herencia, pero pueden implementar interfaces. Para más información, vea [Interfaces](../interfaces/index.md).  
  
 Conceptualmente, una clase derivada es una especialización de la clase base. Por ejemplo, si tiene una clase base `Animal`, podría tener una clase derivada denominada `Mammal` y otra clase derivada denominada `Reptile`. `Mammal` es `Animal` y `Reptile` también es `Animal`, pero cada clase derivada representa especializaciones diferentes de la clase base.  
  
 Cuando se define una clase para que derive de otra clase, la clase derivada obtiene implícitamente todos los miembros de la clase base, salvo sus constructores y sus finalizadores. La clase derivada puede reutilizar el código de la clase base sin tener que volver a implementarlo. Puede agregar más miembros en la clase derivada. De esta manera, la clase derivada amplía la funcionalidad de la clase base.  
  
 En la ilustración siguiente se muestra una clase `WorkItem` que representa un elemento de trabajo de un proceso empresarial. Como con todas las clases, se deriva de <xref:System.Object?displayProperty=nameWithType> y hereda todos sus métodos. `WorkItem` agrega cinco miembros propios. Entre estos se incluye un constructor, dado que los constructores no se heredan. La clase `ChangeRequest` hereda de `WorkItem` y representa un tipo concreto de elemento de trabajo. `ChangeRequest` agrega dos miembros más a los miembros que hereda de `WorkItem` y de <xref:System.Object>. Debe agregar su propio constructor y además agrega `originalItemID`. La propiedad `originalItemID` permite que la instancia `ChangeRequest` se asocie con el `WorkItem` original al que se aplica la solicitud de cambio.  
  
 ![Diagrama que muestra la herencia de clases](./media/inheritance/class-inheritance-diagram.png)  
  
 En el ejemplo siguiente se muestra cómo se expresan en C# las relaciones de clase de la ilustración anterior. En el ejemplo también se muestra cómo `WorkItem` reemplaza el método virtual <xref:System.Object.ToString%2A?displayProperty=nameWithType> y cómo la clase `ChangeRequest` hereda la implementación `WorkItem` del método.  
  
 [!code-csharp[csProgGuideInheritance#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#49)]  
  
## <a name="abstract-and-virtual-methods"></a>Métodos abstractos y virtuales  
 Cuando una clase base declara un método como [virtual](../../language-reference/keywords/virtual.md), una clase derivada puede [reemplazar](../../language-reference/keywords/override.md) el método con su propia implementación. Si una clase base declara un miembro como [abstracto](../../language-reference/keywords/abstract.md), ese método se debe reemplazar en todas las clases no abstractas que hereden directamente de dicha clase. Si una clase derivada es abstracta, hereda los miembros abstractos sin implementarlos. Los miembros abstractos y virtuales son la base del polimorfismo, que es la segunda característica principal de la programación orientada a objetos. Para obtener más información, vea [Polimorfismo ](./polymorphism.md).  
  
## <a name="abstract-base-classes"></a>Clases base abstractas  
 Puede declarar una clase como [abstracta](../../language-reference/keywords/abstract.md) si quiere impedir la creación directa de instancias mediante el operador [new](../../language-reference/operators/new-operator.md). Si lo hace, la clase solo se puede usar si se deriva de ella una clase nueva. Una clase abstracta puede contener una o más firmas de método que, a su vez, se declaran como abstractas. Estas firmas especifican los parámetros y el valor devuelto, pero no tienen ninguna implementación (cuerpo del método). Una clase abstracta no tiene que contener miembros abstractos, pero si lo hace, la clase debe declararse como abstracta. Las clases derivadas que no son abstractas deben proporcionar la implementación para todos los métodos abstractos de una clase base abstracta. Para más información, vea [Clases y miembros de clase abstractos y sellados](./abstract-and-sealed-classes-and-class-members.md).  
  
## <a name="interfaces"></a>Interfaces  
 Una *interfaz* es un tipo de referencia similar a una clase base abstracta formada únicamente por miembros abstractos. Cuando una clase implementa una interfaz, debe proporcionar una implementación para todos los miembros de la interfaz. Una clase puede implementar varias interfaces, aunque solo puede derivar de una única clase base directa.  
  
 Las interfaces se usan para definir funciones específicas para clases que no tienen necesariamente una relación "es un/una". Por ejemplo, la interfaz <xref:System.IEquatable%601?displayProperty=nameWithType> se puede implementar mediante cualquier clase o struct que deba permitir que el código de cliente determine si dos objetos del tipo son equivalentes (pero el tipo define la equivalencia). <xref:System.IEquatable%601> no implica el mismo tipo de relación "es un/una" que existe entre una clase base y una clase derivada (por ejemplo, `Mammal` es `Animal`). Para más información, vea [Interfaces](../interfaces/index.md).  
  
## <a name="preventing-further-derivation"></a>Impedir la derivación adicional  
 Una clase puede impedir que otras clases hereden de ella o de cualquiera de sus miembros. Para ello, se declara a sí misma o declara su miembro como [sellado](../../language-reference/keywords/sealed.md). Para obtener más información, vea [Clases y miembros de clase abstractos y sellados](./abstract-and-sealed-classes-and-class-members.md).  
  
## <a name="derived-class-hiding-of-base-class-members"></a>Clase derivada que oculta miembros de clase base  
 Una clase derivada puede ocultar miembros de clase base si declara los miembros con el mismo nombre y firma. Se puede usar el modificador [new](../../language-reference/keywords/new-modifier.md) para indicar explícitamente que el miembro no está diseñado para reemplazar al miembro base. No es necesario usar [new](../../language-reference/keywords/new-modifier.md), pero se generará una advertencia del compilador si no se usa [new](../../language-reference/keywords/new-modifier.md). Para obtener más información, vea [Control de versiones con las palabras clave Override y New ](./versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New](./knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [class](../../language-reference/keywords/class.md)
- [struct](../../language-reference/keywords/struct.md)
