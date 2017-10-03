---
title: sealed (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sealed
- sealed_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a8d0fe959eac03aad4f1ae1fada61c0ad2fd65cd
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="sealed-c-reference"></a>sealed (Referencia de C#)
Cuando se aplica a una clase, el modificador `sealed` impide que otras clases hereden de ella. En el ejemplo siguiente, la clase `B` hereda de la clase `A`, pero ninguna clase puede heredar de la clase `B`.  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 También puede usar el modificador `sealed` en un método o propiedad que invalida un método o propiedad virtual en una clase base. De este modo, puede permitir que las clases deriven de su clase e impedir que invaliden determinados métodos o propiedades virtuales.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `Z` hereda de `Y` pero `Z` no puede invalidar la función virtual `F` que se declara en `X` y se sella en `Y`.  
  
 [!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 Al definir nuevos métodos o propiedades en una clase, puede impedir que las clases derivadas los invaliden. Para ello, no los declare como [virtuales](../../../csharp/language-reference/keywords/virtual.md).  
  
 Es un error usar el modificador [abstract](../../../csharp/language-reference/keywords/abstract.md) con una clase sellada, porque una clase abstracta debe heredarla una clase que proporcione una implementación de los métodos o propiedades abstractos.  
  
 Cuando se aplica a un método o propiedad, el modificador `sealed` siempre se debe usar con [override](../../../csharp/language-reference/keywords/override.md).  
  
 Dado que los structs están sellados implícitamente, no puede heredarse.  
  
 Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Para obtener más ejemplos, vea [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 En el ejemplo anterior, podría intentar heredar de la clase sellada mediante la instrucción siguiente:  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 El resultado es un mensaje de error:  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a>Comentarios  
 Para determinar si se debe sellar una clase, un método o una propiedad, por lo general debe tener en cuenta los dos puntos siguientes:  
  
-   Las posibles ventajas que podrían obtener las clases derivadas con la capacidad de personalizar la clase.  
  
-   La posibilidad de que las clases derivadas modifiquen las clases de tal manera que no funcionen correctamente o del modo esperado.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)

