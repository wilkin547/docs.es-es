---
title: "Clases gen&#233;ricas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, clases genéricas"
  - "genéricos [C#], clases"
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Clases gen&#233;ricas (Gu&#237;a de programaci&#243;n de C#)
Las clases genéricas encapsulan operaciones que no son específicas de un tipo de datos concreto.  Las clases genéricas se utilizan frecuentemente con colecciones como listas vinculadas, tablas hash, pilas, colas, árboles, etc.  Las operaciones de agregar y quitar elementos de la colección se realizan básicamente de la misma forma, independientemente del tipo de datos que se van a almacenar.  
  
 En la mayoría de los escenarios que necesitan clases de colección, el enfoque recomendado es utilizar las que proporciona la biblioteca de clases de .NET Framework.  Para obtener más información sobre el uso de estas clases, vea [Tipos genéricos en la biblioteca de clases de .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).  
  
 Normalmente, para crear clases genéricas se empieza a partir de una clase concreta existente y se cambian los tipos, uno a uno, por parámetros de tipo hasta que se obtiene un equilibrio óptimo entre generalización y utilidad.  Al crear sus propias clases genéricas, debe tener en cuenta las siguientes consideraciones importantes:  
  
-   Tipos que se generalizan como parámetros de tipo.  
  
     Como regla general, cuantos más tipos se puedan parametrizar, más flexible y reutilizable será el código.  Sin embargo, un exceso de generalización puede producir código difícil de leer o comprender para otros programadores.  
  
-   Restricciones, en su caso, que se aplicarán a los parámetros de tipo \(Vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)\).  
  
     Una buena regla consiste en aplicar el mayor número de restricciones posible que siga permitiendo manejar los tipos que se deben utilizar.  Por ejemplo, si sabe que la clase genérica está exclusivamente destinada al uso con tipos de referencia, aplique la restricción de clase.  Esto evitará el uso imprevisto de la clase con tipos de valor y permitirá utilizar el operador `as` en `T` y comprobar si hay valores nulos.  
  
-   Factorizar o no el comportamiento genérico en las clases base y las subclases.  
  
     Dado que las clases genéricas pueden actuar como clases base, se aplican las mismas consideraciones de diseño que con las clases no genéricas.  Vea las reglas sobre cómo heredar de las clases base genéricas más adelante en este tema.  
  
-   Implementar o no una o varias interfaces genéricas.  
  
     Por ejemplo, si está diseñando una clase que se utilizará para crear elementos en una colección basada en genéricos, puede que tenga que implementar una interfaz como <xref:System.IComparable%601>, donde `T` es el tipo de la clase.  
  
 Para obtener un ejemplo de una clase genérica simple, vea [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
 Las reglas para los parámetros de tipo y las restricciones tienen varias implicaciones en el comportamiento de la clase genérica, especialmente en lo relativo a la herencia y accesibilidad de los miembros.  Antes de continuar, debería entender algunos términos.  Para una clase genérica `Node<T>,`, el código cliente puede hacer referencia a la clase especificando un argumento de tipo para crear un tipo construido cerrado \(`Node<int>`\).  Como alternativa, puede dejar el parámetro de tipo sin especificar, por ejemplo, al especificar una clase base genérica, para crear un tipo construido abierto \(`Node<T>`\).  Las clases genéricas pueden heredar de clases base construidas cerradas o construidas abiertas:  
  
 [!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-classes_1.cs)]  
  
 Las clases no genéricas, es decir, concretas, pueden heredar de las clases base construidas cerradas, pero no de las clases construidas abiertas ni de los parámetros de tipo 'from', ya que no hay ninguna forma de que el código cliente pueda proporcionar el tipo de argumento necesario para crear una instancia de la clase base en tiempo de ejecución.  
  
 [!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-classes_2.cs)]  
  
 Las clases genéricas que heredan de tipos construidos abiertos deben proporcionar argumentos de tipo para cada parámetro de tipo de clase base no compartidos con la clase que hereda, tal como se muestra en el código siguiente:  
  
 [!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-classes_3.cs)]  
  
 Las clases genéricas que heredan de tipos construidos abiertos deben especificar restricciones que impliquen o sean un superconjunto de las restricciones sobre el tipo base:  
  
 [!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-classes_4.cs)]  
  
 Los tipos genéricos pueden utilizar varios parámetros y restricciones de tipo, de la forma siguiente:  
  
 [!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-classes_5.cs)]  
  
 Los tipos construidos abiertos y construidos cerrados se pueden utilizar como parámetros de método:  
  
 [!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-classes_6.cs)]  
  
 Si una clase genérica implementa una interfaz, todas las instancias de esa clase se pueden convertir explícitamente a esa interfaz.  
  
 Las clases genéricas son invariables.  En otras palabras, si un parámetro de entrada especifica una `List<BaseClass>`, obtendrá un error de compilación si intenta proporcionar una `List<DerivedClass>`.  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Saving the State of Enumerators](http://go.microsoft.com/fwlink/?LinkId=112390)   
 [An Inheritance Puzzle, Part One](http://go.microsoft.com/fwlink/?LinkId=112380)