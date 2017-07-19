---
title: const (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
dev_langs:
- CSharp
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 28
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
ms.openlocfilehash: 700e80272384a946609d538c5516f0480b7fed27
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="const-c-reference"></a>const (Referencia de C#)
La palabra clave `const` se usa para declarar un campo constante o una local constante. Los campos y locales constantes no son variables y no se pueden modificar. Las constantes pueden ser números, valores booleanos, cadenas o una referencia nula. No cree una constante para representar información que esperas que cambie en algún momento. Por ejemplo, no use un campo constante para almacenar el precio de un servicio, un número de versión de producto o el nombre comercial de una compañía. Estos valores pueden cambiar con el tiempo y, como los compiladores propagan las constantes, otro código compilado con sus bibliotecas tendrán que volver a compilarse para ver los cambios. Vea también la palabra clave [readonly](../../../csharp/language-reference/keywords/readonly.md). Por ejemplo:  
  
```  
      const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a>Comentarios  
 El tipo de una declaración constante especifica el tipo de los miembros que la declaración presenta. El inicializador de una local constante o de un campo constante debe ser una expresión constante que se pueda convertir implícitamente al tipo de destino.  
  
 Una expresión constante es una expresión que se puede evaluar por completo en tiempo de compilación. Por lo tanto, los únicos valores posibles para las constantes de tipos de referencia son `string` y una referencia nula.  
  
 La declaración de constante puede declarar varias constantes, tales como:  
  
```  
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 El modificador `static` no se permite en una declaración de constante.  
  
 Una constante puede participar en una expresión constante, de la siguiente manera:  
  
```  
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  La palabra clave [readonly](../../../csharp/language-reference/keywords/readonly.md) difiere de la palabra clave `const`. Un campo `const` solo se puede inicializar en la declaración del campo. Un campo `readonly` se puede inicializar en la declaración o en un constructor. Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use. Además, aunque un campo `const` es una constante en tiempo de compilación, el campo `readonly` se puede usar para constantes en tiempo de ejecución, como en esta línea: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo demuestra cómo usar las constantes como variables locales.  
  
 [!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [readonly](../../../csharp/language-reference/keywords/readonly.md)

