---
title: Juegos de caracteres y serialización (.NET)
description: Obtenga información acerca cómo distintos valores de CharSet pueden cambiar la forma en que .NET serializa los datos al código nativo.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 2ff6c485906db481cb5236f83e885ba9fd46450b
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "56411471"
---
# <a name="charsets-and-marshalling"></a>Juegos de caracteres y serialización

La forma en que los valores `char`, y los objetos `string` y `System.Text.StringBuilder` se serializan depende del valor del campo `CharSet` en la estructura o P/Invoke. Puede establecer el elemento `CharSet` de P/Invoke estableciendo el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al declarar su P/Invoke. Con el fin de establecer el elemento `CharSet` para una estructura, establezca el campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> en la declaración de la estructura. Cuando no se establecen estos campos de atributo, es decisión del compilador de lenguaje determinar qué `CharSet` usar. C# usa el juego de caracteres <xref:System.Runtime.InteropServices.CharSet.Ansi> de forma predeterminada.

En la tabla siguiente se muestra una asignación entre cada juego de caracteres y cómo se representa un carácter o una cadena cuando se serializan con ese juego de caracteres:

| CharSet | Windows | Unix | Mono en Unix |
|---------|---------|-------|-------|
| Ansi    | `char` (ANSI)  | `char` (ANSI en macOS, UTF-8 en Linux) | `char` (UTF-8) |
| Unicode | `wchar_t` (UTF-16) | `char16_t` (UTF-16) | `char16_t` (UTF-16) |
| Automático | `wchar_t` (UTF-16) | `char16_t` (UTF-16) | `char` (UTF-8) |

Asegúrese de que sabe qué representación espera su representación nativa cuando se selecciona el juego de caracteres.
