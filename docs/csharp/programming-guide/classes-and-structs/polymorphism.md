---
title: 'Polimorfismo: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, polymorphism
- polymorphism [C#]
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
ms.openlocfilehash: 4f65082ad5094eb0aab28edeb06790a9af4019c6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714729"
---
# <a name="polymorphism-c-programming-guide"></a>Polimorfismo (Guía de programación de C#)
El polimorfismo suele considerarse el tercer pilar de la programación orientada a objetos, después de la encapsulación y la herencia. Polimorfismo es una palabra griega que significa "con muchas formas" y tiene dos aspectos diferentes:  
  
- En tiempo de ejecución, los objetos de una clase derivada pueden ser tratados como objetos de una clase base en lugares como parámetros de métodos y colecciones o matrices. Cuando ocurre, el tipo declarado del objeto ya no es idéntico a su tipo en tiempo de ejecución.  
  
- Las clases base pueden definir e implementar *métodos* [virtuales](../../language-reference/keywords/virtual.md), y las clases derivadas pueden [invalidarlos](../../language-reference/keywords/override.md), lo que significa que pueden proporcionar su propia definición e implementación. En tiempo de ejecución, cuando el código de cliente llama al método, CLR busca el tipo en tiempo de ejecución del objeto e invoca esa invalidación del método virtual. Por lo tanto, en el código fuente puede llamar a un método en una clase base y hacer que se ejecute una versión del método de la clase derivada.  
  
 Los métodos virtuales permiten trabajar con grupos de objetos relacionados de manera uniforme. Por ejemplo, supongamos que tiene una aplicación de dibujo que permite a un usuario crear varios tipos de formas en una superficie de dibujo. En tiempo de compilación, no sabe qué tipos específicos de formas creará el usuario. Sin embargo, la aplicación tiene que realizar el seguimiento de los distintos tipos de formas que se crean, y tiene que actualizarlos en respuesta a las acciones del mouse del usuario. Para solucionar este problema en dos pasos básicos, puede usar el polimorfismo:  
  
1. Crear una jerarquía de clases en la que cada clase de forma específica deriva de una clase base común.  
  
2. Usar un método virtual para invocar el método apropiado en una clase derivada mediante una sola llamada al método de la clase base.  
  
 Primero, cree una clase base llamada `Shape` y clases derivadas como `Rectangle`, `Circle` y `Triangle`. Dé a la clase `Shape` un método virtual llamado `Draw` e invalídelo en cada clase derivada para dibujar la forma determinada que la clase representa. Cree un objeto `List<Shape>` y agregue Circle, Triangle y Rectangle a él. Para actualizar la superficie de dibujo, use un bucle [foreach](../../language-reference/keywords/foreach-in.md) para iterar por la lista y llamar al método `Draw` en cada objeto `Shape` de la lista. Aunque cada objeto de la lista tenga un tipo declarado de `Shape`, se invocará el tipo en tiempo de ejecución (la versión invalidada del método en cada clase derivada).  
  
 [!code-csharp[csProgGuideInheritance#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#50)]  
  
 En C#, cada tipo es polimórfico porque todos los tipos, incluidos los definidos por el usuario, heredan de <xref:System.Object>.  
  
## <a name="polymorphism-overview"></a>Introducción al polimorfismo  
  
### <a name="virtual-members"></a>Miembros virtuales  
 Cuando una clase derivada hereda de una clase base, obtiene todos los métodos, campos, propiedades y eventos de la clase base. El diseñador de la clase derivada tiene las siguientes opciones:  
  
- Invalidar los miembros virtuales de la clase base.  
  
- Heredar el método de la clase base más próximo sin invalidarlo.  
  
- Definir una nueva implementación no virtual de esos miembros que oculte las implementaciones de la clase base.  
  
 Una clase derivada puede invalidar un miembro de la clase base si este se declara como [virtual](../../language-reference/keywords/virtual.md) o [abstracto](../../language-reference/keywords/abstract.md). El miembro derivado debe usar la palabra clave [override](../../language-reference/keywords/override.md) para indicar explícitamente que el propósito del método es participar en una invocación virtual. El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#20)]  
  
 Los campos no pueden ser virtuales; solo los métodos, propiedades, eventos e indizadores pueden ser virtuales. Cuando una clase derivada invalida un miembro virtual, se llama a ese miembro aunque se acceda a una instancia de esa clase como una instancia de la clase base. El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#21)]  
  
 Los métodos y propiedades virtuales permiten a las clases derivadas extender una clase base sin necesidad de usar la implementación de clase base de un método. Para obtener más información, consulte [Control de versiones con las palabras clave Override y New](./versioning-with-the-override-and-new-keywords.md). Una interfaz proporciona otra manera de definir un método o conjunto de métodos cuya implementación se deja a las clases derivadas. Para más información, vea [Interfaces](../interfaces/index.md).  
  
### <a name="hiding-base-class-members-with-new-members"></a>Ocultar miembros de clase base con nuevos miembros  
 Si quiere que el miembro derivado tenga el mismo nombre que un miembro de una clase base, pero no quiere que participe en la invocación virtual, puede usar la palabra clave [new](../../language-reference/keywords/new-modifier.md). La palabra clave `new` se coloca antes que el tipo devuelto del miembro de la clase que se está reemplazando. El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#18)]  
  
 Aún se puede acceder a los miembros de la clase base ocultos desde el código de cliente convirtiendo la instancia de la clase derivada en una instancia de la clase base. Por ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#19)]  
  
### <a name="preventing-derived-classes-from-overriding-virtual-members"></a>Evitar que las clases derivadas invaliden los miembros virtuales  
 Los miembros virtuales permanecen virtuales indefinidamente, independientemente de cuántas clases se hayan declarado entre el miembro virtual y la clase que originalmente la declaró. Si la clase A declara un miembro virtual y la clase B deriva de A, y la clase C deriva de B, la clase C hereda el miembro virtual y tiene la opción de invalidarlo, independientemente de que la clase B declarara una invalidación para ese miembro. El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#22)]  
  
 Una clase derivada puede detener la herencia virtual al declarar una invalidación como [sealed](../../language-reference/keywords/sealed.md). Para ello, es necesario colocar la palabra clave `sealed` antes de la palabra clave `override` en la declaración del miembro de la clase. El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#24)]  
  
 En el ejemplo anterior, el método `DoWork` ya no es virtual para ninguna clase que derive de C. Sigue siendo virtual para instancias de C, aunque se conviertan al tipo B o A. Los métodos sellados pueden reemplazarse por las clases derivadas al usar la palabra clave `new`, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideInheritance#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#25)]  
  
 En este caso, si se llama a `DoWork` en D usando una variable de tipo D, se llama al nuevo `DoWork`. Si se usa una variable de tipo C, B o A para acceder a una instancia de D, la llamada a `DoWork` seguirá las reglas de herencia virtual y enrutará dichas llamadas a la implementación de `DoWork` en la clase C.  
  
### <a name="accessing-base-class-virtual-members-from-derived-classes"></a>Acceder a miembros virtuales de clases base desde clases derivadas  
 Una clase derivada que ha reemplazado o invalidado un método o propiedad puede seguir accediendo al método o propiedad en la clase base usando la siguiente palabra clave `base`. El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#26)]  
  
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
