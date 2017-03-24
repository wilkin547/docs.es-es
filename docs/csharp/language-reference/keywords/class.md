---
title: "class (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "class_CSharpKeyword"
  - "class"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "class (palabra clave) [C#]"
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# class (Referencia de C#)
Las clases se declaran mediante la palabra clave `class`, como se muestra en el ejemplo siguiente:  
  
```  
  
      class TestClass  
{  
    // Methods, properties, fields, events, delegates   
    // and nested classes go here.  
}  
```  
  
## Comentarios  
 Sólo la herencia única se permite en C\#.  En otras palabras, una clase puede heredar la implementación de una sola clase base.  Sin embargo, una clase puede implementar más de una interfaz.  La siguiente tabla muestra ejemplos de herencia de clases e implementación de interfaces:  
  
|Herencia|Ejemplo|  
|--------------|-------------|  
|None|`class ClassA { }`|  
|Simple|`class DerivedClass: BaseClass { }`|  
|Ninguna, implementa dos interfaces|`class ImplClass: IFace1, IFace2 { }`|  
|Simple, implementa una interfaz|`class ImplDerivedClass: BaseClass, IFace1 { }`|  
  
 Las clases que se declara directamente dentro de un espacio de nombres, no anidadas dentro de otras clases, pueden ser [público](../../../csharp/language-reference/keywords/public.md) o [interno](../../../csharp/language-reference/keywords/internal.md).  Las clases son `internal` de forma predeterminada.  
  
 Los miembros de clase, incluso clases anidadas, pueden ser [público](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protegido](../../../csharp/language-reference/keywords/protected.md), [interno](../../../csharp/language-reference/keywords/internal.md), o [private](../../../csharp/language-reference/keywords/private.md).  Los miembros son [private](../../../csharp/language-reference/keywords/private.md) de forma predeterminada.  
  
 Para obtener más información, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Puede declarar las clases genéricas que tienen parámetros de tipo.  Para obtener más información, vea [Clases genéricas](../../../csharp/programming-guide/generics/generic-classes.md).  
  
 Una clase puede contener declaraciones de los siguientes miembros:  
  
-   [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md)  
  
-   [Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)  
  
-   [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [Indizadores](../../../csharp/programming-guide/indexers/index.md)  
  
-   [Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [Eventos](../../../csharp/programming-guide/events/index.md)  
  
-   [Delegados](../../../csharp/programming-guide/delegates/index.md)  
  
-   [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [Interfaces](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
## Ejemplo  
 En el siguiente ejemplo se muestra la declaración de campos de clase, constructores y métodos.  También muestra la creación de instancias de objetos y la impresión de datos de instancia.  En este ejemplo, se declaran dos clases, la clase `Child`, que contiene dos campos privados \(`name` y `age`\) y dos métodos públicos.  La segunda clase, `StringTest`, se utiliza para contener `Main`.  
  
 [!code-cs[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]  
  
## Comentarios  
 En el ejemplo anterior, observe que sólo se puede obtener acceso a los campos privados \(`name` y `age`\) a través de los métodos públicos de la clase `Child`.  Por ejemplo, no es posible imprimir el valor name de la clase child desde el método `Main` con una instrucción como ésta:  
  
```  
Console.Write(child1.name);   // Error  
```  
  
 El acceso a los miembros privados de `Child` desde `Main` sólo sería posible si `Main` fuera un miembro de la clase.  
  
 Los tipos declarados dentro de una clase sin un valor predeterminado del modificador de acceso a `private`, por lo que los miembros de datos de este ejemplo todavía se `private` si la palabra clave se quitó.  
  
 Por último, observe que, para el objeto creado mediante el constructor predeterminado \(`child3`\), el campo age se inicializó a cero de forma predeterminada.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)