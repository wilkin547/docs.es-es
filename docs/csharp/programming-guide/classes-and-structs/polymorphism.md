---
title: "Polimorfismo (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, polimorfismo"
  - "polimorfismo [C#]"
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# Polimorfismo (Gu&#237;a de programaci&#243;n de C#)
El polimorfismo suele considerarse el tercer pilar de la programación orientada a objetos, después de la encapsulación y la herencia.  Polimorfismo es una palabra griega que significa "con muchas formas" y tiene dos aspectos diferentes:  
  
-   En tiempo de ejecución, los objetos de una clase derivada pueden ser tratados como objetos de una clase base en lugares como parámetros de métodos y colecciones o matrices.  Cuando ocurre, el tipo declarado del objeto ya no es idéntico a su tipo en tiempo de ejecución.  
  
-   Las clases base pueden definir e implementar *métodos* [virtuales](../../../csharp/language-reference/keywords/virtual.md), y las clases derivadas pueden [invalidarlos](../../../csharp/language-reference/keywords/override.md), lo que significa que pueden proporcionar su propia definición e implementación.  En tiempo de ejecución, cuando el código de cliente llama al método, CLR busca el tipo en tiempo de ejecución del objeto e invoca esa invalidación del método virtual.  Por lo tanto, en el código fuente puede llamar a un método en una clase base y hacer que se ejecute una versión del método de la clase derivada.  
  
 Los métodos virtuales permiten trabajar con grupos de objetos relacionados de manera uniforme.  Por ejemplo, supongamos que tiene una aplicación de dibujo que permite a un usuario crear varios tipos de formas en una superficie de dibujo.  En tiempo de compilación, no sabe qué tipos específicos de formas creará el usuario.  Sin embargo, la aplicación tiene que realizar el seguimiento de los distintos tipos de formas que se crean, y tiene que actualizarlos en respuesta a las acciones del mouse del usuario.  Para solucionar este problema en dos pasos básicos, puede usar el polimorfismo:  
  
1.  Crear una jerarquía de clases en la que cada clase de forma específica deriva de una clase base común.  
  
2.  Usar un método virtual para invocar el método apropiado en una clase derivada mediante una sola llamada al método de la clase base.  
  
 Primero, cree una clase base llamada `Shape` y clases derivadas como `Rectangle`, `Circle` y `Triangle`.  Dé a la clase `Shape` un método virtual llamado `Draw` e invalídelo en cada clase derivada para dibujar la forma determinada que la clase representa.  Cree un objeto `List<Shape>` y agregue Circle, Triangle y Rectangle a él.  Para actualizar la superficie de dibujo, use un bucle [foreach](../../../csharp/language-reference/keywords/foreach-in.md) para iterar por la lista y llamar al método `Draw` en cada objeto `Shape` de la lista.  Aunque cada objeto de la lista tenga un tipo declarado de `Shape`, se invocará el tipo en tiempo de ejecución \(la versión invalidada del método en cada clase derivada\).  
  
 [!code-cs[csProgGuideInheritance#50](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/polymorphism_1.cs)]  
  
 En C\#, cada tipo es polimórfico porque todos los tipos, incluidos los definidos por el usuario, heredan de <xref:System.Object>.  
  
## Introducción al polimorfismo  
  
### Miembros virtuales  
 Cuando una clase derivada hereda de una clase base, obtiene todos los métodos, campos, propiedades y eventos de la clase base.  El diseñador de la clase derivada tiene las siguientes opciones:  
  
-   Invalidar los miembros virtuales de la clase base.  
  
-   Heredar el método de la clase base más próximo sin invalidarlo.  
  
-   Definir una nueva implementación no virtual de esos miembros que oculte las implementaciones de la clase base.  
  
 Una clase derivada puede invalidar un miembro de la clase base si este se declara como [virtual](../../../csharp/language-reference/keywords/virtual.md) o [abstracto](../../../csharp/language-reference/keywords/abstract.md).  El miembro derivado debe usar la palabra clave [override](../../../csharp/language-reference/keywords/override.md) para indicar explícitamente que el propósito del método es participar en una invocación virtual.  El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-cs[csProgGuideInheritance#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/polymorphism_2.cs)]  
  
 Los campos no pueden ser virtuales; solo los métodos, propiedades, eventos e indizadores pueden ser virtuales.  Cuando una clase derivada invalida un miembro virtual, se llama a ese miembro aunque se acceda a una instancia de esa clase como una instancia de la clase base.  El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-cs[csProgGuideInheritance#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/polymorphism_3.cs)]  
  
 Los métodos y propiedades virtuales permiten a las clases derivadas extender una clase base sin necesidad de usar la implementación de clase base de un método.  Para obtener más información, vea [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md).  Una interfaz proporciona otra manera de definir un método o conjunto de métodos cuya implementación se deja a las clases derivadas.  Para obtener más información, vea [Interfaces](../../../csharp/programming-guide/interfaces/index.md).  
  
### Ocultar miembros de clase base con nuevos miembros  
 Si quiere que el miembro derivado tenga el mismo nombre que un miembro de una clase base, pero no quiere que participe en la invocación virtual, puede usar la palabra clave [new](../../../csharp/language-reference/keywords/new.md).  La palabra clave `new` se coloca antes que el tipo devuelto del miembro de la clase que se está reemplazando.  El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-cs[csProgGuideInheritance#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/polymorphism_4.cs)]  
  
 Aún se puede acceder a los miembros de la clase base ocultos desde el código de cliente convirtiendo la instancia de la clase derivada en una instancia de la clase base.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/polymorphism_5.cs)]  
  
### Evitar que las clases derivadas invaliden los miembros virtuales  
 Los miembros virtuales permanecen virtuales indefinidamente, independientemente de cuántas clases se hayan declarado entre el miembro virtual y la clase que originalmente la declaró.  Si la clase A declara un miembro virtual y la clase B deriva de A, y la clase C deriva de B, la clase C hereda el miembro virtual y tiene la opción de invalidarlo, independientemente de que la clase B declarara una invalidación para ese miembro.  El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-cs[csProgGuideInheritance#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/polymorphism_6.cs)]  
  
 Una clase derivada puede detener la herencia virtual declarando una invalidación como [sealed](../../../csharp/language-reference/keywords/sealed.md).  Para ello, es necesario colocar la palabra clave `sealed` antes de la palabra clave `override` en la declaración del miembro de la clase.  El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-cs[csProgGuideInheritance#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/polymorphism_7.cs)]  
  
 En el ejemplo anterior, el método `DoWork` ya no es virtual para ninguna clase que derive de C.  Sigue siendo virtual para las instancias de C, aunque se conviertan al tipo B o al tipo A.  Los métodos sellados se pueden reemplazar por clases derivadas usando la palabra clave `new`, como muestra el ejemplo siguiente:  
  
 [!code-cs[csProgGuideInheritance#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/polymorphism_8.cs)]  
  
 En este caso, si se llama a `DoWork` en D usando una variable de tipo D, se llama al nuevo `DoWork`.  Si se usa una variable de tipo C, B o A para acceder a una instancia de D, la llamada a `DoWork` seguirá las reglas de herencia virtual y enrutará dichas llamadas a la implementación de `DoWork` en la clase C.  
  
### Acceder a miembros virtuales de clases base desde clases derivadas  
 Una clase derivada que ha reemplazado o invalidado un método o propiedad puede seguir accediendo al método o propiedad en la clase base usando la siguiente palabra clave base.  El siguiente fragmento de código muestra un ejemplo:  
  
 [!code-cs[csProgGuideInheritance#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/polymorphism_9.cs)]  
  
 Para obtener más información, vea [base](../../../csharp/language-reference/keywords/base.md).  
  
> [!NOTE]
>  Se recomienda que las máquinas virtuales usen `base` para llamar a la implementación de la clase base de ese miembro en su propia implementación.  Dejar que se produzca el comportamiento de la clase base permite a la clase derivada concentrarse en implementar el comportamiento específico de la clase derivada.  Si no se llama a la implementación de la clase base, depende de la clase derivada hacer que su comportamiento sea compatible con el de la clase base.  
  
## En esta sección  
  
-   [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)  
  
-   [Saber cuándo utilizar las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)  
  
-   [Cómo: Invalidar el método ToString](../../../csharp/programming-guide/classes-and-structs/how-to-override-the-tostring-method.md)  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)   
 [Tipos](../../../csharp/programming-guide/types/index.md)