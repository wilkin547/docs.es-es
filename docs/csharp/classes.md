---
title: "Clases: Guía de C#"
description: "Obtenga información sobre los tipos de clases y cómo crearlas"
keywords: .NET, .NET Core, C#
author: BillWagner
ms.author: wiwagn
ms.date: 10/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 95c686ba-ae4f-440e-8e94-0dbd6e04d11f
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cb43cdbc23dc15b45fe117927fb57867af58c306
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="classes"></a>Clases
Una *clase* es una construcción que le permite crear tipos personalizados propios mediante la agrupación de variables de otros tipos, métodos y eventos. Una clase es como un plano. Define los datos y el comportamiento de un tipo. Si la clase no se declara como estática, el código de cliente puede usarla mediante la creación de *objetos* o *instancias* que se asignan a una variable. La variable permanece en memoria hasta que todas las referencias a ella están fuera del ámbito. En ese momento, CLR la marca como apta para la recolección de elementos no utilizados. Si la clase se declara como [estática](https://msdn.microsoft.com/library/98f28cdx.aspx), solo existe una copia en memoria y el código de cliente solo puede tener acceso a ella a través de la propia clase y no de una *variable de instancia*. Para obtener más información, vea [Clases estáticas y sus miembros](https://msdn.microsoft.com/library/79b3xss3.aspx).  

## <a name="reference-types"></a>Tipos de referencia  
Un tipo que se define como una [clase](https://msdn.microsoft.com/library/0b0thckt.aspx), es un *tipo de referencia*. Al declarar una variable de un tipo de referencia en tiempo de ejecución, la variable contiene el valor [NULL](https://msdn.microsoft.com/library/edakx9da.aspx) hasta que se crea explícitamente una instancia del objeto mediante el operador [new](https://msdn.microsoft.com/library/51y09td4.aspx) o se le asigna un objeto creado en otro lugar mediante [new](https://msdn.microsoft.com/library/51y09td4.aspx), como se muestra en el ejemplo siguiente:  

[!code-csharp[Tipos de referencia](../../samples/snippets/csharp/concepts/classes/reference-type.cs)]
  
Cuando se crea el objeto, se asigna la memoria en el montón administrado y la variable solo contiene una referencia a la ubicación del objeto. Los tipos del montón administrado producen sobrecarga cuando se asignan y cuando los reclama la función de administración de memoria automática de CLR, conocida como *recolección de elementos no utilizados*. En cambio, la recolección de elementos no utilizados también está muy optimizada y no crea problemas de rendimiento en la mayoría de los escenarios. Para obtener más información sobre la recolección de elementos no utilizados, vea [Administración automática de la memoria y recolección de elementos no utilizados](../standard/garbage-collection/gc.md).  
  
Los tipos de referencia admiten completamente la *herencia*, una característica fundamental de la programación orientada a objetos. Al crear una clase, puede heredar de cualquier otra interfaz o clase que no esté definida como [sealed](https://msdn.microsoft.com/library/88c54tsw.aspx); y otras clases pueden heredar de la clase e invalidar sus métodos virtuales. Para obtener más información, vea [Herencia](https://msdn.microsoft.com/library/ms173149.aspx).

## <a name="declaring-classes"></a>Declarar clases  
Las clases se declaran mediante la palabra clave [class](https://msdn.microsoft.com/library/0b0thckt.aspx), como se muestra en el siguiente ejemplo:  
  
[!code-csharp[Declarar clases](../../samples/snippets/csharp/concepts/classes/declaring-classes.cs)]  
  
La palabra clave **class** va precedida del modificador de acceso. Como en este caso se usa [public](https://msdn.microsoft.com/library/yzh058ae.aspx), cualquier usuario puede crear objetos de esta clase. El nombre de la clase sigue a la palabra clave **class**. El resto de la definición es el cuerpo de la clase, donde se definen los datos y el comportamiento. Los campos, las propiedades, los métodos y los eventos de una clase se denominan de manera colectiva *miembros de clase*.  
  
## <a name="creating-objects"></a>Creación de objetos  
Una clase define un tipo de objeto, pero no es un objeto en sí. Un objeto es una entidad concreta basada en una clase y, a veces, se conoce como una instancia de una clase.  
  
Los objetos se pueden crear usando la palabra clave [new](https://msdn.microsoft.com/library/51y09td4.aspx), seguida del nombre de la clase en la que se basará el objeto, como en este ejemplo:  
  
[!code-csharp[Creación de objetos](../../samples/snippets/csharp/concepts/classes/creating-objects.cs)]   
  
Cuando se crea una instancia de una clase, se vuelve a pasar al programador una referencia al objeto. En el ejemplo anterior, `object1` es una referencia a un objeto que se basa en `Customer`. Esta referencia apunta al objeto nuevo, pero no contiene los datos del objeto. De hecho, puede crear una referencia de objeto sin tener que crear ningún objeto:  
  
[!code-csharp[Creación de objetos](../../samples/snippets/csharp/concepts/classes/creating-objects2.cs)]  
  
No se recomienda crear referencias de objeto como esta, que no hace referencia a ningún objeto, ya que, si se intenta obtener acceso a un objeto a través de este tipo de referencia, se producirá un error en tiempo de ejecución. Pero dicha referencia puede haberse creado para hacer referencia a un objeto, ya sea creando un nuevo objeto o asignándola a un objeto existente, como en el siguiente ejemplo:  
  
[!code-csharp[Creación de objetos](../../samples/snippets/csharp/concepts/classes/creating-objects3.cs)]  
  
Este código crea dos referencias de objeto que hacen referencia al mismo objeto. Por lo tanto, los cambios efectuados en el objeto mediante `object3` se reflejarán en los usos posteriores de `object4`. Dado que los objetos basados en clases se tratan por referencia, las clases se denominan tipos de referencia.  
  
## <a name="class-inheritance"></a>Herencia de clases  
La herencia se consigue mediante una *derivación*, en la que se declara una clase mediante una *clase base*, desde la que hereda los datos y el comportamiento. Una clase base se especifica anexando dos puntos y el nombre de la clase base seguido del nombre de la clase derivada, como en el siguiente ejemplo:  
  
[!code-csharp[Herencia](../../samples/snippets/csharp/concepts/classes/inheritance.cs)]  
  
Cuando una clase declara una clase base, hereda todos los miembros de la clase base excepto los constructores.  
  
A diferencia de C++, una clase de C# solo puede heredar directamente de una clase base. En cambio, dado que una clase base puede heredar de otra clase, una clase podría heredar indirectamente varias clases base. Además, una clase puede implementar directamente más de una interfaz. Para obtener más información, vea [Interfaces](programming-guide/interfaces/index.md).  
  
Una clase puede declararse [abstracta](https://msdn.microsoft.com/library/sf985hc5.aspx). Una clase abstracta contiene métodos abstractos que tienen una definición de firma, pero no tienen ninguna implementación. No se pueden crear instancias de las clases abstractas. Solo se pueden usar a través de las clases derivadas que implementan los métodos abstractos. Por el contrario, la clase [sealed](https://msdn.microsoft.com/library/88c54tsw.aspx) no permite que otras clases se deriven de ella. Para obtener más información, vea [Clases y miembros de clase abstractos y sellados](https://msdn.microsoft.com/library/ms173150.aspx).  
  
Las definiciones de clase se pueden dividir entre distintos archivos de código fuente. Para obtener más información, vea [Clases y métodos parciales](https://msdn.microsoft.com/library/wa80x488.aspx).  
  
 
## <a name="example"></a>Ejemplo
En el ejemplo siguiente se define una clase pública que contiene un solo campo, un método y un método especial denominado constructor. Para obtener más información, vea [Constructores](https://msdn.microsoft.com/library/ace5hbzh.aspx). Después, se crea una instancia de la clase con la palabra clave **new**.

[!code-csharp[Ejemplo de clase](../../samples/snippets/csharp/concepts/classes/class-example.cs)]  
  
## <a name="c-language-specification"></a>especificación del lenguaje C#  
Para obtener más información, vea la [Especificación del lenguaje C#](https://msdn.microsoft.com/library/ms228593.aspx). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también  
[Guía de programación de C#](https://msdn.microsoft.com/library/67ef8sbd.aspx)   
[Polimorfismo](https://msdn.microsoft.com/library/ms173152.aspx)   
[Miembros](https://msdn.microsoft.com/library/ms173113.aspx)   
[Métodos](https://msdn.microsoft.com/library/ms173114.aspx)   
[Constructors](https://msdn.microsoft.com/library/ace5hbzh.aspx)  (Constructores [Guía de programación de C#])  
[Finalizadores](https://msdn.microsoft.com/library/66x5fx1b.aspx)   
[Objects](https://msdn.microsoft.com/library/ms173110.aspx)


