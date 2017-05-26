---
title: virtual (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
dev_langs:
- CSharp
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e2268fcc3888bf4b3a30f5855a31bfafcbd3ca49
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="virtual-c-reference"></a>virtual (Referencia de C#)
La palabra clave `virtual` se usa para modificar una declaración de método, propiedad, indizador o evento y permitir que se invalide en una clase derivada. Por ejemplo, cualquier clase que herede este método puede reemplazarlo:  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 Un [miembro de reemplazo](../../../csharp/language-reference/keywords/override.md) de una clase derivada puede modificar la implementación de un miembro virtual. Para obtener más información sobre cómo usar la palabra clave `virtual`, vea [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="remarks"></a>Comentarios  
 Cuando se invoca a un método virtual, se busca un miembro de reemplazo en el tipo en tiempo de ejecución del objeto. Se llama al miembro de reemplazo en la clase más derivada, que podría ser el miembro original si ninguna clase derivada ha invalidado al miembro.  
  
 De forma predeterminada, los métodos son no virtuales. No se puede invalidar un método no virtual.  
  
 No se puede usar el modificador `virtual` con los modificadores `static`, `abstract, private` o `override`. En el siguiente ejemplo se muestra una propiedad virtual:  
  
 [!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 Las propiedades virtuales se comportan como métodos abstractos, salvo por las diferencias en la sintaxis de declaración e invocación.  
  
-   Es un error usar el modificador `virtual` en una propiedad estática.  
  
-   Una propiedad virtual heredada se puede invalidar en una clase derivada al incluir una declaración de propiedad que use el modificador `override`.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase `Shape` contiene las dos coordenadas `x`, `y` y el método virtual `Area()`. Las distintas clases de formas como `Circle`, `Cylinder` y `Sphere` heredan la clase `Shape` y se calcula el área de cada figura. Cada clase derivada tiene su propia implementación de invalidación de `Area()`.  
  
 Observe que las clases heredadas `Circle`, `Sphere` y `Cylinder` usan constructores que inicializan la clase base, como se muestra en la siguiente declaración.  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 El programa siguiente calcula y muestra el área apropiada de cada figura al invocar a la implementación adecuada del método `Area()`, según el objeto asociado al método.  
  
 [!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [new](../../../csharp/language-reference/keywords/new.md)
