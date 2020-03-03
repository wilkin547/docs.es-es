---
title: 'Polimorfismo: Guía de programación de C#'
ms.date: 02/08/2020
helpviewer_keywords:
- C# language, polymorphism
- polymorphism [C#]
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
ms.openlocfilehash: 169ba2a1307a301c80b3d9ccac45f4ac9f707921
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626293"
---
# <a name="polymorphism-c-programming-guide"></a>Polimorfismo (Guía de programación de C#)

El polimorfismo suele considerarse el tercer pilar de la programación orientada a objetos, después de la encapsulación y la herencia. Polimorfismo es una palabra griega que significa "con muchas formas" y tiene dos aspectos diferentes:
  
- En tiempo de ejecución, los objetos de una clase derivada pueden ser tratados como objetos de una clase base en lugares como parámetros de métodos y colecciones o matrices. Cuando se produce este polimorfismo, el tipo declarado del objeto ya no es idéntico a su tipo en tiempo de ejecución.
- Las clases base pueden definir e implementar *métodos* [virtuales](../../language-reference/keywords/virtual.md), y las clases derivadas pueden [invalidarlos](../../language-reference/keywords/override.md), lo que significa que pueden proporcionar su propia definición e implementación. En tiempo de ejecución, cuando el código de cliente llama al método, CLR busca el tipo en tiempo de ejecución del objeto e invoca esa invalidación del método virtual. En el código fuente puede llamar a un método en una clase base y hacer que se ejecute una versión del método de la clase derivada.

Los métodos virtuales permiten trabajar con grupos de objetos relacionados de manera uniforme. Por ejemplo, supongamos que tiene una aplicación de dibujo que permite a un usuario crear varios tipos de formas en una superficie de dibujo. En tiempo de compilación, no sabe qué tipos específicos de formas creará el usuario. Sin embargo, la aplicación tiene que realizar el seguimiento de los distintos tipos de formas que se crean, y tiene que actualizarlos en respuesta a las acciones del mouse del usuario. Para solucionar este problema en dos pasos básicos, puede usar el polimorfismo:

1. Crear una jerarquía de clases en la que cada clase de forma específica deriva de una clase base común.
1. Usar un método virtual para invocar el método apropiado en una clase derivada mediante una sola llamada al método de la clase base.

Primero, cree una clase base llamada `Shape` y clases derivadas como `Rectangle`, `Circle` y `Triangle`. Dé a la clase `Shape` un método virtual llamado `Draw` e invalídelo en cada clase derivada para dibujar la forma determinada que la clase representa. Cree un objeto `List<Shape>` y agréguele una instancia de `Circle`, `Triangle` y `Rectangle`. 

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#PolymorphismOverview)]

Para actualizar la superficie de dibujo, use un bucle [foreach](../../language-reference/keywords/foreach-in.md) para iterar por la lista y llamar al método `Draw` en cada objeto `Shape` de la lista. Aunque cada objeto de la lista tenga un tipo declarado de `Shape`, se invocará el tipo en tiempo de ejecución (la versión invalidada del método en cada clase derivada).

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UsePolymorphism)]

En C#, cada tipo es polimórfico porque todos los tipos, incluidos los definidos por el usuario, heredan de <xref:System.Object>.  

## <a name="polymorphism-overview"></a>Introducción al polimorfismo

### <a name="virtual-members"></a>Miembros virtuales

Cuando una clase derivada hereda de una clase base, obtiene todos los métodos, campos, propiedades y eventos de la clase base. El diseñador de la clase derivada puede tener diferentes opciones para el comportamiento de los métodos virtuales:

- La clase derivada puede invalidar los miembros virtuales de la clase base, y definir un comportamiento nuevo.
- La clase derivada hereda el método de clase base más cercano sin invalidarlo, para conservar el comportamiento existente, pero permite que más clases derivadas invaliden el método.
- La clase derivada puede definir una nueva implementación no virtual de esos miembros que oculte las implementaciones de la clase base.

Una clase derivada puede invalidar un miembro de la clase base si este se declara como [virtual](../../language-reference/keywords/virtual.md) o [abstracto](../../language-reference/keywords/abstract.md). El miembro derivado debe usar la palabra clave [override](../../language-reference/keywords/override.md) para indicar explícitamente que el propósito del método es participar en una invocación virtual. El siguiente fragmento de código muestra un ejemplo:

[!code-csharp[Virtual overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#VirtualMethods)]

Los campos no pueden ser virtuales; solo pueden serlo los métodos, propiedades, eventos e indizadores. Cuando una clase derivada invalida un miembro virtual, se llama a ese miembro aunque se acceda a una instancia de esa clase como una instancia de la clase base. El siguiente fragmento de código muestra un ejemplo:

[!code-csharp[Virtual overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#VirtualMethods)]

Los métodos y propiedades virtuales permiten a las clases derivadas extender una clase base sin necesidad de usar la implementación de clase base de un método. Para obtener más información, consulte [Control de versiones con las palabras clave Override y New](./versioning-with-the-override-and-new-keywords.md). Una interfaz proporciona otra manera de definir un método o conjunto de métodos cuya implementación se deja a las clases derivadas. Para más información, vea [Interfaces](../interfaces/index.md).

### <a name="hide-base-class-members-with-new-members"></a>Ocultación de miembros de clase base con miembros nuevos

Si quiere que la clase derivada tenga un miembro con el mismo nombre que el de un miembro de una clase base, puede usar la palabra clave [new](../../language-reference/keywords/new-modifier.md) para ocultar el miembro de clase base. La palabra clave `new` se coloca antes que el tipo devuelto del miembro de la clase que se está reemplazando. El siguiente fragmento de código muestra un ejemplo:

[!code-csharp[New method overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#NewMethods)]

Se puede acceder a los miembros de la clase base ocultos desde el código de cliente si se convierte la instancia de la clase derivada en una instancia de la clase base. Por ejemplo:

[!code-csharp[New method overview usage](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UseNewMethods)]

### <a name="prevent-derived-classes-from-overriding-virtual-members"></a>Evasión de que las clases derivadas invaliden los miembros virtuales  

Los miembros virtuales siguen siendo virtuales con independencia de cuántas clases se hayan declarado entre el miembro virtual y la clase que originalmente lo haya declarado. Si la clase `A` declara un miembro virtual y la clase `B` deriva de `A`, y la clase `C` de `B`, la clase `C` hereda el miembro virtual y puede invalidarlo, independientemente de que la clase `B` haya declarado una invalidación para ese miembro. El siguiente fragmento de código muestra un ejemplo:

[!code-csharp[Basic hierarchy](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#FirstHierarchy)]

Una clase derivada puede detener la herencia virtual al declarar una invalidación como [sealed](../../language-reference/keywords/sealed.md). Para detener la herencia, es necesario colocar la palabra clave `sealed` antes de la palabra clave `override` en la declaración del miembro de la clase. El siguiente fragmento de código muestra un ejemplo:

[!code-csharp[A sealed overridden member](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#SealedOverride)]

En el ejemplo anterior, el método `DoWork` ya no es virtual para ninguna clase que se derive de `C`. Sigue siendo virtual para las instancias de `C`, aunque se conviertan al tipo `B` o al tipo `A`. Los métodos sellados se pueden reemplazar por clases derivadas mediante la palabra clave `new`, como se muestra en el ejemplo siguiente:

[!code-csharp[New method declaration](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#NewDeclaration)]

En este caso, si se llama a `DoWork` en `D` con una variable de tipo `D`, se llama a la nueva instancia de `DoWork`. Si se usa una variable de tipo `C`, `B` o `A` para acceder a una instancia de `D`, la llamada a `DoWork` seguirá las reglas de herencia virtual y enrutará esas llamadas a la implementación de `DoWork` en la clase `C`.

### <a name="access-base-class-virtual-members-from-derived-classes"></a>Acceso a miembros virtuales de clases base desde clases derivadas

Una clase derivada que ha reemplazado o invalidado un método o propiedad puede seguir accediendo al método o propiedad en la clase base usando la siguiente palabra clave `base`. El siguiente fragmento de código muestra un ejemplo:

```csharp
public class Base
{
    public virtual void DoWork() {/*...*/ }
}
public class Derived : Base
{
    public override void DoWork()
    {
        //Perform Derived's work here
        //...
        // Call DoWork on base class
        base.DoWork();
    }
}
```

Para obtener más información, vea [base](../../language-reference/keywords/base.md).

> [!NOTE]
> Se recomienda que las máquinas virtuales usen `base` para llamar a la implementación de la clase base de ese miembro en su propia implementación. Dejar que se produzca el comportamiento de la clase base permite a la clase derivada concentrarse en implementar el comportamiento específico de la clase derivada. Si no se llama a la implementación de la clase base, depende de la clase derivada hacer que su comportamiento sea compatible con el de la clase base.

## <a name="in-this-section"></a>En esta sección

- [Control de versiones con las palabras clave Override y New](./versioning-with-the-override-and-new-keywords.md)
- [Saber cuándo utilizar las palabras clave Override y New](./knowing-when-to-use-override-and-new-keywords.md)
- [Invalidación del método ToString](./how-to-override-the-tostring-method.md)

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Herencia](./inheritance.md)
- [Clases y miembros de clase abstractos y sellados](./abstract-and-sealed-classes-and-class-members.md)
- [Métodos](./methods.md)
- [Eventos](../events/index.md)
- [Propiedades](./properties.md)
- [Indizadores](../indexers/index.md)
- [Tipos](../types/index.md)
