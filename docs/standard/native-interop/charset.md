---
title: 'Juegos de caracteres y serialización: .NET'
description: Obtenga información acerca cómo distintos valores de CharSet pueden cambiar la forma en que .NET serializa los datos al código nativo.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: a29d53f8e422da1a78e131110972d83987c5464a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337920"
---
# <a name="charsets-and-marshaling"></a>Juegos de caracteres y serialización

La forma en que los valores `char` y los objetos `string` y `System.Text.StringBuilder` se serializan depende del valor del campo `CharSet` en la estructura o P/Invoke. Puede establecer el elemento `CharSet` de P/Invoke estableciendo el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al declarar su P/Invoke. Para establecer el `CharSet` para un tipo, establezca el campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> en la declaración de clase o estructura. Cuando no se establecen estos campos de atributo, es decisión del compilador de lenguaje determinar qué `CharSet` usar. C#y Visual Basic usar el juego de caracteres <xref:System.Runtime.InteropServices.CharSet.Ansi> de forma predeterminada.

En la tabla siguiente se muestra una asignación entre cada juego de caracteres, así como la forma en que un carácter o una cadena se representan cuando se serializan con ese juego de caracteres:

| Valor de `CharSet` | Portal            | .NET Core 2.2 y versiones anteriores en Unix | .NET Core 3.0 y versiones posteriores y Mono en Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (la página de códigos de [Windows [ANSI]](/windows/win32/intl/code-pages) predeterminada del sistema)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Unicode         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Auto            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Asegúrese de que sabe qué representación espera su representación nativa cuando se selecciona el juego de caracteres.
