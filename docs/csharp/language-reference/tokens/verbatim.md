---
title: '@ (Referencia de C#)'
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 08e3da6aaeee037d7272ea8cddc4382a436b683b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-c-reference"></a><span data-ttu-id="91304-102">@ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="91304-102">@ (C# Reference)</span></span>

<span data-ttu-id="91304-103">El carácter especial `@` actúa como un identificador textual.</span><span class="sxs-lookup"><span data-stu-id="91304-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="91304-104">Se puede usar de estas formas:</span><span class="sxs-lookup"><span data-stu-id="91304-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="91304-105">Para habilitar el uso de palabras clave de C# como identificadores.</span><span class="sxs-lookup"><span data-stu-id="91304-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="91304-106">El carácter `@` actúa como prefijo de un elemento de código que el compilador debe interpretar como un identificador en lugar de como una palabra clave de C#.</span><span class="sxs-lookup"><span data-stu-id="91304-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="91304-107">En el ejemplo siguiente se usa el carácter `@` para definir un identificador denominado `for` que se usa en un bucle `for`.</span><span class="sxs-lookup"><span data-stu-id="91304-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   <span data-ttu-id="91304-108">[!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="91304-108">[!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]</span></span>

1. <span data-ttu-id="91304-109">Para indicar que un literal de cadena se debe interpretar literalmente.</span><span class="sxs-lookup"><span data-stu-id="91304-109">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="91304-110">El carácter `@` de esta instancia define un *literal de cadena textual*.</span><span class="sxs-lookup"><span data-stu-id="91304-110">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="91304-111">Las secuencias de escape sencillas (como `"\\"` para una barra diagonal inversa), las secuencias de escape hexadecimal (como `"\x0041"` para una A mayúscula) y las secuencias de escape Unicode (como `"\u0041"` para una A mayúscula) se interpretan literalmente.</span><span class="sxs-lookup"><span data-stu-id="91304-111">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A, and Unicode escape sequences, such as `"\u0041"` for an uppercase A, are interpreted literally.</span></span> <span data-ttu-id="91304-112">Solo las secuencias de escape de comillas (`""`) no se interpretan literalmente, sino que generan una comilla simple.</span><span class="sxs-lookup"><span data-stu-id="91304-112">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="91304-113">En el siguiente ejemplo se definen dos rutas de archivo idénticas, una mediante un literal de cadena normal y otra mediante el uso de un literal de cadena textual.</span><span class="sxs-lookup"><span data-stu-id="91304-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="91304-114">Este es uno de los usos más comunes de los literales de cadena textual.</span><span class="sxs-lookup"><span data-stu-id="91304-114">This is one of the more common uses of verbatim string literals.</span></span>

   <span data-ttu-id="91304-115">[!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="91304-115">[!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]</span></span>

   <span data-ttu-id="91304-116">En el ejemplo siguiente se muestra el efecto de definir un literal de cadena normal y un literal de cadena textual que contienen secuencias de caracteres idénticos.</span><span class="sxs-lookup"><span data-stu-id="91304-116">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   <span data-ttu-id="91304-117">[!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="91304-117">[!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]</span></span>

1. <span data-ttu-id="91304-118">Para permitir que el compilador distinga entre los atributos en caso de conflicto de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="91304-118">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="91304-119">Un atributo es un tipo que deriva de @System.Attribute.</span><span class="sxs-lookup"><span data-stu-id="91304-119">An attribute is a type that derives from @System.Attribute.</span></span> <span data-ttu-id="91304-120">Normalmente, su nombre de tipo incluye el sufijo **Attribute**, aunque el compilador no exige el cumplimiento de esta convención.</span><span class="sxs-lookup"><span data-stu-id="91304-120">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="91304-121">Es posible hacer referencia al atributo en el código mediante su nombre de tipo completo (por ejemplo, `[InfoAttribute]`) o mediante su nombre abreviado (por ejemplo, `[Info]`).</span><span class="sxs-lookup"><span data-stu-id="91304-121">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="91304-122">Pero se produce un conflicto de nomenclatura si dos nombres abreviados de tipo de atributo son idénticos, y un nombre de tipo incluye el sufijo **Attribute** y el otro no.</span><span class="sxs-lookup"><span data-stu-id="91304-122">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="91304-123">Por ejemplo, el código siguiente produce un error al compilarse porque el compilador no puede determinar si el atributo `Info` o `InfoAttribute` se aplica al método `Main`.</span><span class="sxs-lookup"><span data-stu-id="91304-123">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Main` method.</span></span>

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

   <span data-ttu-id="91304-124">Si el identificador textual se usa para identificar el atributo `Info`, el ejemplo se compila correctamente.</span><span class="sxs-lookup"><span data-stu-id="91304-124">If the verbatim identifier is used to identify the `Info` attribute, the example compiles successfully.</span></span>

   <span data-ttu-id="91304-125">[!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="91304-125">[!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]</span></span>

## <a name="see-also"></a><span data-ttu-id="91304-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="91304-126">See Also</span></span>  
 <span data-ttu-id="91304-127">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="91304-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="91304-128">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="91304-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="91304-129">Caracteres especiales de C#</span><span class="sxs-lookup"><span data-stu-id="91304-129">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)

