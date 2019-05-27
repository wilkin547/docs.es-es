---
title: 'Juegos de caracteres y serialización: .NET'
description: Obtenga información acerca cómo distintos valores de CharSet pueden cambiar la forma en que .NET serializa los datos al código nativo.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: c50c58ad639b1efb29c13e5124fe3c32e8af96fc
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063330"
---
# <a name="charsets-and-marshaling"></a>Juegos de caracteres y serialización

La forma en que los valores `char` y los objetos `string` y `System.Text.StringBuilder` se serializan depende del valor del campo `CharSet` en la estructura o P/Invoke. Puede establecer el elemento `CharSet` de P/Invoke estableciendo el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al declarar su P/Invoke. Con el fin de establecer el elemento `CharSet` para una estructura, establezca el campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> en la declaración de la estructura. Cuando no se establecen estos campos de atributo, es decisión del compilador de lenguaje determinar qué `CharSet` usar. C# y VB usan el juego de caracteres <xref:System.Runtime.InteropServices.CharSet.Ansi> de manera predeterminada.

En la tabla siguiente se muestra una asignación entre cada juego de caracteres, así como la forma en que un carácter o una cadena se representan cuando se serializan con ese juego de caracteres:

| Valor de`CharSet`  | Windows            | .NET Core 2.2 y versiones anteriores en Unix | .NET Core 3.0 y versiones posteriores y Mono en Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (ANSI)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Unicode         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Automático            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Asegúrese de que sabe qué representación espera su representación nativa cuando se selecciona el juego de caracteres.
