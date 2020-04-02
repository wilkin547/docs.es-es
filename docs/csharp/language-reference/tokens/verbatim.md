---
title: '@: Referencia de C#'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
ms.openlocfilehash: b37f77273e767a5e5292e7707933892f57811d2a
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291772"
---
# <a name="-c-reference"></a>@ (Referencia de C#)

El carácter especial `@` actúa como un identificador textual. Se puede usar de estas formas:

1. Para habilitar el uso de palabras clave de C# como identificadores. El carácter `@` actúa como prefijo de un elemento de código que el compilador debe interpretar como un identificador en lugar de como una palabra clave de C#. En el ejemplo siguiente se usa el carácter `@` para definir un identificador denominado `for` que se usa en un bucle `for`.

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. Para indicar que un literal de cadena se debe interpretar literalmente. El carácter `@` de esta instancia define un *literal de cadena textual*. Las secuencias de escape sencillas (como `"\\"`, que es una barra diagonal inversa), las secuencias de escape hexadecimales (como `"\x0041"`, que es una A mayúscula) y las secuencias de escape Unicode (como `"\u0041"` que es una A mayúscula) se interpretan literalmente. Solo las secuencias de escape de comillas (`""`) no se interpretan literalmente, sino que generan comillas dobles. De igual modo, en el caso de una [cadena interpolada](interpolated.md) literal, las secuencias de escape de llave (`{{` y `}}`) no se interpretan literalmente, sino que generan caracteres de llave simple. En el siguiente ejemplo se definen dos rutas de archivo idénticas, una mediante un literal de cadena normal y otra mediante el uso de un literal de cadena textual. Este es uno de los usos más comunes de los literales de cadena textual.

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   En el ejemplo siguiente se muestra el efecto de definir un literal de cadena normal y un literal de cadena textual que contienen secuencias de caracteres idénticos.

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. Para permitir que el compilador distinga entre los atributos en caso de conflicto de nomenclatura. Un atributo es una clase que deriva de <xref:System.Attribute>. Normalmente, su nombre de tipo incluye el sufijo **Attribute**, aunque el compilador no exige el cumplimiento de esta convención. Es posible hacer referencia al atributo en el código mediante su nombre de tipo completo (por ejemplo, `[InfoAttribute]`) o mediante su nombre abreviado (por ejemplo, `[Info]`). Pero se produce un conflicto de nomenclatura si dos nombres abreviados de tipo de atributo son idénticos, y un nombre de tipo incluye el sufijo **Attribute** y el otro no. Por ejemplo, el código siguiente produce un error al compilarse porque el compilador no puede determinar si el atributo `Info` o `InfoAttribute` se aplica a la clase `Example`. Vea [CS1614](../compiler-messages/cs1614.md) para obtener más información.

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Caracteres especiales de C#](./index.md)
