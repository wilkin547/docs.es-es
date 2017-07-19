---
title: '@ (Referencia de C#) | Microsoft Docs'
ms.date: 2017-02-09
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@_CSharpKeyword'
- '@'
dev_langs:
- CSharp
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
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
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: c32a3d83730c8e9ba5e74f74a436174294538d95
ms.contentlocale: es-es
ms.lasthandoff: 05/24/2017

---
# <a name="-c-reference"></a>@ (Referencia de C#)

El carácter especial `@` actúa como un identificador textual. Se puede usar de estas formas:

1. Para habilitar el uso de palabras clave de C# como identificadores. El carácter `@` actúa como prefijo de un elemento de código que el compilador debe interpretar como un identificador en lugar de como una palabra clave de C#. En el ejemplo siguiente se usa el carácter `@` para definir un identificador denominado `for` que se usa en un bucle `for`.

   [!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. Para indicar que un literal de cadena se debe interpretar literalmente. El carácter `@` de esta instancia define un *literal de cadena textual*. Las secuencias de escape sencillas (como `"\\"` para una barra diagonal inversa), las secuencias de escape hexadecimal (como `"\x0041"` para una A mayúscula) y las secuencias de escape Unicode (como `"\u0041"` para una A mayúscula) se interpretan literalmente. Solo las secuencias de escape de comillas (`""`) no se interpretan literalmente, sino que generan una comilla simple. En el siguiente ejemplo se definen dos rutas de archivo idénticas, una mediante un literal de cadena normal y otra mediante el uso de un literal de cadena textual. Este es uno de los usos más comunes de los literales de cadena textual.

   [!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   En el ejemplo siguiente se muestra el efecto de definir un literal de cadena normal y un literal de cadena textual que contienen secuencias de caracteres idénticos.

   [!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. Para permitir que el compilador distinga entre los atributos en caso de conflicto de nomenclatura. Un atributo es un tipo que deriva de @System.Attribute. Normalmente, su nombre de tipo incluye el sufijo **Attribute**, aunque el compilador no exige el cumplimiento de esta convención. Es posible hacer referencia al atributo en el código mediante su nombre de tipo completo (por ejemplo, `[InfoAttribute]`) o mediante su nombre abreviado (por ejemplo, `[Info]`). Pero se produce un conflicto de nomenclatura si dos nombres abreviados de tipo de atributo son idénticos, y un nombre de tipo incluye el sufijo **Attribute** y el otro no. Por ejemplo, el código siguiente produce un error al compilarse porque el compilador no puede determinar si el atributo `Info` o `InfoAttribute` se aplica al método `Main`.

   ```csharp
   using System;

   [AttributeUsage(AttributeTargets.Class)]
   public class Info : Attribute
   {
      private string information;
      
      public Info(string info)
      {
          information = info;
      }
   }

   [AttributeUsage(AttributeTargets.Method)]
   public class InfoAttribute : Attribute
   {
      private string information;
      
      public InfoAttribute(string info)
      {
          information = info;
      }
   }

   [Info("A simple executable.")]
   public class Example
   {
      [InfoAttribute("The entry point.")]
      public static void Main()
      {
      }
   }
   ```  

   Si el identificador textual se usa para identificar el atributo `Info`, el ejemplo se compila correctamente.

   [!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]

## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Caracteres especiales de C#](../../../csharp/language-reference/tokens/index.md)

