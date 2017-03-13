---
title: "Clases y miembros de clase abstractos y sellados (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "clases abstractas [C#]"
  - "clases selladas [C#]"
  - "lenguaje C#, clases abstractas"
  - "lenguaje C#, sellado"
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Clases y miembros de clase abstractos y sellados (Gu&#237;a de programaci&#243;n de C#)
La palabra clave [abstract](../../../csharp/language-reference/keywords/abstract.md) permite crear clases y miembros de [clase](../../../csharp/language-reference/keywords/class.md) que están incompletos y se deben implementar en una clase derivada.  
  
 La palabra clave [sealed](../../../csharp/language-reference/keywords/sealed.md) permite impedir la herencia de una clase o de ciertos miembros de clase marcados previamente como [virtuales](../../../csharp/language-reference/keywords/virtual.md).  
  
## Clases y miembros de clase abstractos  
 Las clases se pueden declarar como abstractas si se incluye la palabra clave `abstract` antes de la definición de clase.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]  
  
 No se pueden crear instancias de una clase abstracta.  El propósito de una clase abstracta es proporcionar una definición común de una clase base que múltiples clases derivadas pueden compartir.  Por ejemplo, una biblioteca de clases puede definir una clase abstracta que se utiliza como parámetro para muchas de sus funciones y solicitar a los programadores que utilizan esa biblioteca que proporcionen su propia implementación de la clase mediante la creación de una clase derivada.  
  
 Las clases abstractas también pueden definir métodos abstractos.  Esto se consigue agregando la palabra clave `abstract` antes del tipo de valor que devuelve el método.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]  
  
 Los métodos abstractos no tienen ninguna implementación, de modo que la definición de método va seguida por un punto y coma en lugar de un bloque de método normal.  Las clases derivadas de la clase abstracta deben implementar todos los métodos abstractos.  Cuando una clase abstracta hereda un método virtual de una clase base, la clase abstracta puede reemplazar el método virtual con un método abstracto.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]  
  
 Si un método `virtual` se declara como `abstract`, sigue siendo virtual para cualquier clase que herede de la clase abstracta.  Una clase que hereda un método abstracto no puede tener acceso a la implementación original del método; en el ejemplo anterior, `DoWork` de la clase F no puede llamar a `DoWork` de la clase D.  De esta forma, una clase abstracta puede obligar a las clases derivadas a proporcionar nuevas implementaciones de método para los métodos virtuales.  
  
## Clases y miembros de clase sellados  
 Las clases se pueden declarar como [selladas](../../../csharp/language-reference/keywords/sealed.md) si se incluye la palabra clave `sealed` antes de la definición de clase.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]  
  
 Una clase sellada no se puede utilizar como clase base.  Por esta razón, tampoco puede ser una clase abstracta.  Las clases selladas evitan la derivación.  Puesto que nunca se pueden utilizar como clase base, algunas optimizaciones en tiempo de ejecución pueden hacer que sea un poco más rápido llamar a miembros de clase sellada.  
  
 Un método, indizador, propiedad o evento de una clase derivada que reemplaza a un miembro virtual de la clase base puede declarar ese miembro como sellado.  Esto niega el aspecto virtual del miembro para cualquier clase derivada adicional.  Esto se logra colocando la palabra clave `sealed` antes de la palabra clave [override](../../../csharp/language-reference/keywords/override.md) en la declaración del miembro de clase.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)   
 [Cómo: Definir propiedades abstractas](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)