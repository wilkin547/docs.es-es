---
title: class (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- class_CSharpKeyword
- class
dev_langs:
- CSharp
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 92750040466914389abc3e8bf1de84c44bb0987c
ms.lasthandoff: 03/13/2017

---
# <a name="class-c-reference"></a>class (Referencia de C#)
Las clases se declaran mediante la palabra clave `class`, como se muestra en el siguiente ejemplo:  
  
```  
  
      class TestClass  
{  
    // Methods, properties, fields, events, delegates   
    // and nested classes go here.  
}  
```  
  
## <a name="remarks"></a>Comentarios  
 Solo la herencia simple se permite en C#. En otras palabras, una clase puede heredar la implementación solo de una clase base. En cambio, una clase puede implementar más de una interfaz. En la tabla siguiente se muestran ejemplos de herencia de clases e implementación de interfaces:  
  
|Herencia|Ejemplo|  
|-----------------|-------------|  
|Ninguna|`class ClassA { }`|  
|Single|`class DerivedClass: BaseClass { }`|  
|Ninguna, implementa dos interfaces|`class ImplClass: IFace1, IFace2 { }`|  
|Única, implementa una interfaz|`class ImplDerivedClass: BaseClass, IFace1 { }`|  
  
 Las clases que se declaran directamente dentro de un espacio de nombres, que no están anidadas dentro de otras clases, pueden ser de tipo [public](../../../csharp/language-reference/keywords/public.md) o [internal](../../../csharp/language-reference/keywords/internal.md). De forma predeterminada, las clases son `internal`.  
  
 Los miembros de clase, incluidas las clases anidadas, pueden ser de tipo [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md). Los miembros son [private](../../../csharp/language-reference/keywords/private.md) de forma predeterminada.  
  
 Para obtener más información, consulte [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Puede declarar clases genéricas que tengan parámetros de tipo. Para obtener más información, consulte [Clases genéricas](../../../csharp/programming-guide/generics/generic-classes.md).  
  
 Una clase puede contener declaraciones de los miembros siguientes:  
  
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
  
-   [Estructuras](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar campos de clase, constructores y métodos. También se muestra la creación de instancias de objeto y la impresión de datos de instancias. En este ejemplo se declaran dos clases, la clase `Child`, que contiene dos campos privados (`name` y `age`) y dos métodos públicos. La segunda clase, `StringTest`, se usa para contener `Main`.  
  
 [!code-cs[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]  
  
## <a name="comments"></a>Comentarios  
 Observe que en el ejemplo anterior solo se puede acceder a los campos privados (`name` y `age`) a través de los métodos públicos de la clase `Child`. Por ejemplo, no puede imprimir el nombre de la clase child, desde el método `Main`, mediante una instrucción como esta:  
  
```  
Console.Write(child1.name);   // Error  
```  
  
 El acceso a miembros privados de `Child` desde `Main` solo sería posible si `Main` fuera un miembro de la clase.  
  
 Los tipos declarados dentro de una clase sin un modificador de acceso adoptan el valor predeterminado de `private`, por lo que los miembros de datos de este ejemplo seguirían siendo `private` si se quitara la palabra clave.  
  
 Por último, tenga en cuenta que, para el objeto creado mediante el constructor predeterminado (`child3`), el campo age se ha inicializado a cero de forma predeterminada.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)
