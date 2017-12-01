---
title: "Clases (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
caps.latest.revision: "40"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 37e810fc5a5397a6b9240346ac28505b11b1e817
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="classes-c-programming-guide"></a>Clases (Guía de programación de C#)
Una *class* es una construcción que le permite crear sus propios tipos personalizados agrupando las variables de otros tipos, métodos y eventos. Una clase es como un plano. Define los datos y el comportamiento de un tipo. Si la clase no se declara como estática, el código de cliente puede usarla mediante la creación de *objetos* o *instancias* que se asignan a una variable. La variable permanece en memoria hasta que todas las referencias a ella están fuera del ámbito. En ese momento, CLR la marca como apta para la recolección de elementos no utilizados. Si la clase se declara como [estática](../../../csharp/language-reference/keywords/static.md), solo habrá una copia en la memoria y el código de cliente solo podrá tener acceso a ella a través de la propia clase, y no a través de una *variable de instancia*. Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 A diferencia de los structs, las clases admiten la *herencia*, una característica fundamental de la programación orientada a objetos. Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
## <a name="declaring-classes"></a>Declarar clases  
 Las clases se declaran mediante la palabra clave [class](../../../csharp/language-reference/keywords/class.md), como se muestra en el siguiente ejemplo:  
  
 [!code-csharp[csProgGuideObjects#79](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_1.cs)]  
  
 La palabra clave `class` va precedida del nivel de acceso. Como en este caso se usa [public](../../../csharp/language-reference/keywords/public.md), cualquier usuario puede crear objetos de esta clase. El nombre de la clase sigue a la palabra clave `class`. El resto de la definición es el cuerpo de la clase, donde se definen los datos y el comportamiento. Los campos, las propiedades, los métodos y los eventos de una clase se denominan de forma colectiva *miembros de clase*.  
  
## <a name="creating-objects"></a>Crear objetos  
 Aunque a veces se usan indistintamente, una clase y un objeto son cosas diferentes. Una clase define un tipo de objeto, pero no es un objeto en sí. Un objeto es una entidad concreta basada en una clase y, a veces, se conoce como una instancia de una clase.  
  
 Los objetos se pueden crear usando la palabra clave [new](../../../csharp/language-reference/keywords/new.md), seguida del nombre de la clase en la que se basará el objeto, como en este ejemplo:  
  
 [!code-csharp[csProgGuideObjects#80](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_2.cs)]  
  
 Cuando se crea una instancia de una clase, se vuelve a pasar al programador una referencia al objeto. En el ejemplo anterior, `object1` es una referencia a un objeto que se basa en `Customer`. Esta referencia apunta al objeto nuevo, pero no contiene los datos del objeto. De hecho, puede crear una referencia de objeto sin tener que crear ningún objeto:  
  
 [!code-csharp[csProgGuideObjects#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_3.cs)]  
  
 No se recomienda crear referencias de objeto como esta, que no hace referencia a ningún objeto, ya que, si se intenta obtener acceso a un objeto a través de este tipo de referencia, se producirá un error en tiempo de ejecución. Pero dicha referencia puede haberse creado para hacer referencia a un objeto, ya sea creando un nuevo objeto o asignándola a un objeto existente, como en el siguiente ejemplo:  
  
 [!code-csharp[csProgGuideObjects#82](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_4.cs)]  
  
 Este código crea dos referencias de objeto que hacen referencia al mismo objeto. Por lo tanto, los cambios efectuados en el objeto mediante `object3` se reflejarán en los usos posteriores de `object4`. Dado que los objetos basados en clases se tratan por referencia, las clases se denominan "tipos de referencia".  
  
## <a name="class-inheritance"></a>Herencia de clases  
 La herencia se consigue mediante una *derivación*, en la que se declara una clase mediante una *clase base*, desde la que hereda los datos y el comportamiento. Una clase base se especifica anexando dos puntos y el nombre de la clase base seguido del nombre de la clase derivada, como en el siguiente ejemplo:  
  
 [!code-csharp[csProgGuideObjects#83](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_5.cs)]  
  
 Cuando una clase declara una clase base, hereda todos los miembros de la clase base excepto los constructores.  
  
 A diferencia de C++, una clase de C# solo puede heredar directamente de una clase base. En cambio, dado que una clase base puede heredar de otra clase, una clase podría heredar indirectamente varias clases base. Además, una clase puede implementar directamente más de una interfaz. Para obtener más información, vea [Interfaces](../../../csharp/programming-guide/interfaces/index.md).  
  
 Una clase puede declararse [abstracta](../../../csharp/language-reference/keywords/abstract.md). Una clase abstracta contiene métodos abstractos que tienen una definición de firma, pero no tienen ninguna implementación. No se pueden crear instancias de las clases abstractas. Solo se pueden usar a través de las clases derivadas que implementan los métodos abstractos. Por el contrario, la clase [sealed](../../../csharp/language-reference/keywords/sealed.md) no permite que otras clases se deriven de ella. Para más información, vea [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Las definiciones de clase se pueden dividir entre distintos archivos de código fuente. Para obtener más información, consulte [Clases y métodos parciales](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## <a name="description"></a>Descripción  
 En el ejemplo siguiente se define una clase pública que contiene un solo campo, un método y un método especial denominado "constructor". Para obtener más información, vea [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md). Luego, se crea una instancia de la clase con la palabra clave `new`.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideObjects#84](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_6.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Programación orientada a objetos](../concepts/object-oriented-programming.md)  
 [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [Miembros](../../../csharp/programming-guide/classes-and-structs/members.md)  
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [Objects](../../../csharp/programming-guide/classes-and-structs/objects.md)
