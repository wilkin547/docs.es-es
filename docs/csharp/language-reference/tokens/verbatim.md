---
description: '@: Referencia de C#'
title: '@: Referencia de C#'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
ms.openlocfilehash: 7d78b28479ed6128321207073dc94976710f10b6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138909"
---
# <a name="-c-reference"></a><span data-ttu-id="b9e5c-103">@ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b9e5c-103">@ (C# Reference)</span></span>

<span data-ttu-id="b9e5c-104">El carácter especial `@` actúa como un identificador textual.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-104">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="b9e5c-105">Se puede usar de estas formas:</span><span class="sxs-lookup"><span data-stu-id="b9e5c-105">It can be used in the following ways:</span></span>

1. <span data-ttu-id="b9e5c-106">Para habilitar el uso de palabras clave de C# como identificadores.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-106">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="b9e5c-107">El carácter `@` actúa como prefijo de un elemento de código que el compilador debe interpretar como un identificador en lugar de como una palabra clave de C#.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-107">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="b9e5c-108">En el ejemplo siguiente se usa el carácter `@` para definir un identificador denominado `for` que se usa en un bucle `for`.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-108">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="b9e5c-109">Para indicar que un literal de cadena se debe interpretar literalmente.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-109">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="b9e5c-110">El carácter `@` de esta instancia define un *literal de cadena textual*.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-110">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="b9e5c-111">Las secuencias de escape sencillas (como `"\\"`, que es una barra diagonal inversa), las secuencias de escape hexadecimales (como `"\x0041"`, que es una A mayúscula) y las secuencias de escape Unicode (como `"\u0041"` que es una A mayúscula) se interpretan literalmente.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-111">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A), and Unicode escape sequences (such as `"\u0041"` for an uppercase A) are interpreted literally.</span></span> <span data-ttu-id="b9e5c-112">Solo las secuencias de escape de comillas (`""`) no se interpretan literalmente, sino que generan comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-112">Only a quote escape sequence (`""`) is not interpreted literally; it produces one double quotation mark.</span></span> <span data-ttu-id="b9e5c-113">De igual modo, en el caso de una [cadena interpolada](interpolated.md) literal, las secuencias de escape de llave (`{{` y `}}`) no se interpretan literalmente, sino que generan caracteres de llave simple.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-113">Additionally, in case of a verbatim [interpolated string](interpolated.md) brace escape sequences (`{{` and `}}`) are not interpreted literally; they produce single brace characters.</span></span> <span data-ttu-id="b9e5c-114">En el siguiente ejemplo se definen dos rutas de archivo idénticas, una mediante un literal de cadena normal y otra mediante el uso de un literal de cadena textual.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-114">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="b9e5c-115">Este es uno de los usos más comunes de los literales de cadena textual.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-115">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="b9e5c-116">En el ejemplo siguiente se muestra el efecto de definir un literal de cadena normal y un literal de cadena textual que contienen secuencias de caracteres idénticos.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-116">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="b9e5c-117">Para permitir que el compilador distinga entre los atributos en caso de conflicto de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-117">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="b9e5c-118">Un atributo es una clase que deriva de <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-118">An attribute is a class that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="b9e5c-119">Normalmente, su nombre de tipo incluye el sufijo **Attribute**, aunque el compilador no exige el cumplimiento de esta convención.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-119">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="b9e5c-120">Es posible hacer referencia al atributo en el código mediante su nombre de tipo completo (por ejemplo, `[InfoAttribute]`) o mediante su nombre abreviado (por ejemplo, `[Info]`).</span><span class="sxs-lookup"><span data-stu-id="b9e5c-120">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="b9e5c-121">Pero se produce un conflicto de nomenclatura si dos nombres abreviados de tipo de atributo son idénticos, y un nombre de tipo incluye el sufijo **Attribute** y el otro no.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-121">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="b9e5c-122">Por ejemplo, el código siguiente produce un error al compilarse porque el compilador no puede determinar si el atributo `Info` o `InfoAttribute` se aplica a la clase `Example`.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-122">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Example` class.</span></span> <span data-ttu-id="b9e5c-123">Vea [CS1614](../compiler-messages/cs1614.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b9e5c-123">See [CS1614](../compiler-messages/cs1614.md) for more information.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a><span data-ttu-id="b9e5c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9e5c-124">See also</span></span>

- [<span data-ttu-id="b9e5c-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b9e5c-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b9e5c-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b9e5c-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b9e5c-127">Caracteres especiales de C#</span><span class="sxs-lookup"><span data-stu-id="b9e5c-127">C# Special Characters</span></span>](./index.md)
