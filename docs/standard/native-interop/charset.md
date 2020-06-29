---
title: 'Juegos de caracteres y serialización: .NET'
description: Obtenga información acerca cómo distintos valores de CharSet pueden cambiar la forma en que .NET serializa los datos al código nativo.
ms.date: 01/18/2019
ms.openlocfilehash: 39566593aa38bacfa41b44a8af8cc2dfb294d766
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416114"
---
# <a name="charsets-and-marshaling"></a>Juegos de caracteres y serialización

La forma en que los valores `char` y los objetos `string` y `System.Text.StringBuilder` se serializan depende del valor del campo `CharSet` en la estructura o P/Invoke. Puede establecer el elemento `CharSet` de P/Invoke estableciendo el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al declarar su P/Invoke. Con el fin de establecer el elemento `CharSet` para un tipo, establezca el campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> en la declaración de la estructura o la clase. Cuando no se establecen estos campos de atributo, es decisión del compilador de lenguaje determinar qué `CharSet` usar. C# y Visual Basic usan el juego de caracteres <xref:System.Runtime.InteropServices.CharSet.Ansi> de manera predeterminada.

En la tabla siguiente se muestra una asignación entre cada juego de caracteres, así como la forma en que un carácter o una cadena se representan cuando se serializan con ese juego de caracteres:

| Valor de`CharSet` | Windows            | .NET Core 2.2 y versiones anteriores en Unix | .NET Core 3.0 y versiones posteriores y Mono en Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| `Ansi`          | `char` (la página de códigos de [Windows [ANSI]](/windows/win32/intl/code-pages) predeterminada del sistema)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| `Unicode`       | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| `Auto`          | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Asegúrese de que sabe qué representación espera su representación nativa cuando se selecciona el juego de caracteres.
