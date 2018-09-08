---
title: '@ (Referencia de C#)'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7dbab5a743b4f9fed759210e8410cd6e3459efac
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44135944"
---
# <a name="-c-reference"></a><span data-ttu-id="f0e86-102">@ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f0e86-102">@ (C# Reference)</span></span>

<span data-ttu-id="f0e86-103">El carácter especial `@` actúa como un identificador textual.</span><span class="sxs-lookup"><span data-stu-id="f0e86-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="f0e86-104">Se puede usar de estas formas:</span><span class="sxs-lookup"><span data-stu-id="f0e86-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="f0e86-105">Para habilitar el uso de palabras clave de C# como identificadores.</span><span class="sxs-lookup"><span data-stu-id="f0e86-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="f0e86-106">El carácter `@` actúa como prefijo de un elemento de código que el compilador debe interpretar como un identificador en lugar de como una palabra clave de C#.</span><span class="sxs-lookup"><span data-stu-id="f0e86-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="f0e86-107">En el ejemplo siguiente se usa el carácter `@` para definir un identificador denominado `for` que se usa en un bucle `for`.</span><span class="sxs-lookup"><span data-stu-id="f0e86-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="f0e86-108">Para indicar que un literal de cadena se debe interpretar literalmente.</span><span class="sxs-lookup"><span data-stu-id="f0e86-108">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="f0e86-109">El carácter `@` de esta instancia define un *literal de cadena textual*.</span><span class="sxs-lookup"><span data-stu-id="f0e86-109">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="f0e86-110">Las secuencias de escape sencillas (como `"\\"`, que es una barra diagonal inversa), las secuencias de escape hexadecimales (como `"\x0041"`, que es una A mayúscula) y las secuencias de escape Unicode (como `"\u0041"` que es una A mayúscula) se interpretan literalmente.</span><span class="sxs-lookup"><span data-stu-id="f0e86-110">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A), and Unicode escape sequences (such as `"\u0041"` for an uppercase A) are interpreted literally.</span></span> <span data-ttu-id="f0e86-111">Solo las secuencias de escape de comillas (`""`) no se interpretan literalmente, sino que generan una comilla simple.</span><span class="sxs-lookup"><span data-stu-id="f0e86-111">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="f0e86-112">De igual modo, en el caso de una [cadena interpolada](interpolated.md) literal, las secuencias de escape de llave (`{{` y `}}`) no se interpretan literalmente, sino que generan caracteres de llave simple.</span><span class="sxs-lookup"><span data-stu-id="f0e86-112">Additionally, in case of a verbatim [interpolated string](interpolated.md) brace escape sequences (`{{` and `}}`) are not interpreted literally; they produce single brace characters.</span></span> <span data-ttu-id="f0e86-113">En el siguiente ejemplo se definen dos rutas de archivo idénticas, una mediante un literal de cadena normal y otra mediante el uso de un literal de cadena textual.</span><span class="sxs-lookup"><span data-stu-id="f0e86-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="f0e86-114">Este es uno de los usos más comunes de los literales de cadena textual.</span><span class="sxs-lookup"><span data-stu-id="f0e86-114">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="f0e86-115">En el ejemplo siguiente se muestra el efecto de definir un literal de cadena normal y un literal de cadena textual que contienen secuencias de caracteres idénticos.</span><span class="sxs-lookup"><span data-stu-id="f0e86-115">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="f0e86-116">Para permitir que el compilador distinga entre los atributos en caso de conflicto de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="f0e86-116">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="f0e86-117">Un atributo es un tipo que deriva de <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="f0e86-117">An attribute is a type that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="f0e86-118">Normalmente, su nombre de tipo incluye el sufijo **Attribute**, aunque el compilador no exige el cumplimiento de esta convención.</span><span class="sxs-lookup"><span data-stu-id="f0e86-118">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="f0e86-119">Es posible hacer referencia al atributo en el código mediante su nombre de tipo completo (por ejemplo, `[InfoAttribute]`) o mediante su nombre abreviado (por ejemplo, `[Info]`).</span><span class="sxs-lookup"><span data-stu-id="f0e86-119">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="f0e86-120">Pero se produce un conflicto de nomenclatura si dos nombres abreviados de tipo de atributo son idénticos, y un nombre de tipo incluye el sufijo **Attribute** y el otro no.</span><span class="sxs-lookup"><span data-stu-id="f0e86-120">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="f0e86-121">Por ejemplo, el código siguiente produce un error al compilarse porque el compilador no puede determinar si el atributo `Info` o `InfoAttribute` se aplica a la clase `Example`.</span><span class="sxs-lookup"><span data-stu-id="f0e86-121">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Example` class.</span></span>

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

   <span data-ttu-id="f0e86-122">Si el identificador textual se usa para identificar el atributo `Info`, el ejemplo se compila correctamente.</span><span class="sxs-lookup"><span data-stu-id="f0e86-122">If the verbatim identifier is used to identify the `Info` attribute, the example compiles successfully.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]

## <a name="see-also"></a><span data-ttu-id="f0e86-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0e86-123">See Also</span></span>

- [<span data-ttu-id="f0e86-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f0e86-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f0e86-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f0e86-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f0e86-126">Caracteres especiales de C#</span><span class="sxs-lookup"><span data-stu-id="f0e86-126">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)
