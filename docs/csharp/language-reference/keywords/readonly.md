---
title: "readonly (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "readonly_CSharpKeyword"
  - "readonly"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "readonly (palabra clave) [C#]"
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# readonly (Referencia de C#)
La palabra clave `readonly` corresponde a un modificador que se puede utilizar en campos.  Cuando una declaración de campo incluye un modificador `readonly`, las asignaciones a los campos que aparecen en la declaración sólo pueden tener lugar en la propia declaración o en un constructor de la misma clase.  
  
## Ejemplo  
 En este ejemplo, el valor del campo `year` no se puede cambiar en el método `ChangeYear`, aunque se asigne un valor en el constructor de clase:  
  
 [!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 Sólo se puede asignar un valor a un campo `readonly` en los siguientes contextos:  
  
-   Cuando la variable se inicializa en la declaración, por ejemplo:  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   Para un campo de instancia, en los constructores de instancia de la clase que contiene la declaración de campo; para un campo estático, en el constructor estático de la clase que contiene la declaración de campo.  Éstos son también los únicos contextos en los que es válido pasar un campo `readonly` como parámetro [out](../../../csharp/language-reference/keywords/out.md) o [ref](../../../csharp/language-reference/keywords/ref.md).  
  
> [!NOTE]
>  La palabra clave `readonly` es diferente de la palabra clave [const](../../../csharp/language-reference/keywords/const.md).  Un campo `const` sólo puede inicializarse en la declaración del campo.  Un campo `readonly` puede inicializarse en la declaración o en un constructor.  Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se utilice.  Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede utilizarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## Ejemplo  
 [!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 En el ejemplo anterior, si se utiliza una instrucción como:  
  
 `p2.y = 66;        // Error`  
  
 se obtendrá el siguiente mensaje de error del compilador:  
  
 `The left-hand side of an assignment must be an l-value`  
  
 que es el mismo error que se obtiene al intentar asignar un valor a una constante.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)