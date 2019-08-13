---
title: 'Juegos de caracteres y serialización: .NET'
description: Obtenga información acerca cómo distintos valores de CharSet pueden cambiar la forma en que .NET serializa los datos al código nativo.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: cac71c5d09514dfe1244d16224944e05826edfa9
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817839"
---
# <a name="charsets-and-marshaling"></a>Juegos de caracteres y serialización

La forma en que los valores `char` y los objetos `string` y `System.Text.StringBuilder` se serializan depende del valor del campo `CharSet` en la estructura o P/Invoke. Puede establecer el elemento `CharSet` de P/Invoke estableciendo el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al declarar su P/Invoke. Con el fin de establecer el elemento `CharSet` para una estructura, establezca el campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> en la declaración de la estructura. Cuando no se establecen estos campos de atributo, es decisión del compilador de lenguaje determinar qué `CharSet` usar. C# y VB usan el juego de caracteres <xref:System.Runtime.InteropServices.CharSet.Ansi> de manera predeterminada.

En la tabla siguiente se muestra una asignación entre cada juego de caracteres, así como la forma en que un carácter o una cadena se representan cuando se serializan con ese juego de caracteres:

| Valor de`CharSet` | Windows            | .NET Core 2.2 y versiones anteriores en Unix | .NET Core 3.0 y versiones posteriores y Mono en Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (la página de códigos de [Windows [ANSI]](/windows/win32/intl/code-pages) predeterminada del sistema)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Unicode         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Automático            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Asegúrese de que sabe qué representación espera su representación nativa cuando se selecciona el juego de caracteres.
