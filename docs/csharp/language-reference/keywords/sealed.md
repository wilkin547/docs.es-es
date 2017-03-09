---
title: "sealed (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "sealed"
  - "sealed_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sealed (palabra clave) [C++]"
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# sealed (Referencia de C#)
El modificador `sealed`, cuando se aplica a una clase, impide que otras clases se hereden de él.  En el ejemplo siguiente, la clase `B` se hereda de la clase `A`, pero no es posible heredar ninguna clase de la clase `B`.  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 El modificador `sealed` también puede utilizarse en un método o propiedad que invalide un método o propiedad virtual en una clase base.  De esta forma, puede permitir la derivación de clases de su clase e impedir que invaliden determinados métodos o propiedades virtuales.  
  
## Ejemplo  
 En el ejemplo siguiente, `Z` se hereda de `Y`, pero `Z` no puede invalidar la función virtual `F` que se declara en `X` y se sella en `Y`.  
  
 [!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#16)]  
  
 Al definir nuevos métodos o propiedades en una clase, puede impedir que las clases derivadas invaliden dichos métodos o propiedades no declarándolos como [virtual](../../../csharp/language-reference/keywords/virtual.md).  
  
 Es un error utilizar el modificador [abstract](../../../csharp/language-reference/keywords/abstract.md) con una clase sealed, puesto que una clase abstract debe heredarla una clase que proporcione una implementación de los métodos o propiedades abstract.  
  
 Cuando se aplica a un método o propiedad, el modificador `sealed` siempre se debe utilizar con [override](../../../csharp/language-reference/keywords/override.md).  
  
 Dado que los structs son tipos sealed implícitamente, no se pueden heredar.  
  
 Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Para obtener más ejemplos, vea [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
## Ejemplo  
 [!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#17)]  
  
 En el ejemplo anterior, podría intentar heredar de la clase sealed utilizando la siguiente instrucción:  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 El resultado es un mensaje de error:  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Comentarios  
 Normalmente, para determinar si debe sellar una clase, método o propiedad, debe considerar los siguientes aspectos:  
  
-   Las posibles ventajas que supondría para las clases derivadas la capacidad de personalizar su clase.  
  
-   La posibilidad de que las clases derivadas pudieran modificar sus clases de forma que dejasen de funcionar correctamente o del modo esperado.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)