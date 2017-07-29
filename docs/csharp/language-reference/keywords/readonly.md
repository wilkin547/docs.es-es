---
title: readonly (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
dev_langs:
- CSharp
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 16
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
ms.openlocfilehash: 2660aa56721815cbbeb668328863956473cce8f1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="readonly-c-reference"></a>readonly (Referencia de C#)
La palabra clave `readonly` corresponde a un modificador que se puede usar en campos. Cuando una declaración de campo incluye un modificador `readonly`, las asignaciones a los campos que aparecen en la declaración solo pueden tener lugar en la propia declaración o en un constructor de la misma clase.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, el valor del campo `year` no se puede cambiar en el método `ChangeYear`, aunque se asigne un valor en el constructor de clase:  
  
 [!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 Solo se puede asignar un valor a un campo `readonly` en los siguientes contextos:  
  
-   Cuando la variable se inicializa en la declaración, por ejemplo:  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   Para un campo de instancia, en los constructores de instancia de la clase que contiene la declaración de campo; para un campo estático, en el constructor estático de la clase que contiene la declaración de campo. Estos son también los únicos contextos en los que es válido pasar un campo `readonly` como parámetro [out](../../../csharp/language-reference/keywords/out.md) o [ref](../../../csharp/language-reference/keywords/ref.md).  
  
> [!NOTE]
>  La palabra clave `readonly` es diferente de la palabra clave [const](../../../csharp/language-reference/keywords/const.md). Un campo `const` solo se puede inicializar en la declaración del campo. Un campo `readonly` se puede inicializar en la declaración o en un constructor. Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use. Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede usarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 En el ejemplo anterior, si se usa una instrucción como:  
  
 `p2.y = 66;        // Error`  
  
 se obtendrá el siguiente mensaje de error del compilador:  
  
 `The left-hand side of an assignment must be an l-value`  
  
 que es el mismo error que se obtiene al intentar asignar un valor a una constante.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)

