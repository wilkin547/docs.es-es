---
title: "Objetos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "objetos [C#], acerca de objetos"
  - "variables [C#]"
ms.assetid: af4a5230-fbf3-4eea-95e1-8b883c2f845c
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Objetos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una definición de clase o struct es como un plano que especifica qué puede hacer el tipo.  Un objeto es básicamente un bloque de memoria que se ha asignado y configurado en función del plano.  Un programa puede crear muchos objetos de la misma clase.  Los objetos también se denominan instancias y se pueden almacenar en una variable con nombre o en una matriz o colección.  El código cliente es el código que utiliza estas variables para llamar a los métodos y obtener acceso a las propiedades públicas del objeto.  En un lenguaje orientado a objetos como C\#, un programa típico se compone de varios objetos que interactúan dinámicamente.  
  
> [!NOTE]
>  Los tipos estáticos se comportan de manera diferente a la que se describe aquí.  Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## Instancias de Struct VS. instancias de clase  
 Dado que las clases son tipos de referencia, una variable de un objeto de clase contiene una referencia a la dirección del objeto en el montón administrado.  Si un segundo objeto del mismo tipo se asigna al primer objeto, ambas variables hacen referencia al objeto en esa dirección.  Este punto se analiza con más detalle más adelante, en este mismo tema.  
  
 Las instancias de clases se crean utilizando el [operador new](../../../csharp/language-reference/keywords/new-operator.md).  En el ejemplo siguiente, `Person` es el tipo y `person1` y `person 2` son instancias, u objetos, de ese tipo.  
  
 [!code-cs[csProgGuideStatements#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_1.cs)]  
  
 Dado que los structs son tipos de valor, una variable de un objeto de struct contiene una copia de todo el objeto.  También se pueden crear instancias de structs utilizando el operador `new`, pero no es obligatorio, como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideStatements#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_2.cs)]  
  
 La memoria para `p1` y `p2` se asigna en la pila de subprocesos.  Esta memoria se reclama junto con el tipo o método en el que se declara.  Ésta es una razón por la que los structs se copian en la asignación.  Por el contrario, Common Language Runtime reclama automáticamente \(mediante la recolección de elementos no utilizados\) la memoria asignada a una instancia de clase cuando todas las referencias al objeto han quedado fuera del ámbito.  No es posible destruir de manera determinista un objeto de clase como se hace en C\+\+.  Para obtener más información sobre la recolección de elementos no utilizados en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], vea [Garbage Collection](../Topic/Garbage%20Collection.md).  
  
> [!NOTE]
>  La asignación y desasignación de memoria en el montón administrado están muy optimizadas en Common Language Runtime.  En la mayoría de los casos no existe una diferencia significativa de costo de rendimiento entre asignar una instancia de clase en el montón frente a asignar una instancia de struct en la pila.  
  
## Identidad de objetos VS. igualdad de valores  
 Al comparar dos objetos para comprobar si son iguales, primero debe diferenciar si desea conocer si las dos variables representan al mismo objeto en memoria o si los valores de uno o más de sus campos son equivalentes.  Si desea comparar valores, debe considerar si los objetos son instancias de tipos de valor \(structs\) o tipos de referencia \(clases, delegados, matrices\).  
  
-   Para determinar si dos instancias de clase hacen referencia a la misma ubicación en memoria \(lo que significa que tienen la misma *identidad*\), utilice el método estático <xref:System.Object.Equals%2A>.  \(<xref:System.Object?displayProperty=fullName> es la clase base implícita para todos los tipos de valor y de referencia, incluyendo las clases y structs definidos por el usuario.\)  
  
-   Para determinar si los campos de instancia de dos instancias de struct tienen los mismos valores, utilice el método <xref:System.ValueType.Equals%2A?displayProperty=fullName>.  Dado que todas los structs heredan implícitamente de <xref:System.ValueType?displayProperty=fullName>, se llama al método directamente en el objeto como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideStatements#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_3.cs)]  
  
 La implementación <xref:System.ValueType?displayProperty=fullName> de `Equals` utiliza la reflexión porque debe ser capaz de determinar qué son los campos en cualquier struct.  Al crear sus propios structs, invalide el método `Equals` para proporcionar un algoritmo de igualdad eficaz específico de su tipo.  
  
-   Para determinar si los valores de los campos de dos instancias de clase son iguales, puede usar el método <xref:System.Object.Equals%2A> o el [operador \=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md).  Sin embargo, se deben utilizar solo si la clase los ha invalidado o sobrecargado para proporcionar una definición personalizada de lo que significa “igualdad” para los objetos de ese tipo.  La clase también puede implementar las interfaces <xref:System.IEquatable%601> o <xref:System.Collections.Generic.IEqualityComparer%601>.  Ambas interfaces proporcionan métodos que se pueden utilizar para probar si sus valores son iguales.  Al diseñar sus propias clases que invaliden `Equals`, asegúrese de seguir las directrices indicadas en [Cómo: Definir la igualdad de valores para un tipo](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md) y <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>.  
  
## Secciones relacionadas  
 Para obtener más información:  
  
-   [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [Eventos](../../../csharp/programming-guide/events/index.md)  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [objeto](../../../csharp/language-reference/keywords/object.md)   
 [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [clase](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [new \(Operador\)](../../../csharp/language-reference/keywords/new-operator.md)   
 [Sistema de tipos comunes](../../../standard/base-types/common-type-system.md)