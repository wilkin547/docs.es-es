---
title: readonly (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d2f8a2f192dc319ad806aeef4bfbaeecc44b07a3
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="readonly-c-reference"></a>readonly (Referencia de C#)
La palabra clave `readonly` corresponde a un modificador que se puede usar en campos. Cuando una declaración de campo incluye un modificador `readonly`, las asignaciones a los campos que aparecen en la declaración solo pueden tener lugar en la propia declaración o en un constructor de la misma clase.  
  
## <a name="readonly-field-example"></a>Ejemplo de campo readonly  
 En este ejemplo, el valor del campo `year` no se puede cambiar en el método `ChangeYear`, aunque se asigne un valor en el constructor de clase:  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 Solo se puede asignar un valor a un campo `readonly` en los siguientes contextos:  
  
-   Cuando la variable se inicializa en la declaración, por ejemplo:  
  
    ```csharp  
    public readonly int y = 5;  
    ```  
  
-   Para un campo de instancia, en los constructores de instancia de la clase que contiene la declaración de campo; para un campo estático, en el constructor estático de la clase que contiene la declaración de campo. Estos son también los únicos contextos en los que es válido pasar un campo `readonly` como parámetro [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) o [ref](../../../csharp/language-reference/keywords/ref.md).  
  
> [!NOTE]
>  La palabra clave `readonly` es diferente de la palabra clave [const](../../../csharp/language-reference/keywords/const.md). Un campo `const` solo se puede inicializar en la declaración del campo. Un campo `readonly` se puede inicializar en la declaración o en un constructor. Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use. Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede usarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:  
  
```csharp  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="comparing-readonly-and-non-readonly-instance-fields"></a>Comparación de campos de instancia readonly y non-readonly  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
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
