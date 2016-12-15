---
title: "Clases (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "clases [C#]"
  - "lenguaje C#, clases"
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
caps.latest.revision: 40
caps.handback.revision: 40
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Clases (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una *clase* es una construcción que permite crear tipos personalizados propios mediante la agrupación de variables de otros tipos, métodos y eventos.  Una clase es como un plano.  Define los datos y el comportamiento de un tipo.  Si la clase no se declara como estática, el código de cliente puede utilizarla mediante la creación de *objetos* o *instancias* que se asignan a una variable.  La variable permanece en memoria hasta todas las referencias a ella están fuera del ámbito.  En ese momento, CLR la marca como apta para la recolección de elementos no utilizados.  Si la clase se declara como [estática](../../../csharp/language-reference/keywords/static.md), solo existe una copia en memoria y el código de cliente solo puede tener acceso a ella a través de la propia clase y no de una *variable de instancia*.  Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 A diferencia de los structs, las clases admiten la *herencia*, una característica fundamental de la programación orientada a objetos.  Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
## Declarar clases  
 Las clases se declaran mediante la palabra clave [class](../../../csharp/language-reference/keywords/class.md), tal como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideObjects#79](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_1.cs)]  
  
 El nivel de acceso precede a la palabra clave `class`.  Como, en este caso, se utiliza [public](../../../csharp/language-reference/keywords/public.md), cualquiera puede crear objetos a partir de esta clase.  El nombre de la clase sigue a la palabra clave `class`.  El resto de la definición es el cuerpo de clase, donde se definen el comportamiento y los datos.  Los campos, propiedades, métodos y eventos de una clase se conocen colectivamente como *miembros de clase*.  
  
## Crear objetos  
 Aunque se utilizan a veces de forma intercambiable, una clase y un objeto son cosas diferentes.  Una clase define un tipo de objeto, pero no es propiamente un objeto.  Un objeto es una entidad concreta basada en una clase y, a veces, se denomina instancia de una clase.  
  
 Los objetos se pueden crear con la palabra clave [new](../../../csharp/language-reference/keywords/new.md) seguida del nombre de la clase en la que se basará el objeto, de la manera siguiente:  
  
 [!code-cs[csProgGuideObjects#80](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_2.cs)]  
  
 Cuando se crea una instancia de una clase, una referencia al objeto se vuelve a pasar al programador.  En el ejemplo anterior, `object1` es una referencia a un objeto basado en `Customer`.  Esta referencia apunta al nuevo objeto, pero no contiene los datos del objeto.  De hecho, se puede crear una referencia a objeto sin crear un objeto:  
  
 [!code-cs[csProgGuideObjects#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_3.cs)]  
  
 No se recomienda crear este tipo de referencias que realmente no apuntan a un objeto existente, ya que al intentar el acceso a un objeto a través de esa referencia se producirá un error en tiempo de ejecución.  No obstante, este tipo de referencia se puede crear para hacer referencia a un objeto, ya sea creando un nuevo objeto o asignándola a un objeto existente, de la forma siguiente:  
  
 [!code-cs[csProgGuideObjects#82](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_4.cs)]  
  
 Este código crea dos referencias a objeto que se refieren al mismo objeto.  Por consiguiente, los cambios realizados en el objeto a través de `object3` se reflejarán en los usos posteriores de `object4`.  Puesto que el acceso a los objetos basados en clases se realiza por referencia, las clases se denominan tipos por referencia.  
  
## Herencia de clase  
 La herencia se realiza a través de una *derivación*, lo que significa que una clase se declara utilizando una *clase base* de la cual hereda los datos y el comportamiento.  Una clase base se especifica anexando dos puntos y el nombre de la clase base a continuación del nombre de la clase derivada, del modo siguiente:  
  
 [!code-cs[csProgGuideObjects#83](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_5.cs)]  
  
 Cuando una clase declara una clase base, hereda todos los miembros de la clase base excepto los constructores.  
  
 A diferencia de C\+\+, una clase en C\# solo puede heredar directamente de una clase base.  Sin embargo, dado que una clase base puede heredar de otra clase, una clase puede heredar indirectamente de varias clases base.  Además, una clase puede implementar directamente más de una interfaz.  Para obtener más información, vea [Interfaces](../../../csharp/programming-guide/interfaces/index.md).  
  
 Una clase se puede declarar como [abstracta](../../../csharp/language-reference/keywords/abstract.md).  Una clase abstracta contiene métodos abstractos que incluyen una definición de firma pero ninguna implementación.  No se pueden crear instancias de las clases abstractas.  Solo se pueden utilizar a través de clases derivadas que implementan los métodos abstractos.  Por el contrario, una clase [sellada](../../../csharp/language-reference/keywords/sealed.md) no permite que otras clases deriven de ella.  Para obtener más información, vea [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Las definiciones de clase se pueden dividir entre archivos de código fuente diferentes.  Para obtener más información, vea [Clases y métodos parciales](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## Descripción  
 En el ejemplo siguiente, se define una clase pública que contiene un campo único, un método y un método especial denominado constructor.  Para obtener más información, vea [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md).  Luego se crean instancias de la clase con la palabra clave `new`.  
  
## Ejemplo  
 [!code-cs[csProgGuideObjects#84](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_6.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Programación orientada a objetos](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)   
 [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)   
 [Miembros](../../../csharp/programming-guide/classes-and-structs/members.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [Objetos](../../../csharp/programming-guide/classes-and-structs/objects.md)